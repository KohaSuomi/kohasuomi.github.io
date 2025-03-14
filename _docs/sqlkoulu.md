---
title: 'Miten tehdä SQL-raportteja'
permalink: /dokumentaatio/sqlkoulu/
redirect_FROM:
  - /theme-setup/
toc: true
---

Ohjeen tekijä: Johanna Räisä<br />
Päivittänyt: Anneli Österman / 3.4.2020 / 26.7.2023 / 18.6.2024 / 3.1.2025


[Kohan tietokantaskeema](https://schema.koha-community.org/)

[Koha-Suomen tietokantaskeema.ods](https://github.com/user-attachments/files/19023351/Kohan.skeema.ods) (päivitetty 28.2.2025)

[Tutkimusmatka Kohan tietokantaan](https://youtu.be/lH7Z8OetO3c) -koulutuksen tallenne.

## SQL-lauseiden rakentaminen

### Kielletyt sanat ja muodot

Kohan Tallennetut raportit eivät salli käytettäväksi seuraavia SQL-käskyjä:

* UPDATE
* DELETE
* DROP
* INSERT
* SHOW
* CREATE

![Virheilmoitus, kun käytetään kiellettyjä termejä](/assets/files/docs/Ohjeet/kielletytsanat.png)

Myöskään SET ei toimi, mutta se antaa erilaisen virheilmoituksen. 

![Virheilmoitus, kun kyselyssä on käytetty sanaa SET](/assets/files/docs/Ohjeet/kielletytsanat1.png)

Yllä olevia sanoja ei voi käyttää myöskään sarakkeen nimissä esim. _SELECT biblionumber AS 'Delete these' FROM biblio;_

Versiossa 24.05 tuli muutos, jonka myötä tallennetuilla raporteilla ei voi hakea tietoturvasyistä seuraavien nimisten kenttien sisältöä:

* password
* token
* UUID
* secret

Tämä käytännössä estää tekemästä esimerkiksi borrowers-tauluun kyselyn _SELECT * FROM borrowers;_, koska tulos pitäisi sisällään myös password-kentän. Kysely pitää tällöin rakentaa niin, että mukaan ei tule yllä mainittuja kenttiä.

![Virheilmoitus, kun on käytetty tietoturvan vuoksi estettyjä sarakenimiä](/assets/files/docs/Ohjeet/kielletytsanat2.png)

**Taulujen nimet** pitää kirjoittaa **pienillä kirjaimilla**, jotta kysely toimii. Esimerkiksi _SELECT cardnumber FROM BORROWERS;_ aiheuttaa virheilmoituksen, että BORROWERS-nimistä taulua ei ole olemassa.

![Virheilmoitus, kun taulun nimen kirjoittaa isoilla kirjaimilla](/assets/files/docs/Ohjeet/kielletytsanat3.png)

### Lauseen rakentaminen

Lausetta rakentaessa kannattaa ensin miettiä mikä on päätaulu, eli mitä tietoa halutaan ja tarvitseeko siihen yhdistellä muita tauluja.

Esimerkki: Haluan asiakkaat ja niille maksut ajalta 01.06.2022-10.06.2022, lisäksi sellaiset maksut joita ei ole vielä maksettu. Järjestetään ne vielä päivämäärän mukaan laskevasti, eli uusimmasta vanhimpaan.

```
SELECT b.surname as 'Sukunimi', b.firstname as 'Etunimi', a.amountoutstANDing as 'Maksun määrä', a.description as 'Kuvaus' FROM borrowers b
JOIN accountlines a on b.borrowernumber = a.borrowernumber
WHERE a.amountoutstanding != 0 AND date(a.date) between '2022-06-01' AND '2022-06-10' ORDER BY date desc;
```

Kannattaa myös katsoa ensin [Koha-yhteisön raporttikirjastosta](https://wiki.koha-community.org/wiki/SQL_Reports_Library) onko siellä mallia, josta saisi pienellä muokkauksella sopivan.


### SELECT-lause

Lause, jolla haetaan tietoa tietokannasta.
Yksinkertaisimmillaan lause on:

```
SELECT * FROM borrowers;
```

Tällä komennolla haetaan kaikki taulun kentät ilman rajausta. Tätä tulee välttää raportteja luodessa, niissä pitäisi määritellä tarvittavat kentät. Versiossa 24.05 lähtien yllä oleva esimerkki ei myöskään toimi, koska se sisältää tietoturvasyistä kielletyn password-kentän tuloksissa.

Taulusta voidaan myös kysellä pelkästään tiettyjä kenttiä kirjoittamalla tähden tilalle halutut kentät.

```
SELECT borrowernumber, cardnumber, address FROM borrowers;
```

Kenttien nimiä voidaan myös muuttaa, jos ei haluta näyttää englanninkielisiä sarakeotsikoita. Tämä tapahtuu "as"-sanalla.

```
SELECT borrowernumber as 'Asiakasnumero', cardnumber as 'Kortin numero', address as 'Osoite' FROM borrowers;
```

Nimi kannattaa laittaa yksöishipsuihin, varsinkin jos se on kaksiosainen tai sisältää ääkkösiä.

### WHERE

Jos halutaan rajata haku tiettyjen parametrien mukaan, niin silloin SELECT-lauseeseen lisätään WHERE-komento.

```
SELECT * FROM borrowers WHERE categorycode = 'LAPSI';
```

Arvot, joissa on kirjaimia tulee olla hipsujen sisässä. Jos et tiedä onko kenttä numerokenttä, niin on turvallisinta ympäröidä hipsuilla.

WHERE-komentoon voi lisätä useita rajoituksia AND- ja OR-sanalla.

```
SELECT * FROM items WHERE itype = '28VRK' AND location = 'A';
SELECT * FROM items WHERE itype = '14VRK' OR itype = '28VRK';
```

Mallissa AND-sanan tulosjoukko muodostuu riveistä, joilla on nidetyyppi 28VRK ja hyllypaikka aikuiset.
Mallissa OR-sanan tulosjoukko muodostuu riveistä, joilla on nidetyyppi 14VRK tai nidetyyppi 28VRK. Eli tulosjoukko muodostuu kummastakin nidetyypistä.

Joskus on helpompi saada tulosjoukko rajoittamalla negatiivisesti. Siihen käytetään määritystä !=

```
SELECT * FROM items WHERE itype != '28VRK' AND homebranch = 'MLI_PK';
```

Mallin haussa tulosjoukko muodostuu Mikkelin pääkirjaston kaikista muista niteistä paitsi e-kirjasta.

Jos Kohassa halutaan valita kirjastopiste ennen raportin käynnistystä niin silloin raporttin laitetaan ohjelmoitu valintatyökalu.

```
SELECT * FROM items WHERE itype != '28VRK' AND homebranch=<<Kotikirjasto|branches>>;
```

Käyttääksesi WHERE-rajauksia sinun tulee tietää tunnusarvot. Tietokannassa käytetään lyhyitä tunnuksia, joilla on nopeampi hakea. Kuvaukset ovat yleensä ihmisiä varten ja ne näytetään vain käyttöliittymässä.

### LIKE

SELECT-lauseissa voidaan käyttää vertailussa myös LIKE-sanaa. Esim, jos halutaan jonkun tietyn kunnan kirjastopisteet samaan tulosjoukkoon.

```
SELECT * FROM items WHERE homebranch LIKE 'MLI%';
```

Mallin tulosjoukkoon tulee kaikki niteet kirjastopisteistä joiden lyhenne alkaa sanalla MLI. LIKE-vertailussa pystytään käyttämään %-merkkiä, joka toimii villinä korttina haussa. Tämä on todella paljon hitaampaa, kuin suoraan =-merkillä muodostettu lause.

LIKE-komennossakin on mahdollisuus negatiiviseen rakenteeseen. Tällöin käytetään määritettä 'NOT LIKE'.

```
SELECT * FROM items WHERE homebranch NOT LIKE 'MLI%';
```

LIKE-komennon yhteydessä voi käyttää :all-lisämäärettä parametrissä, jolloin kyselyä ajaessa käyttäjä voi valita Kaikki-vaihtoehdon. Esim.

```
SELECT * FROM items WHERE homebranch LIKE <<Valitse kirjasto|branches:all>>;
```

näyttää ajettaessa tältä:

![](/assets/files/docs/Ohjeet/sqlkoulu17.png)

### IN

IN-komennolla voidaan määrittää, että haetaan esimerkiksi tiettyjä biblionumbereita:

```
SELECT * FROM items WHERE biblionumber IN (12, 13, 14, 15);
```

Sen avulla voi luoda esimerkiksi parametrin, joka antaa käyttäjän valita, mitä kirjastoja haetaan. Tällöin käytetään myös auktorisoidun arvon perässä :in-lisämäärettä:

```
SELECT * FROM items WHERE homebranch IN <<Valitse kirjasto|branches:in>>;
```

![](/assets/files/docs/Ohjeet/sqlkoulu16.png)

Voit myös luoda lista-ajonaikaisella parametrilla kyselyn, jossa käyttäjä voi syöttää useamman hakuehdon, yhden per rivi. Esim.

```
SELECT * FROM items WHERE homebranch IN <<Syötä kirjastojen tunnukset yksi per rivi|list>>;
```

![](/assets/files/docs/Ohjeet/sqlkoulu18.png)

### JOIN

Haussa tulosjoukkoon saadaan tietoa muista tauluista relaatioiden avulla. JOIN-komento on keskeisessä roolissa tässä yhdistelyssä.

```
SELECT b.author as 'Tekijä', b.title as 'Nimeke', i.location as 'Hyllypaikka', i.homebranch as 'Kotikirjasto' FROM items i 
JOIN biblio b on i.biblionumber = b.biblionumber 
WHERE i.itype = '28VRK';
```

Mallissa yhdistetään items-taulu ja biblio-taulu ja otetaan kummastakin tietoa tulosjoukkoon. Lauseessa tauluille on annettu lyhenteet, joita käytetään selventämään mistä taulusta tieto pitäisi tulla. Jos tauluissa on paljon saman nimisiä kenttiä, SQL ei tiedä kummasta on kyse, siksi kentän eteen tulee laittaa tietoa taulusta joko taulun koko nimellä tai sitten määritellyllä lyhenteellä.

Lauseessa voi olla ääretön määrä join-komentoja, jos vain tauluilla on jokin yhdistävä kenttä (relaatio). Kuitenkin mitä enemmän yhdistetään taulujen tietoa sitä hitaammaksi haut käyvät.

JOIN-komentoja on erilaisia. [Katso visuaalinen esittely JOINien eroista](https://www.codeproject.com/Articles/33052/Visual-Representation-of-SQL-Joins).

### Taulujen aliakset

Kyselyssä voi määrittää tauluille aliaksen, jolla voi viitata muualla kyselyssä tauluun. Tämä on helppo ja nopea tapa kertoa, mistä taulusta tieto halutaan hakea, jos useassa taulussa on sama sarake käytössä. Jos taulua ei määrittele, ilmoittaa Koha tiedon olevan "ambiguous" eli epämääräinen eikä aja raporttia.

Aliaksen voi keksiä itse, mutta se kannattaa olla helposti muistettava ja lyhyt. Alias kirjoitetaan kyselyssä heti taulun nimen perään. Alla olevassa kyselyssä biblionumber löytyy kummastakin taulusta, joten se on määritetty haettavaksi biblio-taulusta.

```
SELECT b.title,b.biblionumber,i.barcode
FROM biblio b
JOIN items i USING (biblionumber)
WHERE i.holdingbranch='OUPK'
```

### Ajalla rajaaminen

Tulosjoukkon rajaaminen ajan mukaan voidaan määritellä monella eri tavalla, mutta yksin kertaisin on opetella BETWEEN-lause.

```
SELECT *
FROM items
WHERE date(dateaccessioned) BETWEEN '2022-01-01' AND '2022-12-31';
```

Tietokannassa päivämäärät ovat yleensä muodossa 2016-01-01 12:00:00, mallin lauseessa halutaan vain päiväys eikä kellonaikaa. Siksi päivämäärä-kenttä on ympyröity date:lla.

Kohassa päivämäärä valinnan saa raporttiin kun vaihtaa nuo luvut sisäänrakennettuun valintatyökaluun.

```
SELECT *
FROM items
WHERE date(dateaccessioned) BETWEEN <<AloitusPvm |date>> AND <<LopetusPvm |date>>;
```

Aloitus- ja lopetuspäivämäärien kuvaus eli yllä esim. AloitusPvm, kannattaa olla eri nimiset, muuten Koha yhdistelee ne samaksi kentäksi.

### COUNT

COUNT-komennolla voidaan laskea tulosjoukon rivien määrä yhteen.

```
SELECT count(*) FROM items WHERE itype = '28VRK';
```

### GROUP BY

GROUP BY -komennolla voidaan ryhmitellä tulosjoukkoa.

```
SELECT * FROM issues group by itemnumber;
```

Mallin lause antaa lainat-taulusta tulosjoukon niteen numeron mukaan, eli joka rivillä on eri itemnumber. Tätä joudutaan käyttämään joskus jos tulosjoukkoon tulee paljon samoja rivejä.

### ORDER BY

ORDER BY -komennolla voidaan järjestää tulosjoukkoa halutulla tavalla.

```
SELECT * FROM borrowers ORDER BY surname ASC;
```

Mallin lause järjestää tulosjoukon sukunimen mukaan nousevasti (ascending), eli A:sta Ö:hön.

```
SELECT * FROM borrowers ORDER BY surname DESC;
```

Mallin lause järjestää tulosjoukon sukunimen mukaan laskevasti (descending), eli Ö:stä A:han.

### LIMIT

LIMIT-komennolla voidaan rajata hakutuloksen tulosjoukkoa.

```
SELECT * FROM borrowers LIMIT 100;
```

Mallin  lause hakee 100 ensimmäistä riviä borrowers-taulusta.


### CONCAT

CONCAT-komennolla voidaan muodostaa yhtenäisiä merkkijonoja. 

```
SELECT concat(b.surname,' ', b.firstname) as 'Asiakas' FROM borrowers WHERE categorycode = 'HENKILO';
```

Mallissa yhteen sarakkeeseen tulee asiakkaan sukunimi, väli ja etunimi.

### ExtractValue

ExtractValue-komennolla voidaan kysellä tietoa kentän sisällä olevasta rakenteesta. Kannattaa huomioida, että nämä voivat hidastaa kyselyä.

```
SELECT * FROM biblio_metadata bm
WHERE ExtractValue(bm.metadata, '//datafield[@tag="773"]/subfield[@code="w"]') = '';
```

Jos MARC-kentän tiedot halutaan hakea vain taulukon sarakkeeseen, sen voi tehdä näin:

```
SELECT title, ExtractValue(bm.metadata, '//datafield[@tag="264"]/subfield[@code="c"]')
FROM biblio_metadata bm
JOIN biblio b using (biblionumber)
WHERE biblionumber=1234
```

Mallissa mennään marcxml-kentän sisälle ja tarkastellaan xml-rakennetta. Mallin haku antaa tulosjoukoksi luettelointitiedot, joilla ei ole kenttää 773w eli se on tyhjä.

Nimiöstä 7. merkkipaikalta lähtien 2 merkkiä eteenpäin ei ole "im":
```
SUBSTR(ExtractValue(bm.metadata,'//leader'),7,2) NOT IN ('im') 
```

Kiinteämittaisista kentistä 007-kentässä 1. merkkipaikalta 2 merkkiä eteenpäin on "ss":
```
SUBSTR(ExtractValue(bm.metadata,'//controlfield[@tag="007"]'),1,2) IN ('ss')
```

Kiinteämittaisista kentistä 007-kenttää voi toistaa ja kummatkin kentät saa haettua näin erikseen:

```
SELECT biblionumber, ExtractValue(metadata, '//controlfield[@tag="007"][1]'), ExtractValue(metadata, '(//controlfield[@tag="007"][2])')
FROM biblio_metadata
WHERE ExtractValue(metadata, 'count(//controlfield[@tag="007"])') > 1
```
Toistumat liimataan toisiinsa "välilyönnillä" haettaessa, joten myös kokonaismerkkijonoa voi hakea. Esim. jos ensimmäisessä toistumassa on merkkipaikoilla 00-01 'ou' ja toisessa toistumassa merkkipaikalla 00 'r', eikä muilla merkkipaikoilla ole tietoa, on lopputulos 'ou r'. Sitä voi hakea näin:

```
SELECT biblionumber, ExtractValue(bm.metadata,'//controlfield[@tag="007"]') AS '007'
FROM biblio_metadata bm
WHERE ExtractValue(bm.metadata,'//controlfield[@tag="007"]') = ('ou r')
```

Jos hakuehtona on, että 007-kentän toisessa toistumassa on tietyt tiedot tietyillä merkkipaikoilla, se onnistuu näin:

```
SELECT biblionumber, ExtractValue(bm.metadata,'//controlfield[@tag="007"]') AS '007'
FROM biblio_metadata bm
WHERE SUBSTR(ExtractValue(bm.metadata,'//controlfield[@tag="007"][2]'),1,1) = 'k'
AND SUBSTR(ExtractValue(bm.metadata,'//controlfield[@tag="007"][2]'),5,1) = ' '
AND ExtractValue(metadata, 'count(//controlfield[@tag="007"])') > 1
```

#### metadata-sarake näkyviin kuten se on tietokantaan tallennettu

Jos halutaan nähdä biblio_metadata.metadata-sarakkeen tiedot xml-muodossa eli näkyvillä on myös MARC-kenttien tägit ja rivitykset, voi metadata-kentän tiedon hakea raportilla alla olevalla tavalla. Käytännössä siinä korvataan <- ja >-merkit &lt;- ja &gt; -merkeillä (ettei selain tulkitse niitä xml-tägeiksi ja piilota niitä) ja pre-tagilla määritetään näkyviin tiedot sellaislla asettelulla kuin ne on tietokantaan tallennettu. 

```
CONCAT('<pre>', REPLACE(REPLACE(bi.metadata, '<', '&lt;'), '>', '&gt;'), '</pre>') as metadata
```


### NULL ja tyhjä

Tietokannassa voi olla kahden tyyppisiä "tyhjiä"-kenttiä. NULL tarkoittaa, että kenttään ei ole määritelty mitään. Toinen vaihtoehto on, että kentässä on tyhjä merkkijono. NULL-määreen kanssa käytetään IS-sanaa =-merkin tilalla. Negatiivisia hakuja tehdessä käytetään 'IS NOT NULL'.

```
SELECT * FROM items WHERE barcode IS NULL AND homebranch = 'MLI_PK';
SELECT * FROM items WHERE barcode = '' AND homebranch = 'MLI_PK';
```

Jos "tyhjiä" halutaan käyttää vertailussa niin silloin kannattaa testata kumpaakin yhtä aikaa.

```
SELECT * FROM items WHERE (barcode IS NULL OR barcode = '') AND homebranch = 'MLI_PK';
```

Mallin tulosjoukko muodostuu niteistä, joilla ei ole viivakoodia. *Huomaa sulut OR-vertailujen ympärillä!* Jos sekoitellaan AND- ja OR-vertailua, niin OR pitää ympyröidä suluilla.

### Relaatiot

Relaatioilla tarkoitetaan tauluja yhdistäviä tekijöitä, kuten asiakkaiden relaatiota lainoihin.

```
SELECT count(*) FROM borrowers b
JOIN issues i on b.borrowernumber = i.borrowernumber
JOIN old_issues oi on b.borrowernumber = oi.borrowernumber
WHERE b.borrowernumber = 1;
```

Mallin lause antaa kaikki nykyiset ja vanhat lainat asiakkaalle, jonka borrowernumber on yksi.

Kohan relaatiot löytyvät [tietokantarakenteesta](http://schema.koha-community.org/). 
Yleensä relaatiot on nimetty samalla nimellä, kuten mallissa kaikista tauluista löytyy borrowernumber-kenttä.


## Tallennetut raportit

Kohan tallennetuissa raporteissa voi käyttää ehdoissa hyväksi myös auktorisoituja arvoja, jolloin ne saadaan kyselyn ajovaiheessa alasvetovalikkoon. Ne määritellään käyttöön seuraavasti:

```
sarakkeen nimi = <<Kuvaus tiedosta|auktorisoitu arvo>>
```

Se näkyy raportin ajovaiheessa näin:

![](/assets/files/docs/Ohjeet/sqlkoulu2.png)

Arvoja saa lisättyä kyselyyn myös _Lisää ajoajan parametri_ -valikosta valitsemalla soveltuvan.

![](/assets/files/docs/Ohjeet/sqlkoulu1.png)

### 1. Kirjasto

```
SELECT * FROM items WHERE homebranch=<<Valitse kirjasto|branches>>
```

![](/assets/files/docs/Ohjeet/sqlkoulu.png)

tai

```
SELECT * FROM bORrowers WHERE branchcode=<<Asiakkaan kotikirjasto|branches>>
```

### 2. Hyllypaikka

```
SELECT * FROM items WHERE location=<<Valitse hyllypaikka|loc>>
```

![](/assets/files/docs/Ohjeet/sqlkoulu3.png)

### 3. Nidetyyppi

```
SELECT * FROM items WHERE itype=<<Valitse nidetyyppi|itemtypes>>
```

![](/assets/files/docs/Ohjeet/sqlkoulu4.png)


### 4. Aineistotyyppi

```
SELECT * FROM biblioitems WHERE itemtype = <<Valitse aineistotyyppi|MTYPE>>
```

![](/assets/files/docs/Ohjeet/sqlkoulu5.png)

### 5. Kokoelma

```
SELECT * FROM items WHERE ccode=<<Valitse kokoelma|CCODE>>
```

![](/assets/files/docs/Ohjeet/sqlkoulu6.png)

### 6. Päivämäärän valinta kalenterista

```
SELECT * FROM issues WHERE issue_date=<<Lainauspäivä|date>>
```

![](/assets/files/docs/Ohjeet/sqlkoulu7.png)

### 7. Linkin lisääminen raportille

Raporttiin voi lisätä linkin esimerkiksi asiakkaaseen, teokseen, niteeseen, luettelointitietueeseen tai varaukseen. Se tehdään CONCAT-toiminnolla SELECT-riville. Kohdeosoitteen voi tarkistaa osoiteriviltä halutussa Kohan osiossa.

**Huom!** Versiosta 22.11 lähtien Koha lisää automaattisesti linkin asiakkaaseen, niteeseen ja tietueeseen, jos raportin tuloksissa on sarakkeessa borrowernumber, itemnuber tai biblionumber.

![](/assets/files/docs/Ohjeet/sqlkoulu8.png)

Jos klikkaat borrowernumberin, itemnumberin tai biblionumberin vieressä olevaa pientä kolmiota, pääset suoraan kyseisen asiakkaan, niteen tai tietueen tietoihin tai muokkaukseen. Asiakkaan osalta pääset myös suoraan lainaamaan.

![](/assets/files/docs/Ohjeet/sqlkoulu9.png)

Jos kuitenkin haluat näkyville esim. kirjastokortin numeron tai teoksen nimekkeen, alla on siihen ohjeet.

#### 7.1 Asiakkaaseen

Linkki asiakkaaseen siten, että tekstinä näkyy kirjastokortin numero ja osoitteeseen lisätään asiakkaan borrowernumber. Linkki avautuu uuteen välilehteen.

```
SELECT CONCAT('<a href=\"/cgi-bin/koha/members/mORemember.pl?borrowernumber=',b.bORrowernumber,'" target="_blank">',b.cardnumber,'</a>') AS 'Asiakas'
FROM borrowers b
WHERE zipcode=<<Postinumero>>
```

b.cardnumber-tiedon sijalle voi periaatteessa laittaa minkä tahansa borrowers-taulun tiedon, mutta kannattaa muistaa ettei tee turhia asiakastietojen katseluja raporteillakaan.

#### 7.2 Teoksen perustiedot-näytölle

Linkki teokseen siten, että tekstinä näkyy teoksen nimeke ja osoitteeseen lisätään teoksen biblionumber. Linkki avautuu uuteen välilehteen.

```
SELECT CONCAT('<a href=\"/cgi-bin/koha/catalogue/detail.pl?biblionumber=',b.biblionumber,'" target="_blank">',b.title,'</a>') AS Nimeke
FROM biblio b
WHERE datecreated BETWEEN <<Luontipäivä aikaisintaan|date>> AND <<Luontipäivä viimeistään|date>>
```

####  7.3 Niteen muokkaukseen

Linkki tietyn niteen muokkaukseen niin, että osoitteeseen lisätään biblionumber, itemnumber ja linkkitekstiksi tulee viivakoodi. Linkki avautuu uuteen välilehteen.

```
SELECT CONCAT('<a href=\"/cgi-bin/koha/cataloguing/additem.pl?op=edititem&biblionumber=',i.biblionumber,'&itemnumber=',i.itemnumber,'" target="_blank">',i.barcode,'</a>') AS 'Viivakoodi'
FROM items i
WHERE i.ccode='CELIA'
```

#### 7.4 Tietueen muokkaukseen

Linkki tietueen muokkaukseen siten, että osoitteeseen lisätään biblionumber ja linkin tekstiksi tulee biblionumber. Linkin tekstiksi voi helposti muokata myös teoksen nimen halutessaan vaihtamalla jälkimmäiseen b.biblionumber-kohtaan b.title. Linkki avautuu uuteen välilehteen.

```
SELECT CONCAT('<a href=\"/cgi-bin/koha/cataloguing/addbiblio.pl?biblionumber=',b.biblionumber,'" target="_blank">',b.biblionumber,'</a>') AS 'Teos',
FROM biblio b
WHERE datecreated=<<Valitse päivä|date>>
```

#### 7.5 Varausjonoon

Linkki tietueen varausjonoon siten, että linkkitekstinä on tietueen nimeke. Linkki avautuu uuteen välilehteen.

```
SELECT CONCAT('<a href=\"/cgi-bin/koha/reserve/request.pl?biblionumber=',b.biblionumber,'" target="_blank">',b.title,'</a>') AS 'Varausjonoon'
FROM reserves r
JOIN biblio b USING (biblionumber)
WHERE r.branchcode=<<Valitse noutokirjasto|branches>>
```

### 8. Automaattiset ehdotukset

Versiossa 23.11 Kohan raportteihin lisättiin automaattiset ehdotukset. Kun kirjoitat, ehdottelee Koha kirjoittamiasi merkkejä vastaavia ehdotuksia tauluista ja "käskyistä". Esimerkiksi, jos kirjoitat 'i', saat näkyville pienen valikon, jossa on ehdolla i:llä alkavia taulujen nimiä kuten items ja issues ja käskyjä kuten IS ja IN.

![](/assets/files/docs/Ohjeet/sqlkoulu10.png)

Jos määrittelet kyselyssä taululle aliaksen esim. items i, niin voit saada ehdotuksia kyseisen taulun sarakkeista kirjoittamalla aliaksen ja pisteen. Eli esimerkiksi 'i.'.

![](/assets/files/docs/Ohjeet/sqlkoulu11.png)

Ehdotukset voi valita joko hiirellä tai näppäimistöllä nuolinäppäimillä ja ENTER-painikkeella. Huomioi, että jos olet vaihtamassa riviä ENTERillä ja Koha antaa automaattisen ehdotuksen, tulee ensimmäinen ehdotus valituksi kun tarkoitus oli vaihtaa riviä vaihtaessa. Ehdotuksesta pääsee eroon lisäämällä esimerkiksi välilyönnin ennen rivinvaihtoa ja sitten poistamalla sen.

### 9. Ajonaikaiset parametrit

Tallennetulle raportille pystyy lisäämään ajoaikaisia parametrejä myös SQL-laatikon yläpuolella olevasta valikosta _Lisää ajoajan parametri_.
![](/assets/files/docs/Ohjeet/sqlkoulu12.png)

Kun valitaan jokin vaihtoehto, avautuu ponnahdusikkuna, jossa voi täyttää tarkempia tietoja
![](/assets/files/docs/Ohjeet/sqlkoulu13.png)
- _Parametrit_: Parametrin otsikko kyselyssä. Esim. Kirjasto, Hyllypaikka, Päivämäärä jne. Voit jättää kenttään ehdotetun tekstin tai muokata sen halutunlaiseksi.
- _Auktorisoidun arvon luokka_: Valitse, minkä auktorisoidun arvon luokan tiedot näytetään raportin ajajalle. HUOM! Tämä tulee tarjolle vain, kun valittuna on Auktorisoidun arvon lisääminen raportille.
- _Parametrivaihtoehdot_:
  - _Vain yksi parametri_: Kyselyn pitää käyttää =-merkkiä. Esim. ```SELECT barcode FROM items WHERE notforloan = <<Ei lainata -tila|NOT_LOAN>>```
  - _Sisällytä vaihtoehto kaikille_: Kyselyn pitää käyttää LIKE-käskyä. Tällä vaihtoehdolla pystyy hakemaan myös kaikki vaihtoehdot, kun siihen lisää :all-lisämääreen auktorisoidun arvon perään. Esim. ```SELECT barcode FROM items WHERE notforloan LIKE <<Ei lainata -tila|NOT_LOAN:all>>```
  - _Salli useita valintoja_: Kyselyn pitää käyttää IN-käskyä ja auktorisoidun arvon perään lisätään :in-lisämääre. Esim. ```SELECT barcode FROM items WHERE notforloan IN <<Ei lainata -tila|NOT_LOAN:in>>```
- _Lisää parametri_ -napilla saa lisättyä valinnat raportille, _Peruuta_-napilla valinnat saa peruttua.

Toiminto lisää valinnat SQL-laatikkoon valittuna olleeseen kohtaan.

![](/assets/files/docs/Ohjeet/sqlkoulu14.png)

Eri parametrit tarjoajavat erilaisia vaihtoehtoja

![](/assets/files/docs/Ohjeet/sqlkoulu15.png)

## Pölkyillä vai ei?

Monesti kyselyt kirjoitetaan niin, että "käskyt" kirjoitetaan pölkkykirjaimin, jolloin ne on helpompi erottaa tekstin seasta. Kohan kannalta ei ole merkitystä, kirjoitetaanko pölkyillä vai ei.

## Ei toimi?

* tarkista, että hipsuilla " tai ' ja sulkeilla on vastakappaleet, monesti ne esiintyvät pareittain.
* tarkista kirjoitusvirheet. Esimerkiksi biblionumber-sanan voi kirjoittaa kovin monella tapaa väärin (bilionumber, biblionumer..).
* onhan lauseessa sana SELECT?
* onhan haettava taulu määritetty?
