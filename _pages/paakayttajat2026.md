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

## Viikko 7

Aika: Ti 10.2.2026 klo 9.15<br />
Läsnä: Anneli Österman (Koha-Suomi)

**Yhteiset**
* [Viikon 7 päivitys](https://github.com/KohaSuomi/Koha/discussions/2162)
* [Helmikuun kuukausihuolto](https://github.com/KohaSuomi/Koha/discussions/2159)
* [Kuinka edetään preferred_name-ajon kanssa?](https://github.com/KohaSuomi/Koha-25x/issues/128)

Pohjoisesta etelään

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2026#viikko-7) - [Palaa sivun alkuun](/paakayttajat2026)

## Viikko 6

Aika: Ti 3.2.2026 klo 9.15<br />
Läsnä: Anneli Österman ja Lari Strand (Koha-Suomi), Leena Kinnunen, Maria Joona ja Pia Kusmin (Lappi), Päivi Knuutinen, Irina Halminen, Hanna Hyttinen (Vaara), Elina Uotila ja Erika Miettinen (Kirkes), Hanna Ikonen (Lumme), Katariina Pohto, Piia Semenoff ja Pirkko-Liisa Lauhikari (OUTI), Reetta Pihlaja (Siilinjärvi), Anni Mäki-Mantila (Vaski), Lotta Juvonen ja Kati Sillgren (Helle), Janne Seppänen ja Lauri Hänninen (Lastu)

**Yhteiset**
* Versionvaihto:
  * [Onko kaikilla preferred_name-kenttä näkyvissä Finnassa](https://github.com/KohaSuomi/Koha-25x/issues/160)? Voiko tiketin sulkea?
  * [Uusien käyttäjäoikeuksien create_public_lists ja use_public_lists lisääminen versiopäivityksessä #205](https://github.com/KohaSuomi/Koha-25x/issues/205)
  * [Varaushyllyjen varaamis- ja lukitustoimintojen intuitiivisuus #198](https://github.com/KohaSuomi/Koha-25x/issues/198) - Mielipiteitä?
  * [Testattava: 25711 Move ExpireReservesMaxPickUpDelayCharge to the circulation rules #166](https://github.com/KohaSuomi/Koha-25x/issues/166) - Helle, Kyyti, Lumme, puuttuu vielä kuittaus, että säännöt tehty ja toimivat tarkoituksenmukaiseksi. Lainasäännöt kopioidaan nexteiltä tuotantoon versionvaihdossa.
* Matrixin siivous: Onko pääkäyttäjien huoneessa mukana henkilöitä, jotka eivät ole (enää) pääkäyttäjiä? Voiko heidät poistaa?
  * Sovittiin, että kaikki kimpat tarkistavat sekä Matrixin jäsenet että superlibrarians-ryhmän Githubissa ja ilmoittavat Annelille poistettavat käyttäjät.
* [Kaukolainamoduulin testaaminen](https://github.com/KohaSuomi/Koha/issues/1703) -tiketti jo kiinni, koska käyttöönotto on jo käytännössä tehty?
  * Kyllä, suljetaan. Jatkossa uusista ehdotuksista ja ongelmista erilliset tiketit.

Etelästä pohjoiseen

**Lappi**
* Uutena pääkäyttäjänä aloittanut Mauri Aittaniemi Rovaniemeltä.
* Kaukopalvelumoduuli saatu testaukseen nextille
* Asiakkaalle muodostunut hyvitys maksutyypillä "liikamaksun hyvitys", ie. Overpayment refund.

**OUTI**
* Piia tekee kaukopalvelumoduulin kehitysehdotuksen Bugzillaan ja Githubbiin. Toiveena on, että kun kaukolaina lainataan, niin kaukolainatilauksen tilaksi päivittyy "Kaukolaina lainattu asiakkaalle". Samassa tiketissä  ehdotetaan myös kaukolainan palautuksessa vastaavaa tilauksen tilan päivittymistä.
* OUTIssa signumeiden korjausajo tehdään vasta versiopäivityksen jälkeen, kun kimpassa on saatu päätettyä, erotetaanko lasten ja nuorten aineisto toisistaan. Uusi signum-liitännäinen otetaan käyttöön versiopäivityksen yhteydessä.
* OUTIn kokoelmatyöryhmä pohtii, otettaisiinko uutuusaineistoille käyttöön lyhyempi laina-aika tietyksi ajaksi. Muutamissa kimpoissa tämä on käytössä. Kiitos taas vastauksista, joita on tullut, kun kysyttiin kimpoilta lyhyemmän laina-ajan käytänteistä ja kokemuksista.
* OUTIssa on muutamalla kunnilla koulukirjastojen kokoelmat kunnan pääkirjaston alla. Yhdestä kunnasta on kaipailtu apua OKM-tilastoihin ja koulukirjaston tilastojen erottamisesta kokonaistuloksista.

**Vaara**
* normaalia ylläpitoa
* herätettiin keskustelu virkailijan kirjautumiskirjastosta, olisiko se mahdollista saada valittavaksi joka kerta, ettei tapahdu lainojen ja palautusten rekisteröitymistä väärään kirjastoon

**Kirkes**
* Elina kerännyt jo listaa henkilöistä, jotka voi poistaa Matrixista, ja toimittaa sen Annelille.
* Elina lisännyt nextille Kirkes-kirjastojen laina- ja maksusääntöjä, enää Tuusulan kirjastoauto puuttuu.
* Kirkes-kirjastojen henkilökunnalta tulee aika ajoin pyyntöjä siitä, saisiko pitkien, Aurora-aikaisten, numeromuotoisten varaustunnusten noutokuitteihin välilyönnin. Tähän on vaihtoehtona maksullinen muutosajo, mutta välilyönnin voisi ehkä saada kuittiin myös Template Toolkitillä. Tutkitaan.
* Erika linkannut Matrixiin 30.1. pidetyn Suomi.fi-viestitukiklinikan materiaalit. Tilastoista:  https://kehittajille.suomi.fi/ajankohtaista/suomi-fi-palveluiden-raportit-jatkossa-vain-kirjautuneelle-kayttajalle ja esitysmateriaali: https://cdn.verkkopalvelu.suomi.fi/files/30.1.2026%20Suomi.fi-viestien%20tukiklinikka%20-%20Kirkes-kirjastojen%20s%C3%A4hk%C3%B6iset%20viestit-19f9fb80fbfd3743559fb9de8fb8e666.pdf

**Lumme**
* Normaalia ylläpitoa.
* Laina- ja maksusääntöjä esitestailtu Nextillä, todettu alustavasti toimivaksi. Vaatii vielä laajempaa testailua.
* Tehty kehitysehdotus laina- ja maksusääntöjen kopioinnista, tiketti #2155.

**Siilinjärvi**
* Tarkistettu että LinkMobilityn omaan päivitykseen liittyvä IP-osoitteiden tarkistuspyyntö ei aiheuta toimenpiteitä, Koha-viestit eivät käytä IP-osoitteita.
* Palataan API-avainten uusintoihin versiopäivityksen jälkeen.
* Matrix- ja GitHub-jäsenyydet Siilin osalta ok.

**Vaski**
* Melko paljon saatu tehtyä versiopäivityksen testailua ja valmistelua.
* Kysellään automaattitoimittajalta lajittelusääntömuutosten tekemisestä signum-muutokseen liittyen.

**Helle**
* Hellen 83 asiakastiedossa on arvo käytöstä poistetussa kentässä phonepro. Arvojen massapoisto Kohan työkalulla ei onnistu. Kun phonepro-arvon laittaa käyttöön (asetus borrowerunwantedfield), näkyy kenttä asiakastiedon muokkauksessa ja asiakkaan tiedoissa. Kenttä ei näy eikä ole muokattavissa työkalussa Asiakkaiden muokkaus eräajona.
* Hankintaportaalin kautta muodostuneissa tietueissa saattaa edelleen olla kentässä 084a luokka-arvon alussa virheellisesti kirjain. Ainakin näitä kirjaimia esiintyy luokka-arvon alussa: K tai L tai T.

**Lastu**
* Finnasta tulee ilmoituksia käyttäjätilin vanhentumisesta asiakkaille, joilla on ollut ennen järjestelmänvaihtoa käytössä useampi kuin yksi kirjastokortti ja jotka ovat käyttäneet kirjautumiseen aiemmin muuta korttia kuin vaihdon jälkeen. Kohassa korttien vaihdossa tätä ei enää ilmene, eli on vain tämän kevään ongelma (Finna-käyttäjätilit vanhenevat 18kk käyttämättömyyden jälkeen)
* Matrix ja GitHub Lastun osalta ok

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2026#viikko-6) - [Palaa sivun alkuun](/paakayttajat2026)

## Viikko 5

Aika: Ti 27.1.2026 klo 9.15<br />
Läsnä: Elina Uotila ja Erika Miettinen (Kirkes), Pirkko-Liisa Lauhikari ja Piia Semenoff (OUTI); Reetta Pihlaja (Siilinjärvi), Hanna Ikonen (Lumme), Leena Kinnunen (Lappi), Lotta Juvonen ja Kati Sillgren (Helle), Anneli Österman, Pasi Kallinen ja Johanna Räisä (Koha-Suomi), Irina Halminen (Vaara, klo 9.45 saakka), Auli Rantasalo (Vaara, klo 10 saakka), Hanna Hyttinen (Vaara), Roosa Väisänen (Kyyti)

**Yhteiset**
* Onko käytössä ulkoisia palveluita, joihin olisi tarpeen vaihtaa salasana? Esim. tekstiviestipalvelut, posti? / Johanna
* Talteen ja tiedoksi: [DVV:n PowerBI-raportti Suomi.fi viesteistä](https://app.powerbi.com/view?r=eyJrIjoiNWM5NWQ1Y2YtNjliZS00NDQ4LTk5YzItYWJjZjFmNWNmYzkxIiwidCI6ImFhMjE1NzcyLTgzYmYtNDc4OC04MDY1LTUyNDU2ZmEyNjAyNyIsImMiOjh9)
  * Täältä voi esim. tutkia, minkä tyyppisinä viestit on mennyt käyttäjille (paperi/sähköinen).
  * Linkki lakkaa toimimasta jossain vaiheessa.
* Versionvaihto:
  * [Nexteiltä kopioitavat tiedot](https://github.com/KohaSuomi/Koha-25x/wiki/Versionvaihdon-muistiinpanot-kehitt%C3%A4jille#nexteilt%C3%A4-kopioitavat-tiedot) - käydään läpi ja tarkistetaan, onko kaikki listatut tarpeen ja puuttuuko jotain.
  * [Niteet, jotka ovat paikalla noutokirjastossa piiloon muiden hyllyvarauslistalta](https://github.com/KohaSuomi/Koha/issues/1262#issuecomment-3798749609) - Taulujen asetuksissa uusi vaihtoehto, jolla saa käyttäjäkohtaisesti talteen haun ja suodatuksen tilan ja muistamaan asetukset sivua vaihdettaessa.

Pohjoisesta etelään

**Kirkes**
 * Elina tehnyt testauksia ja muokkauksia nextillä.
 * Erika esittelee Kirkes-kirjastojen Suomi.fi-viestiprosessia Suomi.fi-tukiklinikalla pe 30.1. klo 8.30-9.15. https://kehittajille.suomi.fi/tapahtumat/kirkes-kirjastojen-sahkoiset-viestit-suomi-fi Myös Johanna on Kohan puolelta mukana. Klinikan alussa esitellään sivusto, josta raportit esim. sähköisten ja paperiviestien jakautumisesta jatkossa löytyvät. Materiaali laitetaan Koha-pääkäyttäjille jakoon klinikan jälkeen.
 * Tuusulan kirjastoautossa ollut joitain kummallisia varausten viimeisiä noutopäiviä, vaikka laina- ja maksusääntöihin tms. ei ole tehty muutoksia. Selvitellään lisää ja palataan asiaan, jos selitystä ei löydy.

**OUTI**
* Pääkäyttäjät käyvät tänään läpi uuden version järjestelmäasetukset, kuinka ne halutaan kimpassa olevan ja mitä uutta versioon on tulossa. Katsotaan, pitkääkö joistain asioista ehdä kimpassa erillinen päätös.

**Siilinjärvi**
* Meillä on jäänyt aikanaan päivittämättä luettelointipohjiin kenttä 952$y Kohan aineistolaji -> Kohan nidetyyppi. Nyt päivitetty, joten niteen muokkauslomakkeellakin otsikko näkyy oikein.

**Lumme**
* Nextin työstöä valmiiksi. Tarkoituksena testailla laina- ja maksusääntöjä.
* Kuvailijat käyvät edelleen läpi Celia-muutoksia.

**Lappi**
* Virheelliset postinumerot -rapsalle oli tullut ulkomainen postinumero. Löytyi vanha tieto, että virheelliset postinumerot estävät e-kirjeiden lähetyksen, mutta onko tilanne edelleen tämä?
* Silmäilty avoimia tikettejä joissa Lappi mukana: tiketin 750 vaihe oli epäselvä, selvitetään tilanne.

**Helle**
* Johanna lisännyt Kaukolaina-toimintoon liittyvät kaksi IntranetUserJS-rimpsua liittyen lisäkenttiin ja käännöksiin.
[Helle, IntranetUserJS-rimpsu käyttöön: "Lisää uusi kaukolainapyyntö-lomakkeelle automaattisesti kaksi lisäkenttää"](https://github.com/KohaSuomi/Koha/issues/2144)
* Lisätty Koha-yhteisön Bugzillaan tiketti Kaukolaina-toimintoon tarvittavasta Eräpäivä-kentästä
[Add new field to ILL request]( https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=41712)

**Kyyti**
* Selvitetty mahdollisuutta ottaa eräpäivän mukaan järjestykseen lajiteltu lainakuitti käyttöön.


[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2026#viikko-5) - [Palaa sivun alkuun](/paakayttajat2026)


## Viikko 4

Aika: Ti 20.1.2026 klo 9.15<br />
Läsnä: Anneli Österman ja Kodo Korkalo (Koha-Suomi), Päivi Knuutinen, Auli Rantasalo, Hanna Hyttinen (Vaara), Maria Joona ja Pia Kusmin (Lappi), Anni Mäki-Mantila (Vaski), Kati Sillgren (Helle), Janne Seppänen ja Lauri Hänninen (Lastu), Elina Uotila (Kirkes), Tuomas Kunttu ja Roosa Väisänen (Kyyti), Piia Semenoff ja Pirkko-Liisa Lauhikari (OUTI), Hanna Ikonen (Lumme), Reetta Pihlaja (Siilinjärvi)

**Yhteiset**
* [Uuden delete_bibliographic_records-oikeuden asettaminen käyttäjille](https://github.com/KohaSuomi/Koha-25x/issues/195)
  * Käykää kaikki kommentoimassa, miten haluatte oikeuden omassa kimpassa.
* Versionvaihto
  * [Käykää kaikki tekemässä sorting rule -sääntö](https://github.com/KohaSuomi/Koha-25x/issues/18)
* [Käykää merkkaamassa, koska teidän kimppaan haluatte, että tehdään 0000-00-00-korjausajo tuotannossa](https://github.com/KohaSuomi/Koha/issues/1957)

Etelästä pohjoiseen.

**Vaara**
* Perjantaina tuli Joensuun johtajalle tieto yhdestä Vaara-kirjastosta, että heidän sähköpostiinsa oli tullut Paytraililta viesti maksusta 11,50 euroa. Tätä ihmeteltiin, kunnes katsoin Paytrailin maksutaulukosta kyseisen summan kohdalta, mistä maksusta on kysymys. Osoittautui, että nykyään seutukirjaston asiakkaana oleva henkilö oli maksanut mainitun summan eikä asiakkaan tiedoissa ollut sähköpostiosoitetta ollenkaan. Ryhdyin tutkimaan lokitietoja ja sieltä selvisi, että asiakas oli ollut toisen Vaara-kirjaston kotipalveluasiakas aikaisemmin ja sen vuoksi asiakkaan tiedoissa oli ko. kirjaston sähköpostiosoite. Asiakkaalta oli poistettu tiedoista tämä kirjaston sähköpostiosoite vuonna 2023. Ihmettelin asiaa Paytrailille, joka vastasi, että "selvittää tarkemmin asiointipalvelun teknisentuen kanssa" eli käytännössä Finna-tuen kanssa. Sieltä selvisi, että Finna käyttää ensisijaisesti omaan asiakasrekisteriinsä tallennettua sähköpostiosoitetta. Tätähän me emme pysty mitenkään näkemään asiakkaan tiedoista Kohassa. Pyysin Finna-tukea poistamaan asiakkaan sähköpostiosoitteen, koska hänellä ei Kohassa ole mitään sähköpostiosoitetta.
Tämä Finnan oma sähköpostikenttä aiheuttaa kyllä ongelmia.

**Lappi**
* Versionvaihtoon ja signum-muutokseen liittyviä töitä
* Lapin Koha-käyttäjäryhmä kokoontui viime perjantaina

**Vaski**
* PIN-koodin tallentamiseen lisätty tarkistus verkkokirjastossa ja Kohassa. Kyseltiin olisiko kiinnostusta yhteiselle kehitysehdotukselle Kohan osalta, mutta kiinnostusta ei ilmennyt joten mennään omalla js-koodilla.
* Hankinta ihmetellyt tilausten siirron yhteydessä sitä, että osittain saapuneet tilaukset ovat kokonaisuudessaan siirtyneet uuden budjettivuoden alle. Todettu, ettei oikein voi toimia toisin, koska hankinnan tili määritellään koko tilaukselle eikä tilauksen niteille erikseen.

**Helle**
* Porvoon kirjastoautosta ilmoittivat, että perjantaina 16.1.2026 noin klo 17.30 Koha oli lakannut toimimasta. Muihin järjestelmiin ja nettiin oli päässyt normaalisti. Porvoon kirjastoautossa on aiemmin ollut usein perjantaisin huomattavaa Kohan hidastelua klo 17.00 jälkeen.

**Lastu**
* Automaatin testauksia jatkettu, SIP-palvelimen päässä tehty regex toimii ja asiakkaan AF-kentässä välittyvä viesti on siistimpi.
* Kaukolainan "Maksettu hinta"-kentässä ongelmaa numeron 0 tallentamisessa, tiketti tehty: https://github.com/KohaSuomi/Koha/issues/2138

**Kirkes**
* Signum-muutoksen valmistelut lähes valmiita, vielä yhdessä kirjastossa tarkistettava automaattien lajittelusääntöjen tilanne.

**Kyyti**
* Perustietonäkymässä näkyy sarjatieto kentästä 800 ja sen kuvailusäännöt ovat muuttuneen siten, että sarjalinkin haku ei enää löydä sarjan vanhoja eri tavalla kuvailtuja osia. 490-kentässä sarja on kirjattu vanhalla tavalla ja jos se näkyisi perustietonäkymässä ja sarjan nimi olisi linkki löytyisi myös sarjan vanhat osat. Finnassa näkyy linkkeinä sekä 800 että 490.
Anneli arveli, että tietuenäyttöjen mukautuksessa voisi kokeilla 490-kentän laittamista näkyville, mutta saako sen linkiksi, ei ole tietoa. Toinen vaihtoehto olisi laittaa kehitysehdotusta yhteisöön.
* Kouvolalla on tahtotila saada PowerBI:n kokoelmaraportit päivittymään raportterirajapinnan kautta palvelimelle. Kysyin toimintatapaa. Sovitaan palaveri Kodon ja palvelinta hallinnoivan tahon kanssa.

**OUTI**
* Oulun aineistojen kellutuspoikkeuksien testausta FloatRules-järjestelmäasetukseen tallennettujen määritysten mukaisesti, ettei tietyt nidetyypit ja hyllypaikat kelluisi Oulussa, vaan pyrkisivät kotikirjastoon. Hyllypaikkasääntö ei toimi vielä.

**Lumme**
* Viime viikon perjantain pienen käyttökatkon syyksi paljastui Plack-ongelma. Ongelma saatiin korjattua nopeasti.
* Otettiin käyttöön asetus kausijulkaisuille, joka muuttaa edelliset numerot automaattisesti Saatavana-tilaan.

**Siilinjärvi**
* [Aineistotyyppimuutos äänikirjoille](https://github.com/KohaSuomi/Koha/issues/750) ajettu, vielä jäi jotain korjattavaa jälkikäteenkin.
* Muuten ei mitään erikoista.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2026#viikko-4) - [Palaa sivun alkuun](/paakayttajat2026)

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

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2026#viikko-3) - [Palaa sivun alkuun](/paakayttajat2026)

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
