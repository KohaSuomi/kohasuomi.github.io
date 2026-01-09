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

## Viikko 3

Aika: Ti 12.1.2026 klo 9.15<br />
Läsnä:

**Yhteiset**
* [Tammikuun huoltokatko 14.1.2026](https://github.com/KohaSuomi/Koha/discussions/2121)

Pohjoisesta etelään

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
