---
layout: single
permalink: /paakayttajat2025
header:
  overlay_color: '#5e616c'
  overlay_image: /assets/images/cropped-pexels-photo-113850.jpeg
toc: true
title: 'Koha-Suomen pääkäyttäjäryhmän muistiot 2025'
---

Koha-Suomen pääkäyttäjäryhmä kokoontuu kerran viikossa. Ylimmäisenä on aina uusin muistio.

## Viikko 3

Aika: 14.1.2025 klo 9.15<br />
Läsnä: Leena Kinnunen ja Pia Kusmin (Lappi), Anneli Österman ja Pasi Kallinen (Koha-Suomi), Pirkko-Liisa Lauhikari ja Piia Semenoff (OUTI), Kati Sillgren (Helle)

**Yhteiset**
* LockExpiredDelay-järjestelmäasetukseen kaikilla 0 tai tyhjä siltä varalta, että aletaan ajamaan cleanup_database-cronia säännöllisesti.
* [Viikon 3 päivitys](https://github.com/KohaSuomi/Koha/discussions/1610)
* [Asiantuntijaryhmän kuulumiset](https://koha-suomi.fi/asiantuntijaryhma2025#muistio-12025)
* Muistutus deadlinesta: [Kohan ohje suomeksi -ohjeen päivitys](https://github.com/KohaSuomi/Koha/issues/1488) tammikuun loppuun mennessä.
* [TrackLastPatronActivityTriggers-asetukseen](https://github.com/KohaSuomi/Koha/issues/1606) uusi vaihtoehto ehdotettavaksi yhteisöön?
* [Hakutulosnäytön ei saatavana -termit](https://github.com/KohaSuomi/Koha-translations/issues/58#issuecomment-2589168299)
* Uusia raportteja:
  * [OKM-tilastojen mukainen hankintaraportti, joka listaa hankitut tietueet](https://koha-suomi.fi/dokumentaatio/raporttikirjasto/#okm-liit%C3%A4nn%C3%A4isen-mukainen-hankintaportti-joka-listaa-tietueet-jotka-on-hankittu-tietyll%C3%A4-aikav%C3%A4lill%C3%A4-tietyss%C3%A4-kirjastossa)
  * [Tietueet, joiden 008-kenttä ei ole 40 merkkiä pitkä](https://koha-suomi.fi/dokumentaatio/raporttikirjasto/#tietueet-joissa-008n-pituus-ei-ole-40-merkki%C3%A4)
  * [Tietueiden haku kiinteämittaisen kentän pituuden mukaan](https://koha-suomi.fi/dokumentaatio/raporttikirjasto/#tietueiden-haku-kiinte%C3%A4mittaisen-kent%C3%A4n-pituuden-mukaan)
    * Huom! Tämän käyttäminen voi olla vähän "kinkkistä" ja vaatii hoksaamista, miten raportti toimii ja miten merkkimäärät lasketaan raportin merkkimäärä-sarakkeeseen.

Etelästä pohjoiseen

**Lappi**
* Lopetettujen kirjastopistiden teettämiä töitä. Ongelmia tuli niteiden erämuokkauksessa. Vika korjaantunut päivityksessä.
* Koha-ohjeen päivitystä.
* Normaalia ylläpitoa.

**OUTI**
* Oulun yhdestä kirjastosta on tullut palautetta, että versiopäivityksen jälkeen heillä on tullut tapauksia, kun virkailija alkaa palauttamaan aineistoa, kun Kohassa on ehtinyt tulla timeout, tästä huolimatta Koha näyttäisi, että palautus olisi onnistunut. Tässä vaiheessa ei tule kuulemma kirjautumisikkunaa Kohaan. Virkailija tekee oletuksen, että laina oli palautunut, vaikka todellisuudessa näin ei ole tapahtunut. Vastaavaa tilannetta testattu Koha-tuessa, mutta ongelmaa ei ole saatu toistettua. Koha antaa aina ensin kirjautumisikkunan, jonka jälkeen Koha avautuu tyhjälle palautussivulle, eikä missään vaiheessa näy, että lainaa olisi palautettu. Kirjastoa on ohjeistettu tilanteisiin, kun Kohaa ei ole käytetty vähään aikaan. Pyydetty myös yksityiskohtainen kuvaus palautusprosessista, kun ongelma tulee seuraavan kerran eteen ja myös näytön kuva, jossa timeoutin jälkeen palautettu nide näkyy Palautus-sivulla palautettuna.
* Kuusamon kirjastosta tuli kyselyä, mistä voisi johtua raporttiliitännäisen vuoden 2024 tulevat erot koko vuoden lainatilastojen ja kuukausittain kerättyjen lainatilastojen välillä. Kuusamon pääkirjaston vuositilasto antaa 1551 isomman lainatilaston kuin kuukausittain kerätyt lainaluvut. Kuusamon kirjastoauton vuositilasto antaa taas 1575 lainaa pienemmän tilaston.
* Saimme asiakkaalta Finna-kehitysehdotuksen, että verkkokirjastossa voisi varata usean teoksen yhtäaikaa eli niitä voisi tiedonhaun tuloksista siirtää ns. koriin ja yhdellä kertaa varata kaikki korissa olevat teokset.
  * Piia tekee kehitysehdotuksen GitHubiin.
 
**Helle**
* Tietueen Niteet-välilehden lainassa olevan niteen uusintamäärä-tieto on aiheuttanut epäselvyyttä. Arvon on oletettu olevan niteen kaikkien lainojen uusintamäärä. Kentän nimi suomeksi Uusintoja, ruotsiksi Aktuella omlån, englanniksi Current renewals. Tiketti suomenkielisen kenttänimen muutosehdotuksesta [Saisiko Tietueen Niteet -välilehden Uusintoja-kenttänimeen muutoksen](https://github.com/KohaSuomi/Koha-translations/issues/62)
* Nidehaku-hakutuloksessa näkyy niteen lainamäärä, uusintamäärää ei. Tiketti uusintamäärän näkymisestä (Saisiko Nidehaku-toiminnon hakutulokseen niteen lainojen uusintamäärät)[https://github.com/KohaSuomi/Koha/issues/1617]

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-3) - [Palaa sivun alkuun](/paakayttajat2025)

## Viikko 2

Aika: 7.1.2025 klo 9.15<br />
Läsnä: Leena Kinnunen, Pia Kusmin (Lappi), Katariina Pohto ja Pirkko-Liisa Lauhikari (OUTI), Hanna Ikonen (Lumme), Kati Sillgren (Helle), Anneli Österman ja Lari Strand (Koha-Suomi), Reetta Pihlaja (Siilinjärvi), Auli Rantasalo ja Hanna Hyttinen (Vaara)

**Yhteiset**
* [Viikon 2 päivitys](https://github.com/KohaSuomi/Koha/discussions/1595)
* [Tammikuun huoltotiedote](https://github.com/KohaSuomi/Koha/discussions/1594)

**Lappi**
* Normaalia ylläpitoa.

**OUTI**
* Julkisoikeudellisten maksujen vanhentamisajo tehtiin 3.1.2025 aamusta, koska ajon ajastus 1.1. oli ollut väärin OUTIssa.
* 7.1.2025 tuli voimaan uudet käyttösäännöt:
  * Noutamattoman varauksen maksu nousi 1 e -> 2 e.
  * Lainauskiellon maksuraja nousi 12 e -> 15 e.
  * Kaukolainamaksu nousi 1 e -> 2 e + mahdolliset lähettäjäkirjaston maksut. Maksua ei ole määritelty Kohaan.
* 7.1. aamulla hyllyvarauksia oli reilut 4500, joka on OUTIn ennätys. :)

**Lumme**
* Normaalia ylläpitoa.

**Helle**
* Maksukorotuksia vuodenvaihteessa: noutamaton varaus, lainan kertyvä päiväkohtainen myöhästymismaksu. Lisäksi lainauskiellon maksuraja nostettu, samoin lainakohtaisen myöhästymismaksun enimmäismäärä.

**Siilinjärvi**
* Ei mainittavaa
* Kyseltiin onko Helle saanut palautetta takautuvasti nousseista myöhästymismaksuista. Yriteään Siilissä tiedottaa asiasta kovasti ennen 1.2.2025.

**Vaara**
* Pääkäyttäjävaje tammikuun ajan, muuten ei mainittavaa



Pohjoisesta etelään

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-2) - [Palaa sivun alkuun](/paakayttajat2025)
