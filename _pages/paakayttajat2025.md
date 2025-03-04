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

## Viikko 10

Aika: 4.3.2025<br />
Läsnä: Johanna Räisä (Koha-Suomi), Pirkko-Liisa Lauhikari ja Piia Semenoff (OUTI), Päivi Knuutinen ja Irina Halminen (Vaara), Leena Kinnunen (Lappi), Janne Seppänen ja Lauri Hänninen (Lastu), Kati Sillgren (Helle)

**Yhteiset**
* Viikon 10 päivitys
  * 260-kentässä järjestys ei ole vielä oikein, pitää tarkistaa?
* Uusia raportteja kirjastossa:
  * [Uusien asiakkaiden määrä aikavälillä jaoteltuna ikäryhmittäin](https://koha-suomi.fi/dokumentaatio/raporttikirjasto/#uusien-asiakkaiden-m%C3%A4%C3%A4r%C3%A4-aikav%C3%A4lill%C3%A4-jaoteltuna-ik%C3%A4ryhmiin). Liittyy [tikettiin #1706](https://github.com/KohaSuomi/Koha/issues/1706).
  * TäTin tallennettuihin raportteihin lisätty raportti, joka hakee tietueet, joiden nimeke päättyy "; :". Sen kaveriksi lisätty Kuvailu-osioon MARC-muokkauspohja, jolla saa muokattua raportin antamat tietueet sellaisiksi, että nimekkeestä tiputetaan pois kaksoispiste ja jäljelle kentän loppuun jää puolipiste. Liittyy [tikettiin #1699](https://github.com/KohaSuomi/Koha/issues/1699). Vastaavan korjauksen voi tehdä myös tarvittaessa paikalliskantoihin.
  * [Käsiteltyjen hyllyvarausten määrä](https://koha-suomi.fi/dokumentaatio/raporttikirjasto/#k%C3%A4siteltyjen-hyllyvarausten-m%C3%A4%C3%A4r%C3%A4) sisältä kaksi eri raporttia, joista toinen laskee omaan kirjastoon jääneitä käsiteltyjä hyllyvarauksia ja toinen kuljetukseen lähteneitä hyllyvarauksia. Huomioi, että jälkimmäinen toimii oikein vain, jos kimpassa on päällä HoldsAutoFill-järjestelmäasetus. Liittyy [tikettiin #1680](https://github.com/KohaSuomi/Koha/issues/1680).
* Kohan tietokantaskeema lisätty [Miten tehdä SQL-raportteja](https://koha-suomi.fi/dokumentaatio/sqlkoulu/) -sivulle taulukkona. Koha-Suomen omat taulut on merkitty boldilla ja niiden rakenne on kuvattu omilla välilehdillään. Yhteisön taulujen rakenne löytyy [yhteisön skeemasivulta](https://schema.koha-community.org/).
  
**Lappi**
* Hoidettu yhtä konetta lukuunottamatta, että Mikroväylä-ovikoneet lähettää 63 viestin AO kentässä kirjaston toimipistekoodin.
* Alettu selvittää käyttöoikeuksien mallipohjien luontia
* Väistöissä oleviin kirjastoihin liittyen ylläpitotöitä
* Muuten rauhallista, pohjoisen talvilomaviikko

**OUTI**
* OUTIssa on kuvailupohjia, joista puuttuu tietoa tai kenttien järjestys on muuttunut esim. OUTIssa kuvailijan säätämät osakenttäjärjestykset ovat kadonneet useista pohjista. Sen vuoksi haimme Tätistä MARC-kuvailupohjan paikalliskantaan, mutta tuonti ei onnistunut suoraan, sillä kaikki ne kentät puuttuivat pohjista, joissa oli auktorisoitujen arvojen valikko kiinni (mm. 336a ja 336b). Ongelma johtui siitä, että Tätin pohjassa oli määritetty noihin tiettyihin kenttiin sellaisia auktorisoituja arvoja joita ei ole paikalliskannassa. Anneli haki kuvailupohjan Tätistä open office -muodossa ja muokkasi manuaalisesti tiedostosta pois auktorisoidut arvot, joita OUTIssa ei ole ja vei sitten muokatun pohjan OUTIin onnistuneesti.
* Oulun Finvoice-laskuja luodessa oli laskuttaja saanut virheilmoituksen: ”Tapahtui virhe: Korjaa asiakkastiedot: 564A*******, 564A6******” Kyseessä oli kaksi yhteisöasiakasta, joiden lainoilta laskuttaja oli poistanut "Laskuta"-täpät. Näiltä yhteisöasiakkailta puuttuu etunimet, joten siinä mielessä ilmoitus muodostui oikein. Koska laskuttaja sai pelkän virheilmoituksen eikä lainkaan tietoa siitä, että muutoin laskutus on onnistunut, niin laskutusajo näytti hänestä päättyneen virheeseen. Voisiko virheilmoitusta muokata tai lisätä toisen ilmoituksen, jossa kerrottaisiin, että laskutusajo on onnistunut?
  * Piia tekee tästä oman tiketin. (Tiketti tehty kokouksen jälkeen: https://github.com/KohaSuomi/koha-plugin-overdue-tool/issues/21)
 * Oulun koulukirjastoissa on ongelmana, että heillä Kohan itsepalvelulainaus-palautus -toiminto menee useita kertoja päivässä pois päältä. Näytölle tulee ilmoitus: ”Pyydetty sivu ei ole saatavilla, Virhe 403. Lomakkeen lähetys epäonnistui (väärä CSRF token). Päivitä sivu yrittääksesi uudelleen.” Tämän jälkeen, kun yrittävät kirjautua ohjelmaan uudelleen sisään, tulee ilmoitus ”404 Forbidden”.  Tämän jälkeen ohjelmiston saa käyntiin ainoastaan käynnistämällä pääte uudestaan. Muutamaan koulukirjastoon on vaihdettu myös uudet päätteet, mutta ongelma on jatkunut myös niissä. Tietääksemme itsepalvelupäätteissä ei käytetä Kohan virkailijaliittymää, mutta tähän vielä odotetaan varmistusta.

**Vaara**
* Tehty tiketti viime viikolla mainitun lähettämättömien palautuskehotusten lähettämisestä omatoimiasiakkaille
* Kesälahden lainausautomaattiin vaihdettu ip-osoite ja sen käyttöönotto-ongelmasta (tunnelointi?) tehty tukipyyntö

**Lastu**
* Seudun kirjastossa ollut ongelmia aineiston vastaanotossa, vastaavia ongelmia ei muualla. Tiedustellaan tarkempi kuvaus ongelmasta ja miten vastaanotto on tehty ongelmatapauksissa, ja tehdään tiketti mikäli ongelmat jatkuvat

**Helle**
* Otettu käyttöön Nidetyypin automaattinen generointi -toiminto.
* Tullut vastaan tilanne, jossa tietueen perustiedoissa Porvoon niteet eivät lataudu/tule näkyviin. Koha ilmoittanut: Jotain meni pieleen taulua ladattaessa. 500 internal server error. Ilmoituksen aiheutti yhdessä Porvoon niteessä oleva Aineistotyyppi-arvo Nidetyyppi-kentässä. 
Muissa kimpoissa ollut muutama vastaava tapaus nidettä tallentaessa. Tiketti (Uuden niteen tallennus antaa Internal server error)[https://github.com/KohaSuomi/Koha/issues/1667]


## Viikko 9

Aika: 25.2.2025<br />
Läsnä: Janne Seppänen (Lastu), Päivi Knuutinen ja Auli Rantasalo (Vaara), Hanna Ikonen (Lumme), Leena Kinnunen, Pia Kusmin, Maria Joona (Lappi), Pirkko-Liisa Lauhikari, Katariina Pohto ja Piia Semenoff (OUTI), Susanna Sandell (Vaski), Anneli Österman ja Emmi Takkinen (Koha-Suomi), Annika Helastila ja Elina Uotila (Kirkes), Kati Sillgren (Helle), Roosa Väisänen (Kyyti)

**Yhteiset**
* [Viikon 9 päivitys](https://github.com/KohaSuomi/Koha/discussions/1709)
  * Anneli lupasi tarkistaa, tuleeko kaikkiin maksutyyppeihin nyt kirjastotieto. Tulos: ei tule ajastetun ajon kautta lisättyihin noutamattoman varauksen maksuihin. [Siitä nyt tiketti avattu](https://github.com/KohaSuomi/Koha/issues/1713).

Etelästä pohjoiseen

**Vaski** 
* Selvitetään, voisiko Koulukirjastojen niteille voisi asettaa jo tilausvaiheessa varaamisen estävä damaged-tila. Näin sellaisiin tietueisiin, joissa on vain koulukirjastojen niteitä ei voisi tulla varauksia tilausvaiheessa. Vaski tekee kehitysehdotuksen.
* Keskustelu "hutilainoista" ja asiakkaan mahdollisesta vaatimuksesta korjata virheellinen lainatieto. Vielä ei ole tällaisia tapauksia tullut. Siivous vaatisi todennäköisesti muutoksia useampaan tauluun.
   
**Lastu**
* Henkilökunnalta tullut toive, että varauksen voisi poistaa varatun niteen palauttamisesta syntyvässä popparissa. Nykyisellään se on piilotettu, koska noutamattoman varauksen maksu syntyy, mikäli palautusta ei tehdä palautussivulla, koska maksun käsittelyssä on sivukohtainen asetus. Maksun käsittely oikein vaatisi uuden järjestelmäasetuksen.
* Toinen toive on, että varausten huomautuksia voisi muokata varauksen teon jälkeen. Tästä on olemassa [tiketti yhteisössä](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=26476). Tulevassa varausten erämuokkaustyökalussa huomautusten muokkaaminen on mahdollista.
* Muistuteltiin maaliskuun uutiskirjeestä, jonka deadline on 21.3. Linkki pohjaan Elementin pääkäyttäjäkanavalla.

**Vaara**
* Minulle tultiin ihmettelemään tekijäfasetissa näkyviä nimiä, jotka olivat suorassa järjestyksessä tai ensin oli alkuperäisen tekijän nimi ja hänen perässään suomentajan nimi. Tein asiasta tiketin https://github.com/KohaSuomi/Koha/issues/1707 jonka Anneli siirsi indeksointityöryhmän käsiteltäväksi.
* Sitten paljastui oma moka eli kun marraskuun lopulla siirryttiin Toveri-ovilaitteista Mikroväylän laitteisiin, täytyi tehdä uusia asiakastyyppejä omatoimikäyttäjiä varten. Näille ei muistettu tehdä overdue-asetuksia eli näille asiakkaille ei ole mennyt palautuskehotuksia. Tein raporttipyynnön näistä lainoista ja pyritään saamaan ajo, jolla nämä puuttuvat muistutukset saataisiin lähtemään asiakkaille. https://github.com/KohaSuomi/Koha/issues/1710

**Lumme**
* Varkaudessa virkailijoiden koneilla ollut häröilyä perjantaisen tietohallinnon päivityksen jälkeen. Kaikki virkailijat eivät pääse kirjautumaan kaikille koneille ja joissakin Kohan toiminnallisuuksissa osalle virkailijoista tulee Kohassa palvelinongelmaviestiä. Asiaa selvitellään.
* Kuvailijoilta tullut kommenttia valutuksen hitaudesta. Syynä mahdolliset lomat, valutuksen hitaus, koska paljon kimppoja. Jäädään seuraamaan tilannetta.

**Lappi**
* Otettu käyttöön asetus AllowItemsOnHoldCheckoutSIP-asetus.
* Selvitetty kirjastojen tarvetta lähettää yhteisöasiakkaille palautuskehotuksia.
* Viime viikolla otettu käyttöön tiettyjen nidetyyppien rajaus tietyille kirjastoille. Väärin käytetyt nidetyypit. Joitain kyselyjä aiheesta, sekä virheilmoitus nidetietojen näkymisessä sekä asiakkaan varausnäkymässä Kohassa että Finnassa.

**OUTI**
* Finnassa lainaushistorian lataus ei onnistu tiedostoon tai suosikkeihin, jos historiassa on paljon teoksia. Testeissä alle 400:n lainahistorian lataus onnistuu, mutta yli 500 ei enää onnistu. Finnan viimeisimpään versioon on tullut toiminnallisuus, että lainahistorian pystyy lataamaan osissa. Ohjelma kyllä yrittää ladata historiaa osissa 1/2, mutta latauspainike palaa aina alkutilanteeseen "Lataa osa 1/2".  OUTIsta laitetaan ongelmasta Finna-tukeen.
* Oulussa huomattiin, että Mikro-Väylän omatoimilaitteissa ei toiminut asiakkaalle asetettu omatoimen käyttökielto. Syyksi selvisi, että Mikro-Väylän omatoimilaitteille ei ole määritelty toimipistekoodia (institution ID:tä), jonka ovikoneet lähettää Kohalle 63-viestin AO-kentässä. Eli Koha ei tiennyt asettaa estoa ko. omatoimikoneelle. Toimipistekoodi lisätty ovikoneelle, jonka jälkeen käyttökielto on toiminut.
* Pohdittu vaihtoehtoja, mitä signum-muutos aiheuttaa OUTIssa, jossa lasten ja nuorten aineistot ovat samalla hyllypaikalla ja osa kirjastoista ovat muokanneet signum-kentän hyllypaikkatietoa kirjastokohtaiseksi.

**Kirkes**
* Kadonneita osakohteita on metsästetty. Vaikuttaa siltä, että ne ovat poistuneet vahingossa.
* Tilausta tehdessä havaittu tietueen ilmestyvän monografian osakohteena, eikä monografiana. Pitänyt korjata jälkikäteen erikseen, jotta nimekkeeseen voi tehdä varauksia.

**Helle**
* Vaihdettu MaxSearchResultsItemsPerRecordStatusCheck-asetuksen arvoksi 200 (oli aiemmin 25). Vaikutus: tiedonhaun hakutuloksessa Saatavana-tieto kertoo oikein tietueen Saatavana-tilaisten niteiden määrän. Koskee tietueita, joilla on niteitä enintään 200.  
(Tiketti Hakutulosnäytöllä niteiden saatavuustiedot ovat harhaanjohtavia)[https://github.com/KohaSuomi/Koha-translations/issues/58#issuecomment-2659103199]

**Kyyti**
* Asiakaspalvelusta tuli palautetta, että Finnaan kaivattaisiin uutta välilehteä, jolta asiakas voisi tarkistaa oman maksuhistoriansa. Asiakaspalvelussa tulee välillä vastaan tilanteita, joissa asiakkaalle kerrotaan että hänellä on maksuja jotka täytyy maksaa ennen kuin lainaus taas onnistuu ja asiakas saattaa näissä tilanteissa väittää, että on jo maksanut kyseisen maksun. Tästä syystä ajateltiin, että olisi asiakkaille selkeämpää, jos he voisivat ennen asiakaspalveluun tulemista tarkistaa mitä maksuja ovat oikeasti maksaneet. Pääkäyttäjäkokouksessa idea ei saanut kannatusta, vaan koettiin, että asiakkaiden maksuhistoria on arkaluonteista tietoa, josta ei haluta muistuttaa asiakkaita.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-9) - [Palaa sivun alkuun](/paakayttajat2025)

## Viikko 8

Aika: 18.2.2025<br />
Läsnä: Anni Mäki-Mantila (Vaski), Päivi Knuutinen ja Auli Rantasalo (Vaara), Pirkko-Liisa Lauhikari, Katariina Pohto ja Piia Semenoff (OUTI), Kati Sillgren (Helle), Anneli Österman (Koha-Suomi), Reetta Pihlaja (Siilinjärvi), Annika Helastila ja Elina Uotila (Kirkes), Lauri Hänninen (Lastu), Leena Kinnunen, Pia Kusmin, Maria Joona (Lappi)


**Yhteiset**
* [Viikon 8 päivitys](https://github.com/KohaSuomi/Koha/discussions/1692)
* [Asiantuntijaryhmän muistio 2/2025](https://github.com/KohaSuomi/Koha/discussions/1684)
  * Signum-muutos etenee, aikataulutusta ja suunnittelua tulossa
* Uusi raportti: [Apuraportti](https://koha-suomi.fi/dokumentaatio/raporttikirjasto/#niteiden-er%C3%A4muokkaus-ty%C3%B6kalun-apuraportti), jolla voi hakea niteitä erämuokkausta varten. Raportti jättää ulkopuolelle lainassa olevat, kuljetuksessa olevat ja sellaiset, joilla on jokin notforloan-arvo. Raporttia voi käyttää esim. silloin kun pitää muuttaa jonkin kirjaston niteiden sijaintipiste kirjaston mennessä sulki tms. Raportti kysyy parametrinä kotikirjaston. Raporttia voi säätää eteenpäin tarvittaessa vastaamaan sen hetkistä tarvetta.
  * Palaverissa tullut hoksautus: _MaxItemsToProcessForBatchMod_-järjestelmäasetukseen voi laittaa luvuksi 10 000, jolloin niteiden erämuokkauksessa voi käsitellä kerralla 10 000 nidettä. Järjestelmäasetukseen _MaxItemsToDisplayForBatchMod_ kannattaa kuitenkin jättää luvuksi esim. 1000, koska nidetietojen hakeminen näytille on raskasta puuhaa ja jos yrittää noutaa näytille 10 000 niteen tiedot, voi haku päättyä virheeseen. Niteitä kuitenkin käsitellään aina _MaxItemsToProcessForBatchMod_-asetuksen mukaisesti, vaikka kaikkia ei näytetäkään liittymässä.

Pohjoisesta etelään

**Vaski**
* Tullut pariin otteeseen toive siitä, että Kohassa asiakkaiden sukunimi esitettäisiin isoilla kirjaimilla. Tarpeen taustalla ulkomaalaiset nimet, joista vaikea erottaa mihin etunimi loppuu ja sukunimi alkaa. Kohassa on järjestelmäasetus UppercaseSurnames, jonka päälle laittamalla sukunimi tallentuu tietokantaan isoin kirjaimin, mutta sen päälle laittaminen ei riittäisi vaan vanhojen asiakkaiden sukunimille tarvittaisiin muutosajo. Tällä hetkellä nimi-kentät eivät ole omia class-elementtejä ja css-muutos ei mahdollista sukunimen esitystavan muuttamista, mutta yhteisössä on asiaan liittyen tiketti. Sovittiin, että Vaski tekee kehitysehdotuksen Githubiin - josko voitaisiin saada yhteisön kautta muutos (jo ennen vuoden 2026 versiopäivitystä).
* Mikko tehnyt raportin hyllyvarausten määrien hakemiseksi, hyödyntää action_logissa viimeisimmästä versiopäivityksestä lähtien mukana ollutta diff-saraketta. Mikko lisää raportin [tikettiin](https://github.com/KohaSuomi/Koha/issues/1680).

**Vaara**
* Viime viikolla tuli tarve saada tietää hyllyvarausten määrä ja Anneli teki raportin, joka toimi mm. Outissa, mutta ei esim. Vaarassa. Erona oli se, että järjestelmäasetus HoldsAutoFill oli Vaarassa "Älä täytä"-muodossa, Outissa "Täytä" samoin kuin tähän liittyvä kuittien tulostusasetus. Laitoin Vaarassa asetuksen uuteen asentoon maanantaina (olin ensin varoittanut käyttäjiä, että toiminto muuttuu) ja kyllä se jostain syystä vaikuttaa raportin toimintaan eli nyt raportilla tulee Vaarassakin järkevän näköisiä lukuja.

**OUTI**
* Oulun kirjastojen Ceepos-ympäristö siirtyy 1.4.2025 Oulun Monetran käyttöympäristöön, missä myös kaupungin muiden hallintokuntien kassaympäristöt ovat. Kirjaston ympäristö on ollut tähän asti omanaan. Kassa- ja tuotetunnisteet muuttuvat. Vaatii uudet kassakohtaiset tuotemäppäykset Ceepos-liitännäiseen, uudet kassatunnisteet payment_type -auktorisoituun arvoon (voi ilmeisesti muokata käytössä olevia, jos joku ei mene rikki) ja kassatunnisteiden muutokset palvelimelle.
* Asiakaspalvelussa on tullut vastaan muutama tapaus, jossa asiakastiedot ovat kadonneet asiakkaiden siivousajon jälkeen. Esim. tapaus, kun asiakkaan kirjastokorttia oli käytetty vain silloin, kun hänelle oli lisätty kopiomaksuja ja kun asiakas oli maksanut niitä. Muuten asiakas ei ollut kirjastokorttiaan käyttänyt kirjastoasioinnissa. Kun siivousajo tehtiin, asiakkaalla ei ollut maksuja, joten hänen tili poistettiin siivousajossa.
* Asiakkaalta saatu palautetta, että Finnassa hakutuloksen oletusjärjestyksessä käytetty termi "Relevanssi" on liian vaikeaselkoinen. Voisiko sanan vaihtaa johonkin muuhun?
  * Päivi Vaarasta lupasi testata voiko sanan vaihtaa itse, jos ei voi, niin sovimme, että Piia tekee tiketin. Kokouksen jälkeinen tieto: Päivi testasi Vaaran testi-Finnassa ja sai termin vaihdettua Finnan hallintaliittymässä kielikäännöksissä kohdassa sort_relevance.
  * Vaihtoehtoja Relevanssille: Paras osuma, Parhaiten vastaava, Hakua vastaavin, Osuvuuden mukaan ja Osuvuus.
 
**Siilinjärvi**
* Ei mainittavaa.

**Kirkes**
* Ei ihmeitä. Edelleen mietitään eBookingille korvaajaa.

**Lastu**
* Otettiin toinenkin tabletti testikäyttöön hylläreihin ja kokoelman hoitoon.
* Tiketti bugikorjauksen tuonnista, kirjastokortin numerolla haku tarttuu myös syntymäaikoihin.
* Nidevarausta tehdessä niteiden haku-toiminto tarttuu myös virkailijan valitsemaan kirjastoon, eli Sallitut noutopaikat -valikon aktiiviseen valintaan. Tämä tarkoittaa käytännössä sitä, että virkailija ei voi suodattaa nidelistaa omalla kirjastollaan.

**Lappi**
* Posion väistöä varten muutettuu niteet ei-lainattava, ei-varattava -tilaan.
* Kemijärvellä oli etuileva varaus, syytä uuden varauksen nousemisesta varauslistan kärkeen ei selvinnyt.
* Muuten normaalia ylläpitoa. 

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-8) - [Palaa sivun alkuun](/paakayttajat2025)

## Viikko 7

Aika: 11.2.2025 klo 9.15<br />
Läsnä: Anneli Österman ja Emmi Takkinen (Koha-Suomi), Janne Seppänen ja Lauri Hänninen (Lastu), Päivi Knuutinen ja Auli Rantasalo (Vaara), Annika Helastila ja Elina Uotila (Kirkes), Leena Kinnunen, Maria Joona ja Pia Kusmin (Lappi), Kati Sillgren (Helle), Piia Semenoff (OUTI), Hanna Ikonen (Lumme), Tuomas Kunttu (Kyyti)

**Yhteiset asiat**
* [Hakutulosnäytön harhaanjohtavat termit](https://github.com/KohaSuomi/Koha-translations/issues/58)
  * ehdotettu, että saatavana-termiä ei muutettaisi ollenkaan, vaan muutettaisiin vain _ei saatavilla_-otsikko esim. muotoon _Tarkista saatavuus_.
  * saatavana-otsikon alla olevat näyttäisivät olevan lainattavissa olevia.
  * ei saatavilla -otsikon alla taas on erilaisissa tiloissa (damaged, kuljetettavat, yms.) olevia niteitä.
* [Viikon 7 päivitys](https://github.com/KohaSuomi/Koha/discussions/1675)
* [Raporttitoive](https://github.com/KohaSuomi/Koha/issues/1671), onko muilla tarvetta tällaiselle tai jopa valmiina jotain tämän tyyppistä?
* [Maanantaina oli suunnittelematon käyttökatkos](https://github.com/KohaSuomi/Koha/discussions/1677)
* Vaskissa otettiin pois päältä [Varausjono-raportin luovat ajot](https://github.com/KohaSuomi/Koha/issues/1550) ja kokeiltiin, auttaisiko se siihen, että varaukset eivät jää kiinni väärässä järjestyksessä. Tällä hetkellä näyttäisi siltä, että se auttoi ongelmaan. Olisiko tarpeellista ottaa varausjono-ajot pois muissakin kimpoissa?
  * Päätös: Otetaan kaikista kimpoista cronit pois päältä ja tyhjennetään siihen liittyvät taulut. [Tiketti #1679](https://github.com/KohaSuomi/Koha/issues/1679)
* Aina välillä tulee asiakkailta suoria yhteydenottoja Koha-Suomeen heidän saamistaan kirjastoviesteistä (sähköposteja), koska ilmeisesti eivät ole tienneet kehen muuhunkaan olla yhteydessä. Pystyisittekö tarkistamaan ja tarvittaessa lisäämään viestipohjiin tarkempia kirjaston/kimpan yhteystietoja tai linkki, mistä yhteystiedot löytyvät?

Etelästä pohjoiseen

**Lastu**
* Tekstiviesteistä tullut viime aikoina tavallista enemmän palautetta, että noutoilmoitukset eivät olisi menneet perille asiakkaalle. Laitettu tiedustelua DNA:n suuntaan, sitä odotellessa toimitetaan asiakaspalveluun [tämä ohje](https://koha-suomi.fi/dokumentaatio/ongelmatilanteet/#tekstiviestit).
* Ainakin Lahdessa havaittiin eilisen katkon yhtedessä, että yhteydettömän tilan lainauksen ohjeessa oleva C:\Temp-kansio tyhjenee asiakaspalvelun koneella kun koneelta kirjautuu ulos. Muutetaan ohjeeseen, että kannattaa luoda uusi kansio C:n juureen.

**Vaara**
* Ysa/yso-konversio tehty Vaaraan ja virheraportit toimitettu kuvailijoille
* Kysymys viestien lähtöaikataulusta asiakkaalle, kun varaus on jäänyt kiinni. Kaikissa kimpoissa viestit lähtevät saman aikataulun mukaan vartin välein eli tasalta, vartin yli, puolelta jne. Jos varaus jää kiinni pari minuuttia ennen viesti lähtöaikaa, noutoilmoitus menee asiakkaalle ennen kuin varaus on ehtinyt noutohyllyyn.

**Kirkes**
* Telian tekstiviestipalvelussa on ollut toimitusongelmia. Asian selvittely siirretään Keravalta Järvenpäähän. Mahdollisesti vanhassa rajapinnassa ongelmia.
* Yhdessä kirjastossa on tullut vastaan yksittäinen tapaus, jossa varaus ei vanhentunut ajossa, vaikka noutoaika oli ylittynyt. Pikaisella tarkastelulla ei löytynyt mitään erikoista syytä, mutta palataan tähän jos näitä alkaa tulla lisää. 

**Lappi**
* Hoidettu rästitehtäviä, mm. ilmoituksiin liittyen.
* Työn alla Posion kirjaston väistöön sekä Rovaniemen pääkirjastoon paluuseen liittyvät tehtävät.
* Muuten rauhallista.

**Helle**
* Telian tekstiviestipalvelussa viestin toimitusongelmia (kuten Kirkes-kimpassa). [KIRKES: Tekstiviestin toimitus asiakkaalle ei ole onnistunut](https://github.com/KohaSuomi/Koha/issues/1673)
* YSA -> YSO -konversio valmistunut. [YSA YSO konversio kaikille kimpoille](https://github.com/KohaSuomi/Koha/issues/390)
* Vuoden 2023 lehtitilaukset suljettu. [Helle: vuoden 2023 kausijulkaisutilausten sulkeminen](https://github.com/KohaSuomi/Koha/issues/1678)

**OUTI**
* OUTIssa asiakkailta tullut jo muutaman kerran toive, että Finnassa voisi hakea aineistoa sivumäärän perusteella.
  * Piia tekee tiketin Finna-kehitysehdotuksiin.
* Raahen ja Pyhäjoen kirjastoille on tehty kellutus-kirjastoryhmä. Raahen kirjastojen ja Pyhäjoen kirjastojen välillä kelluu nyt kaikki aineisto molempiin suuntiin.
* Asiakkaalla oli useita varauksia samaan tietueeseen, joista yksi oli jo vanhentunut. Asiakkaan varaukset lainattiin siten, että vanhentuneen varauksen lainaaminen täytti toisen varauksen, jossa oli jo nide odottamassa, jolloin noudettavana ollut nide meni Saatavana-tilaan ja virkailija sai popparin, että niteeseen/tietueeseen on toinen varaus toisaalla. Kun tämä nide lainattiin, niin se taas puolestaan täytti toisen noutoa odottavan niteen varauksen. Saatavana olevat kappaleet täyttivät lainoja reserve_id:n mukaisessa järjestyksessä eli vanhan varauksen lainaaminen irrotti niteet omista reserve-ID:stä. Edellisen kerran tämä on tapahtunut OUTIssa syyskuussa 2024.
  * Jatketaan OUTIssa vielä vähän tämän ihmettelyä/tutkimista
 
**Lumme**
* Normaalia ylläpitoa.

**Kyyti**
* Kouvola on siirtymässä tänä vuonna Timmiin ja rajapintaa Kohaan ollaan hyödyntämässä.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-7) - [Palaa sivun alkuun](/paakayttajat2025)

## Viikko 6

Aika: 4.2.2025 klo 9.15<br />
Läsnä: Anneli Österman ja Pasi Kallinen (Koha-Suomi), Leena Kinnunen, Pia Kusmin (Lappi), Susanna Sandell (Vaski), Pirkko-Liisa Lauhikari, Katariina Pohto ja Piia Semenoff (OUTI), Janne Seppänen ja Lauri Hänninen (Lastu), Hanna Ikonen (Lumme), Lotta Juvonen (Helle), Reetta Pihlaja (Siilinjärvi), Tuomas Kunttu (Kyyti), Auli Rantasalo ja Päivi Knuutinen (Vaara), Annika Helastila ja Elina Uotila (Kirkes)

**Yhteiset**
* [Viikon 6 päivitys](https://github.com/KohaSuomi/Koha/discussions/1663)
* Omatoimikirjastojen estojen asettaminen
  * käytönesto ajastetaan tulemaan voimaan yöllä
  * pääkäyttäjät tarkistavat aamulla, että rajoitus on mennyt päälle ja ilmoittaa, jos ei ole. Rajoite laitetaan sitten käsin päällle.
  * Ohje lisätty Koha-tietovarannon [Omatoimen käytöneston lisääminen](https://github.com/KohaSuomi/Koha/wiki/Omatoimen-k%C3%A4yt%C3%B6neston-lis%C3%A4%C3%A4minen) -wikiin
* Testeillä on nähtävissä yksi ratkaisu liittyen [kehitysehdotus-tikettiin #886](https://github.com/KohaSuomi/Koha/issues/886). Keskustellaan, voiko ratkaisua ottaa käyttöön.
  * Ongelmana on, että itse lisättyjen fasettien otsikot eivät käänny, koska ne kuvaukset ovat tietokannassa, eikä käännösmekanismi osaa "katsoa" sinne.
  * testillä olevassa ehdotuksessa jokaiselle kielelle luodaan oma indeksi, joille sitten määritetään CSS:llä käännökset ja piilotetaan muut kuin käyttöliittymän kielivalinnan mukaiset kieliversiot.
  * ongelmana on myös se, että kielikoodeja ei saa käännettyä kuin liittämällä fasettiin auktorisoidun arvon, jolloin niille saa
    selkokielisen kuvauksen yhdellä kielellä (tai sitten auktorisoidun arvon kuvaukseen lisää kaikki versiot, joka voi olla sekavaa)
  * Päätös: Keskusteltiin, tarviiko käännöksiä tehdä ja päätettiin kokeilla ensin ilman käännöksiä fasettien otsikoihin ja kielikoodeihin. Ei tehdä omia Koha-Suomi-spesifejä säätöjä vaan pyritään saamaan yhteisön kautta fasetit käänneettäviksi. Pohditaan asiaa uudelleen, jos aiheesta saadaan palauttetta käyttäjiltä. 
* [Koha-seminaarin ilmoittautuminen avattu](https://github.com/KohaSuomi/Koha/discussions/1665). Ohjelma on vielä vajaavainen, mutta täydennetään niin pian kuin mahdollista.
* [Kohan ohje suomeksi -päivitys](https://github.com/KohaSuomi/Koha/issues/1488)
* [Ratkaisu ehdotettu](https://github.com/orgs/KohaSuomi/projects/4/views/15) -tilaisia tikettejä paljon. Muistattehan sulkea itse avaamanne tiketit (tai siirtää toiseen tilaan, jos eivät vielä toimikaan oikein). :)

Pohjoisesta etelään

**Lappi**
* Posion kirjaston väistön suunnittelu alkamassa, samoin Rovaniemen kirjaston paluu pääkirjastoon
* Nidetyyppien rajausta Rovaniemen kirjastolle selvitetään, liittyy vain Rovaniemellä käytössä olevaan laina-/nidekohtaiseen maksuun
* Kohaan vaihdettu kimpan logo, alaosaan jäi musta palkki
* Muuten rauhallista

**Vaski**
* Siirtyminen Turun seudullisen tapahtumakalenterin käyttöön verkkokirjastossa (Linked Events) 
*	Suunnittelemme käsin lisätty-maksutyypin poistamista, jotta ei olisi houkutusta lisätä ALVillisia maksuja järjestelmään. Mitätöi maksutapahtuma-toiminto on nyt piilotettuna, mutta piilotuksen poistoa suunnitellaan.

**OUTI**
* Pudasjärven kirjasto on luopumassa Ceepos-kassan käytöstä.
  * Riittänee, että poistamme Kohasta Pudasjärven maksurajapintaan liittyvät määritykset ja tuotteiston sekä kehittäjät poistavat Koha-palvelimelta kassaan liittyvät määritykset.
  * Teemme tiketin, kun asia ajankohtainen.
* Oulussa on pari kertaa tullut tapaus, että tietue on mennyt vähän kuin rikki tilanteessa, kun tietueelle on lisätty uusi nide Perustiedot-näytöltä Uusi nide -toiminnolla. OUTIssa on käytössä automaattinen nidetyyppiliitännäinen.
  * Käyttäjä oli tallentanut niteelle tarvittavat tiedot ja tämän jälkeen hän oli joutunut klikkailemaan useamman kerran nidetyyppikentän kolmea pistettä ennen kuin ohjelma oli antanut oikean nidetyypin kenttään. Tämän jälkeen käyttäjä oli tallentanut tietueen, mutta tallennuksessa oli tapahtunut jotain kummallista (?).
  * Tämän jälkeen molempien tapausten tietueet antoivat Internal server error -ilmoitusta. Tapauksessa 1 tietueen niteitä pääsi muokkaamaan. Tapauksessa 2 näkyville ei tullut enää yhtään tietueen nidettä.
  * Tapauksessa 2 Finnassa tietueelle tuli ilmoitus: "Järjestelmä pois käytöstä. Kirjastojärjestelmä on juuri nyt pois käytöstä. Saatavuustiedot eivät ole juuri nyt käytettävissä…”
  * Kun tutkimme ongelmaa, niteille oli molemmissa tapauksissa tallentunut nidetyypiksi KIRJA eli aivan kuin sinne olisi tullut jostain aineistotyypin Koha-tunnus.
  * Tapaus 1 ongelma saatiin korjattua, kun nidetyyppi korjattiin oikeaksi niteen muokkaussivulla. Tapaus 2 saatiin korjattua niteiden erämuokkauksella.
  * Tehdään tiketti, jos tapauksia alkaa ilmeneen muillakin.https://github.com/KohaSuomi/Koha/issues/1667

**Lastu**
* Pohdittu miten varauksiin käytettäviä resursseja olisi mahdollista kehittää vähemmän työaikaa vieväksi Kohan avulla
* Muuten tavallista ylläpitoa

**Lumme**
* Tehty tietueiden erämuokkauksia YSO-muutosta ajatellen. Hommat jatkuu vielä.
* Raportoitu tapauksia, missä automaatti ei suostu lainaamaan asiakkaalle hyllystä napattua kirjaa silloin, kun kirjassa on hyllyvaraus. Kohan asetusten puolesta tämän pitäisi onnistua. Epäiltiin olisiko kyseessä sellainen nide, jossa on ollut varaus, se on palautettu automaatilla ja kirja on mennyt vahingossa hyllyyn. Kyseessä ei vaikuta olevan tällainen tapaus ja sitä tutkitaan edelleen.

**Siilinjärvi**
* Myöhästymismaksu muutettu 1.2.2025 alkaen 0,20 eurosta 0,30 euroon, muutos näyttäisi päivittyneen oikein. Asiakaspalautetta odotellaan.
* Siilinjärvellä päätetty jättää lapset eli alle 18-vuotiaat vanhentumisajon ulkopuolelle. Perusteluna uudelleenrekisteröitymisen vaikeus varsinkin ryhmäkäynneillä ja kannustus lukuharrastukseen. Vanhentuneet lapsiasiakkaat poistuvat sitten siirtyessään aikuisasiakkaiksi.
* Kuntasovelluksessa on ollut taas korjaus/päivitystarvetta.

**Kyyti**
* Esittelin eilen Kyyti-joryssa Annelin ajankohtaisdiasarjaa. Kiitos siitä.
* Kysyin tarkennuksia YSA-YSO-konversioon liittyvään valmisteluajoon 648, 650, 651, 655 -kenttien 9-osakenttien tyhjentämisestä. Kaikki 9-osakentät saa siis poistaa.

**Vaara**
* Ei mainittavaa

**Kirkes**
* Kehittäjä raportoinut viallisesti luetteloidusta tietueesta, jonka luetteloija korjannut.
* OKM-tilastoja tutkiessa huomattiin, että kaunon ja tiedon hankinnat eivät olleet raportilla oikein. Syypää oli väärä luokitusopas, jonka vaihtamisen jälkeen virheelliset cn_sort-kentät korjattiin ja tilastot ajettiin uusiksi. Tiketti [#1652](https://github.com/KohaSuomi/Koha/issues/1652)
  
[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-6) - [Palaa sivun alkuun](/paakayttajat2025)

## Viikko 5

Aika: 28.1.2025 klo 9.15<br />
Läsnä: Anneli Österman, Kodo Korkalo ja Lari Strand (Koha-Suomi), Leena Kinnunen, Maria Joona ja Pia Kusmin (Lappi), Anni Mäki-Mantila ja Susanna Sandell (Vaski), Hanna Ikonen (Lumme), Katariina Pohto, Piia Semenoff ja Pirkko-Liisa Lauhikari (OUTI), Reetta Pihlaja (Siilinjärvi), Annika Helastila ja Elina Uotila (Kirkes), Auli Rantasalo ja Päivi Knuutinen (Vaara), Janne Seppänen ja Lauri Hänninen (Lastu)

**Yhteiset**
* [Viikon 5 päivitys](https://github.com/KohaSuomi/Koha/discussions/1648)
* Finna-kehitysedotusten prosessin selkeyttäminen. [Nykyisen prosessin kuvaus](https://github.com/KohaSuomi/Finna-kehitysehdotukset/wiki)
  * Kuinka monta kertaa vuodessa tavataan Kansalliskirjasto. Ehdotus: 6 kk välein tai tarpeen mukaan (jos esim isompi kehitystyö meneillään). Aina ennen Kansalliskirjaston tapaamista tehdään Finna-tikettien priorisointi Koha-Suomen kesken.
  * Tikettien priorisointipalaverin ja Kansalliskirjaston palaverin seuraava vetovastuu sopimatta. Olisiko jatkossa kiertävä? Seuraava vetäjä ja ajankohta sovitaan edellisessä priorisointipalaverissa. Vetäjä kutsuu koolle ja valmistelee molemmat palaverit.
  * Pitääkö ohje päivittää kun saadaan nämä sovittua? Vai mihin dokumentoidaan?
  * Seuraava vetäjä alustavasti Helle, vahvistus ensi viikolla.
  * Seuraava priorisointipalaveri toukokuun alussa. (Ennen kesälomia)
* Raportit YSO-konversion valmistelua varten [Raporttikirjastossa](https://koha-suomi.fi/dokumentaatio/raporttikirjasto/#raportti-yso-konversiota-varten) ja [tiketissä 1621](https://github.com/KohaSuomi/Koha/issues/1621#issuecomment-2612351054)
* EDItX-virheraportointi sähköpostiin ei ole toiminut versionpäivityksen jälkeen. Nyt korjattu.

Etelästä pohjoiseen

**Lappi**
* Kausijulkaisutietue oli poistettu ja sen mukana tilaukset ja niteet. Tietue palautettiin, mutta tilauset jouduttiin tekemään uudelleen. Tietue myös ilmestyi järjestelmäasetuksiin huomautuksena: tietue sekä taulussa biblio ja deletedbiblioitems. 
* Muutoin rauhallista, lähinnä käyttäjätunnusten päivityksiä.

**Vaski**
* Tuotiin esille Finna-kehitysehdotus siitä, että Finnan palautelomakkeen mukana välittyisi asiakkaan id Kohassa mikäli asiakas on palautetta jättäessään kirjautunut verkkokirjastoon. Idea sai ajatuksen tasolla kannatusta, mutta vaatii vielä miettimistä onko ehdotuksessa jotakin tietoturvan kannalta ongelmallista. Susanna tekee tiketin ja kehittäjät kommentoivat siihen pohdinnan jälkeen onko ehdotus toteutuskelpoinen.
* Normaalia ylläpitoa, joitakin epäonnistuneita EDItX-sanomia tullut nyt tammikuussa kun virheilmoituksia ei lähtenyt sähköpostiin. Osan uudelleenkäsittely oli jo lopetettu, joten Vaski tekee niistä tukipyynnöt.

**Lumme**
* Valmistellaan tulevaa asiakasrekisterin siivousajoa. Pitää vielä päättää, mitä tehdään laskutettavien kanssa.
* Finnan omissa tiedoissa olisi hyvä saada suosikkilistat aakkosjärjestykseen. Asiasta on tehty tiketti.

**OUTI**
* OKM-korjausajon jälkeen Oulussa huomattiin, että mm. kokoelma -tilasto oli uudessa OKM-tilastossa noin 1500 nidettä pienempi kuin alkuvuonna otetussa. Hankinnoissa oli myös pientä eroavaisuutta edelliseen ajoon mm. tietokirjallisuus oli vähentynyt ja kaunokirjallisuus oli miltei samassa määrin enentynyt.
  * Koska poistojen tilasto oli pysynyt täsmälleen samana molemmissa OKM-ajoissa, niin on luultavaa, että OKM-ajojen välillä on tehty poistoja, jotka ovat vaikuttaneet vuoden 2024 kokoelman kokoon. Ajojen välillä tehdyt poistot tilastoituvat vuoden 2025 poistoihin.
  * Hankinnan lukujen erot voisivat johtua siitä, että hankinnassa olevan aineiston luokkia on muutettu tietokirjaluokista kaunoluokkiin, jolloin tilastot muuttuivat ”ristiin” ajojen välillä.
  * Emmiltä saimme varmistuksen, että yllä luetellut arvelut luultavasti pitävät paikkansa, sillä tilastoja ei ole mahdollista "jäädyttää" tiettyyn hetkeen, koska ne otetaan kokoelmien ja hankintojen osalta tauluista, joissa tilanne elää koko ajan. Poistot, luokkien vaihdot, muutokset notforloan-arvoon, aineistolajiin, kieleen, niteen sijaintiin jne. vaikuttavat siihen, että tilastojen määrät voivat heitellä sen mukaan milloin tilasto on otettu.
* Raahen kaupunginkirjasto siirtyy tämän kevään aikana Varaamosta Timmiin.

**Siilinjärvi**
* Ei mainittavaa

**Kirkes**
* Normaaleja tukitöitä ja muita kiireitä.

**Vaara**
* On havaittu mm. 9-luokkalaisten asiakkaiden kirjastokorttien häviämistä tietokannasta. Vai eivätkö ole käyttäneet kortteja 5 vuoteen?

**Lastu**
* Hyllyvarauksiin käytettävät tabletit saatu Lahteen, alettu kartoittamaan kannettavia kuittareita ja viivakoodinlukijoita
* Muuten tavallista ylläpitoa
  
[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-5) - [Palaa sivun alkuun](/paakayttajat2025)

## Viikko 4

Aika: 21.1.2025 klo 9.15<br />
Läsnä: Pirkko-Liisa Lauhikari, Katariina Pohto, Piia Semenoff (OUTI), Iina Niemi (Vaski), Leena Kinnunen ja Pia Kusmin (Lappi), Kati Sillgren (Helle),  Anneli Österman ja Emmi Takkinen (Koha-Suomi), Reetta Pihlaja (Siilinjärvi), Janne Seppänen ja Lauri Hänninen (Lastu), Annika Helastila ja Elina Uotila (Kirkes), Tuomas Kunttu ja Roosa Väisänen (Kyyti), Hanna Ikonen (Lumme), Auli Rantasalo (Vaara)

**Yhteiset**
* [Viikon 4 päivitys](https://github.com/KohaSuomi/Koha/discussions/1630)
  * [OKM-tilastojen korjaukset](https://github.com/KohaSuomi/Koha/discussions/1628) - uudelleenajot käynnissä, Emmi tiedottaa edistymisestä Matrixissa.
* Kuvailupohjista kannattaa poistaa oletusarvot nidetyyppi-kentästä 952y,jos ne eivät ole oikeita nidetyyppejä. Osalla siellä saattaa olla arvoja tyyliin KI tai KIRJA, joita ei löydy nidetyypeistä.
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

**Siilinjärvi**
* Tutkittu poistettavien asiakkuuksien listausta. Tulossa olisi iso siivous: lähdössä on 27 000 41 000:sta!
* Raportin antamat oletusnidetyypit poistettu kuvailupohjista.

**Lastu**
* Sip2SortBinMapping-asetusta testailtu Larin kanssa, syy toimimattomuudelle löytynyt rivivaihtojen käsittelystä. Alkuperäinen tiketti: https://github.com/KohaSuomi/Koha/issues/1559
* Nidehaun tuloksiin toivottu mukaan niteen edellisestä havaintoa sekä niteen huomautuskenttiä. Yhteisöstä löytyi näille tiketit, kommentoitu sinne:
  * https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=13965
  * https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=13823
 
**Kirkes**
* Kadonneet osakohteet pelastettu. <a href="https://github.com/KohaSuomi/Koha/issues/1612#issuecomment-2602226804">#1612</a>
* Viestipohjien päivittämistä
* Työntekijä teki haun "Hae tietokannasta" -hakukentän kautta lehdelle El Pais semanal 2024 ja tarkensi hakua faseteista "14 vrk lehti". Tuli 403 -virheilmoitus:
Programming error - op 'cud-login' must not start with 'cud-' for GET https://kirkes.koha-suomi.fi/intranet/catalogue/search.pl?idx=kw&q=el%20pais%202024&op=cud-login&sort_by=pubdate_dsc&count=50&limit=itype:14VRKLE (referer: https://kirkes.koha-suomi.fi/cgi-bin/koha/catalogue/search.pl). Vastaavaa virhettä ei kuitenkaan onnistuttu toistamaan.

**Lumme**
* Käyty kuvailupohjia lävitse ja yhtenäistetty pakollisia kenttiä. Poistettu myös kenttien oletusarvoja, jotta tietueisiin ei tulisi virhe 500 -ilmoitusta.
* Lehtien vastaanotossa tuli ilmi, että vastaanotossa valittu päivämäärä muuttuu tallennuksen jälkeen päivämäärään 30.11.1899. Asiasta tehty tiketti #1636.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-4) - [Palaa sivun alkuun](/paakayttajat2025)

## Viikko 3

Aika: 14.1.2025 klo 9.15<br />
Läsnä: Leena Kinnunen ja Pia Kusmin (Lappi), Anneli Österman ja Pasi Kallinen (Koha-Suomi), Pirkko-Liisa Lauhikari ja Piia Semenoff (OUTI), Kati Sillgren & Lotta Juvonen (Helle), Hanna Ikonen (Lumme), Tuomas Kunttu (Kyyti), Annika Helastila ja Elina Uotila (Kirkes), Auli Rantasalo (Vaara), Janne Seppänen (Lastu)

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
* Osakohteita kadonnut luetteloidusta teoksesta.

**Lastu**
* Raindance-integraatio otettu Lahdessa käyttöön onnistuneesti
* Asiakkaita ihmetyttänyt Finnan varausjonon sija 0. Tämä tarkoittaa, että varaus/nide on käsittelyssä. Selvitellään voiko tämän ilmaista Finnassa muulla tavoin.

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
