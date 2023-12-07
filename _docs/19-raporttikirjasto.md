---
title: 'Raporttikirjasto'
permalink: /dokumentaatio/raporttikirjasto/
redirect_from:
  - /theme-setup/
toc: true
---

Tälle sivulle on kerätty erilaisia SQL-raportteja.


Tänne voi tallentaa valmiita SQL-raportteja. Laita raportti olemassa olevien otsikoiden alle tai lisää uusi otsikko, jos mikään ei sovellu tarkoitukseen. Kuvaa raportin toiminta ja laita myös nimesi ja lisäyspäivä kuvauksen alle.

## Miten tehdä SQL-raportteja

[Täältä löydät lyhkäsen oppimäärän](/dokumentaatio/sqlkoulu/), miten Kohassa tehdään SQL-raportteja.

## Miten saa raportille salasanan kyselyn

Raportille voi laittaa myös salasanakyselyn esim. näin:

```and md5(<<Kirjoita salasana>>) = '043fd4dd68d7348a052b021cd3bc6cfa'```

* =-merkin jälkeinen merkkijono on valitun salasanan md5 algoritmillä laskettu tiiviste
* tiivistäminen on yksisuuntainen prosessi eikä käytetty salasana ole johdettavissa tai pääteltävissä tiivisteestä
* tiivisteen valittuun salasanaan voi pyytää joko kehittäjiltä Matrixissa tai jos on pääsy unix-ympäristöön seuraavalla komennolla: ```echo -n "Sammakko" | md5sum```
  * esimerkin salasanaksi on siis valittu sana Sammakko, joka on hipsujen sisällä. 

Esimerkki kokonaisesta kyselystä, jossa on salasana:

```
SELECT firstname,surname,address,zipcode,city
FROM borrowers
WHERE branchcode = <<Valitse asiakkaan kotikirjasto|branches>>
AND md5(<<Kirjoita salasana>>) = '043fd4dd68d7348a052b021cd3bc6cfa'
```

## PowerBI

PowerBI-ohjelmaa voi hyödyntää tilastojen visualisointiin. Tuomas Kunttu Kouvolasta on kerännyt SQL-kyselyitä ja DAX-lausekkeita [PowerBI-sivulle](/dokumentaatio/powerbi/).

## Hea-tilastot

### Tilastot Koha-yhteisön Hea-muodossa

Raportilla voi laskea omat tilastot Koha-yhteisön Hea-muodossa, jotta pystyy arvioimaan oman sijoittumisen yhteisön tilastoissa. Käytännössä raportti laskee raportin ottohetkellä kannassa olevat asiakkaat (mukaan lasketaan kaikki, myös virkailijat ja muut), niteet, kuvailutietueet (mukaanlukien osakohteet), tilaukset, lehtitilaukset ja auktoriteetit. Lainat ja varaukset lasketaan koko Koha-historian ajalta, mutta mukana ei ole tällä hetkellä aktiivisia lainoja ja varauksia. Myöskään uusintoja ei lasketa. 

