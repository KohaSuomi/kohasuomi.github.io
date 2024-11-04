---
title: 'PowerBI'
permalink: /dokumentaatio/powerbi/
redirect_FROM:
  - /theme-setup/
toc: true
---

Kouvolan kaupunginkirjaston PowerBI-tilastoissa käytettyjä raportteja. 

## SQL-raportteja Kohaan


### Taustaraportit

Näillä raporteilla haetaan taustatietoja PowerBI-tilastoihin. Tyypillisesti ne avaavat muussa datassa olevia lyhenteitä, esim. kirjastoja, hyllypaikkoja ja kokoelmia.

#### Kirjastotiedot

```
select branchcode as 'Kirjaston tunnus', branchname as 'Kirjaston nimi' from branches
```

#### Hyllypaikkatiedot

```
select authorised_value as 'Hyllypaikan lyhenne', lib as 'Hyllypaikan kuvaus' from authorised_values where category='LOC'
```

#### Asiakastyyppitiedot

```
select categorycode as 'Asiakastyypin tunnus', description as 'Asiakastyypin kuvaus' from categories
```

#### Aineistotyyppitiedot

```
select authorised_value as 'Aineistotyypin lyhenne', lib as 'Aineistotyypin kuvaus' from authorised_values where category='MTYPE'
```

#### Kokoelmatiedot

```
select authorised_value as 'Kokoelman lyhenne', lib as 'Kokoelma' from authorised_values where category='CCODE'
```

#### notforloan-tiedot

```
SELECT authorised_value as 'Ei lainattavissa -arvo', lib as 'Ei lainattavissa -tila'
FROM authorised_values 
WHERE category='NOT_LOAN'
```

#### DAMAGED-tiedot

```
SELECT authorised_value as 'Vaurioitunut -arvo', lib as 'Vaurioitunut -tila'
FROM authorised_values 
WHERE category='DAMAGED'
```

#### LOST-tiedot

```
SELECT authorised_value as 'Kadonnut-arvo', lib as 'Kadonnut-tila'
FROM authorised_values 
WHERE category='LOST'
```

#### Toimittajatiedot

```
SELECT id,name AS 'Toimittaja'
FROM aqbooksellers
```

### Lainausdata
päivitetty 4.11.2024
```
SELECT s.type AS 'Tapahtumatyyppi', IFNULL(bi.biblionumber, IFNULL(bi2.biblionumber, dbi.biblionumber)) AS 'Tietuenumero', s.itemnumber AS 'Nidenumero', 
IFNULL(bi.author, IFNULL(bi2.author, dbi.author)) as 'Tekijä', 
CONCAT_WS(' ', IFNULL(bi.title, IFNULL (bi2.title, dbi.title)), IFNULL(bi.subtitle, IFNULL (bi2.subtitle, dbi.subtitle)), IFNULL(bi.part_number, IFNULL(bi2.part_number,dbi.part_number)), IFNULL(bi.part_name, IFNULL (bi2.part_name, dbi.part_name))) as Nimeke,
s.branch AS 'Lainauskirjasto', s.borrowernumber AS 'Asiakas-id',
IFNULL(b.categorycode, db.categorycode) AS 'Asiakastyyppi', 
IFNULL(LEFT(b.dateofbirth, 4), (LEFT(db.dateofbirth, 4))) AS 'Svuosi', 
IFNULL(CAST(b.zipcode AS CHAR(5)), CAST(db.zipcode AS CHAR(5))) AS 'Postinumero', 
LEFT(s.datetime, 10) AS 'Tapahtuma-aika_pvm', 
SUBSTR(s.datetime, 12,2) AS 'Tapahtumatunti', 
COALESCE(bibi1.itemtype, bibi2.itemtype, dbibi.itemtype, dbibi2.itemtype) AS 'Aineistotyyppi',
IFNULL(i.permanent_location, d.permanent_location) AS 'Hyllypaikka', 
s.ccode AS 'Kokoelma',
IFNULL(i.cn_sort, d.cn_sort) AS 'Luokka ja pääsana', 
2024-IFNULL(LEFT(b.dateofbirth, 4), (LEFT(db.dateofbirth, 4))) AS 'Ikä',
IFNULL (bde1.primary_language, bde2.primary_language) AS 'Kieli',
SUBSTR(
    IFNULL(i.cn_sort, d.cn_sort), 
    1,
    INSTR(IFNULL(i.cn_sort, d.cn_sort), ' ') - 1
) AS 'Luokka',
IFNULL(i.dateaccessioned, d.dateaccessioned) AS 'Saapumispäivä', 
IFNULL(LEFT(i.dateaccessioned, 4), (LEFT(d.dateaccessioned, 4))) AS 'Saapumispäivän vuosi'
FROM statistics s
LEFT JOIN deleteditems d ON s.itemnumber = d.itemnumber
LEFT JOIN items i ON s.itemnumber = i.itemnumber
LEFT JOIN deletedbiblio dbi ON d.biblionumber=dbi.biblionumber
LEFT JOIN biblio bi ON i.biblionumber=bi.biblionumber
LEFT JOIN biblio bi2 ON d.biblionumber = bi2.biblionumber
LEFT JOIN deletedbiblioitems dbibi ON i.biblioitemnumber = dbibi.biblioitemnumber
LEFT JOIN deletedbiblioitems dbibi2 ON d.biblioitemnumber = dbibi2.biblioitemnumber
LEFT JOIN biblioitems bibi1 ON i.biblioitemnumber = bibi1.biblioitemnumber
LEFT JOIN biblioitems bibi2 ON d.biblioitemnumber = bibi2.biblioitemnumber
LEFT JOIN deletedborrowers db ON s.borrowernumber = db.borrowernumber
LEFT JOIN borrowers b ON s.borrowernumber = b.borrowernumber
LEFT JOIN koha_plugin_fi_kohasuomi_okmstats_biblio_data_elements bde1 ON i.biblionumber = bde1.biblionumber
LEFT JOIN koha_plugin_fi_kohasuomi_okmstats_biblio_data_elements bde2 ON d.biblionumber = bde2.biblionumber
WHERE date(datetime) BETWEEN <<Aikaväli alkaen|date>> AND <<Päättyen|date>>
AND s.type in ('issue', 'renew')
AND convert(s.branch using 'utf8') LIKE <<Kunta tai kirjasto esim. KOU% tai KOU_PK>>
AND b.categorycode != 'EITILASTO'
```

