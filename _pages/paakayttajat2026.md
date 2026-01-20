---
layout: single
permalink: /paakayttajat2026
header:
  overlay_color: '#5e616c'
  overlay_image: /assets/images/cropped-pexels-photo-113850.jpeg
toc: true
title: 'Koha-Suomen pääkäyttäjäryhmän muistiot 2026'
---

Koha-Suomen pääkäyttäjäryhmä kokoontuu kerran viikossa. Ylimmäisenä on aina uusin muistio.

## Viikko 4

Aika: Ti 20.1.2026 klo 9.15<br />
Läsnä: Anneli Österman ja Kodo Korkalo (Koha-Suomi), Päivi Knuutinen, Auli Rantasalo, Hanna Hyttinen (Vaara)

**Yhteiset**
* [Uuden delete_bibliographic_records-oikeuden asettaminen käyttäjille](https://github.com/KohaSuomi/Koha-25x/issues/195)
  * Käykää kaikki kommentoimassa, miten haluatte oikeuden omassa kimpassa.
* Versionvaihto
  * [Käykää kaikki tekemässä sorting rule -sääntö](https://github.com/KohaSuomi/Koha-25x/issues/18)
* [Käykää merkkaamassa, koska teidän kimppaan haluatte, että tehdään 0000-00-00-korjausajo tuotannossa](https://github.com/KohaSuomi/Koha/issues/1957)

Etelästä pohjoiseen.

**Vaara**
* Perjantaina tuli Joensuun johtajalle tieto yhdestä Vaara-kirjastosta, että heidän sähköpostiinsa oli tullut Paytraililta viesti maksusta 11,50 euroa. Tätä ihmeteltiin, kunnes katsoin Paytrailin maksutaulukosta kyseisen summan kohdalta, mistä maksusta on kysymys. Osoittautui, että nykyään seutukirjaston asiakkaana oleva henkilö oli maksanut mainitun summan eikä asiakkaan tiedoissa ollut sähköpostiosoitetta ollenkaan. Ryhdyin tutkimaan lokitietoja ja sieltä selvisi, että asiakas oli ollut toisen Vaara-kirjaston kotipalveluasiakas aikaisemmin ja sen vuoksi asiakkaan tiedoissa oli ko. kirjaston sähköpostiosoite. Ihmettelin asiaa Paytrailille, joka vastasi, että "selvittää tarkemmin asiointipalvelun teknisentuen kanssa" eli käytännössä Finna-tuen kanssa. Sieltä selvisi, että Finna käyttää ensisijaisesti omaan asiakasrekisteriinsä tallennettua sähköpostiosoitetta. Tätähän me emme pysty mitenkään näkemään asiakkaan tiedoista Kohassa. Pyysin Finna-tukea poistamaan asiakkaan sähköpostiosoitteen, koska hänellä ei Kohassa ole mitään sähköpostiosoitetta.
Tämä Finnan oma sähköpostikenttä aiheuttaa kyllä ongelmia.

## Viikko 3

Aika: Ti 13.1.2026 klo 9.15<br />
Läsnä: Anneli Österman, Lari Strand ja Emmi Takkinen (Koha-Suomi), Leena Kinnunen, Pia Kusmin ja Maria Joona (Lappi), Janne Seppänen ja Lauri Hänninen (Lastu), Tuomas Kunttu ja Roosa Väisänen (Kyyti), Päivi Knuutinen, Auli Rantasalo, Irina Halminen, Hanna Hyttinen (Vaara), Katariina Pohto, Piia Semenoff ja Pirkko-Liisa Lauhikari (OUTI), Iina Niemi (Vaski), Hanna Ikonen (Lumme), Kati Sillgren (Helle), Reetta Pihlaja (Siilinjärvi)

**Yhteiset**
* [Tammikuun huoltokatko 14.1.2026](https://github.com/KohaSuomi/Koha/discussions/2121)
* Signumiin luokka ja pääsana - aikataulutusta?
  * Saa tehdä: Lastu, Siili, Vaara ja Kyyti
  * Tarkistetaan tilanne muiden osalta yllä olevien jälkeen
* [Mahdollisia ongelmia](https://github.com/KohaSuomi/Koha-25x/wiki/Mahdollisia-ongelmia) -listaus

Pohjoisesta etelään

**Lappi**
* Tarkistettiin Koha-Suomi - nimen oikea muoto : Koha-Suomi.
* Sodankylän remontti alkamassa maaliskuussa. 
* Signum-muutoksiin liittyen korjattu laskutuspohjia

**Lastu**
* Lyngsoen automaatin toimintaa testattu nextia vasten, kaikki perustoiminnot toimivat oikein. Jatketaan tiketeissä olevien testailuja.
* Uusi järjestelmäasetus SIP2AddOpacMessagesToScreenMessage toimii ja SIP-sanoman AF-kentässä välittyy asiakkaalle lisätty verkkokirjastossa näkyvä viesti. AF-kentän alussa on kuitenkin paljon turhaa, jota kenties on mahdollista suodattaa pois viestistä regexin avulla SIP-palvelimen päässä:
```
AFGreetings from Koha. Huomautus verkkokirjastossa Messages for you: 31.12.2024: Asiakasviesti poistettu tietokannan anonymisoinnissa
```
**Kyyti**
* On alettu edistää SMS Sender ID:n rekisteröintiä ja käyttöönottoa
https://www.traficom.fi/fi/ajankohtaista/organisaatioiden-nimissa-lahetettavia-huijausviesteja-torjutaan-uusilla-keinoilla
* Kouvolassa laskutettu aineisto ei enää aiheuta lainauskieltoa. Tähän päädyttiin kaupunginlakimiehen lausunnon jälkeen. Laskutetut niteet myös poistetaan lainasta ja kirjastojärjestelmästä, kun lasku lähtee.

**Vaara**
* tilastoja ja testausta sekä normaalia ylläpitoa

**OUTI**
* 12.1.2026 ajettu Oulun aineistojen kotikirjastomuutos Oulun keskustakirjasto Saareen, koska pääkirjaston remontin ajan kotikirjastona oli Ruskon kirjavarasto. Ajossa muutettiin kotikirjasto 705 699 niteelle (https://github.com/KohaSuomi/Koha/issues/2114). Varasto- ja lehtiaineistojen kotikirjastomuutokset Koha-tuessa tehdään itse.

**Vaski**
* Vaskissa yritetään keksiä miten saisimme pakotettua kaikille asiakkaille PIN-koodin vaihdon, jotta pääsisimme tietoturvan kannalta riskialttiilta 1234-tyyppisistä salasanoista eroon. Pohdittavana on, miten pakottaa salansan vaihto ja miten informoida tästä asiakkaita.

**Lumme**
* Celia- ja signum-muutosten jatkotyöstöä.
* Alustavasti Mikkelin pääkirjastoon on tulossa LVIS-remontti vuonna 2027 ja kirjasto muuttaa tilapäisiin tiloihin muutamaksi vuodeksi.

**Helle**
* Webkaken API-tunnus poistettu.
* Piilotettu CSS:llä Kaukolaina-toiminnon Kauolainapyynnöt-sivulta Haku-laatikko. (Haun käyttö jumittanut Kohan ainakin OUTI-kimpassa.)

**Siilinjärvi**
* Ei mainittavaa

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2026#viikko-2) - [Palaa sivun alkuun](/paakayttajat2026)

## Viikko 2

Aika: **Keskiviikkona** 7.1.2026 klo 9.15<br />
Läsnä: Anneli Österman, Pasi Kallinen, Johanna Räisä (Koha-Suomi), Erika Miettinen (Kirkes), Anni Mäki-Mantila (Vaski), Katariina Pohto ja Piia Semenoff (OUTI), Leena Kinnunen ja Maria Joona (Lappi), Kati Sillgren (Helle), Janne Seppänen ja Lauri Hänninen (Lastu)

**Yhteiset**
* OKM-tilastot, onko ongelmia?
  * Ei havaittu ainakaan vielä ongelmia. Jos ilmenee vielä, niin selvitellään niitä sitten, kun Emmi palailee lomilta.
* LinkMobilylta tullut tieto, että he ohjeistavat, kuinka pitää toimia lähettäjänimen luvittamisessa. Älkää tehkö sitä ennen mitään. Lakimuutos tulee voimaan 4.5.2026.
  * DNA, Telia ja Arena: kannattaa kysyä operaattorilta ohjeistuksia


Etelästä pohjoiseen

**Vaski**
* Ei erityistä raportoitavaa, mutta suomi.fi-viestit otetaan käyttöön tänään kirjepostin osalta.

**Kirkes**
 * Ei erityistä raportoitavaa. Elina lomalla tämän viikon ja Erika lomalla 12.-25.1.

**OUTI**
* Kotikirjastomuutos Oulun aineistolle tehdään ensi viikolla.
* Perjantaina 2.1.2026 Koha jumitteli kovasti. Syylliseksi paikallistettiin kaukolainamoduulin suodatuskenttä. Pikaisella testauksella ongelmaa ei vaikuttanut olevan enää Nextillä. Kenttä piilotettiin CSS:llä:
```
/* Kaukolainoista Haku-kentän piilotus */
body#illrequests.ill div#ill-requests_filter.dataTables_filter { display: none; }
```
**Lappi**
* Noora Suvanto lopettanut Lapin pääkäyttäjänä vuoden loppuun Pellon kunnan säästösyistä. Pääkäyttäjähaku aukeaa lähiaikoina.
* Normaalia ylläpitoa, nextin asetusten tallennusta.

**Lastu**
* Suljetun Launeen kirjaston kokoelman erämuutos toimi tuotannossa oikein, eli ongelma koski vain testiä.
* Muuten normaalia ylläpitoa

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2026#viikko-2) - [Palaa sivun alkuun](/paakayttajat2026)
