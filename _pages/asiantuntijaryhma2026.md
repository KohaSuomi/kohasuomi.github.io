---
layout: single
permalink: /asiantuntijaryhma2026
hidden: true
header:
  overlay_color: '#5e616c'
  overlay_image: /assets/images/cropped-pexels-photo-113850.jpeg
toc: true
title: 'Koha-Suomen asiantuntijaryhmä 2026'
---

Tältä sivulta löydät Koha-Suomen asiantuntijaryhmän vuoden 2026 muistiot. Uusin muistio on aina ylimmäisenä.

Koha-Suomen asiantuntijaryhmään kuuluvat kokouksesta 8/2025 lähtien Leena Kinnunen (Lapin kirjasto), Noora Valkonen (OUTI-kirjastot), Päivi Knuutinen (Vaara-kirjastot), Hanna Ikonen (Lumme-kirjastot), Roosa Väisänen (Kyyti-kirjastot), Katri Sillgren (Helle-kirjastot), Susanna Sandell (Vaski-kirjastot), Janne Seppänen (Lastu-kirjastot) sekä Elina Uotila (Kirkes-kirjastot). Koha-Suomesta mukana on puheenjohtajana Ari Mäkiranta ja asiantuntijoina Anneli Österman, Emmi Takkinen ja Kodo Korkalo.

Asiantuntijaryhmän valitsee kerran vuodessa Koha-Suomen hallitus.

## Esityslista 2/2026

Aika: Torstai 12.2.2026 klo 13<br />
Läsnä:

### 1. Ajankohtaiset

### 2. Uutiskirje

### 3. Vahvalla tunnistautumisella asiakkaaksi rekisteröityminen

Edellisessä kokouksessa päätettiin selvittää varalta, onko kunnissa olemassa jo lomakkeita, joissa on käytössä vahva tunnistautuminen.

### 4. Paperikirjeiden määrä

Edellisessä kokouksessa päätettiin selvittää, kuinka paljon lähtee paperikirjeitä / kimppa.

## Muistio 1/2026

Aika: Torstai 15.1.2026 klo 13<br />
Läsnä: Elina Uotila (Kirkes-kirjastot), Kati Sillgren (Helle-kirjastot), Hanna Ikonen (Lumme-kirjastot), Noora Valkonen (OUTI-kirjastot), Susanna Sandell (Vaski-kirjastot), Leena Kinnunen (Lapin kirjasto), Päivi Knuutinen (Vaara-kirjastot), Janne Seppänen (Lastu-kirjastot), Ari Mäkiranta, Anneli Österman, Emmi Takkinen ja Johanna Räisä (Koha-Suomi)

### 1. Ajankohtaiset asiat

Koha-Suomessa odotellaan edelleen hankintalakimuutoksen käsittelyä.

Koha-Suomella on ständi [Kirjastopäivillä kesäkuussa ammattimessuilla](https://kirjastopaivat.fi/ammattimessut/). Löytyisikö ständille kirjastoista erilaisia käyttäjiä mukaan esittelemään ja kertomaan Kohasta?

### 2. Kohan toimintalokit ja niiden auditointi

Audit-lokit eli toimintalokit ovat järjestelmän tuottamia tietueita, jotka tallentavat käyttäjien ja järjestelmän suorittamia merkittäviä toimenpiteitä. Audit-lokien seuranta on tärkeää tietoturvan, virhetilanteiden selvittämisen ja lainsäädännön, kuten GDPR:n, noudattamisen kannalta.

Toimintalokit tallentavat tiedot tärkeistä tapahtumista, kuten käyttäjien kirjautumisista, tietojen muutoksista ja järjestelmän asetusten päivityksistä. Lokitietojen seuranta auttaa:

* Havaitsemaan luvattoman käytön
* Selvittämään virhetilanteita
* Täyttämään lakisääteiset vaatimukset (esim. GDPR)

Tarkemmin tietoja [Toimintalokien seuranta -wikissä](https://github.com/KohaSuomi/Koha/wiki/Toimitalokien-seuranta)

Johanna Räisä esittelee asiaa ja tämä on lähinnä tiedoksi asiantuntijaryhmälle, mutta voimme keskustella tarkemmin mitä asioita seurataan.

**Pääkäyttäjäryhmään pohdittavaksi**: Riittääkö, että aktiivisessa action_logs-taulussa säilytetään 2 vuotta, vai onko tarvetta pidemmälle ajalle?

### 3. Tiekartta

Käytiin läpi edellinen tiekartta ja päivitettiin tilanne.

Tiekartta tammikuu 2026: [Tiekartta2026tammi.xlsx](https://github.com/user-attachments/files/24642984/Tiekartta2026tammi.xlsx)

Selvitettävä kimpoissa seuraavaan kokoukseen: 
* Minkälaisia vahvaa tunnistautumista tukevia lomakkeita kunnissa on jo käytössä? Pystyisikö niitä hyödyntämään?
* Kuinka paljon lähtee paperikirjeitä/kimppa?

### 4. Käsiteltävät kehitysehdotukset

* [Lainaus-välilehdelle huomautus ettei tyhjä asiakashaku ole mahdollista #2075](https://github.com/KohaSuomi/Koha/issues/2075)
  * Päätös: Toteutetaan johdonmukaisuuden vuoksi
* [OKM-raportointityökaluun mahdollisuus määritellä tietty nidetyyppi tilastoinnista pois #2097](https://github.com/KohaSuomi/Koha/issues/2097)
  * Päätös: Toteutetaan liitännäiseen uusi asetus, jolla saa määritettyä pois suljettavat nidetyypit (items.itype).
* [Huoltajalta poistuu huollettavan laskusta aiheutunut lainauskielto, kun hän palauttaa omia lainojaan #2118](https://github.com/KohaSuomi/Koha/issues/2118)
  * Siirretään seuraavan kokoukseen, mihin mennessä kimpoissa pohditaan, miten edetään.
  * Teknisesti vaihtoehdot ovat:
    * muutetaan rajoitteen tyypiksi manual, jolloin se ei poistu AutoRemoveOverduesRestrictions-järjestelmäasetuksen toiminnolla. Tämä tarkoittaa, että rajoite pitää poistaa käsin.
    * luovutaan ominaisuudesta, jossa huoltajalle voi lisätä rajoitteen laskutuksen yhteydessä.

### 4. Muut asiat

Keskusteltiin, kuinka tärkeää on [huolehtia toimista, jos virkailijatyöasema](https://koha-suomi.fi/dokumentaatio/ty%C3%B6asemavarkaus/) varastetaan.

### 5. Seuraava kokous

To 12.2.2026 klo 13-15