### Nidedata
päivitetty 4.11.2024
```
SELECT i.biblionumber AS 'Tietuenumero', i.itemnumber AS 'Nidenumero', i.homebranch AS 'Kotikirjasto', i.permanent_location AS 'Hyllypaikka', i.ccode AS 'Kokoelma', i.cn_sort AS 'Luokka ja pääsana', i.dateaccessioned AS 'Saapumispäivä', LEFT(i.dateaccessioned, 4) AS 'Saapumispäivän vuosi', i.datelastborrowed AS 'Viimeksi lainattu', LEFT(i.datelastseen, 10) AS 'Viimeksi havaittu', i.notforloan AS 'Ei lainattavissa -tila', i.damaged AS 'Ei varattavissa', i.itemlost AS 'Kadonnut', i.issues AS 'Lainoja', i.renewals AS 'Uusintoja', (IFNULL(i.issues, 0)+IFNULL(i.renewals, 0)) AS 'Lainoja_yht.', 
bi.itemtype AS 'Aineistotyyppi', b.author AS 'Tekijä', 
CONCAT_WS(' ', b.title, b.subtitle, b.part_number, b.part_name, i.enumchron) as 'Nimeke',
bde.publication_year AS 'julk. vuosi',
bde.primary_language AS 'Kielikoodi',
bde.celia AS 'Daisy',
i.barcode AS 'viivakoodi',

SUBSTR(
    i.cn_sort, 
    1,
    INSTR(i.cn_sort, ' ') - 1
) AS 'Luokka',
SUBSTRING_INDEX(SUBSTRING_INDEX(i.cn_sort, " ",2), " " ,-1) AS 'pääsana'

FROM items i
LEFT JOIN biblioitems bi ON bi.biblioitemnumber=i.biblioitemnumber
LEFT JOIN biblio b ON i.biblionumber=b.biblionumber
LEFT JOIN koha_plugin_fi_kohasuomi_okmstats_biblio_data_elements bde ON i.biblionumber=bde.biblionumber
WHERE convert(i.homebranch using 'utf8') LIKE <<Kunta tai kirjasto esim. KOU% tai KOU_PK>>
```