[Koha-yhteisön Hea-tilastopalvelu](https://hea.koha-community.org/)


Lisännyt: Anneli Österman<br />
Pvm: 2.1.2020

```
select 'Asiakkaat' AS 'Tilasto',count(*) AS 'Yhteensä' from borrowers 
UNION 
select 'Niteet',count(*) from items
UNION
select 'Kuvailutietueet',count(*) from biblio
UNION
select 'Lainat',count(*) from old_issues
UNION
select 'Varaukset',count(*) from old_reserves
UNION
select 'Tilaukset',count(*) from aqorders
UNION
select 'Lehtitilaukset',count(*) from subscription
UNION
select 'Auktoriteetit',count(*) from auth_header
```

## Lainat

### Anonyymit lainat

Tällä raportilla saadaan selville lainaaja, vaikka hän olisi määritellyt yksityisyysasetuksissa ettei halua lainahistoriaansa näkyviin.
Raporttiin luetaan niteen viivakoodi ja se näyttää kaikki "yksityiset" asiakkaat palautusajan mukaan laskevasti.

```
select DATE_FORMAT(s.datetime, '%d.%m.%Y %T') as 'Palautusaika',  
CONCAT('<a href=\"/cgi-bin/koha/catalogue/detail.pl?biblionumber=',bi.biblionumber,'\">',bi.title,'</a>') AS 'Nimeke', 
CONCAT('<a href=\"/cgi-bin/koha/circ/circulation.pl?borrowernumber=',b.borrowernumber,'\">',b.firstname,' ',b.surname,'</a>') AS 'Lainaaja' 
from borrowers b
join statistics s on b.borrowernumber = s.borrowernumber
join items i on i.itemnumber = s.itemnumber
join biblio bi on i.biblionumber = bi.biblionumber
where b.privacy = 2 and s.type = 'return' and barcode=<<barcode>> order by s.datetime desc
```

### Ylen lainat

Lainatilasto Ylen aineistojen lainoista kirjaston ja aikavälin mukaan nimekkeittäin.

```
SELECT b.author AS 'Tekijä', b.title AS 'Nimeke', ExtractValue(bi.marcxml,'//datafield[@tag="245"]/subfield[@code="n"]') AS 'Osa', 
bi.ean AS 'EAN', bi.publicationyear AS 'Vuosi', i.itype AS 'Aineistolaji', count(s.itemtype) AS 'Lainat'
FROM statistics s
LEFT JOIN items i ON i.itemnumber = s.itemnumber
LEFT JOIN biblioitems bi ON i.biblionumber=bi.biblionumber
LEFT JOIN biblio b ON b.biblionumber=i.biblionumber
WHERE s.datetime >= <<Alkupvm|date>> AND
      s.datetime <= DATE_ADD(DATE(<<Loppupvm|date>>), INTERVAL 1 DAY) AND
      s.type IN ('issue', 'renew') AND
      bi.editionresponsibility like '%yle%' AND
      s.categorycode NOT IN ('EITILASTO', 'KAUKOLAINA') AND
      s.branch = <<Kirjasto|branches>>
GROUP BY b.biblionumber
ORDER BY 1,2,3
```

### Ensilainat tunneittain viikonpäivittäin

Laskee ensilainat tunneittain viikonpäivän mukaan valitussa kirjastossa valitulla ajanjaksolla. Raportin tehnyt Pasi Kallinen 2019.

```
SELECT HOUR(datetime) AS Tunti,
       DAYNAME(datetime) AS Paiva,
       count(*) AS Lainat
FROM statistics
WHERE datetime BETWEEN <<AloitusPvm |date>> AND <<LopetusPvm |date>>
      AND branch=<<Kirjasto|branches>>
      AND type = 'issue'
GROUP BY Paiva, Tunti
ORDER BY WEEKDAY(datetime), Tunti
```

### Lainatilasto

Raportti laskee ensilainat (issue) ja uusinnat (renew) sekä niiden summan. Tiedot ryhmitetään kirjastoittain. Raportille annetaan parametriksi kirjastotunnuksen kuntaosio ja %-merkki, (esim. OU% tai JOE%) ja aikaväli. Lainoihin ei lasketa mukaan asiakastyyppien EITILASTO ja KAUKOLAINA lainoja. Muokkaa tarvittaessa asiakastyyppien tunnisteita. Raportti näyttää automaattisesti 100 riviä.

Lisääjä: Anneli Österman<br />
Pvm: 10.12.2021

```
select s.branch AS 'Kirjasto', s.type AS 'Lainan tyyppi', count(*)AS 'Määrä'
from statistics s
where s.branch like <<Kuntaosio ja %-merkki>>
and date(s.datetime) between <<Alkupvm|date>> and <<Loppupvm|date>>
and s.categorycode not in ('EITILASTO', 'KAUKOLAINA')
and s.type in ('issue', 'renew')
group by s.branch, s.type WITH ROLLUP LIMIT 100
```

### Palautustilasto

Raportti laskee lainassa olleiden palautusten määrän aikavälillä ryhmitettynä kirjastoittain. Raportille annetaan parametriksi kirjastotunnuksen kuntaosio ja %-merkki (esim. OU% tai JOE%) sekä aikaväli. Raportti on hidas.

Lisääjä: Anneli Österman<br />
Pvm: 10.12.2021

```
select s.branch AS 'Kirjasto', count(*) AS 'Palautukset'
from statistics s
where (s.branch) like <<Kuntaosio ja %-merkki>>
and (CAST(s.datetime as date) between <<Alkupvm|date>> and <<Loppupvm|date>>)
and s.type='return'
and borrowernumber is not null
group by s.branch WITH ROLLUP LIMIT 50
```




### Automaattikohtainen Lainaus/palautustilasto

Hakee automaatilla tietyllä ajanjaksolla tehdyt lainat ja palautukset ja lajittelee ne kellonajan mukaan. Raporttiin tarvitaan automaatin asiakas-ID -numero (borrowernumber). Muista laittaa haettava ajanjakso päättymään päivää myöhemmin eli esim. tammikuun lainat haetaan 1.1.-1.2. Tiedot selvitetään action_logs-merkinnöistä. Raportti on hidas.

Lisääjä: Lari Strand<br />
Pvm: 14.12.2021

```
SELECT CONCAT(HOUR(timestamp), ':00-', HOUR(timestamp)+1, ':00') AS 'tunnit',
       sum(IF(action = 'ISSUE', 1, 0)) AS 'lainat',
       sum(IF(action = 'RETURN', 1, 0)) AS 'palautukset'

FROM action_logs
 where module = 'CIRCULATION'
  AND user =<<Automaatin ID-numero>>
  AND timestamp BETWEEN <<Alkupäivä|date>> AND <<Loppupäivä|date>>
  AND action IN ('ISSUE','RETURN')
GROUP BY HOUR(timestamp)
```

### Videopelien lainamäärät

Raportti listaa tietueet, joiden aineistotyyppi on videopeli ja näyttää niiden hyllypaikan, konsolityypin (mikäli se on merkitty 753a-kenttään), viimeisimmän lainauspäivän, vastaanottopäivän ja niteen lainamäärän.

Lisätty: 13.1.2022<br />
Lisääjä: Anneli Österman

```
select title as 'Nimeke', location as 'Hyllypaikka', ExtractValue(metadata, '//datafield[@tag="753"]/subfield[@code="a"]') as 'Konsoli', datelastborrowed as 'Viimeksi lainattu', items.datereceived as 'Vastaanottopäivä', issues as 'Lainat'
from statistics
left join items using (itemnumber)
Left join biblio on items.biblionumber=biblio.biblionumber
LEFT JOIN biblioitems on items.biblionumber=biblioitems.biblionumber
LEFT JOIN biblio_metadata on items.biblionumber=biblio_metadata.biblionumber
where biblioitems.itemtype='VIDEOPELI'
and type in ('issue', 'renew')
group by items.itemnumber
order by 2,3,1
LIMIT 2000
```

### PowerBI-koulutusta varten luotu kysely

Raportti on luotu PowerBI-koulutusta varten ja hakee lainoja ja uusintoja. Mukaan ei tule Ei tilasto -asiakastyypin lainoja/uusintoja. Tämä versio on päivitetty toimimaan versiossa 21.11.

Lisätty: 11.10.2022<br />
Lisääjä: Anneli Österman<br />
Versio: 21.11

```
SELECT s.type AS Tapahtumatyyppi, s.itemnumber AS Nidenumero, IFNULL(bi.title, IFNULL (bi2.title, dbi.title)) as Nimeke, s.branch AS Lainauskirjasto,
b.categorycode AS Asiakastyyppi, b.zipcode AS Postinumero, 
s.datetime AS 'Tapahtuma-aika', IFNULL(biblioitems.itemtype, bde.itemtype) AS Aineistotyyppi,
IFNULL(i.permanent_location, d.permanent_location) AS Hyllypaikka,
IFNULL(i.cn_sort, d.cn_sort) AS 'Luokka ja pääsana'
FROM statistics s
LEFT JOIN borrowers b ON s.borrowernumber = b.borrowernumber
LEFT JOIN items i ON s.itemnumber = i.itemnumber
LEFT JOIN deleteditems d ON s.itemnumber = d.itemnumber
LEFT JOIN biblioitems ON i.biblionumber = biblioitems.biblionumber
LEFT JOIN deletedbiblioitems ON d.biblionumber = deletedbiblioitems.biblionumber
LEFT JOIN biblio bi ON i.biblionumber=bi.biblionumber
LEFT JOIN deletedbiblio dbi ON d.biblionumber=dbi.biblionumber
LEFT JOIN biblio bi2 ON d.biblionumber = bi2.biblionumber 
LEFT JOIN koha_plugin_fi_kohasuomi_okmstats_biblio_data_elements bde ON d.biblionumber = bde.biblionumber
WHERE date(datetime) BETWEEN <<Aikaväli alkaen|date>> AND <<Päättyen|date>>
AND b.categorycode != 'EITILASTO'
AND s.type in ('issue', 'renew')
```

### PowerBI-tilasto kunnan mukaan

Lisätty: 29.9.2022<br />
Lisääjä: Anneli Österman<br />
Versio: 21.11

Tämä on sama raportti kuin yllä, mutta mukaan otetaan vain määritetyn kunnan tilastot. Rajaus tehdään kirjoittamalla kuntaosion alku ja %-merkki. Esim. OU%, JOE%. Raportilla voi hakea myös yhden kirjaston tiedot, jos kuntaosio-ehtoon laittaa koko kirjastoyksikön tunnuksen, esim, OUPE%.

```
SELECT s.type AS Tapahtumatyyppi, s.itemnumber AS Nidenumero, IFNULL(bi.title, dbi.title) as Nimeke, s.branch AS Lainauskirjasto,
b.categorycode AS Asiakastyyppi, b.zipcode AS Postinumero, 
s.datetime AS 'Tapahtuma-aika', IFNULL(biblioitems.itemtype, deletedbiblioitems.itemtype) AS Aineistotyyppi,
IFNULL(i.permanent_location, d.permanent_location) AS Hyllypaikka,
IFNULL(i.cn_sort, d.cn_sort) AS 'Luokka ja pääsana'
FROM statistics s
LEFT JOIN borrowers b ON s.borrowernumber = b.borrowernumber
LEFT JOIN items i ON s.itemnumber = i.itemnumber
LEFT JOIN deleteditems d ON s.itemnumber = d.itemnumber
LEFT JOIN biblioitems ON i.biblionumber = biblioitems.biblionumber
LEFT JOIN deletedbiblioitems ON i.biblionumber = deletedbiblioitems.biblionumber
LEFT JOIN biblio bi ON i.biblionumber=bi.biblionumber
LEFT JOIN deletedbiblio dbi ON i.biblionumber=dbi.biblionumber
WHERE date(datetime) BETWEEN <<Aikaväli alkaen|date>> AND <<Päättyen|date>>
AND b.categorycode in ("HENKILO", "KOTIPALVEL","LAPSI", "LAOMATOIMI", "MUUHUOL", "YHTEISO","KAUKOLAINA")
AND s.type in ('issue', 'renew')
AND s.branch like <<Kuntaosio ja %-merkki>>
```

### PowerBI-tilasto, jossa nimekkeestä myös alaotsikko ja osan nimeke

Lisätty: 11.10.2022<br />
Lisääjä: Päivi Knuutinen<br />
Versio: 21.11

```
SELECT s.type AS Tapahtumatyyppi, s.itemnumber AS Nidenumero, 
CONCAT_WS(' ', IFNULL(bi.title, IFNULL (bi2.title, dbi.title)), IFNULL(bi.subtitle, IFNULL (bi2.subtitle, dbi.subtitle)), IFNULL(bi.part_name, IFNULL (bi2.part_name, dbi.part_name))) as Nimeke,
s.branch AS Lainauskirjasto, b.categorycode AS Asiakastyyppi, b.zipcode AS Postinumero, 
s.datetime AS 'Tapahtuma-aika', IFNULL(biblioitems.itemtype, bde.itemtype) AS Aineistotyyppi,
IFNULL(i.permanent_location, d.permanent_location) AS Hyllypaikka,
IFNULL(i.cn_sort, d.cn_sort) AS 'Luokka ja pääsana'
FROM statistics s
LEFT JOIN borrowers b ON s.borrowernumber = b.borrowernumber
LEFT JOIN items i ON s.itemnumber = i.itemnumber
LEFT JOIN deleteditems d ON s.itemnumber = d.itemnumber
LEFT JOIN biblioitems ON i.biblionumber = biblioitems.biblionumber
LEFT JOIN deletedbiblioitems ON d.biblionumber = deletedbiblioitems.biblionumber
LEFT JOIN biblio bi ON i.biblionumber=bi.biblionumber
LEFT JOIN deletedbiblio dbi ON d.biblionumber=dbi.biblionumber
LEFT JOIN biblio bi2 ON d.biblionumber = bi2.biblionumber
LEFT JOIN koha_plugin_fi_kohasuomi_okmstats_biblio_data_elements bde ON d.biblionumber = bde.biblionumber
WHERE date(datetime) BETWEEN <<Aikaväli alkaen|date>> AND <<Päättyen|date>>
AND b.categorycode != 'EITILASTO'
AND s.type in ('issue', 'renew')
```

### Kirjaston voimassa olevien lainojen määrä eräpäiväaikavälillä

Raportti laskee, kuinka monta voimassa olevaa lainaa on valitussa kirjastossa valitulla eräpäiväaikavälillä. Tällä voidaan tarkistaa esim. kirjaston yllättävissä sulkutilanteissa, onko tarpeen siirtää eräpäiviä eteenpäin.

Lisätty: 18.10.2022<br />
Lisääjä: Anneli Österman<br />
Versio: 21.11

```
select date(date_due) as 'Eräpäivä',count(*) as 'Lainojen määrä' 
from issues
where branchcode= <<Kirjasto|branches>>
and date(date_due) between  <<Alkupvm|date>> and  <<Loppupvm|date>>
group by 1 WITH ROLLUP
```

### Celia-äänikirjojen lainat

PUHECD-aineiston 599a Daisy-niteiden lainat+uusinnat yhteensä niteen kotikirjaston mukaan

Lisätty: 24.11.2022<br />
Lisääjä: Päivi Knuutinen<br />
Versio: 21.11

```
select author as 'Tekijä', title as 'Nimeke', items. biblionumber, items.location as 'Hyllypaikka', ExtractValue(metadata, '//datafield[@tag="599"]/subfield[@code="a"]') as 'Celia', datelastborrowed as 'Viimeksi lainattu', items.dateaccessioned as 'Vastaanottopäivä', items.holdingbranch as 'sijaintikirjasto', issues as 'lainat'
from statistics
left join items using (itemnumber)
Left join biblio on items.biblionumber=biblio.biblionumber
LEFT JOIN biblioitems on items.biblionumber=biblioitems.biblionumber
LEFT JOIN biblio_metadata on items.biblionumber=biblio_metadata.biblionumber
where items.homebranch = <<Niteen kotikirjasto|branches>>
and biblioitems.itemtype='PUHECD'
and ExtractValue(metadata, '//datafield[@tag="599"]/subfield[@code="a"]') = 'Daisy'
group by items.itemnumber
order by lainat DESC
```

## Kaukolainat

### Kaukolainojen kuukausitilasto, valitse vuosi

Laskee annetut kaukolainat ja ryhmittelee ne kuukauden ja aineistotyypin mukaan. Parametreiksi annetaan vuosi ja lainaava kirjasto. Mukaan lasketaan vain ensilainat.

Pvm: 2.7.2021<br />
Lisääjä: Anneli Österman

```
SELECT month(datetime) AS 'Kuukausi',itemtype AS 'Nidetyyppi', count(*) AS 'Kaukolainojen määrä'
FROM statistics
WHERE categorycode='KAUKOLAINA'
AND type='issue'
AND year(datetime)=<<Kirjoita vuosiluku>>
AND branch=<<Lähettävä kirjasto|branches>>
GROUP BY month(datetime), itemtype
```

### Kaukolainojen kuukausitilasto, valitse aikaväli

Laskee annetut kaukolainat ja ryhmittelee ne kuukauden ja aineistotyypin mukaan. Parametreiksi annetaan aikaväli ja lainaava kirjasto. Mukaan lasketaan vain ensilainat.

Pvm: 2.7.2021<br />
Lisääjä: Anneli Österman

```
SELECT month(datetime) AS 'Kuukausi',itemtype AS 'Nidetyyppi', count(*) AS 'Kaukolainojen määrä'
FROM statistics
WHERE categorycode='KAUKOLAINA'
AND type='issue'
AND date(datetime) between <<Alkaen|date>> AND <<Päättyen|date>>
AND branch=<<Lähettävä kirjasto|branches>>
GROUP BY month(datetime), itemtype with ROLLUP
```

### Kaukolainojen vuositilasto hyllypaikan mukaan

Laskee annetut kaukolainat. Parametreiksi annetaan vuosi, hyllypaikka ja lainaava kirjasto. Mukaan lasketaan vain ensilainat.

Pvm: 2.7.2021<br />
Lisääjä: Anneli Österman

```
SELECT count(*) AS 'Kaukolainojen määrä'
FROM statistics
LEFT JOIN items using (itemnumber)
WHERE categorycode='KAUKOLAINA'
AND type='issue'
AND year(datetime)=<<Kirjoita vuosiluku>>
AND branch=<<Lähettävä kirjasto|branches>>
AND location=<<Hyllypaikka|LOC>>
GROUP BY year(datetime)
```

### Kaukolainojen vuositilasto, kaunokirjallisuus

Laskee annetut kaukolainat, joiden niteen luokka kuuluu kaunokirjallisuuden luokkaan. Parametreiksi annetaan vuosi, aineistotyyppi ja lainaava kirjasto. Mukaan lasketaan vain ensilainat.

Pvm: 2.7.2021<br />
Lisääjä: Anneli Österman

```
SELECT count(*) AS 'Kaukolainojen määrä'
FROM statistics
LEFT JOIN items using (itemnumber)
WHERE categorycode='KAUKOLAINA'
AND type='issue'
AND year(datetime)=<<Kirjoita vuosiluku>>
AND branch=<<Lähettävä kirjasto|branches>>
AND itemtype=<<Aineistotyyppi|itemtypes>>
AND (cn_sort like '80%' OR cn_sort like '81%' OR cn_sort like '82%' OR cn_sort like '83%' OR cn_sort like '84%' OR cn_sort like '85%')
GROUP BY year(datetime)
```

### Kaukolainojen vuositilasto, postinumero ja aineistotyyppi

Laskee annetut kaukolainat ja ryhmittelee tulokset postinumeron ja aineistotyypin mukaan. Parametreiksi annetaan vuosi ja lainaava kirjasto. Mukaan lasketaan vain ensilainat.

Pvm: 2.7.2021<br />
Lisääjä: Anneli Österman

```
SELECT zipcode AS 'Postinumero', itemtype AS 'Nidetyyppi', count(*) AS 'Kaukolainojen määrä'
FROM statistics
LEFT JOIN borrowers USING (borrowernumber)
WHERE cateogrycode='KAUKOLAINA'
AND type='issue'
AND year(datetime)=<<Kirjoita vuosiluku>>
AND branch=<<Lähettävä kirjasto|branches>>
GROUP BY zipcode, itemtype
```

## Asiakkaat ja tunnukset


### Celia-lainaajien määrä vuoden ja kunnan mukaan

Celian aineistoja lainanneiden asiakkaiden määrä kuntatasolla ja vuoden mukaan.

Lisännyt: Anneli Österman / OUTI-kirjastot<br />
Korjannut: Mikko Liimatainen / Vaski-kirjastot<br />
Aika: 20.8.2019 / 2022

```
select count(distinct(borrowernumber)) as Lainaajat
from statistics s
left join items i ON i.itemnumber=s.itemnumber
left join koha_plugin_fi_kohasuomi_okmstats_biblio_data_elements bde ON bde.biblionumber=i.biblionumber
where type in ('issue') 
and branch like <<Kirjoita kirjastolyhenteen alku ja %>> 
and year(datetime)=<<Vuosiluku>>
and categorycode not in ('EITILASTO')
and bde.celia=1
```

### Epäonnistuneet tekstiviestit

Listaa valitulta aikaväliltä viestijonosta ne viestit, jotka on yritetty lähettää tekstiviestinä ja lähetys on epäonnistunut jostain syystä. Listalle tulee asiakkaan nimi, kirjastokortin numero linkkinä asiakastietoon _(muokkaa linkkiin oman kimppasi osoite)_, tekstiviesti numeroon -tieto, status, epäonnistumisen syy, viestin aihe, viestin sisältö, jonoonlisäämisaika ja asiakkaalla olevat viestit (näkee siis, onko hänellä jo huomautus virheellisestä puhnumerosta).

Lisääjä: Anneli Österman / OUTI-kirjastot

```
SELECT Concat(borrowers.surname, ', ', borrowers.firstname, '<br/>', '<a href=\"/cgi-bin/koha/members/moremember.pl?borrowernumber=',borrowers.borrowernumber,'">',borrowers.cardnumber,'</a>') AS 'Asiakas', borrowers.smsalertnumber AS 'Numero', status AS 'Status', failure_code AS 'Huomatus', subject AS 'Aihe', content AS 'SMS-viesti', time_queued AS 'Jonotusaika', messages.message AS 'Viesti asiakastiedoissa'
FROM message_queue
LEFT JOIN borrowers ON borrowers.borrowernumber = message_queue.borrowernumber
LEFT JOIN messages ON message_queue.borrowernumber = messages.borrowernumber
WHERE message_transport_type = 'sms' 
AND (status = 'failed') 
AND time_queued >= NOW() - INTERVAL <<Monenko päivän ajalta>> DAY 
ORDER BY time_queued ASC
```

### Lähetettyjen viestien määrä

Kyselyllä voi hakea tietyllä aikavälillä lähetettyjen viestien määrä. Tulokset ryhmitellään viestityypin mukaisesti.

Lisätty: 13.10.2023
Lisääjä: Anneli Österman

<pre>
select message_transport_type as 'Viestityyppi',count(*) as 'Viestien määrä aikavälillä' 
from message_queue
where date(time_queued) between <<Aloituspvm|date>> and <<Loppupvm|date>>
group by message_transport_type
</pre>

### Arkistoitujen viestien hakeminen message_queuen vuositaulusta

Kyselyllä voi hakea viesti-taulun vuositauluista vanhempia viestejä, jotka eivät näy enää virkailijaliittymän kautta. Kyselylle annetaan parametriksi asiakkaan borrowernumber.

Pvm: 8.9.2023
Lisääjä: Anneli Österman

```
select * from message_queue_2022
where borrowernumber = <<borrowernumber>>

union 
select * from message_queue_2021
where borrowernumber = <<borrowernumber>>

union 
select * from message_queue_2020
where borrowernumber = <<borrowernumber>>

order by 1 desc
```

### Ylimääräistä tekstiä sisältävät puhelinnumerot

Hakee kaikki ylimääräistä tekstiä sisältävät puhelinnumerot Kohan borrowers-taulusta. Tekstejä on päätynyt puhelinnumerokenttiin ainakin Pallas-konversioissa. Mahdollisesti myös Origoista.

Lisääjä: Kodo Korkalo / Koha-Suomi<br />
Pvm: 8.1.2019

```
SELECT CONCAT('<a href="/cgi-bin/koha/members/moremember.pl?borrowernumber=', borrowernumber, '">', cardnumber, '</a>') AS borrower, phone, mobile, smsalertnumber FROM borrowers
 WHERE LOWER(phone) REGEXP '.*[a-z].*'
    OR LOWER(mobile) REGEXP '.*[a-z].*'
    OR LOWER(smsalertnumber) REGEXP '.*[a-z].*'
```

### Asiakkaat, joiden puhelinnumerot tarkistettava käsin

Hakee kaikki ylimääräisiä merkkejä sisältävät mobiili- ja lankapuhelinnumerot Kohan borrowers-taulusta.

Lisääjä: Lari Strand / Koha-Suomi<br />
Pvm: 30.8.2021

```
SELECT CONCAT('<A href="/cgi-bin/koha/members/moremember.pl?borrowernumber=', borrowernumber, '">', borrowernumber, '</A>') AS 'asiakas-ID',
phone as Lankapuhelin, mobile as Matkapuhelin FROM borrowers where phone REGEXP '[[:alpha:]]|[,]|[.]|[/]' OR mobile REGEXP '[[:alpha:]]|[,]|[.]|[/]'
```

### Tarkistuslista, ketkä virkailijat ovat vaihtaneet salasanan vuonna 2020

Raportilla voi tarkistaa, ketkä virkailijat ovat vaihtaneet salasanat vuonna 2020

Lisääjä: Anneli Österman<br />
Pvm: 4.2.2020

```
select cardnumber,firstname,surname,branchcode from action_logs
JOIN borrowers ON borrowernumber=object
where module='MEMBERS'
and action='CHANGE PASS'
and categorycode='VIRKAILIJA'
and year(timestamp)=2020;
```

### Asiakkaan haku maksun tapahtumanumerolla

Raportilla voi hakea asiakkaan Ceepos-kassan tapahtumanumeron perusteella.

Lisääjä: Anneli Österman<br />
Pvm: 7.4.2020

```
select Concat('<a href=\"/cgi-bin/koha/members/boraccount.pl?borrowernumber=',a.borrowernumber,'">',a.borrowernumber,'</a>') AS 'Asiakas' 
from accountlines a
JOIN payments_transactions_accountlines pta using (accountlines_id)
where pta.transaction_id=<<Tapahtumanumero>>
```

### Takaajattomat lapsiasiakkaat

Raportilla voi hakea lapsiasiakkaat, joilla ei ole takaajaa. Tarkista, että lapsiasiakkaiden asiakastyypit vastaa oman kimpan asiakastyyppejä.

Lisääjä: Anneli Österman<br />
Pvm: 7.4.2020 / Päivitetty 31.5.2023

```
select borrowernumber 
from borrowers 
where categorycode in ('LAPSI', 'LAOMATOIMI') 
and borrowernumber not in (select guarantee_id from borrower_relationships);
```

### Henkilöasiakkaat, joilla takaaja

Raportilla voi hakea henkilöasiakkaat, joilla on takaaja.

Lisääjä: Anneli Österman<br />
Tekijä: Kodo Korkalo<br />
Pvm: 7.4.2020

```
select concat ('<a href="/cgi-bin/koha/members/moremember.pl?borrowernumber=', borrowernumber, '">', coalesce(cardnumber, concat(borrowernumber, ' (borrowernumber)')), '</a>') as Korttinumero, concat(substring(firstname,1,1), '. ', substring(surname,1,1), '.') as Nimikirjaimet, branchcode as Kotikirjasto, categorycode as Asiakastyyppi, concat('<a href="/cgi-bin/koha/members/moremember.pl?borrowernumber=',guarantorid,'">',guarantorid,'</a>') as Takaajalinkki, concat(substring(contactfirstname,1,1), '. ', substring(contactname,1,1), '.') as 'Takaajan nimikirjaimet' from borrowers where (contactfirstname is not null or contactname is not null) and categorycode='HENKILO' order by 3
```

### Kirjastokorttinumerottomat henkilöasiakkaat

Raportti listaa henkilöasiakkaat, joilla ei ole kirjastokortin numeroa. Parametriksi valitaan kirjasto.

Lisääjä: Anneli Österman<br />
Pvm: 7.4.2020

```
select concat ('<a href="/cgi-bin/koha/members/moremember.pl?borrowernumber=', borrowernumber, '">',borrowernumber,'</a>') as Asiakas, branchcode as Kotikirjasto
from borrowers
where cardnumber is null
and categorycode='HENKILO'
AND branchcode=<<Valitse kirjasto|branches>>
```

### Asiakkaat, joilla on mahdollisesti virheellinen syntymäaika

Raportti listaa asiakkaat, joiden syntymäaika on ennen 1.1.1920, mukaan ei oteta asiakastyyppiä EITILASTO.

Lisääjä: Anneli Österman<br />
Pvm: 7.4.2020

```
select concat ('<a href="/cgi-bin/koha/members/moremember.pl?borrowernumber=', borrowernumber, '">', coalesce(cardnumber, concat(borrowernumber, ' (borrowernumber)')), '</a>') as Korttinumero,dateofbirth as 'Syntymäaika' 
from borrowers where dateofbirth< '1920-01-01' 
and categorycode != 'EITILASTO' order by 2
```

### Asiakkaat joilla viallinen sotuavain

```
SELECT CONCAT("<a href='/cgi-bin/koha/members/memberentry.pl?op=modify&borrowernumber=", borrowernumber, "'>", cardnumber, "</a>") AS korttinumero,
       CONCAT("'<tt>", attribute, "</tt>'") AS sotuavain
FROM borrower_attributes
JOIN borrowers USING(borrowernumber)
WHERE code = 'SSN'
  AND attribute NOT REGEXP '^sotu[0-9]+$'
```

### Asiakkaat, joilla ei ole sotu-avainta

Raportilla voi hakea (henkilö)asiakkaat, joilla ei ole sotu-avainta. Haulle annetaan parametrina asiakkaan kotikirjasto. Jos sitä ei halua kyselyyn mukaan, voi jättää kyselyn neljännen rivin pois.

Lisätty: 4.10.2023
Lisääjä: Anneli Österman
Versio: 22.11

```
SELECT borrowernumber, branchcode as Kotikirjasto, b.categorycode as Asiakastyyppi, b.dateenrolled as 'Tullut asiakkaaksi'
FROM borrowers b
WHERE borrowernumber not in (select borrowernumber from borrower_attributes where code='SSN')
AND branchcode=<<Valitse kotikirjasto|branches>>
AND categorycode in ('HENKILO', 'LAPSI', 'MUUHUOL')
```

### Asiakkaiden määrä kirjastoittain

Raportti laskee asiakkaiden määrän kirjastoittain. Mukaan ei tule asiakastyyppejä VIRKAILIJA, AUTOM ja EITILASTO. Näytetään 100 riviä.

Lisääjä: Anneli Österman<br />
Pvm: 9.4.2020

```
SELECT branchcode AS 'Kirjasto',count(*) AS 'Asiakkaiden määrä' 
FROM borrowers
WHERE categorycode not in ('VIRKAILIJA', 'AUTOM', 'EITILASTO')
GROUP BY branchcode limit 100
```

### Asiakkaat, joiden varausmäärä on lähellä sallittua maksimia

Raportti listaa sellaiset asiakkaat, joilla on varauksia lähellä sallittua maksiamia. Raportti laskee myös asiakkaiden voimassa olevien varausten määrän. Muuta raporttiin HAVING COUNT -kohtaan omalle kirjastolle/kimpalle sopiva luku eli esim. jos maksimi on 100 varausta, niin jokin vähän sitä pienempi luku. Raportissa huomioidaan asiakastyypit HENKILO ja LAPSI.

Lisääjä: Anneli Österman<br />
Pvm: 9.4.2020

```
SELECT CONCAT('<a href="/cgi-bin/koha/members/moremember.pl?borrowernumber=', borrowernumber, '">',b.borrowernumber,'</a>') as 'Asiakas', count(*) as 'varausten määrä'
FROM reserves r
JOIN borrowers b USING (borrowernumber)
WHERE categorycode IN ('HENKILO', 'LAPSI')
GROUP BY borrowernumber
HAVING COUNT(*)>90
ORDER BY 2 DESC
```


### Asiakkaat, joilla on huomautuksia

Raportti listaa kirjastoittain asiakkaat, joilla on huomautuksia.

Lisääjä: Anneli Österman<br />
Pvm: 9.4.2020

```
SELECT CONCAT('<a href="https://koha.outikirjastot.fi:8080/cgi-bin/koha/members/moremember.pl?borrowernumber=',borrowers.borrowernumber,'">',borrowers.cardnumber,'</a>') AS 'Asiakas',  opacnote AS 'Huomautus'
FROM borrowers 
WHERE opacnote !=''
AND branchcode=<<Valitse kirjasto|branches>>
```


### Asiakkaan haku varaustunnuksella

Raportilla voi hakea asiakkaan varaustunnisteen perusteella. Välillä asiakashaulla varaustunnuksella hakeminen palauttaa liikaa tuloksia, koska tunnus on hyvin yleinen ja osuu haussa myös muihin tietoihin kuten etu- ja sukunimeen.

Lisääjä: Anneli Österman<br />
Pvm: 25.8.2020

```
SELECT CONCAT('<a href=\"/cgi-bin/koha/members/moremember.pl?borrowernumber=',b.borrowernumber,'" target="_blank">',b.othernames,'</a>') as Varaustunnus
FROM borrowers b
WHERE othernames=<<Kirjoita varaustunnus>>
```

### Asiakkaan epäonnistuneiden kirjautumisyritysten määrän tarkistaminen

Raportilla voi hakea kirjastokortin numeron perusteella asiakkaan epäonnistuneiden kirjautumisyritysten määrän. Jos määrä on sama tai ylittää FailedLoginAttempts-järjestelmäasetukseen määritetyn luvun, on asiakkaan tunnus lukossa ja siihen pitää vaihtaa uusi salasana.

Lisääjä: Anneli Österman<br />
Pvm: 27.4.2021

```
select login_attempts as 'Kirjautumisyrityksiä' from borrowers where cardnumber=<<Kirjastokortin numero>>
```

### Automaatit ja niiden toimittajat

Raportilla voi hakea SIP2-tunnukset, joiden tietoihin on merkitty asiakasmääreet TOIMITTAJA ja AUTOTYPE. [Ohje asiakasmääreiden lisäämisestä](https://tiketti.koha-suomi.fi/projects/koha-suomen-dokumentaatio/wiki/Automaattityypin_ja_toimittajan_lis%C3%A4%C3%A4minen_asiakasm%C3%A4%C3%A4reeksi).

Lisääjä: Anneli Österman<br />
Pvm: 9.6.2021

```
select b.borrowernumber, branchcode, cardnumber, attribute
from borrowers b
join borrower_attributes using (borrowernumber)
where code in ('TOIMITTAJA', 'AUTOTYPE')
order by 3
```


### Asiakkaat, joilla kirjastokortin numero ja varaustunnus sama

Raportilla voi hakea asiakkaat, joilla on kirjastokortin numero ja varaustunnus sama. Säädä tarvittaessa asiakastyyppien tunnuksia, jotta virkailijatunnukset ja ei-tilastoitavat lainat jää pois tuloksista.

Lisääjä: Anneli Österman<br />
Pvm: 3.5.2022

```
select CONCAT('<a href=\"/cgi-bin/koha/members/moremember.pl?borrowernumber=',borrowernumber,'" target="_blank">',cardnumber,'</a>') AS 'Asiakas', othernames from borrowers where cardnumber=othernames and categorycode not in ('VIRKAILIJA', 'EITILASTO')
```

### Asiakkaat, joilla on paljon epäonnistuneita kirjautumisyrityksiä

Raportilla voi hakea asiakkaat, joiden epäonnistuneet kirjautumisyritykset ylittävät tietyn lukumäärän. Tietosuojasyistä huomattavan suuren määrän epäonnistuneita kirjatumisyrityksiä (50 tai yli) omaavien asiakkaiden kirjastokortti voi olla tarpeen vaihtaa.

Lisääjä: Kodo Korkalo<br />
Pvm: 15.11.2022

```
SELECT CONCAT('<a href=\"/cgi-bin/koha/members/moremember.pl?borrowernumber=',borrowernumber,'" target="_blank">',cardnumber,'</a>') AS 'Asiakas',
login_attempts AS 'Kirjautumisyritykset'
FROM borrowers
WHERE login_attempts>=<<Etsi asiakkaat, joilla on yli tämä määrä kirjautumisyrityksiä>>
```

## Varaukset

### Tietueen varaushistoria

Listaa valitulta aikaväliltä tietueen varaukset, jotka eivät ole enää voimassa. Voimassa olevat voi katsoa tietueen varauksista.

```
SELECT o.reservedate, o.branchcode, o.borrowernumber, o.waitingdate, o.expirationdate, i.barcode
FROM old_reserves o
JOIN items i USING (itemnumber)
WHERE o.biblionumber =<<Tietuenumero>>
AND date(o.reservedate) BETWEEN <<Alkupvm|date>> AND <<Loppupvm|date>>
ORDER BY o.reservedate DESC
```

### Nimekkeet, joihin on eniten varauksia

Varausten määrä kannattaa rajata (esim. 50), jotta et saa tulokseksi kaikkia mahdollisia nimekkeitä, joihin on olemassa varaus. Mukaan tulee myös tietueeseen liittyvä nidemäärä. Tuloksessa mukana myös hankinnassa olevat niteet.

Lisääjä: Anneli Österman / OUTI-kirjastot

```
SELECT concat('<a href=\"/cgi-bin/koha/catalogue/detail.pl?biblionumber=',b.biblionumber,'">',b.title,'</a>') AS Nimeke, b.author AS Tekijä, m.cn_class AS Luokka, m.itemtype AS Aineistolaji, count(h.reservedate) AS 'Varaukset', (select count(*) from items where biblionumber=b.biblionumber) AS 'Niteiden määrä'
FROM biblio b
LEFT JOIN biblioitems m USING (biblionumber)
LEFT JOIN reserves h ON (b.biblionumber=h.biblionumber)
GROUP BY b.biblionumber 
HAVING count(h.reservedate)  >= <<Varauksia vähintään>>
ORDER by Varaukset DESC
```


### Eniten uusia varauksia, top20

Raportilla voi hakea top20-listan teoksista, joihin on tehty eniten varauksia seitsemän viime päivän aikana.

Lisääjä: Anneli Österman / OUTI-kirjastot<br />
Pvm: 25.10.2018

```
SELECT count(distinct reserve_id) AS 'Varauksia', title AS 'Teos', author AS 'Tekijä', cn_class AS 'Luokka'
FROM (
SELECT b.title, b.author, b.biblionumber, reserves.reserve_id, bi.cn_class
FROM reserves 
left JOIN biblio b ON (reserves.biblionumber=b.biblionumber)
JOIN borrowers ON (reserves.borrowernumber=borrowers.borrowernumber)
JOIN biblioitems bi ON(b.biblionumber=bi.biblionumber)
WHERE DATE(reserves.reservedate) > DATE_SUB(CURRENT_DATE(),INTERVAL 7 DAY) 
      AND DATE(reserves.reservedate) <=CURRENT_DATE()
AND borrowers.categorycode !='EITILASTO'
UNION ALL
SELECT b.title, b.author, b.biblionumber, old_reserves.reserve_id, bi.cn_class
FROM old_reserves 
left JOIN biblio b ON (old_reserves.biblionumber=b.biblionumber)
JOIN borrowers ON (old_reserves.borrowernumber=borrowers.borrowernumber)
JOIN biblioitems bi ON(b.biblionumber=bi.biblionumber)
WHERE DATE(old_reserves.reservedate) > DATE_SUB(CURRENT_DATE(),INTERVAL 7 DAY) 
      AND DATE(old_reserves.reservedate) <=CURRENT_DATE()
AND borrowers.categorycode !='EITILASTO'
 ) AS myholds 
GROUP BY biblionumber 
ORDER BY 1 DESC 
LIMIT 20;
```

### Varauksen tiedot lokilla

Raportilla voi tarkistaa, mitä tietoja varauksesta on tallentunut action_logs-tauluun. Parametreinä käytetään asiakkaan borrowernumberia ja teoksen biblionumberia. Jos varaus on edelleen voimassa, vaihda old_reserves-taulu reserves-tauluksi.

![kuva](https://github.com/KohaSuomi/kohasuomi.github.io/assets/33121325/79713278-53b7-4262-a9ae-c91425ce724d)


*timestamp*: tapahtuma-aika

*user*: varauksen tekijä. Jos tekijä on virkailija, näkyy tässä hänen borrowernumber. Jos tekijä on asiakas itse, näkyy tässä Finna-apin borrowernumber

*module*: Kohan osio, varauksissa se on aina HOLDS

*action*: tehty toiminto. 
* CREATE = varaus luotu
* SUSPEND = varauksen keskeytys
* RESUME = keskeytys poistettu
* MODIFY = varaukseen on tehty jokin muutos, esim. noutopaikka vaihdettu tai poistettu odottaa-tila. 
* CANCEL = varauksen on poistanut virkailija tai asiakas
* FILL = varaus on lainattu asiakkalle

*object*: varauksen id reserves/old_reserves-taulussa

*info*: tarkempia tietoja varauksesta ja mitä muuttunut. 
* branchcode = noutokirjasto
* cancellation_reason = poiston syy (voidaan määrittää joissain yhteyksissä)
* cancellationdate = poistopäivä
* desk_id = tiskin tunnus, jos käytössä Lainaustiskit-toiminto
* expirationdate = varauksen vanhenemispäivä
* found = varauksen tila (undef, jos voimassa. Muita T=kuljetettavana, P=käsittelyssä, W=odottaa noutoa)
* item_level_hold = nidevaraus (0=ei, 1=kyllä)
* itemtype = nidetyyppi, jos varaus rajataan koskemaan tiettyä nidetyyppiä
* lowestPriority = pidetään jonon hännillä (0=ei, 1=kyllä)
* non_priority = kiireetön varaus (0=ei, 1=kyllä)
* notificationdate = ilmoituspäivä (ei toimi meillä)
* priority = sija jonossa
* reminderdate = noudon muistutuspäivä (jos toiminto käytössä)
* reserve_id = varauksen tunnus reserves/old_reserves-taulussa
* reservedate = varauksen tekopäivä
* reservenote = varaushuomautus
* suspend = keskeytys (0=ei, 1=kyllä)
* suspend_until = keskeytetty tähän päivään asti
* timestamp = tapahtuma-aika
* waitingdate = päivä, jolloin varaus on tullut noudettavaksi.

*interface*: liittymä, jossa tapahtuma on tehty.
* intranet = virkailijaliittymä
* sip = automaatti
* api = rajapinta (esim. Finna)

Lisääjä: Anneli Österman<br />
Pvm: 20.3.2019

```
select * from action_logs where object in (select reserve_id from old_reserves where borrowernumber=<<borrowernumber>> and biblionumber=<<biblionumber>>) and module='HOLDS';
```

### Asiakkaan haku poistetun varauksen niteen viivakoodin perusteella

Raportilla voi hakea asiakkaan, jolla oli viimeksi varaus tiettyyn niteeseen. Parametriksi annetaan niteen viivakoodi. Tällä voi hakea, kenelle varaus kuului, jos varaus poistetaan vahingossa palautustilanteessa. Huom! Tieto pitää hakea ennen kuin nide jää kiinni seuraavaan varaukseen ja poistetaan/lainataan. Jos halutaan nähdä useampi varaaja, pitää poistaa "limit 1" tai laittaa suurempi numero siihen.

Lisääjä: Anneli Österman
Pvm: 31.7.2020

```
SELECT CONCAT('<a href=\"/cgi-bin/koha/members/moremember.pl?borrowernumber=',r.borrowernumber,'" target="_blank">',r.borrowernumber,'</a>') AS 'Asiakas', cancellationdate as 'Varauksen poistopäivä'
from old_reserves r
join items i using (itemnumber)
where i.barcode=<<Niteen viivakoodi>>
order by reserve_id DESC limit 1
```

### Varauslista Finna-muotoon

Raportilla voi hakea varaukset ja tallentaa ne Finnassa näkyvään muotoon. Varausten määrä rajoitettu 25:een, voit muuttaa määrää korvaamalla LIMIT-kohdassa olevan numeron.

Lisääjä: Päivi Knuutinen / Vaara<br />
Pvm: 3.12.2018

```
SELECT
  b.biblionumber AS 'biblionumber',
  count(h.reservedate) AS 'Varauksia' 
FROM biblio b 
LEFT JOIN biblio_metadata m USING (biblionumber) 
LEFT JOIN reserves h ON (b.biblionumber=h.biblionumber) 
GROUP BY b.biblionumber 
ORDER BY Varauksia DESC
LIMIT 25
```

### Varausten noudot päivittäin tunneittain valitulla aikavälillä

Raportilla voi katsoa, miten valitun kirjaston varausten noudot ajoittuvat päivittäin tunneittain valitulla aikavälillä.

Lisääjä: Anneli Österman / OUTI-kirjastot<br />
Pvm: 3.3.2020

```
SELECT date(s.datetime) as Pvm,hour(s.datetime) as Tunti,count(reserve_id) as 'Yhteensä'
FROM old_reserves o
LEFT JOIN statistics s using (borrowernumber)
WHERE found in ('F', 'W') 
AND date(s.datetime) BETWEEN <<Alkupvm|date>> AND <<Loppupvm|date>>
AND o.branchcode=<<Valitse kirjasto|branches>>
AND waitingdate IS NOT NULL
AND o.itemnumber=s.itemnumber
AND s.type='issue'
GROUP BY date(s.datetime), hour(s.datetime)
```

### Varausten noudot tunneittain valitulla aikavälillä

Raportilla voi katsoa, miten valitun kirjaston varausten noudot ajoittuvat tunneittain valitulla aikavälillä.

Lisääjä: Anneli Österman / OUTI-kirjastot<br />
Pvm: 3.3.2020

```
SELECT hour(s.datetime) as Tunti,count(reserve_id) as 'Yhteensä'
FROM old_reserves o
LEFT JOIN statistics s using (borrowernumber)
WHERE found in ('F', 'W') 
AND date(s.datetime) BETWEEN <<Alkupvm|date>> AND <<Loppupvm|date>>
AND o.branchcode=<<Valitse kirjasto|branches>>
AND waitingdate IS NOT NULL
AND o.itemnumber=s.itemnumber
AND s.type='issue'
GROUP BY hour(s.datetime)
```

### Noudettavissa olevat varaukset

Raportilla voi hakea kirjaston mukaan noudettavissa olevat varaukset. Sarakkeina on Varaustunniste, Viimeinen noutopäivä, teoksen nimeke ja niteen viivakoodi. Tiedot järjestetään ensimmäisen sarakkeen mukaan. Jos haluaa, voi ORDER BY -riville lisätä vielä kakkosen, jolloin varaukset järjestetään ensin varaustunnisteen mukaan ja sen sisällä vielä viimeisen noutopäivän mukaan.

Lisääjä: Anneli Österman<br />
Pvm: 9.6.2020

```
SELECT bo.othernames as 'Varaustunniste',r.expirationdate as 'Viimeinen noutopäivä',b.title as 'Teos',i.barcode as 'Viivakoodi'
FROM reserves r
JOIN borrowers bo ON (r.borrowernumber=bo.borrowernumber)
JOIN biblio b ON (r.biblionumber=b.biblionumber)
LEFT JOIN items i ON (r.itemnumber=i.itemnumber)
WHERE r.branchcode=<<Valitse kirjasto|branches>>
AND r.found='W'
ORDER BY 1
```

### Vanhentuneet automaattisesti poistetut varaukset

Raportilla voi hakea automaattisesti poistetut varaukset tietystä toimipaikasta (kun järjestelmäasetus ExpireReservesMaxPickUpDelay on asetettu päälle). Lista on järjestetty varaustunnuksen mukaan.

Lisääjä: Minna Kivinen<br />
Pvm: 28.9.2020<br />
Kohan versio: 20.05 

```
SELECT borrowers.othernames AS "Varaustunnus", items.barcode AS "Nide", biblio.title AS "Nimeke", old_reserves.expirationdate AS "Varaus vanhentunut", old_reserves.cancellationdate AS "Varaus poistettu"
FROM old_reserves 
LEFT JOIN borrowers using(borrowernumber)
LEFT JOIN biblio using(biblionumber)
LEFT JOIN items using(itemnumber)
WHERE cancellationdate = curdate() AND found = "W" AND old_reserves.branchcode = <<Anna noutopaikan koodi>>
ORDER BY borrowers.othernames
```

### Vanhentuneet automaattisesti poistetut varaukset viimeisen noutopäivän perusteella

Ylläolevasta hieman muokattu raportti, jolla voi hakea tietyn viimeisen noutopäivän automaattisesti poistetut varaukset tietystä toimipaikasta (kun järjestelmäasetus ExpireReservesMaxPickUpDelay on asetettu päälle). Lista on järjestetty varaustunnuksen mukaan.

Lisääjä: Hanna Saario<br />
Pvm: 28.9.2020<br />
Kohan versio: 20.05 

```
SELECT borrowers.othernames AS "Varaustunnus", items.barcode AS "Nide", biblio.title AS "Nimeke", old_reserves.expirationdate AS "Varaus vanhentunut", old_reserves.cancellationdate AS "Varaus poistettu" 
FROM old_reserves 
LEFT JOIN borrowers using(borrowernumber)
LEFT JOIN biblio using(biblionumber)
LEFT JOIN items using(itemnumber)
WHERE old_reserves.expirationdate = <<Anna viim. noutopäivä|date>> AND found = "W" AND old_reserves.branchcode = <<Anna noutopaikan koodi>>
ORDER BY borrowers.othernames
```

### Niteet, jotka odottaa uudelleenpalautusta varauksen vuoksi

Raportilla voi hakea sellaiset niteet, jotka on palautettu automaattiin ja jääneet kiinni varaukseen, mutta joita ei ole sen jälkeen palautettu virkailijaliittymässä. 

Lisääjä: Anneli Österman<br />
Pvm: 10.12.2020, päivitetty 8.7.2022<br />
Kohan versio: 21.11

```
select title as 'Nimeke', author as 'Tekijä', CONCAT('<a href=\"/cgi-bin/koha/catalogue/detail.pl?biblionumber=',i.biblionumber,'" target="_blank">',i.barcode,'</a>') AS Nide,datelastseen as 'Nähty viimeksi'
from items i
join reserves using (itemnumber)
join biblio b ON i.biblionumber=b.biblionumber
where found='P' 
and branchcode=<<Valitse kirjasto|branches>>
and itemnumber not in (select itemnumber from branchtransfers where datearrived is not null)
```

### Varausjono 2.0 (Tuunattu versio Kohan Varausjono-listasta)

Raportti näyttää varauksen paikan varausjonossa. Jos sija ei ole 1, kannattaa yleensä odottaa, että jossain muualla kirja poimitaan ensin. Lainassa oleviin niteisiin tehdyt nidevaraukset sotkevat varausjonologiikkaa. Nidevarauksia nimekkeessä -sarakkeesta näkyy, montako nidevarausta tietueeseen on. Nämä yleensä pudottavat listassa näkyvän varauksen sijaintia varausjonossa todellista tilannetta alemmas. MUUTA i.itype <> 'EILAINA' -kohtaa tarpeen mukaan.

Lisääjä: Hannu Jokiranta / 3AMK-kirjastot<br />
Pvm: 19.1.2021<br />
Kohan versio 20.11

```
SELECT 
hft.source_branchcode AS 'Kirjasto',

CONCAT('<b><a href=\"/cgi-bin/koha/catalogue/detail.pl?biblionumber=', b.biblionumber, '\">', b.title, '</a></b>', ' ',
(SELECT 
  ExtractValue((
    SELECT metadata 
    FROM biblio_metadata 
    WHERE biblionumber=hft.biblionumber),
      '//datafield[@tag="245"]/subfield[@code="b"]')),

(SELECT 
  ExtractValue((
    SELECT metadata 
    FROM biblio_metadata 
    WHERE biblionumber=hft.biblionumber),
      '//datafield[@tag="245"]/subfield[@code="n"]')), ' ',

(SELECT 
  ExtractValue((
    SELECT metadata 
    FROM biblio_metadata 
    WHERE biblionumber=hft.biblionumber),
      '//datafield[@tag="245"]/subfield[@code="p"]')), '</br>',


'<i>',
(SELECT 
  ExtractValue((
    SELECT metadata 
    FROM biblio_metadata 
    WHERE biblionumber=hft.biblionumber),
      '//datafield[@tag="100"]/subfield[@code="a"]')), ' ',
'</i>',

(SELECT 
  ExtractValue((
    SELECT metadata 
    FROM biblio_metadata 
    WHERE biblionumber=hft.biblionumber),
      '//datafield[@tag="260"]/subfield[@code="c"]')),

(SELECT 
  ExtractValue((
    SELECT metadata 
    FROM biblio_metadata 
    WHERE biblionumber=hft.biblionumber),
      '//datafield[@tag="264"]/subfield[@code="c"]')), ' ',

(SELECT 
  ExtractValue((
    SELECT metadata 
    FROM biblio_metadata 
    WHERE biblionumber=hft.biblionumber),
      '//datafield[@tag="250"]/*')), '</br>'

' ISBN: ',
(SELECT 
  ExtractValue((
    SELECT metadata 
    FROM biblio_metadata 
    WHERE biblionumber=hft.biblionumber),
      '//datafield[@tag="020"]/subfield[@code="a"]'))

 ) AS 'Nimeke',

i.itemcallnumber AS 'Hyllypaikka', 
i.location AS 'Lokaatio',

CONCAT('<div style="text-align:center">',  '<b>', '<a href=\"/cgi-bin/koha/reserve/request.pl?biblionumber=', hft.biblionumber, '\">', res.priority, '</a>', '</b>', '</div>') AS 'Paikka varausjonossa',
res.branchcode AS 'Lähetä kohteelle',
DATE_FORMAT(res.reservedate, '%e.%c.%Y') AS 'Varauspäivä',
res.reservenotes AS 'Huomautukset', ivl.itemvaraukset AS 'Nidevarauksia nimekkeessä',
(SELECT ii.barcode FROM items ii JOIN reserves rr ON (ii.itemnumber = rr.itemnumber) WHERE rr.itemnumber = res.itemnumber) AS 'Nidevarattu nide',
CONCAT('<a href=\"/cgi-bin/koha/members/moremember.pl?borrowernumber=', hft.borrowernumber, '\">', bor.cardnumber, '</a>' ) AS 'Asiakas'

FROM
hold_fill_targets hft
JOIN reserves res ON (hft.borrowernumber = res.borrowernumber AND hft.biblionumber = res.biblionumber)
JOIN biblio b ON (hft.biblionumber = b.biblionumber)
JOIN items i ON (hft.biblionumber = i.biblionumber AND hft.source_branchcode = i.homebranch AND i.itype <> 'EILAINA')
JOIN borrowers bor ON (hft.borrowernumber = bor.borrowernumber)

/* Haetaan tietueet, joihin liittyy nide-varauksia & nide-varausten lukumäärä per tietue */
LEFT JOIN
(SELECT r.biblionumber, COUNT(r.itemnumber) AS itemvaraukset
FROM reserves r
WHERE r.itemnumber IS NOT NULL
AND r.found IS NULL
GROUP BY r.biblionumber) ivl ON (hft.biblionumber = ivl.biblionumber)

WHERE res.priority > 0
AND hft.source_branchcode = <<Kirjasto|branches>>
GROUP BY hft.biblionumber, hft.borrowernumber
ORDER BY i.itemcallnumber 
```

### Teokset, joihin kohdistuu nidevaraus

Raportilla voi hakea ne teokset/tietueet, joihin kohdistuu nidevaraus. Tulokseen tulee teoksen nimeke ja linkki varausjono-sivulle.

Pvm: 3.6.2021<br />
Lisääjä: Anneli Österman

```
select CONCAT('<a href=\"/cgi-bin/koha/reserve/request.pl?biblionumber=',b.biblionumber,'" target="_blank">',b.title,'</a>') AS 'Varausjonoon', branchcode AS 'Noutokirjasto'
from reserves
join biblio b using (biblionumber)
where itemnumber is not null 
and found is null
order by 2
```

### Noudettavissa olevat varaukset, joiden nide on kuljetettavana

Raportti hakee ne noudettavissa olevat varaukset, joiden nide on kuljetettavana.

Pvm: 28.6.2021, uusi versio 8.7.2021<br />
Lisääjä: Anneli Österman

```
select borrowers.othernames as Varaustunnus, CONCAT('<a href=\"/cgi-bin/koha/catalogue/detail.pl?biblionumber=',biblio.biblionumber,'" target="_blank">',biblio.title,'</a>') AS Nimeke, biblio.author as 'Tekijä', items.barcode as 'Viivakoodi', reserves.branchcode as 'Noutokirjasto', items.holdingbranch as 'Niteen sijaintikirjasto', GROUP_CONCAT(DISTINCT tobranch, '') as 'Kuljetuksen kohdekirjasto',  reserves.waitingdate as 'Varaus jäänyt kiinni', reserves.timestamp as 'Varausta viimeksi käsitelty', items.timestamp as 'Nidettä käsitelty'
from reserves 
LEFT JOIN biblio using (biblionumber)
LEFT JOIN borrowers using (borrowernumber)
LEFT JOIN items using (itemnumber)
LEFT JOIN branchtransfers using (itemnumber)
where found='W' 
and itemnumber in (select itemnumber from branchtransfers where datearrived is null)
AND datearrived is NULL
group by reserves.borrowernumber
```

### Niteet ja asiakkaat, joiden nide on lainassa ja kiinni kuljetettavassa varauksessa

Raportilla voi hakea niteet, jotka ovat sekä lainassa, että siihen liittyy varaus, joka on kuljetustilassa (found='T') toiselle asiakkaalle. Tyypillisesti tilanne voi syntyä, kun nide palautetaan noutokirjastossa palautusautomaattiin, eikä ole vielä sen jälkeen palautettu Kohassa. Raportti listaa varanneen asiakkaan ja varaukseen kiinni jääneen niteen viivakoodin sekä niteen sijaintikirjaston.

Pvm: 14.3.2022<br />
Lisääjä: Anneli Österman

```
select CONCAT('<a href=\"/cgi-bin/koha/members/moremember.pl?borrowernumber=',borrowernumber,'" target="_blank">',borrowernumber,'</a>') AS 'Asiakas', barcode,holdingbranch from items
join reserves using (itemnumber) where itemnumber in (select itemnumber from reserves where found='T') and onloan is not null
```

### Vanhentuneet noutamattomat varaukset

Valitse kirjastoyksikkö ja päivämääräväliin viimeistä noutopäivää seuraava päivä (esim. tiistain päivämäärä, kun etsitään varauksia, joissa on ollut maanantaina viimeinen noutopäivä), koska varaukset vanhennetaan seuraavana päivänä (yöllä). Jos haluat katsoa vain yhden päivän vanhentuneet, valitse kumpaankin päivämäärään sama päivä.

Raportti hakee ne varaukset, joissa on viimeinen noutopäivä yksi päivä aiemmin kuin vanhentumispäivä, eli mukaan tulee vain ne varaukset, joissa on vanhentumispäivää edeltävä päivä. Mukaan voi tulla sellaisia varauksia, joista asiakas on viimeisenä noutopäivänä ilmoittanut, että ei haluakaan sitä. Mukaan ei tule sellaisia, jotka asiakas on pyytänyt poistamaan muuna päivänä kuin viimeisenä noutopäivänä.

Pvm: 10.6.2022 / muokattu 1.7.2022 / muokattu 22.5.2023<br />
Lisääjä: Anneli Österman


```
select ba.attribute as 'Varaustunnus', b.title as 'Teos', i.barcode as 'Viivakoodi', bi.itemtype as 'Aineistotyyppi'
from old_reserves o
LEFT JOIN borrower_attributes ba ON (o.borrowernumber=ba.borrowernumber)
JOIN biblio b using (biblionumber)
JOIN biblioitems bi using (biblionumber)
JOIN items i using (itemnumber)
where o.branchcode=<<Valitse kirjasto|branches>>
and o.cancellationdate between <<Vanhentumispäivä alkaen|date>> AND <<Päättyen|date>>
and o.found='W'
AND o.expirationdate = (o.cancellationdate - INTERVAL 1 DAY)
AND ba.code='HOLDID'
order by 1,2
```

### Nimekkeet, joihin on varauksia mutta ainut nide merkitty kadonneeksi

Raportilla voi hakea nimekkeet, joihin kohdistuu varauksia, mutta ainut nide on merkitty kadonneeksi.

Pvm: 17.11.2022, muokattu 7.12.2022<br />
Lisääjä: Anneli Österman

```
SELECT CONCAT('<a href=\"/cgi-bin/koha/catalogue/detail.pl?biblionumber=',b.biblionumber,'" target="_blank">',b.title,'</a>') AS 'Teos', items.holdingbranch as "Sijaintikirjasto"
FROM reserves
LEFT JOIN biblio b USING (biblionumber)
LEFT JOIN items USING (biblionumber)
WHERE reserves.biblionumber IN (select biblionumber from items where itemlost !=0)
GROUP BY items.biblionumber having count(items.biblionumber)<2
ORDER BY 2
```

### Nimekkeet, joihin on varauksia mutta kaikki niteet kadonneet tai ei varattavia

Raportti hakee nimekkeet, joihin on varauksia mutta kaikki niteet kadonneet tai ei varattavia tai niteitä ei ole ollenkaan. Kehitetty versio yllä olevasta kyselystä.

Pvm: 30.11.2022<br />
Tekijä: Mikko Liimatainen

```
SELECT CONCAT('<a href=\"/cgi-bin/koha/catalogue/detail.pl?biblionumber=',b.biblionumber,'" target="_blank">',b.title,'</a>') AS 'Teos',
	COUNT(DISTINCT(i.itemnumber)) AS 'Nidemäärä'
FROM reserves r
LEFT JOIN biblio b USING (biblionumber)
LEFT JOIN items i USING (biblionumber)
WHERE r.biblionumber IN (SELECT biblionumber
FROM (SELECT i.*, SUM(IF(i.itemlost != 0, 1, 0)) AS 'Kadonneet', SUM(IF(i.damaged != 0, 1, 0)) AS 'Ei_varattavat', SUM(IF(i.itemlost != 0 OR i.damaged != 0, 1, 0)) AS 'Molemmat', COUNT(*) AS 'Kaikki'
FROM items i
GROUP BY i.biblionumber) tilat
WHERE tilat.Molemmat=tilat.Kaikki) OR r.biblionumber not in (select biblionumber from items)
GROUP BY r.biblionumber
ORDER BY Nidemäärä ASC
```

### Varausten määrä valitulla aikavälillä

Tehty: 8.8.2022<br />
Tekijä: Antti Kiviniemi / Koha-Suomen harjoittelija

```
SELECT reserves.branchcode AS 'Kirjaston koodi', 
SUM(CASE WHEN ((reserves.expirationdate < (<<Alkupvm|date>>) AND reserves.reservedate > (<<Loppupvm|date>>)) 
OR (old_reserves.expirationdate < (<<Alkupvm|date>>) AND old_reserves.reservedate > (<<Loppupvm|date>>))) THEN 0 ELSE 1 END)
AS 'Varaukset aikavälillä'
FROM reserves
LEFT JOIN old_reserves ON reserves.reserve_id = old_reserves.reserve_id
LEFT JOIN borrowers ON reserves.borrowernumber = borrowers.borrowernumber
WHERE
reserves.branchcode LIKE <<Kirjasto tai Kuntaosio>> 
AND
reserves.reservedate BETWEEN <<Alkupvm|date>> AND DATE_ADD(<<Loppupvm|date>>, INTERVAL 1 DAY)
AND NOT borrowers.categorycode = "EITILASTO" AND NOT borrowers.categorycode is null
GROUP BY reserves.branchcode WITH ROLLUP
```



## Kokoelma

### Niteettömät nimekkeet

Raportilla voi hakea niteettömät nimekkeet. Raportissa annetaan parametriksi aineistolaji. Jos haluat listata kaikki niteettömät kerralla aineistolajista riippumatta, poista raportista alimmainen rivi.

Lisääjä: Anneli Österman / OUTI-kirjastot<br />
Pvm: 3.7.2019

```
SELECT CONCAT(b.title, ', ', '<br/>', '<a href=\"/cgi-bin/koha/catalogue/detail.pl?biblionumber=',b.biblionumber,'\">',b.biblionumber,'</a>') AS 'Teos',
bi.itemtype AS 'Aineistolaji', b.biblionumber
from biblio b
LEFT JOIN items i ON b.biblionumber = i.biblionumber
LEFT JOIN biblioitems bi ON bi.biblionumber = b.biblionumber
LEFT JOIN biblio_metadata bm ON bm.biblionumber = b.biblionumber
WHERE ExtractValue(bm.metadata,'//datafield[@tag="773"]/subfield[@code="w"]') = ''
AND i.itemnumber IS NULL
AND bi.itemtype=<<Valitse aineistolaji|itemtypes>>
```

### Weeding tool

"Weeding toolilla" voi tutkia esim. nollalainoja kirjaston, aineistolajin, hyllypaikan mukaan. Tehty Koha Reports Libraryn raportin pohjalta. 

Lisääjä: Anneli Österman / OUTI-kirjastot<br />
Päivitetty: 24.11.2020

```
SELECT CONCAT( '<a href=\"/cgi-bin/koha/cataloguing/additem.pl?biblionumber=', biblio.biblionumber,'\">', 
       items.barcode, '</a>' ) AS 'Viivakoodi', items.cn_sort AS 'Luokka ja pääsana', biblio.title AS 'Nimeke', items.enumchron AS 'Lehden numero', items.ccode AS 'Kokoelma',
       biblioitems.publicationyear AS 'Julkaisuvuosi', items.dateaccessioned AS 'Viimeksi nähty', items.itype AS 'Aineistolaji', 
       items.issues AS 'Lainat', items.renewals AS 'Uusinnat', (IFNULL(items.issues, 0)+IFNULL(items.renewals, 0)) AS 'Lainat ja uusinnat yhteensä', 
       items.datelastborrowed AS 'Viimeksi lainattu', items.itemlost AS 'Kadonnut', items.onloan AS 'Lainassa', items.damaged AS 'Vaurioitunut', items.itemnotes AS 'Huomautukset'
FROM items
LEFT JOIN biblioitems ON (items.biblioitemnumber=biblioitems.biblioitemnumber) 
LEFT JOIN biblio ON (biblioitems.biblionumber=biblio.biblionumber)
WHERE items.itype= <<Aineistolaji|itemtypes>> AND items.holdingbranch=<<Sijaintikirjasto|branches>> 
      AND items.cn_sort BETWEEN <<Luokka väliltä, alkaen>> AND <<päättyen>>
AND items.location=<<Hyllypaikka|LOC>>
AND items.issues< <<Lainoja vähemmän kuin>>
AND items.datelastborrowed< <<Viimeksi lainattu aikaisemmin kuin|date>>
ORDER BY 10,2
```

### Kadonneet niteet kirjaston ja hyllypaikan mukaan

Raportti listaa kadonneet niteet kirjaston ja hyllypaikan mukaan.

```
SELECT concat('<a href=\"/cgi-bin/koha/catalogue/detail.pl?biblionumber=',b.biblionumber,'">',b.title,'</a>') AS Nimeke, b.author AS Tekijä, b.serial AS Sarja, b.seriestitle AS Sarjanimeke, i.itemcallnumber AS Signum, i.barcode AS Viivakoodi, i.itype AS Aineistolaji, i.holdingbranch AS Kirjasto, i.datelastseen AS 'Viimeksi nähty', i.itemlost_on AS 'Kadonneeksi merkitty' 
FROM items i
LEFT JOIN biblio b ON (i.biblionumber=b.biblionumber) 
LEFT JOIN authorised_values v ON (i.itemlost=v.authorised_value) 
WHERE i.itemlost != 0 AND i.itemlost = 1 AND v.category='LOST'
AND i.holdingbranch = <<Viimeisin havaintokirjasto|branches>>
AND i.location = <<Hyllypaikka|LOC>>
ORDER BY 7,5
```

### Poistojen apuväline

Lista, jossa on mm. lainamäärät sekä viimeiset havaintopäivät valitun kirjaston, aineistolajin, hyllypaikan ja luokan mukaan. Luokka-kohtaan täytyy jälkimmäiseen laatikkoon laittaa haluttua luokkaa seuraava luokka.

Päivitetty: 24.11.2020 / AÖ

```
SELECT CONCAT( '<a href=\"/cgi-bin/koha/cataloguing/additem.pl?biblionumber=', biblio.biblionumber,'\">', items.barcode, '</a>' ) AS 'Viivakoodi',
       items.cn_sort AS 'Luokka',
       items.ccode AS 'Kokoelma',
       biblio.author AS 'Tekijä',
       biblio.title AS 'Nimeke', 
       ExtractValue(biblio_metadata.metadata,'//datafield[@tag="245"]/subfield[@code="b"]') AS 'Muu nimeke', 
       ExtractValue(biblio_metadata.metadata,'//datafield[@tag="362"]/subfield[@code="a"]') AS 'Numero', 
       biblio.copyrightdate AS 'Vuosi',
       items.dateaccessioned AS 'Hankittu',
       items.itype AS 'Aineistolaji', 
       items.issues AS 'Lainoja',
       items.renewals AS 'Uusintoja',
       (IFNULL(items.issues, 0)+IFNULL(items.renewals, 0)) AS 'Lainoja yht.',
       items.datelastborrowed AS 'Viimeksi lainattu',
       items.datelastseen AS 'Viimeksi havaittu',
       items.itemlost AS 'Kadonnut',
       items.onloan AS 'Lainassa',
       items.itemnotes AS 'Nidehuomautus'
FROM items
LEFT JOIN biblioitems ON (items.biblioitemnumber=biblioitems.biblioitemnumber) 
LEFT JOIN biblio ON (biblioitems.biblionumber=biblio.biblionumber)
LEFT JOIN biblio_metadata ON (biblio.biblionumber=biblio_metadata.biblionumber)
WHERE
     items.itype = <<Aineistolaji|itemtypes>>
 AND items.holdingbranch = <<Kirjastopiste|branches>>
 AND items.location = <<Hyllypaikka|LOC>>
 AND items.cn_sort between <<Luokka väliltä, alkaen>> and <<päättyen>>
 AND items.datelastborrowed < <<Viimeksi lainattu ennen|date>>
 AND items.notforloan not in ('-1', '-2')
ORDER BY items.cn_sort
```

### Niteen havaintohistoria statistics-taulussa

Parametriksi annetaan niteen itemnumber.

Tehnyt: Anneli Österman<br />
Pvm: 6.8.2019

```
select * from statistics where itemnumber=<<Itemnumber>>
```

### Eriparit aineistolajit

Raportti listaa kirjastoittain nimekkeet, joiden aineistolaji poikkeaa kirjaston niteelle asetetusta aineistolajista.

Lisääjä: Anneli Österman<br />
Pvm: 9.4.2020

```
SELECT CONCAT(b.title, ', ', '<br/>', '<a href=\"/cgi-bin/koha/catalogue/detail.pl?biblionumber=',b.biblionumber,'\">',b.biblionumber,'</a>') AS 'Teos', bi.itemtype AS 'Teoksen aineistolaji', i.itype AS 'Niteen aineistolaji', i.holdingbranch AS 'Niteen sijaintikirjasto'
ROM biblio b
JOIN biblioitems bi USING (biblionumber)
JOIN items i USING (biblionumber)
WHERE bi.itemtype != i.itype
AND holdingbranch=<<Valitse sijaintikirjasto|branches>>
GROUP BY biblionumber
ORDER BY 4,1
```

### Nimekkeet, joissa on varauksia, mutta ei niteitä

Raportti listaa nimekkeet, joihin kohdistuu varauksia, mutta niillä ei ole yhtään nidettä, joka voisi täyttää varauksen.

Lisääjä: Anneli Österman<br />
Pvm: 9.4.2020

```
SELECT CONCAT(b.title, ', ', '<br/>', '<a href=\"/cgi-bin/koha/catalogue/detail.pl?biblionumber=',b.biblionumber,'\">',b.biblionumber,'</a>') AS 'Teos', CONCAT('<a href=\"/cgi-bin/koha/members/moremember.pl?borrowernumber=',borrowers.borrowernumber,'">',borrowers.cardnumber,'</a>') AS 'Asiakas'
FROM reserves
LEFT JOIN biblio b USING (biblionumber)
LEFT JOIN items USING (biblionumber)
LEFT JOIN borrowers USING (borrowernumber)
WHERE reserves.biblionumber NOT IN (select biblionumber from items)
```

### Aineistolajittomat niteet

Raportti listaa niteet, joilla ei ole aineistolajia määritetty.

Lisääjä: Anneli Österman<br />
Pvm: 17.4.2020

```
SELECT CONCAT('<a href=\"/cgi-bin/koha/cataloguing/additem.pl?op=edititem&biblionumber=',i.biblionumber,'&itemnumber=',i.itemnumber,'">',i.barcode,'</a>') AS 'Viivakoodi'
FROM items i
WHERE itype IN('NULL', '')
```

### Poistetut niteet ja niiden lainamäärät

Raportti listaa niteet, jotka on poistettu valittuna vuonna ja valitussa kunnassa. Niteistä haetaan nimeke, tekijä, julkaisuvuosi, lehden numero, viivakoodi, sijaintikirjasto, hyllypaikka, aineistolaji, hankintapäivä, viimeksi nähty -päivä, viimeksi lainattu -päivä ja lainakerrat. Tulokset järjestetään sarakkeen 12 mukaan (lainakerrat).

Lisääjä: Anneli Österman<br />
Pvm: 29.3.2021 (muokattu 8.12.2021)

```
select b.title as 'Nimeke',b.author as 'Tekijä',b.copyrightdate as 'Julkaisuvuosi',enumchron as 'Lehden numero',barcode as 'Viivakoodi',holdingbranch as 'Sijaintikirjasto',location as 'Hyllypaikka',itemtype as 'Aineistotyyppi',dateaccessioned as 'Hankintapäivä',datelastseen as 'Viimeksi nähty',datelastborrowed as 'Viimeksi lainattu',issues as 'Lainakerrat'
from deleteditems
join biblio b using (biblionumber)
join biblioitems bi using (biblionumber)
where convert(homebranch using 'utf8') like (@Kunta:= <<Kuntaosio ja prosenttimerkki>>)
and convert(year(deleteditems.timestamp) using 'utf8') like (@Vuosi:= <<Kirjoita vuosi>>)

UNION ALL
select db.title as 'Nimeke',db.author as 'Tekijä',db.copyrightdate as 'Julkaisuvuosi',enumchron as 'Lehden numero',barcode as 'Viivakoodi',holdingbranch as 'Sijaintikirjasto',location as 'Hyllypaikka', itemtype as 'Aineistotyyppi',dateaccessioned as 'Hankintapäivä',datelastseen as 'Viimeksi nähty',datelastborrowed as 'Viimeksi  lainattu',issues as 'Lainakerrat'
from deleteditems
join deletedbiblio db using (biblionumber)
join deletedbiblioitems using (biblionumber)
where convert(homebranch using 'utf8') like @Kunta
and convert(year(deleteditems.timestamp) using 'utf8') like @Vuosi

ORDER BY 12 desc
```

### Poistetut niteet kotikirjaston, hyllypaikan ja kokoelman  mukaan

Raportti listaa valitulla aikavälillä poistetut niteet, joiden kotikirjasto, hyllpaikka ja kokoelmakoodi on valitun mukaiset. Kaikki raportin kysymät parametrit pitää syöttää, jotta saisi tuloksia. Tiedot järjestetään sarakkeen 12 mukaan nousevasti, eli lainamäärien mukaan. Tämä on muunnos yläpuolella olevasta "Poistetut niteet ja niiden lainamäärät" -raportista.

Lisääjä: Anneli Österman<br />
Aika: 1.4.2021 (muokattu 8.12.2021)

```
select b.title as 'Nimeke',b.author as 'Tekijä',b.copyrightdate as 'Julkaisuvuosi',enumchron as 'Lehden numero',barcode as 'Viivakoodi',holdingbranch as 'Sijaintikirjasto',location as 'Hyllypaikka',itemtype as 'Aineistotyyppi',dateaccessioned as 'Hankintapäivä',datelastseen as 'Viimeksi nähty',datelastborrowed as 'Viimeksi lainattu',issues as 'Lainakerrat'
from deleteditems
join biblio b using (biblionumber)
join biblioitems using (biblionumber)
where convert(homebranch using 'utf8') like (@Kunta:= <<Kuntaosio ja prosenttimerkki>>)
and convert(date(deleteditems.timestamp) using 'utf8') between (@Alkaen:= <<Lähtien|date>>) and (@Loppuen:= <<saakka|date>>)
and convert(ccode using 'utf8') like (@Kokoelma:= <<Kokoelma|CCODE>>)
and convert(location using 'utf8') like (@Hyllypaikka:= <<Hyllypaikka|LOC>>)

UNION ALL
select db.title as 'Nimeke',db.author as 'Tekijä',db.copyrightdate as 'Julkaisuvuosi',enumchron as 'Lehden numero',barcode as 'Viivakoodi',holdingbranch as 'Sijaintikirjasto',location as 'Hyllypaikka',itemtype as 'Aineistotyyppi',dateaccessioned as 'Hankintapäivä',datelastseen as 'Viimeksi nähty',datelastborrowed as 'Viimeksi  lainattu',issues as 'Lainakerrat'
from deleteditems
join deletedbiblio db using (biblionumber)
join deletedbiblioitems using (biblionumber)
where convert(homebranch using 'utf8') like @Kunta
and convert(date(deleteditems.timestamp) using 'utf8') between @Alkaen and @Loppuen
and convert(ccode using 'utf8') like @Kokoelma
and convert(location using 'utf8') like @Hyllypaikka

ORDER BY 12 asc
```

### Hyllyssä olevien niteiden määrä

Raportti laskee hyllyssä olevien niteiden määrän hyllypaikan ja aineistotyypin mukaan. Raportilla näytetään myös aina hyllypaikan paikalla olevien niteiden kokonaismäärä. Raportille annetaan parametriksi sijaintikirjasto.

Lisääjä: Anneli Österman<br />
Pvm: 8.12.2021

```
select location as 'Hyllypaikka',itemtype as 'Aineistotyyppi',count(*) as 'Niteiden määrä'
from items
join biblioitems USING (biblionumber)
where holdingbranch=<<Valitse kirjasto|branches>>
and onloan is null 
group by location, itemtype with ROLLUP
```

### Tietueet, joissa 942-kenttä kahdesti

Raportti hakee tietueet, joissa 942-kenttä esiintyy kahdesti. HUOM! Raskas ajo, aja vain hiljaisena hetkenä. 

Lisääjä: Emmi Takkinen<br />
Pvm: 14.12.2021

```
SELECT
    CONCAT('<a href=\"/cgi-bin/koha/catalogue/detail.pl?biblionumber=',biblionumber,'\">',biblionumber,'</a>') AS 'Tietue'
FROM biblio_metadata
WHERE ExtractValue(metadata,'count(//datafield[@tag="942"])') > 1
```

### Niteet, joiden signumin perässä on ylimääräinen välilyönti

Raportti hakee kaikki niteet, joiden perässä on ylimääräinen välilyönti

Lisääjä: Emmi Takkinen<br />
Pvm: 10.8.2022

```
SELECT CONCAT('<a href=\"/cgi-bin/koha/catalogue/detail.pl?biblionumber=',b.biblionumber,'\">',b.title,'</a>') AS 'Nimeke', 
CONCAT('<a href=\"/cgi-bin/koha/cataloguing/additem.pl?op=edititem&biblionumber=',b.biblionumber,'&itemnumber=',i.itemnumber,'\">',i.barcode,'</a>') AS 'Viivakoodi' 
FROM items i 
LEFT JOIN biblio b ON(i.biblionumber = b.biblionumber) 
WHERE i.itemcallnumber REGEXP '\\s$'
```

### Niteet joissa "Hakintapäivämäärä" tai "Hinta voimassa alkaen" kentässä on arvo 0000-00-00

Raportti hakee kaikki niteet, joissa "Hakintapäivämäärä" tai "Hinta voimassa alkaen" kentässä on arvo 0000-00-00.

Lisääjä: Emmi Takkinen<br />
Pvm: 29.11.2022

```
SELECT itemnumber AS "Nidenumero", biblionumber AS "Tietuenumero", 
dateaccessioned AS "Hankintapäivämäärä (dateaccessioned)", 
replacementpricedate AS "Hinta voimassa alkaen (replacementpricedate)" 
FROM items
WHERE dateaccessioned = "0000-00-00"
OR replacementpricedate = "0000-00-00"
```

### Niteet, joissa viivakoodin perässä on ylimääräinen välilyönti

Raportti hakee niteet, joiden viivakoodissa on perässä ylimääräinen välilyönti.

Lisääjä: Anneli Österman<br />
Pvm: 18.1.2023

```
SELECT CONCAT('<a href=\"/cgi-bin/koha/catalogue/detail.pl?biblionumber=',b.biblionumber,'\">',b.title,'</a>') AS 'Nimeke', 
CONCAT('<a href=\"/cgi-bin/koha/cataloguing/additem.pl?op=edititem&biblionumber=',b.biblionumber,'&itemnumber=',i.itemnumber,'\">',i.barcode,'</a>') AS 'Viivakoodi', i.homebranch as 'Kotikirjasto'
FROM items i 
LEFT JOIN biblio b ON(i.biblionumber = b.biblionumber) 
WHERE i.barcode REGEXP '\\s$'
```

### Niteet, joiden cn_sort-kenttä alkaa kirjaimella

Raportti hakee niteet, joiden cn_sort-kenttä alkaa kirjaimella. cn_sort pitäisi aina alkaa numerolla, jotta okm-tilastoissa toimii jako kaunoon/tietoon ja tiedonhaussa luokalla järjestäminen.

Lisääjä: Anneli Österman<br />
Pvm: 19.1.2023

```
select homebranch,CONCAT('<a href=\"/cgi-bin/koha/cataloguing/additem.pl?op=edititem&biblionumber=',biblionumber,'&itemnumber=',itemnumber,'\">',barcode,'</a>') AS 'Viivakoodi',CONCAT('<a href=\"/cgi-bin/koha/catalogue/detail.pl?biblionumber=',biblionumber,'\">',biblionumber,'</a>') AS 'Teos',itype,itemcallnumber,cn_sort 
from items
where cn_sort regexp '^[A-Ö]'
and dateaccessioned> <<Hankittu pvm:n jälkeen|date>>
order by 1
```

### Niteet, joilta puuttuu signum

Niteet, joilta puuttuu signum ei tule mukaan hyllyvarauslistalle. Tällä raportilla voi listata kirjastoittain niteet, joiden signum-kenttä on tyhjä ja jolla ei ole mitään Ei lainata -arvoa.

Tekijä: Lari Strand
Lisätty: 14.11.2023
Versio: 22.11

```
select biblio.title as 'Nimeke', CONCAT('<a href="/cgi-bin/koha/catalogue/moredetail.pl?biblionumber=', biblio.biblionumber, '#item', i.itemnumber, '">', i.barcode, '</a>') AS 'Viivakoodi',
itemnumber, i.biblionumber, homebranch as 'Kotikirjasto', holdingbranch as 'Sijaintikirjasto', onloan as 'Eräpäivä', location as 'Hyllypaikka', itype as 'Nidetyyppi', enumchron as 'Lehden numero'
from items i
inner join biblio ON i.biblionumber = biblio.biblionumber
and i.itemcallnumber is null and i.notforloan = 0 and i.itemlost = 0
and i.holdingbranch = <<Sijaintikirjasto|branches>>
order by 1 asc
```

## Laskutus

### Laskutettavat niteet (OUTI)

Lista niteistä ja asiakkaista, jotka ovat menossa laskutukseen. Ne niteet, joita ei haluta laskuttaa, muokataan niteen muokkauksessa "Ei laskuteta" -tilaan. Kirjastorajaus perustuu kirjastoryhmiin. Jos "Laskutettu"-tila on jotain muuta kuin "6" tai "Ei laskuteta"-tila muuta kuin "8", muuta ne kohtaan "AND i.notforloan not in (6,8)".

Lisääjä: Anneli Österman / OUTI-kirjastot

```
SELECT 
    p.categorycode AS 'Asiakaslaji',
    concat_ws('', IFNULL(p.surname, ' '), ', ', IFNULL(p.firstname, ' '), '<br>' '<a href="https://koha.outikirjastot.fi:8080/cgi-bin/koha/members/moremember.pl?borrowernumber=',p.borrowernumber,'">',p.cardnumber,'</a>') AS 'Asiakas',
    Concat_ws('', IFNULL(g.surname, ' '), ' ', IFNULL(g.firstname, ' '), '<br/>' '<a href="https://koha.outikirjastot.fi:8080/cgi-bin/koha/members/moremember.pl?borrowernumber=',g.borrowernumber,'">',g.cardnumber,'</a>') AS 'Takaaja',
    Concat_ws(' ',
        IF(LENGTH(p.address),p.address,NULL),
        IF(LENGTH(p.zipcode),p.zipcode,NULL),
        '\n',
        IF(LENGTH(p.city),p.city,NULL)
    ) AS 'Osoite',
    (SELECT attribute FROM borrower_attributes WHERE code = 'SSN' AND borrowernumber = c.borrowernumber) AS SSN,
    Concat_ws(' - ',
        IF(LENGTH(b.author),b.author,NULL),
        IF(LENGTH(b.title),b.title,NULL)
    ) AS 'Teos',
    i.itemcallnumber AS 'Hyllypaikka', 
    Concat('<a href="https://koha.outikirjastot.fi:8080/cgi-bin/koha/cataloguing/additem.pl?op=edititem&biblionumber=',i.biblionumber,'&itemnumber=',i.itemnumber,'">',i.barcode,'</a>') AS 'Viivakoodi',
    i.replacementprice AS 'Korvaus',
    (TO_DAYS(curdate())-TO_DAYS( date_due)) AS 'Myöhässä' ,
    c.branchcode as 'Lainauspaikka',
    it.description as 'Aineistolaji',    
    i.holdingbranch AS 'Havaintopaikka'
FROM issues c
LEFT JOIN borrowers p ON (p.borrowernumber=c.borrowernumber) 
LEFT JOIN items i ON (c.itemnumber=i.itemnumber) 
LEFT JOIN itemtypes it ON (i.itype = it.itemtype)
LEFT JOIN biblio b ON (i.biblionumber=b.biblionumber) 
LEFT JOIN borrowers g ON (p.guarantorid=g.borrowernumber)
LEFT JOIN branchrelations br ON (c.branchcode = br.branchcode)
LEFT JOIN branchcategories bc ON (br.categorycode = bc.categorycode)
WHERE (TO_DAYS(curdate())-TO_DAYS(date_due)) >= 60
AND bc.categorycode = <<Kirjastoryhmä|branchcategories>>
AND p.categorycode not in ('AUTOM','EITILASTO','VIRKAILIJA')
AND i.notforloan not in (6,8)
GROUP BY i.itemnumber
ORDER BY p.surname, p.firstname
```

### Palautetut laskutetut niteet

Raportilla voi seurata niteitä, jotka on palautettu, mutta ovat edelleen laskutettu-tilassa. Kirjastorajaus tehdään kirjoittamalla kirjastolyhenteestä kuntaosio ja %-merkki, esim. KE% tai  KA% tai LIE%. Jos Laskutettu-tila on jokin muu kuin "6", muuta se oikeaksi kohdassa "and i.notforloan = 6".

Lisääjä: Anneli Österman / OUTI-kirjastot

```
select Concat(b.surname, ', ', b.firstname, '<br/>', '<a href=\"/cgi-bin/koha/members/moremember.pl?borrowernumber=',b.borrowernumber,'">',b.cardnumber,'</a>') AS 'Nimi',
Concat('<a href=\"/cgi-bin/koha/cataloguing/additem.pl?op=edititem&biblionumber=',i.biblionumber,'&itemnumber=',i.itemnumber,'">',i.barcode,'</a>') AS 'Viivakoodi',
iss.date_due AS 'Eräpäivä',
iss.branchcode,
iss.returndate AS 'Palautuspäivä'
from old_issues iss, items i, borrowers b,
(select i.itemnumber, max(o.issue_id) as issue_id
from old_issues o, items i
where o.branchcode like <<Kuntaosio ja %-merkki>>
and DATE(o.returndate) between DATE(<<Palautuspäiväväli|date>>) and DATE(<<Päättyen|date>>)
and i.notforloan = 6
and i.itemnumber = o.itemnumber
group by i.itemnumber) d
where b.borrowernumber = iss.borrowernumber
and i.itemnumber = iss.itemnumber
and iss.issue_id = d.issue_id
and iss.itemnumber = d.itemnumber
```

### Palautetut Ei laskuteta -niteet

Raportilla voi seurata palautettuja "Ei laskuteta" -tilassa olevia niteitä. Kirjastorajaus tehdään kirjoittamalla kirjastolyhenteen kuntaosio ja %-merkki, esim. KE%, KA% ja LIE%. Jos "Ei laskuteta" -tila on muuta kuin "8", muuta se kohtaan "and i.notforloan = 8".

Lisääjä: Anneli Österman / OUTI-kirjastot

```
select Concat(b.surname, ', ', b.firstname, '<br/>', '<a href="https://koha.outikirjastot.fi:8080/cgi-bin/koha/members/moremember.pl?borrowernumber=',b.borrowernumber,'">',b.cardnumber,'</a>') AS 'Nimi', 
Concat('<a href="https://koha.outikirjastot.fi:8080/cgi-bin/koha/cataloguing/additem.pl?op=edititem&biblionumber=',i.biblionumber,'&itemnumber=',i.itemnumber,'">',i.barcode,'</a>') AS 'Viivakoodi',
iss.date_due, iss.branchcode, iss.returndate 
from old_issues iss, items i, borrowers b,
(select i.itemnumber, max(o.issue_id) as issue_id
from old_issues o, items i
where o.branchcode like <<Kuntaosio ja %-merkki>>
and DATE(o.returndate) between DATE(<<Palautuspäiväväli|date>>) and DATE(<<Palautuspäiväväli|date>>)
and i.notforloan = 8
and i.itemnumber = o.itemnumber
group by i.itemnumber) d
where b.borrowernumber = iss.borrowernumber
and i.itemnumber = iss.itemnumber
and iss.issue_id = d.issue_id
and iss.itemnumber = d.itemnumber
```

### Finvoice-laskujen niteiden yhteismäärä ja laskutetun aineiston yhteissumma

Raportilla voi tarkastella tietyllä aikavälillä message_queue-tauluun lisättyjen Finvoice-laskujen muodostamaa laskutettujen niteiden yhteismäärää sekä laskutetun aineston yhteissummaa 

Lisääjä: Lari Strand

```
SELECT  
ExtractValue(content, 'Finvoice/MessageTransmissionDetails/MessageReceiverDetails/ToIntermediator') AS 'Asiakas-ID', 
ExtractValue(content, 'Finvoice/InvoiceDetails/InvoiceTotalVatIncludedAmount') AS 'laskutettu yhteensä', ExtractValue(content, 'Finvoice/InvoiceRow/ArticleName') AS 'niteet', 
ExtractValue(content, 'count(Finvoice/InvoiceRow/ArticleName)') AS 'niteiden lkm'  
FROM message_queue 
WHERE message_transport_type = 'finvoice'  
AND (CAST(time_queued as date) between <<Alkupvm|date>> AND <<Loppupvm|date>>)
UNION ALL 
SELECT 'Total', 
SUM(CONVERT(REPLACE(ExtractValue(content, 'Finvoice/InvoiceDetails/InvoiceTotalVatIncludedAmount'), ',', '.' ), DECIMAL(16,2))), 
NULL, 
SUM(convert((ExtractValue(content, 'count(Finvoice/InvoiceRow/ArticleName)')), SIGNED)) 
FROM message_queue 
WHERE message_transport_type = 'finvoice'
AND (CAST(time_queued as date) between <<Alkupvm|date>> AND <<Loppupvm|date>>)
```


## Maksut

### Ceepos-verkkomaksujen tulot kirjastoittain

Erotellaan kirjastoittain kaikki verkkomaksuista kertyneet tulot. Toimii vain *Ceepos-verkkomaksujen* kanssa. Ei esim. Finna-Paytrail-maksujen kanssa.

```
SELECT Verkkomaksutulot, branch, branchcity, branchphone FROM (SELECT CAST(SUM(payments.paid_price_cents)/100.00 as decimal(19,2)) AS Verkkomaksutulot, IF(homebranch IS NULL, user_branch, homebranch) AS branch FROM 
	(SELECT DISTINCT payments_transactions_accountlines.transaction_id, payments_transactions.borrowernumber, status, paid_price_cents, payments_transactions_accountlines.accountlines_id, accountlines.itemnumber, payments_transactions.user_branch FROM payments_transactions, payments_transactions_accountlines, accountlines 
	WHERE payments_transactions.is_self_payment=1 
	AND payments_transactions.transaction_id=payments_transactions_accountlines.transaction_id
	AND payments_transactions.status='paid'
	AND accountlines.accountlines_id=payments_transactions_accountlines.accountlines_id
        AND date(payments_transactions.timestamp) BETWEEN <<Alkupäivä|date>> AND <<Loppupäivä|date>> ) AS payments
LEFT JOIN items
ON payments.itemnumber=items.itemnumber
GROUP BY branch) AS tulot
LEFT JOIN branches
ON(tulot.branch=branches.branchcode COLLATE utf8_general_ci)
ORDER BY branchcity
```

### Asiakkaiden maksut maksutyypin mukaan aikaväliltä

Muuta: Tämä raportti hakee tietyltä aikaväliltä käsiteltyjä maksuja. Käsittely voi tarkoittaa joko maksun luomista tai päivittämistä (maksamista).

Maksutunnukset:
F (myöh.maksut)
FU (myöh.maksut)
HE (noutamaton varaus)
ODUE1
ODUE2
ODUE3 (myöhästymismuistutuksia)
L (kadonnut aineisto, aineiston korvaus)
Korva (aineiston korvaus)
N (uusi kortti)
M (sekalainen)
Kopio (kopio)
Kauko (kaukolainat)
A (käyttäjätilin hallinta)
Konve (konvertoidut maksut esim. OUTI ja Lappi)
 
Lisääjä: Päivi Knuutinen / Vaara-kirjastot<br />
pvm: 30.10.2018

```
SELECT CONCAT('<a href="/cgi-bin/koha/members/moremember.pl?borrowernumber=', accountlines.borrowernumber, '">', accountlines.borrowernumber, '</a>') AS asiakas,
       CONCAT('<a href="/cgi-bin/koha/catalogue/moredetail.pl?type=&itemnumber=', accountlines.itemnumber, '">', accountlines.itemnumber, '</a>') AS Item, 
  accountlines.*
FROM accountlines
WHERE date(accountlines.timestamp) BETWEEN <<Alkupäivä|date>> AND <<Loppupäivä|date>> 
AND accounttype=<<Kohan maksutunnus>> 
AND amountoutstanding>0
ORDER BY accountlines_id
```

### Vanhentuneet maksut

```
SELECT CONCAT('<a href="/cgi-bin/koha/members/boraccount.pl?borrowernumber=', accountlines.borrowernumber, '">', accountlines.borrowernumber, '</a>') AS borrowernumberi,
accountlines.*,
borrowers.* 
FROM accountlines, borrowers WHERE accountlines.amountoutstanding > 0 
AND accountlines.date<NOW()-INTERVAL 3 YEAR 
AND accountlines.borrowernumber LIKE <<borrowernumber TAI syötä %-merkki jos haluat kaikki>> 
AND accountlines.accounttype LIKE <<accounttype TAI syötä %-merkki jos haluat kaikki>> 
AND accountlines.borrowernumber=borrowers.borrowernumber 
AND borrowers.branchcode=<<Lainauskirjasto|branches>> 
GROUP BY borrowernumberi 
ORDER BY DATE DESC
```

Raportti näyttää maksut, jotka on luotu vähintään 3 vuotta sitten. Maksuja voi rajata borrowernumberilla tai maksun tyypillä (accounttype). Merkitse % jos haluat valita kaikki borrowernumberit ja/tai maksutyypit. 

Lisääjä: Päivi Knuutinen / VAARA 5.2.2019

### Asiakkaan haku maksun ID:llä (Ceepos)

Lisääjä: Anneli Österman<br />
Lisätty: 11.10.2022<br />
Versio: 21.11

Asiakkaan haku maksun ID-tunnisteella. Jos tunnisteen edessä on # -merkki, jätä se hakukentästä pois. 

```
select concat('<a href="/cgi-bin/koha/members/boraccount.pl?borrowernumber=',borrowernumber,'">',borrowernumber,'') AS 'Asiakas' from koha_plugin_fi_kohasuomi_ceeposintegration_transactions where transaction_id=<<Tapahtumanumero>>
```



### Asiakkaan miinusmerkkiset maksut

Lisääjä: Pirkko-Liisa Lauhikari<br />
Lisätty: 13.1.2023

Raportilla voi hakea asiakkaat, joiden maksut ovat miinuksella.

```
select distinct(borrowernumber) from accountlines where credit_type_code='PAYMENT' and amountoutstanding<0
```



## Luettelointi

### Viimeksi lisätyt osakohteet

Raportilla voi hakea 300 viimeisimmän osakohteen tietuenumeron.

Lisääjä: Anneli Österman / OUTI-kirjastot<br />
Pvm: 28.11.2018

```
SELECT b.biblionumber
FROM biblio b
LEFT JOIN biblio_metadata bm ON b.biblionumber = bm.biblionumber
WHERE ExtractValue(bm.metadata,'//datafield[@tag="773"]/subfield[@code="w"]') != ''
AND ExtractValue(bm.metadata,'//datafield[@tag="337"]/subfield[@code="a"]') = <<Kirjoita tyyppi>>
ORDER BY b.biblionumber DESC LIMIT 300
```

### Osakohde merkitty monografiaksi

Lisääjä: Anneli Österman / OUTI-kirjastot<br />
Pvm: 26.6.2019

```
SELECT CONCAT(b.title, ', ', '<br/>', '<a href=\"/cgi-bin/koha/catalogue/detail.pl?biblionumber=',b.biblionumber,'\">',b.biblionumber,'</a>') AS 'Teos',
bi.itemtype AS 'Aineistolaji', bi.biblionumber AS 'Biblionro'
from biblio b
LEFT JOIN items i ON b.biblionumber = i.biblionumber
LEFT JOIN biblioitems bi ON bi.biblionumber = b.biblionumber
LEFT JOIN biblio_metadata bm ON bm.biblionumber = b.biblionumber
WHERE ExtractValue(bm.metadata,'//datafield[@tag="773"]/subfield[@code="w"]') != ''
AND i.itemnumber IS NULL
AND SUBSTR(ExtractValue(bm.metadata,'//leader'),8,1) NOT IN ('a', 'b', 'd')
```

### Bibit, joiden tietyssä kentässä tietty merkkijono

Kysely, johon voi syöttää kenttien arvoja. Hakee tietueet, joiden annetussa kentässä annettu merkkijono. Linkki tietueeseen. Toimii ainakin yhteisöversiossa. Tuloksen voi toki järjestää tarpeen mukaan, tässä on haettu aineistoa, jonka linkki on tod.näk. vanhentunut.
Ohje käyttäjälle raportin muuta-boxissa: Esim. 856 u = http% tai 776 i = verkko%

Lisääjä: Hanna Saario / Diakonia-amk:n kirjasto<br />
Pvm: 7.4.2021

```
SELECT CONCAT('<a target="_blank" href=\"/cgi-bin/koha/catalogue/detail.pl?biblionumber=',biblio.biblionumber,'\">',biblio.biblionumber,'</a>') AS biblionumber, biblio.title, biblio.author, copyrightdate
FROM biblio_metadata
JOIN biblio USING (biblionumber)
WHERE ExtractValue(metadata, "//datafield[@tag=<< Field (XXX)>>]/subfield[@code=<<Subfield(Y)>>]")
LIKE <<Search Term (USE % AS wildcard)>>
ORDER BY copyrightdate ASC
```

### Tietueet, joiden linkissä tietty merkkijono

Kysely hakee tietueet, joiden 856u-kentän linkissä on tietty merkkijono. Tässä haetaan "ecom"-sanan sisältävät linkit. Prosenttimerkkien sisään voi muokata myös muun tiedon. Huomaa, että raportti on hidas, koska tiedot haetaan marcxml:stä like-ehdolla.

Lisääjä: Anneli Österman<br />
Pvm: 6.7.2021

```
SELECT CONCAT('<a href=\"/cgi-bin/koha/cataloguing/addbiblio.pl?biblionumber=',bm.biblionumber,'" target="_blank">',bm.biblionumber,'</a>') AS 'Teos' 
FROM biblio_metadata bm 
WHERE ExtractValue(bm.metadata, '//datafield[@tag="856"]/subfield[@code="u"]') like '%ecom%'
```

### Aineistotyypitön tietue

Kysely hakee tietueet, joiden biblioitems.itemtype-kenttä on NULL, tyhjä tai tieto tuplana. Mukaan tulee sekä emot että osakohteet.

Lisääjä: Anneli Österman<br />
Pvm: 9.7.2021

```
SELECT IFNULL(b.title, "Ei nimeä 245a:ssa") AS 'Nimeke', CONCAT('<a href=\"/cgi-bin/koha/catalogue/detail.pl?biblionumber=',b.biblionumber,'\">',b.biblionumber,'</a>') AS 'Teos', bi.itemtype AS 'Teoksen aineistolaji'
FROM biblio b
JOIN biblioitems bi using(biblionumber)
WHERE (bi.itemtype is NULL OR bi.itemtype='' OR bi.itemtype like '%|%')
```

### Aineistotyypitön monografia-tietue

Kysely hakee monografia-tietueet, joiden biblioitems.itemtype-kenttä on NULL, tyhjä tai tieto tuplana. Mukaan ei tule osakohteet. Kysely on hidas, koska se hakee tietoja marcxml:stä.

Lisääjä: Anneli Österman<br />
Pvm: 9.7.2021

```
SELECT IFNULL(b.title, "Ei nimeä") AS 'Nimeke', CONCAT('<a href=\"/cgi-bin/koha/catalogue/detail.pl?biblionumber=',b.biblionumber,'\">',b.biblionumber,'</a>') AS 'Teos', bi.itemtype AS 'Teoksen aineistolaji'
FROM biblio b
LEFT JOIN biblio_metadata bm using (biblionumber)
LEFT JOIN biblioitems bi using(biblionumber)
WHERE (bi.itemtype is NULL OR bi.itemtype='' OR bi.itemtype LIKE '%|%')
AND ExtractValue(bm.metadata,'//datafield[@tag="773"]/subfield[@code="w"]') = ''
```

### Luokattomat nimekkeet

Kysely hakee tietueet, joiden biblioitems.cn_class-kentssä ei ole mitään arvoa. Kyseiseen kenttään viedään 084a-kentän tieto luettelointitiedoista.

Lisääjä: Anneli Österman<br />
Pvm: 24.9.2021

```
select CONCAT(b.title, ', ', '<br/>', '<a href=\"/cgi-bin/koha/catalogue/detail.pl?biblionumber=',b.biblionumber,'\">',b.biblionumber,'</a>') AS 'Teos'
from biblio b
left join biblioitems bi using (biblionumber)
left join items i ON b.biblionumber=i.biblionumber
left join biblio_metadata bm ON b.biblionumber=bm.biblionumber
where bi.cn_class is null
and ExtractValue(bm.metadata,'//datafield[@tag="773"]/subfield[@code="w"]') = ''
and bi.itemtype !='LA'
and bi.itemtype!='ES'
and i.notforloan='0'
group by b.biblionumber
order by b.biblionumber asc
```

### Kielikoodittomat tietueet

Raportti hakee emotietueet, joissa ei ole kielikoodia 041a- ja 041d-kentissä ja 008-kentässä on merkkipaikoilla 35-37 'zxx'.

Lisääjä: Anneli Österman<br />
Pvm: 24.9.2021

```
select CONCAT(b.title, ', ', '<br/>', '<a href=\"/cgi-bin/koha/catalogue/detail.pl?biblionumber=',b.biblionumber,'\">',b.biblionumber,'</a>') AS 'Teos', bi.itemtype AS 'Aineistolaji'
from biblio b
left join biblioitems bi using (biblionumber)
left join biblio_metadata bm using (biblionumber)
where ExtractValue(bm.metadata,'//datafield[@tag="041"]/subfield[@code="a"]') = ''
and ExtractValue(bm.metadata,'//datafield[@tag="041"]/subfield[@code="d"]') = ''
AND SUBSTR(ExtractValue(bm.metadata,'//controlfield[@tag="008"]'),36,3) <> 'zxx'
AND ExtractValue(bm.metadata,'//datafield[@tag="773"]/subfield[@code="w"]') = ''
AND bi.itemtype='KI'
```

### Valuneet tietueet

Raportti hakee tietueet, jotka ovat valuneet päivän sisällä paikalliskantaan.

Lisätty: 18.10.2023<br />
Tekijä: Mikko Liimatainen

<pre>SELECT t1.object AS 'tietuenumero', (select itemtype from biblioitems bi where t1.object=bi.biblionumber) AS 'Aineistotyyppi', datelastseen AS "Viimeisin havaintopvm",
    b.author AS Tekijä,
   	CONCAT('<a href=\"/cgi-bin/koha/catalogue/detail.pl?biblionumber=',b.biblionumber,'" target="_blank">',b.title,IF(b.subtitle != '', CONCAT(' ',b.subtitle),''),IF(b.part_number != '', CONCAT(' ',b.part_number),''),IF(b.part_name != '', CONCAT(' ',b.part_name),''),'</a>') AS 'Nimeke',
	SUBSTRING(t1.info, LOCATE('LDR', t1.info)+21, 1) AS 'vanha leader 17',
	SUBSTRING(ExtractValue(bm.metadata,'//leader'),18,1) AS 'uusi leader 17',
    SUBSTRING(t1.info, LOCATE('040    _a', t1.info)+9, 8) AS 'vanha 040a',
    ExtractValue(bm.metadata,'//datafield[@tag="040"][1]/subfield[@code="a"]') AS 'uusi 040a',
    SUM(CASE WHEN i.notforloan='-2' AND i.homebranch LIKE <<Kirjasto|branches:all>> THEN 1 ELSE 0 END) AS 'Saapuneita niteitä yksikössä',
    t1.timestamp AS 'Valunut',
    STR_TO_DATE(ExtractValue(bm.metadata,'//controlfield[@tag="005"]'),'%Y%m%d%H%i%s') AS 'Muokattu'
FROM (SELECT object, info, MAX(timestamp) AS timestamp
		FROM action_logs al
		WHERE al.timestamp >= NOW() - INTERVAL 1 DAY
    		AND al.module='CATALOGUING'
    		AND al.action='MODIFY'
    		AND SUBSTRING(al.info, LOCATE('LDR', al.info)+21, 1) = 8
		GROUP BY object) t1
LEFT JOIN biblio_metadata bm ON t1.object=bm.biblionumber
LEFT JOIN biblio b ON t1.object=b.biblionumber
CROSS JOIN (SELECT * FROM items WHERE homebranch LIKE <<Kirjasto|branches:all>> AND notforloan != '-1') i ON t1.object=i.biblionumber
WHERE SUBSTRING(ExtractValue(bm.metadata,'//leader'),18,1) != 8
GROUP BY t1.object
order by 2,3,4,5</pre>

## Kuljetukset

### Lähtökirjastossa kuljetuksessa olevat

Näyttää kuljetukset jotka eivät ole saapuneet perille, halutusta kirjastosta, järjestäen vanhemmat kuin 7 päivää ensimmäiseksi.

```
SELECT
   IF(bt.datesent < DATE_SUB(NOW(), INTERVAL 7 DAY), '*', '') AS 'late',
   b.author,
   CONCAT('<a href="/cgi-bin/koha/catalogue/detail.pl?biblionumber=', b.biblionumber, '">', b.title, '</a>') AS 'title',
   CONCAT('<a href="/cgi-bin/koha/catalogue/moredetail.pl?biblionumber=', b.biblionumber, '#item', bt.itemnumber, '">', i.barcode, '</a>') AS 'barcode',
   i.itype,
   i.location,
   bt.tobranch,
   bt.datesent
FROM branchtransfers bt
LEFT JOIN items i ON i.itemnumber = bt.itemnumber
LEFT JOIN biblio b ON b.biblionumber = i.biblionumber
WHERE bt.frombranch = <<Lähtökirjasto|branches>>
  AND bt.datearrived IS NULL
ORDER BY
    late DESC,
    bt.tobranch,
    bt.datesent ASC
```

### Omasta kirjastosta muualle kuljetuksessa olevat niteet

Raportti listaa ajasta riippumatta kaikki niteet, jotka ovat kuljetettavana ja lähettävänä kirjastona on valittu kirjasto.

Lisääjä: Anneli Österman<br />
Pvm: 9.4.2020 / Päivitetty 11.7.2023 AÖ

```
SELECT CONCAT('<a href=\"/cgi-bin/koha/catalogue/detail.pl?biblionumber=',b.biblionumber,'" target="_blank">',b.title, ' ', ExtractValue(bm.metadata,'//datafield[@tag="245"]/subfield[@code="b"]'),'</a>') AS Nimeke, i.enumchron AS 'Lehden numero', b.author AS 'Tekijä', i.barcode AS Viivakoodi, i.cn_sort AS 'Luokka ja pääsana', bt.tobranch AS 'Kuljetettavana kirjastoon', date(bt.datesent) AS 'Asetettu kuljetettavaksi'
FROM branchtransfers bt
JOIN items i USING (itemnumber)
JOIN biblio b USING (biblionumber)
JOIN biblio_metadata bm USING (biblionumber)
WHERE bt.frombranch=<<Valitse kirjasto|branches>>
AND datearrived is null
AND cancellation_reason is null
ORDER BY 5
```

### Lähtevien kuljetusten määrä

Parametreiksi valitaan lähettäjäkirjasto ja vuosi (kirjoita vuosilukuja perään prosenttimerkki, esim. 2018%). Tulokset jaotellaan kuukausittain.

Tehnyt: Anneli Österman<br />
Pvm: 27.2.2019

```
select month(datesent) as 'Kuukausi',count(*) as 'Lähetettyjä niteitä'
from branchtransfers 
where frombranch=<<Lähettäjäkirjasto|branches>>
and datesent like <<Kirjoita vuosi ja prosenttimerkki>>
group by month(datesent)
```

### Saapuvien kuljetusten määrä

Parametreiksi valitaan vastaanottajakirjasto ja vuosi (kirjoita vuosilukuja perään prosenttimerkki, esim. 2018%). Tulokset jaotellaan kuukausittain.

Tehnyt: Anneli Österman<br />
Pvm: 27.2.2019

```
select month(datesent) as 'Kuukausi' ,count(*) as 'Vastaanotetut niteet'
from branchtransfers 
where tobranch=<<Vastaanottajakirjasto|branches>>
and datesent like <<Kirjoita vuosi ja prosenttimerkki>>
group by month(datesent)
```

## Hankinta

### Vastaanotetut hankinnat (Kouvola)

Kouvolassa rahoja seurataan hyllypaikoittain ja osin aineistolajeittain, jotta valitsijoiden on helppo seurata ’omia’ rahojansa. Tässä on varmaan paljon vaihtelua kirjastoittain ja siksi tätä raporttia voi joutua paljonkin kustomoimaan. Aineistojen hintoja on raporttiin haettu paristakin paikasta ihan vertailun vuoksi, me käytämme sum(items.price) eli niteissä olevaa hintaa.

Tehnyt: Tuomas Kunttu<br />
Pvm: 17.1.2021

```
SELECT items.permanent_location AS 'hyllypaikka', count(items.itemnumber) AS 'Hankittu', format(sum(items.price), 0,'fi_FI') AS 'Hinta niteissä', format(sum(aqorders.unitprice), 0,'fi_FI') AS 'Hinta tilauksessa', 'A-hyllypaikka'
FROM items
JOIN aqorders_items ON (aqorders_items.itemnumber=items.itemnumber)
JOIN aqorders ON (aqorders_items.ordernumber=aqorders.ordernumber)
JOIN biblioitems ON (items.biblioitemnumber=biblioitems.biblioitemnumber) 
WHERE aqorders.datereceived BETWEEN (@AloitusPvm:= <<AloitusPvm |date>>) AND (@LopetusPvm:= <<LopetusPvm |date>>) AND items.homebranch like 'KOU%' AND (permanent_location='A' OR location='A')
UNION ALL

SELECT items.permanent_location AS 'hyllypaikka', count(items.itemnumber) AS 'Hankittu', format(sum(items.price), 0,'fi_FI') AS 'Hinta niteissä', format(sum(aqorders.unitprice), 0,'fi_FI') AS 'Hinta tilauksessa', 'A kirjat + muut aineistot'
FROM items
JOIN aqorders_items ON (aqorders_items.itemnumber=items.itemnumber)
JOIN aqorders ON (aqorders_items.ordernumber=aqorders.ordernumber)
JOIN biblioitems ON (items.biblioitemnumber=biblioitems.biblioitemnumber) 
WHERE aqorders.datereceived BETWEEN @AloitusPvm AND @LopetusPvm AND items.homebranch like 'KOU%' AND (permanent_location='A' OR location='A') AND (biblioitems.itemtype="KIRJA" OR biblioitems.itemtype="CDROM" OR biblioitems.itemtype="DIA" OR biblioitems.itemtype="ESINE" OR biblioitems.itemtype="KARTTA" OR biblioitems.itemtype="ATLAS" OR biblioitems.itemtype="LAUTAPELI" OR biblioitems.itemtype="KASIKIRJ" OR biblioitems.itemtype="MIKROF" OR  biblioitems.itemtype="MONIVIES" OR biblioitems.itemtype="TYOPIIR" OR biblioitems.itemtype="PUHECD")
UNION ALL

SELECT items.permanent_location AS 'hyllypaikka', count(items.itemnumber) AS 'Hankittu', format(sum(items.price), 0,'fi_FI') AS 'Hinta niteissä', format(sum(aqorders.unitprice), 0,'fi_FI') AS 'Hinta tilauksessa', 'A kuvatallenteet'
FROM items
JOIN aqorders_items ON (aqorders_items.itemnumber=items.itemnumber)
JOIN aqorders ON (aqorders_items.ordernumber=aqorders.ordernumber)
JOIN biblioitems ON (items.biblioitemnumber=biblioitems.biblioitemnumber) 
WHERE aqorders.datereceived BETWEEN @AloitusPvm AND @LopetusPvm AND items.homebranch like 'KOU%' AND (biblioitems.itemtype="DVD" OR biblioitems.itemtype="BLURAY" OR biblioitems.itemtype="VIDEO") AND (permanent_location='A' OR location='A')
UNION ALL

SELECT items.permanent_location AS 'hyllypaikka', count(items.itemnumber) AS 'Hankittu', format(sum(items.price), 0,'fi_FI') AS 'Hinta niteissä', format(sum(aqorders.unitprice), 0,'fi_FI') AS 'Hinta tilauksessa', 'videopelit'
FROM items
JOIN aqorders_items ON (aqorders_items.itemnumber=items.itemnumber)
JOIN aqorders ON (aqorders_items.ordernumber=aqorders.ordernumber)
JOIN biblioitems ON (items.biblioitemnumber=biblioitems.biblioitemnumber) 
WHERE aqorders.datereceived BETWEEN @AloitusPvm AND @LopetusPvm AND items.homebranch like 'KOU%' AND (biblioitems.itemtype='VIDEOPELI' OR biblioitems.itemtype='ELEKTRON') AND (permanent_location='A' OR location='A')
UNION ALL

SELECT items.permanent_location AS 'hyllypaikka', count(items.itemnumber) AS 'Hankittu', format(sum(items.price), 0,'fi_FI') AS 'Hinta niteissä', format(sum(aqorders.unitprice), 0,'fi_FI') AS 'Hinta tilauksessa', 'N- ja NA KAIKKI'
FROM items
JOIN aqorders_items ON (aqorders_items.itemnumber=items.itemnumber)
JOIN aqorders ON (aqorders_items.ordernumber=aqorders.ordernumber)
JOIN biblioitems ON (items.biblioitemnumber=biblioitems.biblioitemnumber) 
WHERE aqorders.datereceived BETWEEN @AloitusPvm AND @LopetusPvm AND items.homebranch like 'KOU%' AND (permanent_location='N' OR location='N' OR permanent_location='NA' OR location='NA')
UNION ALL

SELECT items.permanent_location AS 'hyllypaikka', count(items.itemnumber) AS 'Hankittu', format(sum(items.price), 0,'fi_FI') AS 'Hinta niteissä', format(sum(aqorders.unitprice), 0,'fi_FI') AS 'Hinta tilauksessa', 'N ja NA Kirjat + muut aineistot'
FROM items
JOIN aqorders_items ON (aqorders_items.itemnumber=items.itemnumber)
JOIN aqorders ON (aqorders_items.ordernumber=aqorders.ordernumber)
JOIN biblioitems ON (items.biblioitemnumber=biblioitems.biblioitemnumber) 
WHERE aqorders.datereceived BETWEEN @AloitusPvm AND @LopetusPvm AND items.homebranch like 'KOU%' AND (biblioitems.itemtype="KIRJA" OR biblioitems.itemtype="CDROM" OR biblioitems.itemtype="DIA" OR biblioitems.itemtype="ESINE" OR biblioitems.itemtype="KARTTA" OR biblioitems.itemtype="ATLAS" OR biblioitems.itemtype="LAUTAPELI" OR biblioitems.itemtype="KASIKIRJ" OR biblioitems.itemtype="MIKROF" OR  biblioitems.itemtype="MONIVIES" OR biblioitems.itemtype="TYOPIIR" OR biblioitems.itemtype="PUHECD") AND (permanent_location='N' OR location='N' OR permanent_location='NA' OR location='NA')
UNION ALL

SELECT items.permanent_location AS 'hyllypaikka', count(items.itemnumber) AS 'Hankittu', format(sum(items.price), 0,'fi_FI') AS 'Hinta niteissä', format(sum(aqorders.unitprice), 0,'fi_FI') AS 'Hinta tilauksessa', 'N ja NA kuvatallenteet'
FROM items
JOIN aqorders_items ON (aqorders_items.itemnumber=items.itemnumber)
JOIN aqorders ON (aqorders_items.ordernumber=aqorders.ordernumber)
JOIN biblioitems ON (items.biblioitemnumber=biblioitems.biblioitemnumber) 
WHERE aqorders.datereceived BETWEEN @AloitusPvm AND @LopetusPvm AND items.homebranch like 'KOU%' AND (biblioitems.itemtype="DVD" OR biblioitems.itemtype="BLURAY" OR biblioitems.itemtype="VIDEO") AND (permanent_location='N' OR location='N' OR permanent_location='NA' OR location='NA')
UNION ALL

SELECT items.permanent_location AS 'hyllypaikka', count(items.itemnumber) AS 'Hankittu', format(sum(items.price), 0,'fi_FI') AS 'Hinta niteissä', format(sum(aqorders.unitprice), 0,'fi_FI') AS 'Hinta tilauksessa', 'N ja NA videopeli'
FROM items
JOIN aqorders_items ON (aqorders_items.itemnumber=items.itemnumber)
JOIN aqorders ON (aqorders_items.ordernumber=aqorders.ordernumber)
JOIN biblioitems ON (items.biblioitemnumber=biblioitems.biblioitemnumber) 
WHERE aqorders.datereceived BETWEEN @AloitusPvm AND @LopetusPvm AND items.homebranch like 'KOU%' AND (biblioitems.itemtype='VIDEOPELI' OR biblioitems.itemtype='ELEKTRON') AND (permanent_location='N' OR location='N' OR permanent_location='NA' OR location='NA')
UNION ALL

SELECT items.permanent_location AS 'hyllypaikka', count(items.itemnumber) AS 'Hankittu', format(sum(items.price), 0,'fi_FI') AS 'Hinta niteissä', format(sum(aqorders.unitprice), 0,'fi_FI') AS 'Hinta tilauksessa', 'N ja NA äänitteet ja nuotit'
FROM items
JOIN aqorders_items ON (aqorders_items.itemnumber=items.itemnumber)
JOIN aqorders ON (aqorders_items.ordernumber=aqorders.ordernumber)
JOIN biblioitems ON (items.biblioitemnumber=biblioitems.biblioitemnumber) 
WHERE aqorders.datereceived BETWEEN @AloitusPvm AND @LopetusPvm AND items.homebranch like 'KOU%' AND (permanent_location='N' OR location='N' OR permanent_location='NA' OR location='NA') AND (biblioitems.itemtype="CD" OR biblioitems.itemtype="AANILEVY" OR biblioitems.itemtype="AANIKAS" OR biblioitems.itemtype='NUOTTI' OR biblioitems.itemtype='MUSATAL')
UNION ALL

SELECT items.permanent_location AS 'hyllypaikka', count(items.itemnumber) AS 'Hankittu', format(sum(items.price), 0,'fi_FI') AS 'Hinta niteissä', format(sum(aqorders.unitprice), 0,'fi_FI') AS 'Hinta tilauksessa', 'M kaikki'
FROM items
JOIN aqorders_items ON (aqorders_items.itemnumber=items.itemnumber)
JOIN aqorders ON (aqorders_items.ordernumber=aqorders.ordernumber)
JOIN biblioitems ON (items.biblioitemnumber=biblioitems.biblioitemnumber) 
WHERE aqorders.datereceived BETWEEN @AloitusPvm AND @LopetusPvm AND items.homebranch like 'KOU%' AND (permanent_location='M' OR location='M')
UNION ALL

SELECT items.permanent_location AS 'hyllypaikka', count(items.itemnumber) AS 'Hankittu', format(sum(items.price), 0,'fi_FI') AS 'Hinta niteissä', format(sum(aqorders.unitprice), 0,'fi_FI') AS 'Hinta tilauksessa', 'X kaikki'
FROM items
JOIN aqorders_items ON (aqorders_items.itemnumber=items.itemnumber)
JOIN aqorders ON (aqorders_items.ordernumber=aqorders.ordernumber)
JOIN biblioitems ON (items.biblioitemnumber=biblioitems.biblioitemnumber) 
WHERE aqorders.datereceived BETWEEN @AloitusPvm AND @LopetusPvm AND items.homebranch like 'KOU%' AND (permanent_location='X' OR location='X')
UNION ALL

SELECT items.permanent_location AS 'hyllypaikka', count(items.itemnumber) AS 'Hankittu', format(sum(items.price), 0,'fi_FI') AS 'Hinta niteissä', format(sum(aqorders.unitprice), 0,'fi_FI') AS 'Hinta tilauksessa', 'muut hyllypaikat'
FROM items
JOIN aqorders_items ON (aqorders_items.itemnumber=items.itemnumber)
JOIN aqorders ON (aqorders_items.ordernumber=aqorders.ordernumber)
JOIN biblioitems ON (items.biblioitemnumber=biblioitems.biblioitemnumber) 
WHERE aqorders.datereceived BETWEEN @AloitusPvm AND @LopetusPvm AND items.homebranch like 'KOU%' AND (permanent_location='CART' OR permanent_location='D' OR location='D' OR permanent_location='K' OR location='K' OR permanent_location='MV' OR location='MV' OR permanent_location='ND' OR location='ND' OR permanent_location='NV' OR location='NV' OR permanent_location='OM' OR location='OM' OR permanent_location='S' OR location='S' OR permanent_location='SA' OR location='SA' OR permanent_location='SN' OR location='SN' OR permanent_location='TH' OR location='TH' OR permanent_location='V' OR location='V')
UNION ALL

SELECT items.permanent_location AS 'hyllypaikka', count(items.itemnumber) AS 'Hankittu', format(sum(items.price), 0,'fi_FI') AS 'Hinta niteissä', format(sum(aqorders.unitprice), 0,'fi_FI') AS 'Hinta tilauksessa', 'OM kaikki'
FROM items
JOIN aqorders_items ON (aqorders_items.itemnumber=items.itemnumber)
JOIN aqorders ON (aqorders_items.ordernumber=aqorders.ordernumber)
JOIN biblioitems ON (items.biblioitemnumber=biblioitems.biblioitemnumber) 
WHERE aqorders.datereceived BETWEEN @AloitusPvm AND @LopetusPvm AND items.homebranch like 'KOU%' AND (permanent_location='OM' OR location='OM')
UNION ALL

SELECT items.permanent_location AS 'hyllypaikka', count(items.itemnumber) AS 'Hankittu', format(sum(items.price), 0,'fi_FI') AS 'Hinta niteissä', format(sum(aqorders.unitprice), 0,'fi_FI') AS 'Hinta tilauksessa', 'muut, joita ei pitäisi ollakaan'
FROM items
JOIN aqorders_items ON (aqorders_items.itemnumber=items.itemnumber)
JOIN aqorders ON (aqorders_items.ordernumber=aqorders.ordernumber)
JOIN biblioitems ON (items.biblioitemnumber=biblioitems.biblioitemnumber) 
WHERE aqorders.datereceived BETWEEN @AloitusPvm AND @LopetusPvm AND items.homebranch like 'KOU%' AND (biblioitems.itemtype="SLEHTI" OR biblioitems.itemtype="ALEHTI" OR biblioitems.itemtype="EKIRJA" OR biblioitems.itemtype="MUU")
```

### Saapumattomien hankintojen raportti

Raportti laskee tilattujen, mutta saapumattomien hankintojen kappalemäärät ja hinnat. Jaottelu hyllypaikoittain. Muuta homebranch koodiin.

Lisääjä: Tuomas Kunttu<br />
Pvm: 24.11.2020

```
SELECT items.location AS 'hyllypaikka', count(items.itemnumber) AS 'Tilattu_kpl', format(sum(aqorders.ecost), 0,'fi_FI') AS 'Hinta tilauksessa (ecost)'
FROM items
JOIN aqorders_items ON (aqorders_items.itemnumber=items.itemnumber)
JOIN aqorders ON (aqorders_items.ordernumber=aqorders.ordernumber)
WHERE aqorders.entrydate BETWEEN <<AloitusPvm |date>> AND <<LopetusPvm |date>> AND items.homebranch like 'KOU%' AND items.notforloan='-1'
GROUP BY items.location WITH ROLLUP
```

### Nimekkeet, joissa on niteitä tilattu-tilassa

Raportti listaa nimekkeet, joissa on valitulla kirjastolla nide/niteitä tilattu-tilassa (notforloan: -1). Lisäksi parametrinä määritetään, että niteen hankintapäivä on aikaisempi kuin valittu päivä. Raportista on erityisesti apua silloin, kun kyseessä on vanhasta järjestelmästä tuodut niteet, joille ei ole tilausta Kohassa.

Lisääjä: Anneli Österman<br />
Pvm: 9.4.2020

```
SELECT CONCAT(b.title, ', ', '<br/>', '<a href=\"/cgi-bin/koha/catalogue/detail.pl?biblionumber=',b.biblionumber,'\">',b.biblionumber,'</a>') AS 'Teos', bi.itemtype AS 'Aineistolaji', b.biblionumber AS 'Teosnumero'
FROM biblio b
LEFT JOIN biblio_metadata bm USING (biblionumber)
LEFT JOIN items i USING (biblionumber)
LEFT biblioitems bi USING (biblionumber)
WHERE ExtractValue(bm.metadata,'//datafield[@tag="773"]/subfield[@code="w"]') = ''
AND i.notforloan='-1'
AND i.homebranch= <<Valitse kotikirjasto|branches>>
AND i.dateaccessioned< <<Hankittu aikaisemmin kuin|date>>
GROUP BY biblionumber
```

### Nimekkeet, joissa on niteitä saapunut-tilassa

Raportti listaa nimekkeet, joissa on valitulla kirjastolla nide/niteitä saapunut-tilassa (notforloan: -2). Lisäksi parametrinä määritetään, että niteen hankintapäivä on aikaisempi kuin valittu päivä. Raportista on erityisesti apua silloin, kun kyseessä on vanhasta järjestelmästä tuodut niteet, joille ei ole tilausta Kohassa.

Lisääjä: Anneli Österman<br />
Pvm: 9.4.2020

```
SELECT CONCAT(b.title, ', ', '<br/>', '<a href=\"/cgi-bin/koha/catalogue/detail.pl?biblionumber=',b.biblionumber,'\">',b.biblionumber,'</a>') AS 'Teos', bi.itemtype AS 'Aineistolaji', b.biblionumber AS 'Teosnumero'
FROM biblio b
LEFT JOIN biblio_metadata bm USING(biblionumber)
LEFT JOIN items i USING (biblionumber)
LEFT JOIN biblioitems bi USING (biblionumber)
WHERE ExtractValue(bm.metadata,'//datafield[@tag="773"]/subfield[@code="w"]') = ''
AND i.notforloan='-2'
AND i.homebranch= <<Valitse kotikirjasto|branches>>
AND i.dateaccessioned< <<Hankittu aikaisemmin kuin|date>>
GROUP BY biblionumber
```

### Uutuusluettelo

Raportilla voi hakea nimekkeet, joihin on otettu vastaan (items.datereceived) nide valitulla aikavälillä. Mukaan ei ole aikakaus ja sanomalehdet. Rajaus kirjastoon tehdään kotikirjaston perusteella ja haetaan syötetyn kirjastojen kuntalyhenteen perusteella ja lisäksi pitää laittaa '%-merkki', esim. 'OU%' tai 'MLI%'.

Lisääjä: Anneli Österman<br />
Pvm: 22.9.2020

```
SELECT IFNULL(b.author, ExtractValue(bm.metadata,'//datafield[@tag="110"]/subfield[@code="a"]')) AS 'Tekijä', CONCAT(b.title, ' ', ExtractValue(bm.metadata,'//datafield[@tag="245"]/subfield[@code="b"]')) AS 'Nimeke', IFNULL(b.copyrightdate, ExtractValue(bm.metadata,'//datafield[@tag="264"]/subfield[@code="c"]')) AS 'Julkaisuvuosi', i.homebranch AS 'Kotikirjasto', i.itemcallnumber AS 'Luokka', i.itype AS 'Aineistolaji'
FROM items i
JOIN biblio b ON b.biblionumber = i.biblionumber
JOIN biblio_metadata bm ON i.biblionumber=bm.biblionumber
WHERE date(i.datereceived) BETWEEN <<AloitusPvm |date>> AND <<LopetusPvm |date>>
AND i.homebranch LIKE <<Kunnan lyhenne ja %-merkki>> 
and i.itype not in ('ALEHTI', 'SLEHTI')
AND i.notforloan !=-1
GROUP BY b.biblionumber
ORDER BY 6,5
```

### Tuplakorit

Raportti luo linkin listaukseen niiden toimittajien tilauskoreista, joiden tilauksia on mahdollisesti käsitelty useammin kuin kerran. Korin poistamalla ylimääräisten niteiden tulisi poistua.

Lisääjä: Emmi Takkinen<br />
Pvm: 2.12.2021

```
SELECT CONCAT('<a href=\"/cgi-bin/koha/acqui/booksellers.pl?booksellerid=',booksellerid,'\">',booksellerid,'</a>') AS 'Aineistotoimittaja', basketname, booksellerid, count(*) 
FROM aqbasket 
WHERE creationdate BETWEEN <<Alkupvm|date>> AND <<Loppupvm|date>> GROUP BY basketname, booksellerid having count(*) > 1 
ORDER BY basketname, booksellerid
```



## Lehtitilaukset

### Lehtitilaukset, joiden luokkakentässä on ylimääräisiä välilyöntejä lopussa

Raportti hakee lehtitilaukset, joiden luokka-kentässä on ylimääräisiä välilyöntejä lopussa. Tulokset rajataan tilauksiin, joiden "hankintavuosi" on 2022. Tulokset järjestetään sarakkeen kaksi eli kirjaston mukaan.

Ylimääräiset välilyönnit signumin perässä aiheuttaa ongelmia nidehaussa, joten on hyvä pitää huoli, että sellaisia ei synny.

Lisääjä: Anneli Österman<br />
Pvm: 15.7.2022

```
select firstacquidate,branchcode,subscriptionid,biblionumber,callnumber from subscription where callnumber REGEXP '\\s$' and year(firstacquidate)=2022 order by 2
```



## Kohan itsepalvelun (SCO) apuraportit

### Muualle kuljetettavana olevat niteet

Raportilla voi hakea niteet, jotka ovat lähteneet kuljetukseen valitusta kirjastosta eivätkä ole vielä saapuneet määränpäähän. Valittavina parametreinä kirjasto ja lähtöpäivämäärä.

Lisännyt: Anneli Österman / OUTI-kirjastot<br />
Pvm: 29.11.2019

```
SELECT CONCAT('<a href=\"/cgi-bin/koha/catalogue/detail.pl?biblionumber=',b.biblionumber,'">',b.title,'</a>') AS Nimeke, b.author AS 'Tekijä', i.barcode AS Viivakoodi, i.cn_sort AS 'Luokka ja pääsana'
FROM branchtransfers bt
JOIN items i USING (itemnumber)
JOIN biblio b USING (biblionumber)
WHERE bt.frombranch=<<Valitse kirjasto|branches>>
AND date(bt.datesent)=<<Valitse päivämäärä|date>>
AND datearrived is null
ORDER BY 4
```



## Ylläpito-, huolto- ja siirtoloitsuja

Tämän otsikon alle kerätään erilaisia ylläpitoon ja siirtoihin liittyviä loitsuja, joilla kehittäjät voivat säätää massana mm. eräpäiviä ja varausten noutopäiviä. Jos luo jonkin uuden "huoltoloitsun", kannattaa se lisätä tänne myöhempääkin käyttöä varten.

### Varausten noutopäivien siirto

```
UPDATE reserves SET expirationdate='2020-06-15' WHERE branchcode IN ('KOU_EL', 'KOU_HA', 'KOU_IN', 'KOU_JA', 'KOU_KO', 'KOU_VA', 'KOU_MY', 'KOU_QU', 'KOU_PK') AND found='W' AND expirationdate BETWEEN '2020-06-06' AND '2020-06-12';
```

tai

```
UPDATE reserves SET expirationdate='2020-09-07' WHERE branchcode IN ('KOU_A1', 'KOU_A2') AND found='W' AND expirationdate = '2020-06-15';
```

tai

```
UPDATE reserves SET expirationdate='2021-11-08' WHERE branchcode = 'KEPK' AND found='W' AND expirationdate = '2021-11-06';
```

### Eräpäivät siirretty

```
UPDATE issues SET date_due='2020-09-07 23:59:01' WHERE branchcode IN ('KOU_A1', 'KOU_A2') AND date_due BETWEEN '2020-06-15' AND '2020-09-02';
```

tai

```
UPDATE issues SET date_due='2020-08-31 23:59:01' WHERE branchcode = 'ROAU' AND date_due LIKE '2020-06-08%';
```

tai

```
UPDATE issues SET date_due='2021-10-18 23:59:01' WHERE branchcode IN ('RAHA', 'RAPA', 'RAPK', 'RAVI') AND date_due LIKE '2021-10-15%';
```

tai

```
UPDATE issues SET date_due='2020-04-01 23:59:01' WHERE branchcode in ('PYPK', 'PYPIR', 'PYKIKI') AND returndate is null AND date_due between '2020-03-13' AND '2020-04-01';
```
### Eräpäivät siirretty asiakaslajilta

```
UPDATE issues iss LEFT JOIN borrowers bor ON (iss.borrowernumber = bor.borrowernumber) SET iss.date_due = '2020-09-14 23:59:01' WHERE iss.branchcode IN ('OUAKSELI', 'OUAS', 'OUH', 'OUHA', 'OUHI', 'OUJA', 'OUKA', 'OUKEL', 'OUKI', 'OUKK', 'OUKL', 'OUKS', 'OUKV', 'OUMA', 'OUMAR', 'OUONNELI', 'OUOS', 'OUPK', 'OUPT', 'OUPV', 'OUR', 'OURI', 'OUTEUVO', 'OUUL', 'OUY', 'OUYKI', 'OUYLI') AND iss.date_due BETWEEN '2020-06-08' AND '2020-09-14' AND bor.categorycode = 'KOTIPALVEL';
```


### Eräpäivän korjaus tietyn päivän lainoilta

```
UPDATE issues SET date_due='2019-11-21 23:59:00' WHERE issuedate like '2019-10-09%' AND branchcode='ROAU';
```

### Noutamattomien varausten maksun poisto

```
UPDATE accountlines SET amountoutstanding=0 WHERE accounttype='HE' AND timestamp like '2020-06-02%' AND amountoutstanding=1;
```

### Asiakastilin vanhenemisen siirto

```
UPDATE borrowers SET dateexpiry=dateexpiry + interval 6 month WHERE dateexpiry BETWEEN '2020-03-17' AND '2020-12-31' AND categorycode!='VIRKAILIJA';
```

### Niteen kotikirjaston muutos

```
UPDATE items SET homebranch='OUPK' WHERE homebranch like 'OU%' AND homebranch not in ('OUBY', 'OUKIKA', 'OUKEPA', 'OUAKSELI', 'OUPK') AND itype not in ('LA', 'SL', 'ES') AND permanent_location not in ('KOULU', 'LUKIO');
```

### Kellutussäännön fiksaus

```
UPDATE floating_matrix SET condition_rules = REPLACE(condition_rules, ' PILA ', ' EIKELLU ') WHERE condition_rules like '%PILA%';
```

### Viestinnän poikkeustilanteet

Otin talteen (tauluun kd_4400) pending-tilaiset viestit ennen tuota haluttua aikaa, ja asetin sitten niitten viestien tilaksi failed.

```
create table kd_4400 like message_queue;
insert kd_4400 select * from message_queue where status='pending' and time_queued < '2020-04-02 10:31:33';
update message_queue set status='failed' where status='pending' and time_queued < '2020-04-02 10:31:33';
```
Laitoin ajastetut viestintäpalikat päälle.


### Varausten keskeytys ja ei-noutopaikaksi laitto

Varaukset noista ('TLYT', 'YPAU', 'YPEN', 'YPKA', 'YPKI', 'YPMU', 'YPPA') keskeytetty (yht. 199 kpl), ja kys. kirjastot laitettu ei-noutopaikoiksi.

Ajetut SQL-komennot:

```
create table reserves_kd4067 like reserves;
insert into reserves_kd4067 select * from reserves where branchcode in ('TLYT', 'YPAU', 'YPEN', 'YPKA', 'YPKI', 'YPMU', 'YPPA') and suspend=0;
update reserves set suspend=1 where branchcode in ('TLYT', 'YPAU', 'YPEN', 'YPKA', 'YPKI', 'YPMU', 'YPPA') and suspend=0
update branches set pickup_location=0 where branchcode in ('TLYT', 'YPAU', 'YPEN', 'YPKA', 'YPKI', 'YPMU', 'YPPA');
```

tai
KEPK:sta noudettavat varaukset keskeytetty (993 kpl), ja kirjasto ei-noutopaikaksi.

```
update branches set pickup_location=0 where branchcode='KEPK';
insert into reserves_kd4067 select * from reserves where branchcode='KEPK' and suspend=0;
update reserves set suspend=1 where branchcode='KEPK';
```

### Varausten noutopaikan vaihtaminen toiseen kirjastoon

Varaukset vaihdettu noudettavaksi JOE_JOE:sta. Tehdyt komennot:

```
create table reserves_kd4071 like reserves;
insert into reserves_kd4071 select * from reserves where branchcode='JOE_RAN';
update reserves set branchcode='JOE_JOE' where reserve_id in (select reserve_id from reserves_kd4071);
```

(Eli kaikki JOE_RAN varaukset otettu ensin talteen reserves_kd4071 -tauluun, ja sitten vaihdettu niistä alkuperäisistä varauksista noutopaikaksi JOE_JOE)

### Varausten noutopäivän siirto vuodella eteenpäin

```
UPDATE reserves SET expirationdate = DATE_ADD(expirationdate, INTERVAL 1 YEAR) WHERE reserve_id IN(SELECT reserve_id FROM reserves WHERE reservedate = DATE_SUB(expirationdate, INTERVAL 1 YEAR) AND (found IS NULL OR found = 'T'));
```

### Hyllypaikan niteiden muuttaminen tilapäisesti ei-lainata -tilaan

Pääkirjaston lastenosaston paikalla olevat niteet laitettu notforloan-arvolle, jonka mukaan niteitä ei lainata eikä varata, mutta arvo poistuu niteen palautuksen yhteydessä (ei koske lehtiä)

```
update items set notforloan=9 where holdingbranch='JOE_JOE' and location='LAP' and itype!='AL' and notforloan=0 and onloan is not null; 
```

korjaus noudettavien varausten osalta:
```
update items i left join reserves r on (i.itemnumber=r.itemnumber) set i.notforloan=0 where i.notforloan=9 and r.found='W';
```

### Lehtitilausten sulkeminen ja odottaa- tilaisten tiputtaminen 'Reklamaatiot' -listalta

```
UPDATE subscription SET closed='1' WHERE enddate < '2020-01-01';
```

```
UPDATE serial SET status=8 WHERE subscriptionid IN (SELECT subscriptionid FROM subscription WHERE closed=1) AND status=1;
```

### Ei-lainassa olevien, ei-varaukseen tärpänneiden ja nidetilattomien niteiden nidetilan päivittäminen

Esimerkki tiketti #5351

```
CREATE TABLE items_kd5351_20220425 SELECT i.itemnumber, i.homebranch, i.onloan, r.found FROM items i LEFT JOIN reserves r ON(i.itemnumber = r.itemnumber) WHERE i.homebranch IN ("ROPK", "ROLO") AND i.notforloan = 0 AND i.onloan IS NULL AND r.found IS NULL;
```

```
UPDATE items i LEFT JOIN reserves r ON(i.itemnumber = r.itemnumber) SET i.notforloan = 9 WHERE i.homebranch IN ("ROPK", "ROLO") AND i.notforloan = 0 AND i.onloan IS NULL AND r.found IS NULL;
```

### Poistettujen niteiden palauttaminen niin, ettei palauteta jo palautettuja niteitä 

```
INSERT IGNORE INTO items SELECT di.* FROM deleteditems di JOIN biblio b USING(biblionumber) WHERE di.enumchron LIKE "2021 : %" AND b.title = "Anna 2021.";
```

### Käyttöoikeuksien käsittely 

Käyttöoikeuksien moduulien id:t ja käyttöoikeuden nimi löytyvät taulusta permissions.

#### Käyttöoikeuksien lisääminen

Yksittäisen oikeuden lisääminen:

```
INSERT INTO user_permissions (borrowernumber, module, code) VALUES (12345, 12, "suggestions_manage");
```

Täysien oikeuksien lisääminen:

#### Käyttöoikeuksien muuttaminen

#### Käyttöoikeuksien poistaminen

Yksittäisen oikeuden poisto:

```
DELETE FROM user_permissions WHERE code = "suggestions_manage" AND borrowernumber='12345';
```

Täysien oikeuksien poisto:

```
UPDATE borrowers SET flags = flags - (1<<12) WHERE flags = flags | (1<<12) AND borrowernumber='12345';
```
### Hyllypaikka ja signum muutoksia

## Lokien katselu

### Asiakkaan tietojen muutokset

Raportilla voi tutkia, mitä muutoksia asiakkaan tietoihin on tehty koko Koha-historian aikana. Parametriksi annetaan asiakkaan borrowernumber.

Lisääjä: Anneli Österman<br />
Lisäyspvm: 25.3.2022, muokattu 29.3.2022, muokattu 8.9.2023
Versio: 22.11

```
select timestamp,user,module,action,object,info,interface from action_logs
where object = <<borrowernumber>>
and action='MODIFY' 

union 
select timestamp,user,module,action,object,info,interface from action_logs_2020
where object = <<borrowernumber>>
and action='MODIFY'

union 
select timestamp,user,module,action,object,info,interface from action_logs_2019
where object = <<borrowernumber>>
and action='MODIFY'

union 
select timestamp,user,module,action,object,info,interface from action_logs_2018
where object = <<borrowernumber>>
and action='MODIFY'

union 
select timestamp,user,module,action,object,info,interface from action_logs_2017
where object = <<borrowernumber>> 
and action='MODIFY'

union 
select timestamp,user,module,action,object,info,interface from action_logs_2016
where object = <<borrowernumber>>
and action='MODIFY'

order by 1 desc
limit 500
```

### Kuvailutietueen muutosten katselu

Tällä raportilla voi hakea kaikista action_logs-tauluista kerralla kuvailutietueisiin (ja sen niteisiin) liittyvät muutokset.

Lisääjä: Anneli Österman
Pvm: 6.9.2023

```
select timestamp,user,module,action,object,info,interface from action_logs
where module='CATALOGUING'
and object=<<biblionumber>>

UNION
select timestamp,user,module,action,object,info,interface from action_logs_2021
where module='CATALOGUING'
and object=<<biblionumber>>

UNION
select timestamp,user,module,action,object,info,interface from action_logs_2020
where module='CATALOGUING'
and object=<<biblionumber>>

UNION
select timestamp,user,module,action,object,info,interface from action_logs_2019
where module='CATALOGUING'
and object=<<biblionumber>>

UNION
select timestamp,user,module,action,object,info,interface from action_logs_2018
where module='CATALOGUING'
and object=<<biblionumber>>

UNION
select timestamp,user,module,action,object,info,interface from action_logs_2017
where module='CATALOGUING'
and object=<<biblionumber>>

ORDER BY 1 DESC
```

## OKM-tilastot

### Yleistä hankintatilastoista

Raportit laskee hankitut niteet ja niiden perustuen niteen datereceived-tietoon, kotikirjastoon, aineistolajiin ja niteeseen merkittyyn hankintahintaan (price). Mukaan ei tule niteet, jotka ovat Tilattu-tilassa (notforloan-arvona -1). 

Raporteissa on käytetty Koha-Suomen yhdessä sovittuja aineistolajeja. Mikäli kimpassa ei ole käytössä ne, muokkaa lyhenteet vastaamaan oman kimpan aineistolajilyhenteitä.

Raportteja ajaessa pitää kenttään kirjoittaa parametriksi kirjastolyhenteen kuntaosa ja %-merkki. Esim. OUTIssa Limingan tilastot saa kun kirjoittaa <notextile>LI%</notextile>. Limingan kirjastotunnisteet ovat LIPK ja LITU. Aikaväli on määritetty valmiiksi.

[Yleisten kirjastojen tilastojen ohjeet](https://www.kirjastot.fi/sites/default/files/content/yleistenkirjastojentilastot_ohjeet2020.pdf)


### Hankinta OKM-aineistolajeittain

Raporti on jaoteltu OKM:n mukaisiin aineistolajeihin ja tulokset on ryhmitelty hyllypaikan mukaan. Ihan sillä, että tuloksia pystyy arvioimaan vähän tarkemmin. Osion alimmaisena on aina sen osion yhteissumma. Raportti näyttää 200 riviä, mikä pitäisi riittää näyttämään kaikki rivit kerralla. Käyttäjän ei tarvitse ottaa näkyville enemmän rivejä tai siirtyä seuraaville sivuille tuloksissa. Jos summa ei riitä, muokkaa LIMIT-sanojen jälkeen isompi numero.

Jos kimpassa ei ole käytössä Koha-Suomen yhteiset aineistolejit, äänitteiden jako musiikki/muut onnistuu tällä sivulla alempana olevalla raportilla.


```
SELECT items.permanent_location AS 'hyllypaikka', count(items.itemnumber) AS 'Hankittu', sum(items.price) AS 'Hinta niteissä', 'Kaikki aineistolajit paitsi lehdet'
FROM items
WHERE items.datereceived BETWEEN (@AloitusPvm:= '2020-01-01') AND (@LopetusPvm:= '2020-12-31')
AND convert(items.homebranch using 'utf8') like (@Kunta:= <<Kuntaosio ja prosenttimerkki>>)
AND itype not in ('ALEHTI', 'SLEHTI')
AND notforloan not in ('-1')
GROUP BY items.permanent_location WITH ROLLUP LIMIT 200
UNION ALL

SELECT items.permanent_location AS 'hyllypaikka', count(items.itemnumber) AS 'Hankittu', sum(items.price) AS 'Hinta niteissä', 'Kirjat'
FROM items
WHERE items.datereceived BETWEEN @AloitusPvm AND @LopetusPvm 
AND convert(items.homebranch using 'utf8') like @Kunta
AND items.itype='KIRJA'
AND notforloan not in ('-1')
GROUP BY items.permanent_location WITH ROLLUP LIMIT 200

UNION ALL

SELECT items.permanent_location AS 'hyllypaikka', count(items.itemnumber) AS 'Hankittu', sum(items.price) AS 'Hinta niteissä', 'Äänitteet'
FROM items
WHERE items.datereceived BETWEEN @AloitusPvm AND @LopetusPvm 
AND convert(items.homebranch using 'utf8') like @Kunta
AND (items.itype='CDMUSA' OR items.itype='AANILEVY' OR items.itype='KASETTIMU' OR items.itype='KASETTIPU' OR items.itype='CDPUHE')
AND notforloan not in ('-1')
GROUP BY items.permanent_location WITH ROLLUP LIMIT 200

UNION ALL
SELECT items.permanent_location AS 'hyllypaikka', count(items.itemnumber) AS 'Hankittu', sum(items.price) AS 'Hinta niteissä', 'Musiikkiäänitteet'
FROM items
WHERE datereceived BETWEEN @AloitusPvm AND @LopetusPvm 
AND convert(items.homebranch using 'utf8') like @Kunta
AND (items.itype='AANILEVY' OR items.itype='KASETTIMU' OR items.itype='CDMUSA')
AND notforloan !='-1'
GROUP BY items.permanent_location WITH ROLLUP LIMIT 200

UNION ALL
SELECT items.permanent_location AS 'hyllypaikka', count(items.itemnumber) AS 'Hankittu', sum(items.price) AS 'Hinta niteissä', 'Puheäänitteet'
FROM items
WHERE datereceived BETWEEN @AloitusPvm AND @LopetusPvm 
AND convert(items.homebranch using 'utf8') like @Kunta
AND (items.itype='KASETTIPU' OR items.itype='CDPUHE')
AND notforloan !='-1'
GROUP BY items.permanent_location WITH ROLLUP LIMIT 200

UNION ALL
SELECT items.permanent_location AS 'hyllypaikka', count(items.itemnumber) AS 'Hankittu', sum(items.price) AS 'Hinta niteissä', 'Muut aineistot'
FROM items
WHERE items.datereceived BETWEEN @AloitusPvm AND @LopetusPvm
AND convert(items.homebranch using 'utf8') like @Kunta
AND (items.itype='ARTIKKELI' OR items.itype='KARTTA' OR items.itype='DIA' OR items.itype='ESINE' OR items.itype='KASIKIRJ' OR items.itype='KUVA' OR items.itype='MIKROF' OR items.itype='MIKROK' OR items.itype='MONIVIES' OR items.itype='TYOPIIR' OR items.itype='KONSOLIPE' OR items.itype='CELIA')
AND notforloan !='-1'
GROUP BY items.permanent_location WITH ROLLUP LIMIT 200

UNION ALL
SELECT items.permanent_location AS 'hyllypaikka', count(items.itemnumber) AS 'Hankittu', sum(items.price) AS 'Hinta niteissä', 'Videotallenteet'
FROM items
WHERE items.datereceived BETWEEN @AloitusPvm AND @LopetusPvm
AND convert(items.homebranch using 'utf8') like @Kunta
AND (items.itype='DVD' OR items.itype='BLURAY' OR items.itype='VIDEOKAS')
AND notforloan !='-1'
GROUP BY items.permanent_location WITH ROLLUP LIMIT 200

UNION ALL
SELECT items.permanent_location AS 'hyllypaikka', count(items.itemnumber) AS 'Hankittu', sum(items.price) AS 'Hinta niteissä', 'Elektroninen'
FROM items
WHERE items.datereceived BETWEEN @AloitusPvm AND @LopetusPvm
AND convert(items.homebranch using 'utf8') like @Kunta
AND (items.itype='EAANIKIRJA' OR items.itype='VERKKOAIN' OR items.itype='ELEHTI')
AND notforloan !='-1'
GROUP BY items.permanent_location WITH ROLLUP LIMIT 200

UNION ALL
SELECT items.permanent_location AS 'hyllypaikka', count(items.itemnumber) AS 'Hankittu', sum(items.price) AS 'Hinta niteissä', 'Nuotit ja partituurit'
FROM items
WHERE items.datereceived BETWEEN @AloitusPvm AND @LopetusPvm
AND convert(items.homebranch using 'utf8') like @Kunta
AND (items.itype='NUOTTI' OR items.itype='PARTITUURI')
AND notforloan !='-1'
GROUP BY items.permanent_location WITH ROLLUP LIMIT 200

UNION ALL
SELECT items.permanent_location AS 'hyllypaikka', count(items.itemnumber) AS 'Hankittu', sum(items.price) AS 'Hinta niteissä', 'Lehdet'
FROM items
WHERE items.datereceived BETWEEN @AloitusPvm AND @LopetusPvm
AND convert(items.homebranch using 'utf8') like @Kunta
AND (items.itype='ALEHTI' OR items.itype='ELEHTI' OR items.itype='SLEHTI')
AND notforloan !='-1'
GROUP BY items.permanent_location WITH ROLLUP LIMIT 200
```

### Kirja-aineiston hankinta tieto/kauno

Raportti jakaa niteet tietoon/kaunoon perustuen niteen cn_sort-kenttään, jonka tieto taas perustuu Kohan koko signum -kenttään (itemcallnumber). cn_sort-kenttä pitää alkaa luokalla, jotta tämä raportti toimisi.

Raportissa on käytetty Koha-Suomen yhdessä sovittuja aineistolajeja. Mikäli kimpassa ei ole käytössä ne, muokkaa lyhenteet vastaamaan oman kimpan aineistolajilyhenteitä.

```
SELECT items.permanent_location AS 'hyllypaikka', count(items.itemnumber) AS 'Hankittu', 'Tietokirjat'
FROM items
WHERE datereceived BETWEEN (@AloitusPvm:= '2020-01-01') AND (@LopetusPvm:= '2020-12-31') 
AND convert(items.homebranch using 'utf8') like (@Kunta:= <<Kuntaosio ja prosenttimerkki>>)
AND itype='KIRJA'
AND notforloan !='-1'
AND (cn_sort like '0%' OR cn_sort like '1%' OR cn_sort like '2%' OR cn_sort like '3%' OR cn_sort  like '4%' OR cn_sort like '5%' OR cn_sort like '6%' OR cn_sort like '7%' OR cn_sort like '86%' OR cn_sort like '87%' OR cn_sort  like '88%' OR cn_sort like '89%' OR cn_sort like '9%')
GROUP BY items.permanent_location WITH ROLLUP LIMIT 200
UNION ALL

SELECT items.permanent_location AS 'hyllypaikka', count(items.itemnumber) AS 'Hankittu', 'Kaunokirjat'
FROM items
WHERE datereceived BETWEEN @AloitusPvm AND @LopetusPvm
AND convert(items.homebranch using 'utf8') like @Kunta
AND items.itype='KIRJA'
AND notforloan !='-1'
AND (cn_sort like '80%' OR cn_sort like '81%' OR cn_sort like '82%' OR cn_sort like '83%' OR cn_sort like '84%' OR cn_sort like '85%')
GROUP BY items.permanent_location WITH ROLLUP  LIMIT 200
```

### Kirja-aineiston hankinta kielen mukaan

Raportti laskee kirja-aineiston hankinnan kielen mukaan. Kielitieto haetaan tietueen 008-kentästä merkkipaikoilta 35-37. Tulokset jaotellaan suomenkielisiin, ruotsinkielisiin ja muun kielisiin. Muun kielisten teosten yhteissumma on alimmalla rivillä.

```
SELECT SUBSTR(ExtractValue(biblio_metadata.metadata,'//controlfield[@tag="008"]'),36,3) AS 'Kieli', count(items.itemnumber) AS 'Hankittu', 'Suomenkielisiä'
FROM items
JOIN biblio_metadata using (biblionumber)
WHERE datereceived BETWEEN (@AloitusPvm:= '2020-01-01') AND (@LopetusPvm:= '2020-12-31') 
AND convert(items.homebranch using 'utf8') like (@Kunta:= <<Kuntaosio ja prosenttimerkki>>)
AND itype='KIRJA'
AND notforloan !='-1'
AND SUBSTR(ExtractValue(biblio_metadata.metadata,'//controlfield[@tag="008"]'),36,3)='fin'
GROUP BY SUBSTR(ExtractValue(biblio_metadata.metadata,'//controlfield[@tag="008"]'),36,3) LIMIT 200

UNION ALL
SELECT SUBSTR(ExtractValue(biblio_metadata.metadata,'//controlfield[@tag="008"]'),36,3) AS 'Kieli', count(items.itemnumber) AS 'Hankittu', 'Ruotsinkielisiä'
FROM items
JOIN biblio_metadata using (biblionumber)
WHERE datereceived BETWEEN @AloitusPvm AND @LopetusPvm 
AND convert(items.homebranch using 'utf8') like @Kunta
AND itype='KIRJA'
AND notforloan !='-1'
AND SUBSTR(ExtractValue(biblio_metadata.metadata,'//controlfield[@tag="008"]'),36,3)='swe'
GROUP BY SUBSTR(ExtractValue(biblio_metadata.metadata,'//controlfield[@tag="008"]'),36,3) LIMIT 200

UNION ALL
SELECT SUBSTR(ExtractValue(biblio_metadata.metadata,'//controlfield[@tag="008"]'),36,3) AS 'Kieli', count(items.itemnumber) AS 'Hankittu', 'Muun kielisiä'
FROM items
JOIN biblio_metadata using (biblionumber)
WHERE datereceived BETWEEN @AloitusPvm AND @LopetusPvm
AND convert(items.homebranch using 'utf8') like @Kunta
AND itype='KIRJA'
AND notforloan !='-1'
AND SUBSTR(ExtractValue(biblio_metadata.metadata,'//controlfield[@tag="008"]'),36,3)!='fin'
AND SUBSTR(ExtractValue(biblio_metadata.metadata,'//controlfield[@tag="008"]'),36,3)!='swe'
GROUP BY SUBSTR(ExtractValue(biblio_metadata.metadata,'//controlfield[@tag="008"]'),36,3) WITH ROLLUP LIMIT 200
```

### Äänitteiden hankinta musiikki/muut

Mikäli kimpassa ei ole käytössä Koha-Suomen yhdessä sovitut aineistolajit, pystyy äänitteiden jaottelun musiikkiäänitteisiin ja muihin äänitteisiin hakemaan tällä raportilla. Muokkaa aineistolajit vastaamaan oman kimpan aineistolajilyhenteitä.

Jako perustuu niteen cn_sort-kentässä olevaan luokkatietoon. cn_sort-kentän tieto taas perustuu Kohan koko signum -kentän (itemcallnumber) tietoon. Mikäli cn_sort-kenttä ei ala numerolla, se ei tule mukaan raportille. Korjaa tarvittaessa virheelliset signumit.

```
SELECT items.permanent_location AS 'hyllypaikka', count(items.itemnumber) AS 'Hankittu', 'Muut'
FROM items
WHERE datereceived BETWEEN (@AloitusPvm:= '2020-01-01') AND (@LopetusPvm:= '2020-12-31') 
AND convert(items.homebranch using 'utf8') like (@Kunta:= <<Kuntaosio ja prosenttimerkki>>)
AND (items.itype='CD' OR items.itype='LP' OR items.itype='KA' OR items.itype='MP' OR items.itype='SI')
AND (cn_sort like '0%' OR cn_sort like '1%' OR cn_sort like '2%' OR cn_sort like '3%' OR cn_sort like '4%' OR cn_sort like '5%' OR cn_sort like '6%' OR cn_sort like '70%' OR cn_sort like '71%' OR cn_sort like '72%' OR cn_sort like '73%' OR cn_sort like '74%' OR cn_sort like '75%' OR cn_sort like '76%' OR cn_sort like '77%' OR cn_sort like '79%' OR cn_sort like '8%' OR cn_sort like '9%' OR cn_sort like '')
AND notforloan !='-1'
GROUP BY items.permanent_location WITH ROLLUP LIMIT 200
UNION ALL

SELECT items.permanent_location AS 'hyllypaikka', count(items.itemnumber) AS 'Hankittu', 'Musiikki'
FROM items
WHERE datereceived BETWEEN @AloitusPvm AND @LopetusPvm
AND convert(items.homebranch using 'utf8') like @Kunta
AND (items.itype='CD' OR items.itype='LP' OR items.itype='KA' OR items.itype='MP' OR items.itype='SI')
AND cn_sort like '78%'
AND notforloan !='-1'
GROUP BY items.permanent_location WITH ROLLUP LIMIT 200
```

### Listaus kaikista vuonna 2020 hankituista niteistä

Tällä raportilla pystyy hakemaan listan kaikista niteistä, joiden datereceived-tieto on vuodelta 2020. Mukaan ei tule Tilattu-tilaiset (notforloan = -1) niteet eikä lehdet. Viivakoodi-sarakkeessa on linkki, joka vie niteen muokkaukseen. Tulokset järjestetään ensin aineistolajin, sen jälkeen vastaanottopvm:n, sitten tekijän ja sen jälkeen nimekkeen mukaan. Voit muokata järjestystä ORDER BY -rivillä vaihtamalla sarakkeet haluttuun järjestykseen (esim. aineistolaji on sarake numero 8).

Raporttia voi käyttää apuna, kun tutkii, onko niteissä virheitä esim. hyllypaikoissa tai signumeissa.

```
SELECT title as 'Nimeke', author as 'Tekijä', ExtractValue(bm.metadata, '//datafield[@tag="264"]/subfield[@code="c"]') AS 'Julkaisuvuosi', CONCAT('<a href=\"/cgi-bin/koha/cataloguing/additem.pl?op=edititem&biblionumber=',items.biblionumber,'&itemnumber=',items.itemnumber,'" target="_blank">',items.barcode,'</a>') AS 'Viivakoodi', location as 'Hyllypaikka', itemcallnumber as 'Signum', cn_sort as 'Luokka ja pääsana', itype as 'Aineistolaji', datereceived as 'Vastaanottopvm'
FROM items
JOIN biblio using (biblionumber)
JOIN biblio_metadata bm using (biblionumber)
WHERE datereceived BETWEEN (@AloitusPvm:= '2020-01-01') AND (@LopetusPvm:= '2020-12-31') 
AND convert(items.homebranch using 'utf8') like (@Kunta:= <<Kuntaosio ja prosenttimerkki>>)
AND itype not in ('ALEHTI', 'SLEHTI')
AND notforloan not in ('-1')
ORDER BY 8,9,2,1
```

### Niteet, joissa virheellinen signum

Raportti listaa niteet, joiden signum on pelkästään numero eli niteen cn_sort on todennäköisesti puutteellinen/virheellinen. Näiltä niteiltä ei pystytä määrittämään luokkaan perustuvia tietoja (tieto/kauno, musiikki/muu). Korjaa tarvittaessa signumit ennen tilastojen ottamista.

```
SELECT title as 'Nimeke', author as 'Tekijä', ExtractValue(bm.metadata, '//datafield[@tag="264"]/subfield[@code="c"]') AS 'Julkaisuvuosi', CONCAT('<a href=\"/cgi-bin/koha/cataloguing/additem.pl?op=edititem&biblionumber=',items.biblionumber,'&itemnumber=',items.itemnumber,'" target="_blank">',items.barcode,'</a>') AS 'Viivakoodi', location as 'Hyllypaikka', itemcallnumber as 'Signum', cn_sort as 'Luokka ja pääsana', itype as 'Aineistolaji', datereceived as 'Vastaanottopvm'
FROM items
JOIN biblio using (biblionumber)
JOIN biblio_metadata bm using (biblionumber)
WHERE datereceived BETWEEN (@AloitusPvm:= '2020-01-01') AND (@LopetusPvm:= '2020-12-31') 
AND convert(items.homebranch using 'utf8') like (@Kunta:= <<Kuntaosio ja prosenttimerkki>>)
AND itemcallnumber REGEXP '^[0-9]'
AND itype not in ('ALEHTI', 'SLEHTI')
AND notforloan not in ('-1')
ORDER BY 8,9,2,1
```
