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

## Viikko 4

Aika: 21.1.2025 klo 9.15<br />
Läsnä: Pirkko-Liisa Lauhikari, Katariina Pohto, Piia Semenoff (OUTI), Iina Niemi (Vaski), Leena Kinnunen ja Pia Kusmin (Lappi), Kati Sillgren (Helle),  Anneli Österman ja Emmi Takkinen (Koha-Suomi)

**Yhteiset**
* [Viikon 4 päivitys](https://github.com/KohaSuomi/Koha/discussions/1630)
  * [OKM-tilastojen korjaukset](https://github.com/KohaSuomi/Koha/discussions/1628) - uudelleenajot käynnissä, Emmi tiedottaa edistymisestä Matrixissa.
* Kuvailupohjista kannattaa poistaa oletusarvot nidetyyppi-kentästä 952y.
  * Kysely, jolla saa etsittyä kuvailupohjat, joissa oletusarvo on asetettuna: ```select tagfield,tagsubfield,frameworkcode,defaultvalue from marc_subfield_structure where defaultvalue !="" and tagfield='952' and tagsubfield='y';```
* [Tiketti 302](https://github.com/KohaSuomi/Koha/issues/302) eli huoltajasuhde valmiiksi valituksi. Onko tälle tarvetta monessa kimpassa, viedäänkö asiantuntijaryhmään päätettäväksi, plugarisoidaanko?
  * Ominaisuudelle oli kiinnostusta, joten viedään asiantuntijaryhmään.
* Uusi raportteja (tai uudehkoja, ennen mainitsemattomia)
  * [Kuljetettavat varaukset, joita ei ole käsitelty Kohassa](https://koha-suomi.fi/dokumentaatio/raporttikirjasto/#kuljetettavat-varaukset-joita-ei-ole-k%C3%A4sitelty-kohassa)

Pohjoisesta etelään

**OUTI**
* Normaalia tukitöitä. Kohan ohje suomeksi päivitystä.

**Vaski**
* Ollaan kokeiltu koodia, jolla voi laittaa tietuenäytölle automaattisuodatuksen kirjautumisyksikköön (sijainti- tai kotikirjasto). Tässä vielä ongelmia joita tutkitaan.

**Lappi**
* Normaalia ylläpitoa ja Koha-ohjeen päivitystä.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-4) - [Palaa sivun alkuun](/paakayttajat2025)

## Viikko 3

Aika: 14.1.2025 klo 9.15<br />
Läsnä: Leena Kinnunen ja Pia Kusmin (Lappi), Anneli Österman ja Pasi Kallinen (Koha-Suomi), Pirkko-Liisa Lauhikari ja Piia Semenoff (OUTI), Kati Sillgren (Helle), Hanna Ikonen (Lumme), Tuomas Kunttu (Kyyti), Annika Helastila ja Elina Uotila (Kirkes), Auli Rantasalo (Vaara)

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
* Tietueen Niteet-välilehden lainassa olevan niteen uusintamäärä-tieto on aiheuttanut epäselvyyttä. Arvon on oletettu olevan niteen kaikkien lainojen uusintamäärä. Kentän nimi on suomeksi Uusintoja, ruotsiksi Aktuella omlån, englanniksi Current renewals. Tiketti suomenkielisen kenttänimen muutosehdotuksesta [Saisiko Tietueen Niteet -välilehden Uusintoja-kenttänimeen muutoksen](https://github.com/KohaSuomi/Koha-translations/issues/62)
* Nidehaku-hakutuloksessa näkyy niteen lainamäärä, uusintamäärää ei. Tiketti uusintamäärän näkymisestä [Saisiko Nidehaku-toiminnon hakutulokseen niteen lainojen uusintamäärät](https://github.com/KohaSuomi/Koha/issues/1617)

**Lumme**
* Tehtiin kehitysehdotus tarratulostukseen: tarratulostuksessa olisi hyvä näkyä numerointi myös tulostukseen tuotujen viivakoodien puolella. Lumpeissa on monia eri tarratulostuspohjia, niin tämä helpottaisi tarroja tulostavien työtä. Ehdotuksesta tehty tiketti.
* Tietueissa esiintynyt säännöllisesti virhe 500 -virhettä, koska niteissä on ollut joku päivämääränä 0000-00-00 tai väärä nidetyyppi. Ongelmaa selvitellään.
* Lyngsoen kirjakaappi antaa lainaan toiselle asiakkaalle varatun teoksen, mutta jättää varauksen varauksen tehneen asiakkaiden tietoihin odottaa-tilaan. Tästä asiakkaalle sitten kertyy maksuja, kun varausta ei ole noudettavana ja se vanhenee. Ongelma johtuu SIP-yhteydestä, koska siinä ei käsitellä ollenkaan varaustilaa. Ongelmasta tehty tiketti.

**Kyyti**
* Ilmeni ongelma, että virkailijat eivät voineet muuttaa asiakkaitten asiakastyyppiä [#1598](https://github.com/KohaSuomi/Koha/issues/1598)

**Kirkes**
* Järvenpäässä ollaan ottamassa käyttöön Canonin kirjastotulostusta. Ei toimi vielä, mutta päivitetään integraatiolistaus sitten, kun toimii. 

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