### Hankintadata
päivitetty 13.11.2023
```
SELECT aqi.itemnumber,
IFNULL(i.biblionumber, d.biblionumber) AS 'Biblionumber', 
IFNULL(i.homebranch, d.homebranch) AS 'Kirjasto', 
IFNULL(i.permanent_location, d.permanent_location) AS 'Hyllypaikka', 
IFNULL(i.ccode, d.ccode) AS 'Kokoelma', 
IFNULL(bibi1.itemtype, IFNULL(bibi2.itemtype, dbibi.itemtype)) AS 'Aineistotyyppi',
SUBSTR(
    IFNULL(i.cn_sort, d.cn_sort), 
    1,
    INSTR(IFNULL(i.cn_sort, d.cn_sort), ' ') - 1
) AS 'Luokka',
aq.entrydate AS 'Tilattu', 
aq.datereceived AS 'Saapunut (tilaustaulu)', 
IFNULL(format(i.price, 2,'fi_FI'), format(d.price, 2,'fi_FI')) AS 'Hinta niteissä', 
IFNULL(i.booksellerid, d.booksellerid) AS 'Toimittaja', 
IFNULL(i.notforloan, d.notforloan) AS 'Notforloan', 
IFNULL (bde1.primary_language, bde2.primary_language) AS 'Kieli',
IFNULL (bde1.publication_year, bde2.publication_year) AS 'Julk. vuosi',
IFNULL (bde1.celia, bde2.celia) AS 'Daisy'
FROM aqorders_items aqi
LEFT JOIN items i ON (i.itemnumber=aqi.itemnumber)
LEFT JOIN aqorders aq ON (aq.ordernumber=aqi.ordernumber)
LEFT JOIN deleteditems d ON (d.itemnumber=aqi.itemnumber)
LEFT JOIN biblio b ON (b.biblionumber=i.biblionumber)
LEFT JOIN deletedbiblio dbi ON (dbi.biblionumber=d.biblionumber)
LEFT JOIN deletedbiblioitems dbibi ON i.biblioitemnumber = dbibi.biblioitemnumber
LEFT JOIN biblioitems bibi1 ON i.biblioitemnumber = bibi1.biblioitemnumber
LEFT JOIN biblioitems bibi2 ON d.biblioitemnumber = bibi2.biblioitemnumber
LEFT JOIN koha_plugin_fi_kohasuomi_okmstats_biblio_data_elements bde1 ON (i.biblionumber = bde1.biblionumber)
LEFT JOIN koha_plugin_fi_kohasuomi_okmstats_biblio_data_elements bde2 ON (d.biblionumber = bde2.biblionumber)
WHERE aq.datereceived BETWEEN <<AloitusPvm|date>> AND <<LopetusPvm|date>> AND IFNULL(i.homebranch, d.homebranch) LIKE <<Kuntaosio ja prosenttimerkki>>
```

### Poistodata
päivitetty 13.11.2023
```
SELECT di.biblionumber, di.itemnumber, di.homebranch AS 'kotikirjasto', di.permanent_location AS 'hyllypaikka', di.ccode AS 'kokoelma', di.cn_sort AS 'signum', di.dateaccessioned AS 'saapumispäivä', LEFT(di.dateaccessioned, 4) AS 'saapumispäivän vuosi', di.datelastborrowed AS 'viimeksi lainattu', LEFT(di.datelastseen, 10) AS 'viimeksi havaittu', di.notforloan AS 'ei lainattavissa -tila', di.damaged AS 'ei varattavissa', di.itemlost AS 'kadonnut', di.issues AS 'lainoja', di.renewals AS 'uusintoja', (IFNULL(di.issues, 0)+IFNULL(di.renewals, 0)) AS 'Lainoja_yht.', 
di.timestamp AS 'poistoaika', 
LEFT(di.timestamp, 4) AS 'poistoajan vuosi',
IFNULL(bi.itemtype, dbi.itemtype) AS 'aineistotyyppi', 
IFNULL(b.author, db.author) AS 'tekijä', 
CONCAT_WS(' ', IFNULL(b.title,db.title), IFNULL(b.subtitle,db.subtitle), IFNULL(b.part_number, db.part_number), IFNULL(b.part_name, db.part_name)) as 'Nimeke',
bde.publication_year AS 'julkaisuvuosi',
bde.primary_language AS 'Kielikoodi',
2024-SUBSTR(ExtractValue(bm.metadata,'//controlfield[@tag="008"]'),8,4) AS 'aineiston ikä',
2024-LEFT(di.dateaccessioned, 4) AS 'aineiston ikä (saapumisesta)',
bde.celia AS 'Daisy',
SUBSTR(di.cn_sort, 
    1,
    INSTR(di.cn_sort, ' ') - 1
) AS 'Luokka'
FROM deleteditems di
LEFT JOIN biblioitems bi ON bi.biblioitemnumber=di.biblioitemnumber
LEFT JOIN biblio b ON di.biblionumber=b.biblionumber
LEFT JOIN biblio_metadata bm ON b.biblionumber=bm.biblionumber
LEFT JOIN deletedbiblioitems dbi ON di.biblioitemnumber = dbi.biblioitemnumber
LEFT JOIN deletedbiblio db ON di.biblionumber=db.biblionumber
LEFT JOIN koha_plugin_fi_kohasuomi_okmstats_biblio_data_elements bde ON di.biblionumber=bde.biblionumber
WHERE convert(di.homebranch using 'utf8') LIKE <<Kunta tai kirjasto esim. KOU% tai KOU_PK>> AND di.timestamp BETWEEN <<AloitusPvm |date>> AND LopetusPvm:= <<LopetusPvm |date>>
```

