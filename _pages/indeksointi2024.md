---
layout: single
permalink: /indeksointiryhma2024
hidden: true
header:
  overlay_color: '#5e616c'
  overlay_image: /assets/images/cropped-pexels-photo-113850.jpeg
toc: true
title: 'Indeksointi- ja tiedonhakuryhmä 2024'
---

Indeksointi- ja tiedonhakuryhmän kokousten muistiot vuodelta 2024. Indeksointi- ja tiedonhakuryhmän tarkoitus on arvioida ja päättää indeksointiin ja tiedonhakuun liittyvien kehitysehdotusten toteutuksesta. Jäsenet: Anneli Österman ja Johanna Räisä (Koha-Suomi), Antti Heikkinen (OUTI), Kai Sormunen (Vaara), Ville Kivioja (Kyyti), Timo Väisänen (Kirkes), Heli Auranen (Lumme), Markku Untinen (Helle), Anna Viitanen (Vaski), Mauri Aittaniemi (Lappi)

## Muistio 2/2024

Aika: To 7.3.2024 klo 12.15-13.15<br />
Läsnä: Ville Kivioja, Johanna Räisä, Heli Auranen, Timo Väisänen, Antti Heikkinen, Anneli Österman

### 1. Käsiteltävät kehitysehdotukset

* [Nidehaun luokkahaku ja sisältyy-sana #421](https://github.com/KohaSuomi/Koha/issues/421)
  * Päätös: Muutettiin tiketti bugi-tyyppiseksi.
* [Nidehaun julkaisuvuosi-hakuun ennen/jälkeen -toiminnot #447](https://github.com/KohaSuomi/Koha/issues/447)
  * Päätös: Yhteisöön tiketti. Tutkitaan, onko toteutettavissa ja mahdollisesti tarjotaan muutosta itse.
* [Tietueen perustiedot -näytön Jatkaa julkaisua -kohdan hakulinkistä erikoinen hakutulos #532](https://github.com/KohaSuomi/Koha/issues/532)
  * Päätös:  Tehdään muutos omaan xslt-tiedostoon, että linkkiin lisätään sulkeet hakusanan ympärille. Tiketin tekijä tekee myös tiketin yhteisön Bugzillaan ja ehdotetaan sinnekin samaa ratkaisua.
* [Kentät 386m ja 386a näkymään Perustiedot-näytöllä otsikolla "Tekijän ominaisuudet" #841](https://github.com/KohaSuomi/Koha/issues/841)
  * Päätös: Tehdään muutos omaan xslt-tiedostoon. Tiketin tekijä tekee tästä myös tiketin yhteisön Bugzillaan, niin tarjotaan samaa muutosta myös sinne. 
* [Kielifasetteja lisää #886](https://github.com/KohaSuomi/Koha/issues/886)
  * Päätös: Lisätään seuraavat fasetit:
     * Alkuteoksen kieli = 041h löytyy language-original -indeksistä
     * Tekstityksen kieli = 041j löytyy ln-subtitle -indeksistä
  * Fasettien järjestystä voi tarvittaessa säätää Hakukoneen asetukset -sivulta. 
* Mikä ero tiketeillä [Uuden osakohteen lisääminen: tietojen siirtyminen #704](https://github.com/KohaSuomi/Koha/issues/704) ja [Emotietueesta osakohteeseen siirtyvät tiedot ja RDA #705](https://github.com/KohaSuomi/Koha/issues/705)?
  * 704:n ongelma on, että tiedot menevät satunnaiseen järjestykseen.
  * 705:n ongelma on, että emosta ei siirry tarvittavat tiedot osakohteen 773-kenttiin.
  * Tiketti 705:n osalta lisäksi päätös, että tämä muutos tarvitaan edelleen. 

### 2. Seuraava kokous

Ke 22.5.2024 klo 13.

## Muistio 1/2024

Aika: Ma 29.1.2024 klo 14-15<br />
Läsnä: Anna Viitanen (Vaski), Markku Untinen (Helle), Kai Sormunen (Vaara), Timo Väisänen (Kirkes), Johanna Räisä (Koha-Suomi), Antti Heikkinen (OUTI), Mauri Aittaniemi (Lappi), Anneli Österman (Koha-Suomi), Heli Auranen (Lumme)

### 1. Käsiteltävät kehitysehdotukset

* [Kenttien muuttaminen hakukelpoisiksi linkeiksi tietueen Perustiedot-näytölle tai hakurajauksiksi Tarkka haku-näytölle #840](https://github.com/KohaSuomi/Koha/issues/840)
* [Sarjajulkaisun hakeminen fasetin kautta #251](https://github.com/KohaSuomi/Koha/issues/251)
* [Tiedonhakuun mukaan tietueen 651z-kenttä #281](https://github.com/KohaSuomi/Koha/issues/281)
* [Nidehaku: ei ole kokoelma -hakuehto ei toimi oikein #380](https://github.com/KohaSuomi/Koha/issues/380)
* [Translitteroimaton tekijätieto ei näy translitteroimattoman nimeketiedon perässä virkailijaliittymässä #410](https://github.com/KohaSuomi/Koha/issues/410)

Päätökset kirjattiin tiketteihin.

### 2. Seuraava kokous

To 7.3.2024 klo 12.15.
