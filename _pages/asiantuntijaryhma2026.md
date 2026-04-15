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

## Esityslista 4/2026

Aika: Torstai 23.4.2026 klo 13 <br />
Läsnä:

### 1. Ajankohtaiset

[KohaCon2026-ilmoittautuminen](https://kohacon26.bibliothek.kit.edu/registration/) on avautunut. KohaCon pidetään tänä vuonna Saksassa Karlsruhessa.

### 2. Kansalliskirjaston suositukset vaatimusmäärittelyjen laatimiseen kirjastojärjestelmämuutoksissa

Käsiteltäväksi asiantuntijakokouksessa: [Kansalliskirjaston suositukset vaatimusmäärittelyjen laatimiseen kirjastojärjestelmämuutoksissa julkaistu](https://www.kiwi.fi/spaces/kuvailuyhteistyo/pages/543064557/Kansalliskirjaston+suositukset+vaatimusm%C3%A4%C3%A4rittelyjen+laatimiseen+kirjastoj%C3%A4rjestelm%C3%A4muutoksissa)

### 3. Koha-seminaarin ohjelma

Koha-seminaari pidetään Oulussa 17.-18.9.2026 ja sinne tarvittaisiin ohjelmaa.

### Käsiteltävät kehitysehdotukset

* [Vastaanotettavien kuljetusten listaukseen hyllypaikka näkyviin #2231](https://github.com/KohaSuomi/Koha/issues/2231)
* [Käyttöoikeuksia voi asettaa vain tietyille asiakastyypeille #2237](https://github.com/KohaSuomi/Koha/issues/2237)
* [cancellation_reason-sarake mukaan varausten vanhenemisajoon #2238](https://github.com/KohaSuomi/Koha/issues/2238)
* [Automaattisten tilinavausten auditointi + repeat lock -esto #111](https://github.com/KohaSuomi/koha-suomi-utility/issues/111)
  * Tiketti on yksityisessä tietovarannossa, joten se ei avaudu kaikille.
  * Tiketin aihe: Automaattisen käyttäjätunnusten hallinnan tietoturvaparannukset



### Muut asiat
### Seuraava kokous

## Muistio 3/2026

Aika: Torstai 19.3.2026 klo 13<br />
Läsnä: Leena Kinnunen (Lapin kirjasto), Erika Miettinen (Kirkes-kirjastot), Hanna Ikonen (Lumme-kirjastot), Janne Seppänen (Lastu-kirjastot), Roosa Väisänen (Kyyti-kirjastot), Päivi Knuutinen (Vaara-kirjastot), Kati Sillgren (Helle-kirjastot), Noora Valkonen (OUTI-kirjastot), Susanna Sandell (Vaski-kirjastot), Emmi Takkinen, Ari Mäkiranta ja Anneli Österman (Koha-Suomi Oy)

### 1. Ajankohtaiset

Versionvaihto on ihan käsillä eli muutosten valmistelu aloitetaan su 22.3.2026 klo 19, jolloin Kohat laitetaan alas. Tämän jälkeen ei toimi mikään palvelu, joka tarvitsee toimiakseen yhteyden Kohaan, esim. automaatit, omatoimet, Finna, erilaiset integraatiot.

### 2. Käsiteltävät kehitysehdotukset

* [Kaukolainapyynnöt: Tulokset automaattisesti esille sijaintikirjaston mukaan #2170](https://github.com/KohaSuomi/Koha/issues/2170)
  * **Päätös**: Ei toteuteta, koska kliksuttelutarve siirtyisi vain kimppoihin/kuntiin, joissa on keskitetty kaukopalvelu. Eli keskitetyissä kaukopalveluissa pitäisi sitten poistaa automaattisesti valituksi tullut kirjastotieto ja tehdä haku.
* [Asiakkaan viestiasetuksiin Ei ilmoitusta-toiminto #337](https://github.com/KohaSuomi/Koha/issues/337)
  * Palautetaan asiantuntijaryhmään ehdotuksella "ei toteuteta"
  * **Päätös**: Ei toteuteta, koska aika ajanut ohi ja tarpeet muuttuneet. Jos jollakin kimpalla on tarve "Tuloste"-viestivaihtoehdolle, niin siitä voisi tehdä erillisen tiketin suoraan yhteisöön.

### 3. Muut asiat

#### 3.1 Hyllyvaraussovellus

Vaski olisi kiinnostunut mahdollisuudesta kehittää erillinen hyllyvaraussovellus, mikäli Koha-Suomella ei ole suurempia suunnitelmia hyllyvarauslistan kehittämiseksi. Ajatuksena on hakea hankkeelle ulkopuolista rahoitusta.

Idea ja tarve on siis seuraavanlainen:

Selvitetään mahdollisuutta kehittää hyllyvaraus-sovellus, jossa käyttäjä mm:
- saa omalle kirjastolleen kohdennetun listan
- pystyy suodattamaan ja järjestelemään listaa haluamallaan tavalla
- näkee nimenomaan niiden niteiden tiedot, jotka ovat hänen kirjastossaan hyllyssä
- voi merkitä varauksia kerätyksi (varaus muuttuisi processing/transferred-tilaan)

**Päätös**: Vaski tutkii ja testaa Varausjono-raporttia, vastaako se nykyään enemmän tarpeita ja toimiiko se paremmin kuin aikaisemmin. Sen jälkeen tutkitaan, voiko sitä kehittämään esim. tuon kerätyksi merkitsemisen osalta. Hyllyvarausten haun työläysongelma koskee lähinnä isompia kirjastoja, joissa on paljon varauksia.

#### 3.2 Kansalliskirjaston suositukset vaatimusmäärittelyjen laatimiseen kirjastojärjestelmämuutoksissa

Tiedoksi, tutustuttavaksi ja käsiteltäväksi seuraavassa asiantuntijakokouksessa: [Kansalliskirjaston suositukset vaatimusmäärittelyjen laatimiseen kirjastojärjestelmämuutoksissa julkaistu](https://www.kiwi.fi/spaces/kuvailuyhteistyo/pages/543064557/Kansalliskirjaston+suositukset+vaatimusm%C3%A4%C3%A4rittelyjen+laatimiseen+kirjastoj%C3%A4rjestelm%C3%A4muutoksissa)

### 4. Seuraava kokous

To 23.4.2026 klo 13

## Muistio 2/2026

Aika: Torstai 12.2.2026 klo 13<br />
Läsnä: Piia Semenoff (OUTI-kirjastot), Hanna Ikonen (Lumme-kirjastot), Päivi Knuutinen (Vaara-kirjastot), Kati Sillgren (Helle-kirjastot), Janne Seppänen (Lastu-kirjastot), Elina Uotila (Kirkes-kirjastot), Susanna Sandell (Vaski-kirjastot), Leena Kinnunen (Lapin kirjasto), Roosa Väisänen (Kyyti-kirjastot), Anneli Österman ja Kodo Korkalo (Koha-Suomi) ja Noora Valkonen OUTIn signum-kohdassa.

### 1. Ajankohtaiset

Ei ajankohtaisia asioita.

### 2. Uutiskirje

Vuonna 2025 julkaistiin Koha-kirjastojen yhteinen uutiskirje kaksi kertaa. Koontivastuussa olivat Lastu ja Lumme. Vuonna 2024 uutiskirjeitä julkaistiin neljä kertaa ja koontivastuissa olivat Vaski, Lappi, OUTI ja Vaara. Koontivastuussa eivät ole vielä olleet: Kyyti, Kirkes ja Helle

* Uutiskirje 1/2026: Huhtikuun loppu eli 29.4.2026: Kirkes
* Uutiskirje 2/2026: Lokakuun loppu eli 30.10.2026: Kyyti

### 3. Vahvalla tunnistautumisella asiakkaaksi rekisteröityminen

Vahvalla tunnistautumisella asiakkaaksi rekisteröityminen on toiveissa saada toimimaan Finnan kautta, koska se on asiakkaille tuttu ympäristö ja kaikilla kimpoilla on se jo käytössä. Edellisessä kokouksessa päätettiin kuitenkin selvittää varalta, onko kunnissa olemassa jo lomakkeita, joissa on käytössä vahva tunnistautuminen. Tehdään koonti valmiista lomakkeista.

* Helle: Sipoossa  Oma asiointi https://asiointi.sipoo.fi/public/fi
* Lumme: Pieksämäki Docuware (Suomi.fi-rajapinta), Savonlinna epalvelulomake, jota pystyy muokkaamaan tarpeen mukaan
* Lapin kirjasto: Rovaniemellä olemassa n. 30 erilaista lomaketta
* Kirkes: Asiointi.jarvenpaa.fi Digiexpress-alusta, Keravalla Microsoft dynamics ja Mäntsälässä Visma Sign
* Vaara: Joensuulla erilaisia lomakkeita
* Kyyti: Kotka palautelomakkeella Suomi.fi-tunnistautuminen, Pyhtäällä pari elomaketta, Kouvolassa Webprobol-lomakkeelle on mahdollista tunnistautua Suomi.fi-tunnistautumisella, mutta rajapinta ei ole REST-rajapinta vielä.
* Vaski: Turulla on Tunnistamo, jossa on Suomi.fi-tunnistautuminen mahdollista. Myös muita kaikenlaisia hakemuksia voi tehdä (esim. venepaikkoja)
* OUTI: Oululla olisi vahvan tunnistautumisen lomakkeita, esim. tonttihaku. Kempeleen kunnan kotisivuilta ja sieltä löytyi Muksunetti. Muhoksella ja Kempeleessä varhaiskasvatuksessa hoitoaikojen ja poissaolojen ilmoittamiseen käytetään Edlevo-palvelua. Pudasjärvellä mm. Kuntalaisaloitteen tekeminen vaatii tunnistautumisen ja varhaiskasvatushakemuksen tekeminen. Tyrnävällä kunta on ottamassa käyttöön Visma Signin sähköisiä allekirjoituksia varten ja palvelussa on mahdollista tehdä myös lomakkeita, jotka allekirjoitetaan vahvalla tunnistautumisella tehdyllä sähköisellä allekirjoituksella.
* Lastu: Lahdella Webprobol, Heinolassa ollut ePalvelu-lomake (Aurora-aikaan robotti)

### 4. Paperikirjeiden määrä

Edellisessä kokouksessa päätettiin selvittää, kuinka paljon lähtee paperikirjeitä / kimppa.

* Vaara: 11 000 / vuosi
* Lumme: 11 000 / vuosi
* Vaski: 22 600 / vuosi
* Lappi: 7600 / vuosi
* Kirkes: 5000 / vuosi
* Kyyti: 4500 / vuosi
* Helle: 2300 / vuosi
* Lastu: 2700 / vuosi
* OUTI: 10 500 / vuosi
* Siili: 1405 / vuosi

### 5. Käsiteltävät kehitysehdotukset

* [Huoltajalta poistuu huollettavan laskusta aiheutunut lainauskielto, kun hän palauttaa omia lainojaan #2118](https://github.com/KohaSuomi/Koha/issues/2118)
  * Siirretty edellisestä kokouksesta, jotta kimpoissa ehditään miettimään, miten edetään.
  * Teknisesti vaihtoehdot ovat:
    * muutetaan rajoitteen tyypiksi manual, jolloin se ei poistu AutoRemoveOverduesRestrictions-järjestelmäasetuksen toiminnolla. Tämä tarkoittaa, että rajoite pitää poistaa käsin.
    * luovutaan ominaisuudesta, jossa huoltajalle voi lisätä rajoitteen laskutuksen yhteydessä.
  * **Päätös**: Luovutaan ominaisuudesta, jossa huoltajalle voi lisätä rajoitteen laskutuksen yhteydessä. Aikataulu: Pudotetaan versionvaihdon yhteydessä
* [Tee kaukolainapyyntö -lomakkeelle valmis arvo Kaukolaina: (Kaukolaina kaksoispiste välilyönti) kenttään Nimeke: #2146](https://github.com/KohaSuomi/Koha/issues/2146)
  * Ei vaadi toimenpiteitä asiantuntijaryhmältä, koska ongelma ratkennut lisäämällä kaukolaina-sana FA-pohjan 245$b-kenttään oletuksena.
* [Kaukopalvelu: ILLRequestsTabs-asetus ei ota huomioon ILL_STATUS_ALIAS-auktorisoituja arvoja #2152](https://github.com/KohaSuomi/Koha/issues/2152)
  * **Päätös**: Toteutus yhteisön kautta. Katsotaan tarkempi toteutus ja aikataulu Koha-Suomen viikkopalaverissa.
* [Laina- ja maksusäännöille kopiointimahdollisuus #2155](https://github.com/KohaSuomi/Koha/issues/2155)
  * **Päätös**: Toteutus yhteisön kautta itse lisäämällä Toiminnot-sarakkeeseen Kopioi-nappi.

### 6. Muut asiat

[Vanhat väliaikaisten rajoitteiden viestit tulevat näkyviin uuden rajoitteen yhteydessä #2130](https://github.com/KohaSuomi/Koha/issues/2130)
* Miten kannattaisi ajastaa vanhojen rajotteiden poistaminen? Päivittäin, kun ne  ovat vanhentuneet?
* Tallentuuko rajoituksen lisääminen action_logsille? Pääkäyttäjillä voi olla olla tarve tarkistaa, onko asiakkaalla joskus ollut rajoite.
  * Jos tieto tallentuu, niin voidaan poistaa yhteisön skriptillä päivittäin.
  * Jos ei tallennu, voidaan kirjoittaa oma skripti, joka kirjaa action_logsille tiedon poistosta (mukaan tieto, mikä rajoite ollut kyseessä ja rajoitteen voimassaoloaika, rajoitteen lisääjän id).

[OUTI signum-ongelman kanssa toimiminen](https://github.com/KohaSuomi/Koha/issues/1939)
* Lyötyisikö Lapset ja nuoret hyllypaikkojen kanssa toimimisesta asiantuntijaryhmästä yhteinen näkemys?
  * Keskusteltiin aiheesta ja todettiin, että täysin yhteneväisen näkemyksen löytäminen voi olla hankalaa mm. erilaisten kirjastotilojen vuoksi sekä nykyisten hyllypaikkojen moninaisuuden vuoksi.
  * Asiaa voidaan pitää mietinnässä, mutta ei tehdä tässä vaiheessa suosituksia.

[Sotu-siilon siivous](https://github.com/KohaSuomi/Koha/issues/1689)
* Vaskissa paljastui jokin aika sitten, että Sotuteekkiin on tallennettu jonkin verran hetuja, joissa on + -merkki (todennäköisesti miinusmerkin sijaan). Osa viivakoodinlukijoistamme ympäri Vaskia on lukenut henkilöllisyystunnuksen viivakoodin siten, että välimerkiksi on tullut virheellisesti  +. Kirjastokorttia tehdessä on luettu henkilöllisyystodistuksen viivakoodi ja tallennettu siten virheellinen hetu. Kaikki Sotuteekissä olevat hetut, joissa on + -merkki, ovat virheellisiä. Toiveissa siis siivousajo.
* Asiantuntijaryhmän kokous: Siivousajoa varten on olemassa skripti. Kodo ajaa skriptin läpi poistamatta vielä henkilötunnuksia ja toimittaa kimppoihin SQL-raportin, jolla kimpoissa voidaan tarkistaa, mihin asiakkaisiin poistoajo vaikuttaisi. Tarkistuksen jälkeen voidaan ajaa varsinaiset poistoajot.

### 7. Seuraava kokous

To 19.3.2026 klo 13

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