## Taustatietoja muista lähteistä

* Halutun alueen asukasmäärät (esim. kunnittain, postinumeroalueitttain, ikäryhmittäin)
* Postinumeroalueet: [postinumerot.xlsx](https://github.com/KohaSuomi/kohasuomi.github.io/files/12169979/postinumerot.xlsx) (postinumerot, postinumeroalueen nimi, kunta)
* Aikatietotaulu: [aikatietotaulu.xlsx](https://github.com/KohaSuomi/kohasuomi.github.io/files/12169988/aikatietotaulu.xlsx), jossa tarkasteltavan ajan päivämäärät, viikonpäivät, kuukaudet, vuodet omina sarakkeinaan
* Luokitustiedot: [luokat_muotoluokat.xlsx](https://github.com/KohaSuomi/kohasuomi.github.io/files/12169992/luokat_muotoluokat.xlsx)
* Kielikoodit: [kielikoodit.xlsx](https://github.com/KohaSuomi/kohasuomi.github.io/files/12170010/kielikoodit.xlsx)
* Aineistotyyppiryhmittelyt: [Aineistoryhmät.xlsx](https://github.com/KohaSuomi/kohasuomi.github.io/files/12170017/Aineistoryhmat.xlsx)
* Ikäryhmät: [ikäryhmät.xlsx](https://github.com/KohaSuomi/kohasuomi.github.io/files/12170028/ikaryhmat.xlsx), joilla haluaa asiakkaita tarkastella

Näistä luokitustiedot ja kielikoodit ovat melko suoraan käytettävissä. Muita voi joutua muokkaamaan halutunlaisiksi.

## DAX-kielisiä lausekkeita

Käytetään PowerBIn sisällä mittareita luotaessa.

### Lainausdataan liittyviä lausekkeita

```
Lainojen määrä = count('Lainausdata'[Tapahtumatyyppi])
```

```
Ensilainojen määrä = CALCULATE('Mittarit'[Lainojen määrä],'Lainausdata'[Tapahtumatyyppi] IN {"issue"})
```

```
Lainaajien määrä = DISTINCTCOUNT('Lainausdata'[asiakas-id])
```

```
Lainaajien keski-ikä = AVERAGEX(SUMMARIZE(Lainausdata, Lainausdata[Asiakas-id], Lainausdata[Ikä]), Lainausdata[Ikä])
```

### Nidedataan liittyviä lausekkeita

```
Aineiston keski-ikä = AVERAGE('Nidedata'[aineiston ikä])
```

```
Niteiden määrä = count('Nidedata'[Nidenumero])
```

```
5 vuotta vanha aineisto = CALCULATE([Niteiden määrä], 'Nidedata'[aineiston ikä] IN {0,1,2,3,4})
```

```
5 vuotta vanhan aineiston osuus = DIVIDE('Mittarit'[5 vuotta vanha aineisto],'Mittarit'[Niteiden määrä])
```

```
Lainat / nide = DIVIDE(SUM('Nidedata'[Lainoja_yht.]), [Niteiden määrä])
```

Jotta saadaan laskettua aineiston, jota ei ole lainattu viiteen vuoteen (=1825 päivää) ja joka on saapunut yli 2 vuotta (=730 päivää) sitten, määrä ja osuus tarvitaan seuraavat mittarit:

```
Viimeksi lainattu -mittari = SELECTEDVALUE('Niteet'[Viimeksi lainattu])
```
```
Päiviä viime lainauksesta = DATEDIFF('Mittarit'[Viimeksi lainattu -mittari];TODAY();DAY)
```
```
Saapumispäivä_mittari = SELECTEDVALUE('Niteet'[Saapumispäivä])
```
```
Päiviä saapumisesta = DATEDIFF('Mittarit'[Saapumispäivä_mittari];TODAY();DAY)
```
```
5 vuoteen ei lainattu = CALCULATE('Mittarit'[Niteiden määrä]; FILTER('Niteet';'Mittarit'[Päiviä viime lainauksesta]>1825); FILTER ('Niteet';'Mittarit'[Päiviä saapumisesta]>730))
```
```
5 vuoteen lainaamattomien osuus = DIVIDE([5 vuoteen ei lainattu]; [Niteiden määrä])
```

### Hankintoihin liittyviä lausekkeita

```
Hankitut niteet = COUNT('Hankintadata'[itemnumber])
```

```
Ei-lainatut hankinnat = CALCULATE('Mittarit'[Hankitut niteet], 'Hankintadata'[Lainoja_yht.]=0)
```

```
Ei-lainattujen hankintojen osuus = DIVIDE([Ei-lainatut hankinnat], [Hankitut niteet])
```
