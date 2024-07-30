---
layout: single
permalink: /paakayttajat2024
header:
  overlay_color: '#5e616c'
  overlay_image: /assets/images/cropped-pexels-photo-113850.jpeg
toc: true
title: 'Koha-Suomen pääkäyttäjäryhmän muistiot 2024'
---

Koha-Suomen pääkäyttäjäryhmä kokoontuu kerran viikossa. Ylimmäisenä on aina uusin muistio.

## Viikko 31 

Aika: 30.7.2024, klo 9.15<br />
Läsnä: Päivi Knuutinen ja Hanna Hyttinen (Vaara)

**Yhteiset asiat:**
* [Viikon 31 päivitys](https://github.com/KohaSuomi/Koha/discussions/1337)
  * Z39.50: jos merkistö menee sekaisin, kokeile muuttaa asetuksiin utf-8 -> iso-8859-1 (tai joissain tapauksissa toisinpäin)

Etelästä pohjoiseen.

**Vaara**
* Raporteilla löytyi aineistotyypittömiä tietueita (osakohteita) yli 2000 kpl. Korjasin niitä erämuokkauksella, mutta ihmettelin, että miksi niitä ylipäätään syntyy. Selvisi, että Vaarassa oli tietueiden yhdistämissäännöissä virhe. Siellä pitää olla 942-kentän kohdalla Suojaa poistamiselta, mutta siellä oli arvona Suojaa (mikä on kaikkien muiden kenttien kohdalla). Tämä esti aineistotyypin valumisen tietueen mukana ja nyt se toimii oikein, kun arvo on korjattu.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2024#viikko-31) - [Palaa sivun alkuun](/paakayttajat2024)

## Viikko 30

Aika: 23.7.2024, klo 9.15<br />
Läsnä: Anneli Österman ja Kodo Korkalo (Koha-Suomi), Päivi Knuutinen ja Hanna Hyttinen (Vaara), Iina Niemi (Vaski), Katariina Pohto, Piia Semenoff ja Pirkko-Liisa Lauhikari (OUTI), Hanna Ikonen (Lumme)

**Yhteiset asiat:**
* [Viikon 30 päivitys](https://github.com/KohaSuomi/Koha/discussions/1328)
* Mobiilikirjautuminen automaateille on korjattu. Automaatit nyt hyväksyvät myös pienen a-kirjaimen kirjautuessa. Samalla korjattiin myös OUTI-alkuisten tunnusten hyväksyminen. Kyse oli kuitenkin automaattien omista säännöistä asiakastunnusten muodolle.
  
Pohjoisesta etelään.

**OUTI**
* Outissa otetaan myös käyttöön Tarkka haku-sivulla olevien ylimääräisten aineistotyyppien rajaus tietylle kirjastolle. Rajaamme ne Ruskon kirjavarastoon, jotta kaikki aineistotyypit näkyvät tarvittaessa kuvailijoille ja hankinnalle. 
* Kohan ohjetta varten asiakashakua testatessa huomattiin, että jos hakee automaattia tai automaatin toimittajaa, niin haku kohdistuu auktorisoituun arvoon eikä kuvailuun, joka näkyy käyttäjille. OUTIssa näissä voi kuvailu olla eri kuin auktorisoitu arvo esim. Aukrotisoitu arvo: Supa ja Kuvailu: Lyngsoe Systems. Eli jos hakee Supalla, niin löytyy Lyngsoen automaatit, mutta Lyngsoella ei löydy mitään. Mikä neuvoksi?
  * Teemme uuden aktorisoidun arvon ja asiakasmuokkauksessa siirrämme toimittajat uudelle arvolle. Poistamme vanhan auktorisoidun arvon, kun se on tyhjä.
* Webkaken palvelimenvaihto ei onnistunut viime su 21.7., joten Jukka yrittää uudelleen ensi su 28.7. Yksi vaihdossa ilmennyt ongelma oli se, että LinkMobilityn tekstiviestit eivät lähteneet vaikka uuden palvelimen nimi ja ip olivat samat kuin vanhalla palvelimella.

**Vaara**
* Aineistotyyppivalikko siivottu tarpeettomista aineistotyypeistä Emmin idean mukaan. Se kirjastovalinta oli hyvä keksintö.
* Vaskiin kiitos Mikolle hankintaluetteloraportista.
* Elements-ongelmaan tuli ehdotukseksi käyttää Firefoxin esr128-versiota. Pitää koettaa saada käyttöön ja testata, toimiiko tulostimien kanssa oikein.

**Vaski**
* Ei raportoitavaa

**Lumme**
* Normaalia ylläpitoa.
* Kummastusta herätti vanhentuneiden varausten raportille varaustunnus, joka kuului anonyymeihin lainoihin. Syy oli raporttikirjastossa ollut raportti, joka ei osaa listata tällaisia varauksia oikein.
  
[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2024#viikko-30) - [Palaa sivun alkuun](/paakayttajat2024)

## Viikko 29

Aika: 16.7.2024, klo 9.15<br />
Läsnä: Pirkko-Liisa Lauhikari, Katariina Pohto, Piia Semenoff (OUTI), Päivi Knuutinen ja Hanna Hyttinen (Vaara), Kati Sillgren (Helle), Maria Joona (Lappi), Annika Helastila ja Elina Uotila (Kirkes), Hanna Ikonen (Lumme), Emmi Takkinen (Koha-Suomi)

**Yhteiset asiat:**
* Viikon 29 päivitystä ei ole.
* Mobiilikirjautuminen automaateille on case sensitive, ei siis hyväksy pieniä kirjaimia. Tämä on aiheuttanut hämmennystä asiakkaissa ja virkailijoissa.
Asiasta on aikoinaan tiedotettu, mutta siitä ei ole mainintaa kirjautumisen yhteydessä. Finnassa toimii kirjautuminen myös pienillä kirjaimilla. Tehdään kehitysehdotus,
että mobiilikirjautumisessa toimisi kirjautumistunnus kirjainten koosta huolimatta.
* Väärin valuneiden tietueiden korjailu vieläkin työn alla Pasilla.
* OUTIssa ongelmia aiheuttanut takaajatomat lapsiasiakkaat. Takaajatiedot voivat edelleenkin kadota tapauksissa, joissa asiakastietueita yhdistetään (taattava voi poistua)
tai kopioidaan (takaaja ei tallennu). Näistä on mahdollisesti jo tiketit olemassa. [Ongelma "Kopioi"-painikkeen käytössä: Takaaja-tieto ei tallennu #610](https://github.com/KohaSuomi/Koha/issues/610)
  
Etelästä pohjoiseen.

**OUTI:**
* Vastaan tuli 16-vuotias asiakas asiakastyypillä 'Lapsi, omatoimi kielletty'. OUTIn käytäntö on, että 16-vuotiaat muuttuvat automaattisesti asiakastyyppiin 'Lapsi, omatoimi sallittu'. 11.4. alkaen oli kuitenkin ajo asiakastyyppien muuttamiseksi jumittunut, syynä takaajatiedoton lapsiasiakas, joka oli täyttänyt sen 16 vuotta. Takaajattomia lapsiasiakkaita oli yht. 15, joista suurin osa oli konversiosta tulleita, ja joitakin vuonna 2022 tehtyjä uusia tallennuksia. Suurin osa asiakkaista oli sellaisia, ettei kortteja ollut käytetty vuosiin. Yhdellä oli laskutuksessa lainoja. Esihenkilön päätöksellä poistettiin nämä asiakkaat lukuunottamatta laskutusasiakasta. Kohaan asetetut yläikärajat antavat vielä luoda sen ikäisen asiakkaan ko. asiakasryhmälle. 16-vuotiaita asiakkaita on jonkin verran luotu väärällä asiakastyypillä.

**Vaara**
* Päivi kyseli, onko missään valmiina hankintaluettelo-raporttia. Vaarassa on jäänyt nämä viralliset dokumentit tekemättä Koha-ajalta. Uutuusluettelosta raportti poikkeaa sen suhteen, että myös aikaisemmilta vuosilta otettavissa hankintaluetteloissa pitää olla myös myöhemmin ehkä poistetut aineistot. Vaskista luvattiin apua tähän asiaan.
* Lehtitietueen poisto aiheutti pähkäilyä. Niteet oli poistettu, mutta nimekettä ei voinut poistaa, koska sillä oli tilauksia (vaikka ne oli jo suljettuja). Ensin siis piti löytää, mistä lehtitilaus poistetaan ja poiston jälkeen pystyi poistamaan myös lehtinimekkeen.

**Helle**
* Palautushylly-automaatti ei ilmoita Laskutettu-tilaisista niteistä. Mahdollisia palautettuja laskutettuja niteitä seurataan raportin avulla.
* Kun käytössä on IntranetUserJs-rimpsu Laita Muutospyynnöt-sivulla oletuksena valinta Hyväksy-kohtaan, päivittää Päivitä asiakastietoja -toiminnon OK-painike kaikki muutospyynnöt. Eikä vain esim. tarkastelussa/avattuna olevan muutospyynnön. Emmi poistaa ko. rimpsun Hellestä.

**Lappi**
* Normaalia ylläpitoa.

**Kirkes**
* Poistettu Kohasta asiakkaiden Finnassa lisäämät valinnat asiakasviestien koosteille.

**Lumme**
* Normaalia ylläpitoa.
  
[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2024#viikko-29) - [Palaa sivun alkuun](/paakayttajat2024)

## Viikko 28

Aika: 9.7.2024, klo 9.15<br />
Läsnä: Pirkko-Liisa Lauhikari ja Katariina Pohto (OUTI), Lari Strand ja Pasi Kallinen (Koha-Suomi), Anni Rajala (Vaski), Janne Seppänen (Lastu), Päivi Knuutinen ja Hanna Hyttinen (Vaara), Kati Sillgren (Helle), Annika Helastila (Kirkes)

**Yhteiset asiat:**
* Viikon 28 päivitystä ei ole.
* Kohan huoltoikkuna ke 10.7. klo 7.00-9.15, ei huoltotoimenpiteitä.
* Koha-varmenne vanhenee 31.8.2024.
* Perjantaiaamuna 5.7. Kohat jumissa. OUTIssa yhteys mennyt heti puolen yön jälkeen 00.00.45. Plack oli alhaalla. Myöhemmin samana päivänä Toveri-plugin kaatui Vaarassa.
* Versionvaihto tulossa syksyllä, ja paljon testattavaa. Konfiguroitavia JS-plugineita valmistellaan versionvaihtoa varten, jotta päästään eroon vanhoista rimpsuista ja pääkäyttäjät voisivat hoitaa konfiguroinnin jatkossa.
* Viime yönä päivittyi Element, ja lakkasi toimimasta Firefoxin ESR-versiossa. Elementiltä vastattu, ettei kuulu tuettaviin Firefox-versioihin. Tästä käydään keskustelua, josko asia korjataan vai joudutaanko vaihtamaan työkalua toiseen. Kaikilla ei ole mahdollisuutta käyttää työpöytä-appia. Chromella Element edelleen toimii, joskin kirjautumisessa tai salausavaimissa ym. voi olla ongelmaa, jos Chrome ei ole ollut käytössä jo ennestään.
  
Pohjoisesta etelään.

**OUTI**
* Ei mitään erityistä.

**Siili**
* Reetta lomalla 12.8. asti. Koha-henkilö puuttuu 22.7. asti, jolloin Kososen Marko tulee töihin. Esimies Nevalaisen Jarkko tulee 29.7. Jos tarvitsee saada yhteys Siiliin niin paras on kirjasto(at)siilinjarvi.fi tai 044 740 1382.

**Lastu**
* Timmiltä saatu tieto ettei liittymää Kohan rajapintaan ole vielä toteutettu. Jatketaan keskustelua heidän kanssaan sellaisen toteuttamiseksi.
* Automaattitestauksia tehty Lyngsoen automaatilla ja toiminta vaikuttaa lupaavalta tuotantoon menoa ajatellen. Testattu myös [Sip2SortBinMapping](https://koha-community.org/manual/23.11/en/html/circulationpreferences.html#sip2sortbinmapping)-asetusta, joka myös vaikuttaa toimivan kuten manuaali lupailee. Konvertoitu asetuksen avulla nykyisiä lajittelusääntöjä Aurorasta Kohaan.

**Vaski**
* Perusylläpitoa, kirjastojen avaamisia remonttien päättymisen myötä.
* Mikko bongannut nextillä js-koodeja testatessa pari koodeihin vaikuttavaa muutosta, näistä tehty tiketit [#91](https://github.com/KohaSuomi/Koha-24.05/issues/91) ja [#92](https://github.com/KohaSuomi/Koha-24.05/issues/92). Jälkimmäinen js muutetaan plugariksi.

**Vaara**
* Viime perjantain Kohan kaatuminen aiheutti isomman revohkan Toverin kanssa. Irinan sanoin: "Vaati Toveri-pluginin uudelleenasennuksen, jossa oli ongelmia ja samallahan se hävitti kaikki oikeudet ovikoneilta, aukioloajat ja ne muut asetukset (olin ottanut ne kyllä talteen). Oikeuksia naputellessa meni sit aikansa myös (ja sitä ennen piti tajuta, että ne puuttuu!). Sit aloin soittelemaan Mikkeliin, kun heillä on se yksi Toveri käytössä. Saatiin sitten Katja kiinni ja hän sai Larin kanssa laitella Suomenniemen Toverin tulille (soitin sinnekin ennen sitä, eivät olleet huomanneet käyttökatkoa). Syytä ei ollut ainakaan perjantaina tiedossa eli ei hajua, miksi plugari reagoi palvelinkatkoon."
* Finnaan tehty korjaus koosteviestien piilotukseen.

**Helle**
* Lisättty kuvailupohjiin Hankintahinta-kentän 952y pakollisuus.
* Poistettu Kohasta asiakkaiden Finnassa lisäämät asiakasviestien Kooste-valinnat. Helle-Finnassa piilotettu asiakasviestien valittava Kooste-vaihtoehto.

**Kirkes**
* Kirkes-Finnassa korjattu koodi, joka piilottaa asiakastiedoista mahdollisuuden valita koosteviestit. Lisätty Kohaan raportti asiakkaista, joilla asetus on käytössä.
  
[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2024#viikko-28) - [Palaa sivun alkuun](/paakayttajat2024)

## Viikko 27

Aika: 2.7.2024, klo 9.15<br />
Läsnä: Pirkko-Liisa Lauhikari ja Katariina Pohto (OUTI), Kati Sillgren ja Lotta Juvonen (Helle), Irina Halminen ja Hanna Hyttinen (Vaara), Mikko Liimatainen (Vaski), Noora Suvanto (Lappi), Janne Seppänen (Lastu), Emmi Takkinen (Koha-Suomi)

**Yhteiset asiat:**
* [Viikon 27 päivitys](https://github.com/KohaSuomi/Koha/discussions/1305)
  * Finna näyttää aktiivisissa varauksissa vain varaukset, jotka eivät ole tärpänneet vielä kiinni varaukseen. Koha näyttää aktiivisissa varauksissa myös kuljetustilassa olevat ja noutoa odottavat varaukset. Halutaanko yhtenäinen tieto myös Kohaan? Kommentit [tikettiin](https://github.com/KohaSuomi/Koha/issues/1170).
* Valutuksen ja tietueiden korjausajojen tilanne.
  * Viikon 26 korjaustoimenpiteiden jälkeen vanhoja tietueita alkoi valumaan edelleen kimppoihin, kun valutus käynnistettiin. Valutukset ovat olleet taas pois päältä Tätistä ja kaikista kimpoista.
  * Ma 1.7. aamusta OUTIn ja Lapin metadatojen timestampit on taas oikaistu, muille kimpoille ajot tehty illalla, koska ajot raskaita.
  * Kun timestampien oikaisuajot kaikkiin kimppoihin tehty, laitetaan yhteen kimppaan Tietuesiirtäjä päälle ja tarkistetaan, ettei vanhoja tietueita enää valu.
  * Tämän jälkeen palautetaan actionlogista muuttuneet tietueet.
* Hankintahintojen oikominen /Emmi
  * Vaski tehnyt tästä [tiketin](https://github.com/KohaSuomi/Koha/issues/1302), onko muilla tarvetta samallaiselle ajolle?
  * Päätettiin, että kaikissa kimpoissa hankintahinta-kenttä laitetaan pakolliseksi.
  * Kimpoista kommentoidaan tikettiin, halutaanko kimpalle tehdä korjausajo ja millä perusteella puuttuva hankintahinta päivitetään niteelle.
* Aineistotyyppi näkyy asiakkaan lainoissa väärin /Emmi
  * Korjataanko nykyiseen versioon vai odotetaanko versionvaihtoa?
  * Korjataan seuraavaan versioon.  
  
Etelästä pohjoiseen.

**OUTI**
* Normaalia ylläpitoa. Käyttäjätunnusten oikeuksien tarkistusta.

**Vaara**
* Ei mitään erityistä. Pitempi muuttokiinniolo tulossa yhdelle kirjastolle heinäkuun lopulta alkaen.

**Lappi**
* Normaalia ylläpitoa.
  
[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2024#viikko-27) - [Palaa sivun alkuun](/paakayttajat2024)

## Viikko 26

Aika: 25.6.2024, klo 9.15<br />
Läsnä: Pirkko-Liisa Lauhikari ja Katariina Pohto (OUTI), Auli Rantasalo (Vaara), Annika Helastila (Kirkes), Reetta Pihlaja (Siilinjärvi), Lotta Juvonen (Helle)

**Yhteiset asiat:**
* [Viikon 26 päivitys](https://github.com/KohaSuomi/Koha/discussions/1300)
* Vanhoja kuvailutietoja valunut uusien päälle viikolla 25.
  * Kun tiketin #1288 ajo muutti TäTissä biblio_metadata-taulun timestampia, ne muuttuivat uudemmiksi kuin paikalliskantojen vastaavien tietueiden biblio_metadata-taulun timestampit, joka aktivoi tietueiden valutuksen paikalliskantoihin. Korjaussuunnitelmana viikolla 26 kehittäjillä on, että päivitetään kimppojen metadatojen timestampit, jottei tietueita enää valu TäTistä. Laitetaan valutus tämän jälkeen päälle. Tehdään ohjelman pätkä, jolla palautetaan actionlogista muuttuneet tietueet.

Pohjoisesta etelään.

**Vaski**
* sovittiin, että laitetaan kuluvana vuonna hankituille nitelle puuttuvat hankintahinnat OKM-tilastojen takia. Vaski tekee tiketin
* Vaskissa tapaus, jossa asiakkalle on syntynyt hyvitystä. Maksutiedoissa on useampi rivi klo 00.05 aikaleimalla "Liikamaksun hyvitys" -rivejä, joista saatavat muodostuvat.

**OUTI**
* Tiketti https://github.com/KohaSuomi/Koha/issues/630 (Nidevaraus ei estä uusimista, kun käytössä AllowRenewalIfOtherItemsAvailable-järjestelmäasetus) avattu uudestaan, koska OUTIsta tuli huomio, että nidevaraus estää muiden lainassa olevien niteiden uusinnan, jos yhtään nidettä ei ole saatavana-tilassa. Uusinta onnistuu, jos tietueessa on muita saatavana olevia niteitä.
* Yhden vanhan kirjatietueen päälle oli ”siirtynyt” uuden CD-levyn niteet ja varaus. Luetteloinnista säikähtivät, että onko järjestelmä voinut tehdä tämän. Nyt on selvinnyt, että ilmeisesti käyttäjä oli vahingossa yhdistänyt väärät tietueet.

**Vaara**
* Ei mainittavaa.

**Kirkes**
* Myöhästymismaksuja muodostunut taas liikaa yksittäisistä niteistä. Epäillään korvaushinnan vaikuttavan joissain tapauksissa. Seurataan tapauksia lisää.

**Siilinjärvi**
* Ei mainittavaa. Heinäkuussa ei juurikaan Koha-ihmisiä töissä, joten kiiretapauksissa paras ottaa Koha-asioissa yhteyttä kirjasto(at)siilinjarvi.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2024#viikko-26) - [Palaa sivun alkuun](/paakayttajat2024)


## Viikko 25

Aika: 18.6.2024 klo 9.15<br />
Läsnä: Kati Sillgren (Helle), Lauri Hänninen (Lastu), Pirkko-Liisa Lauhikari (OUTI), Irina Halminen ja Hanna Hyttinen (Vaara), Reetta Pihlaja (Siilinjärvi), Annika Helastila (Kirkes)

**Yhteiset asiat**
* Vaskilaiset lisäsivät Koha-tietovarannon [Poikkeustilanteisiin ja erikoistilanteisiin ohjeita](https://github.com/KohaSuomi/Koha/wiki/Poikkeustilanteisiin-ja-erikoistilanteisiin-ohjeita#kirjaston-lopullinen-sulkeminen-ja-poistaminen-kohasta) -wikiin heidän muistilistan, mitä kannattaa huomioida, kun kirjasto sulkeutuu lopullisesti.
* [Viikon 25 päivitys](https://github.com/KohaSuomi/Koha/discussions/1292)
* [MARC-esikatselujen suoristus](https://github.com/KohaSuomi/Koha/issues/1288) tuotantoihin ennen RDA-konversiota
* Suljettahan tai muutattehan toiseen tilaan [Ratkaisu ehdotettu -tilassa olevat tikettinne (avaamanne)](https://github.com/orgs/KohaSuomi/projects/4/views/15).

Etelästä pohjoiseen

**Lastu**
* Timmin aikataulu mietityttää, ei kuulumisia Tammikuussa annetun aikaikkunan jälkeen. Laitetaan viestiä Timmin suuntaan.

**OUTI**
* Oulun luetteloinnista Heikkisen Antti on pyytänyt korjausraportteja MARC-tietueiden korjauksia varten. Anneli on niitä tehnyt ja lisännyt raporttikirjastoon raportit: ”Tietueet, joissa MARC-kentässä 007 tietty merkkijono" ja "Tietueet, joissa 007/00 on ‘k’ ja 007/04 on tyhjä".
* Kirjastojen kesän sulkuajoille on jälleen alettu tekemään sulkutoimenpiteitä, mm. suljetuille kirjastoille tehdään oma noutoilmoitus, jos varaukset ovat noudettavissa sulkuaikana jostain toisesta kirjastosta.
* Katariina Pohto (Kassu) on valittu Annelin sijaiseksi OUTIn pääkäyttäjähommiin ajalle 24.6.-31.12.2024. Kassu tekee pääkäyttäjähommia 40% työajastaan.

**Vaara**
* Lainausautomaateilla tehdyt uusinnat eivät päivity heti uudelle eräpäivälle eivätkä tulostu oikein kuitille. Uudelleenkirjautumisen jälkeen uusinnat näkyvät oikealla päiväyksellä (ja tulostuvat myös kuitille ko. päivämäärällä). Lari tehnyt aiheesta tiketin: https://github.com/KohaSuomi/Koha/issues/1291 (yhteisöstä tuodaan tänään ratkaisu bugiin). Vaskissa luvattu testata ratkaisua testiautomaatilla.
* Asiakaspalautteena on tullut toive, että lainausautomaateilla näkyisi myös varaustunnus. Keskusteltiin, mitä tietoja automaateilla näkyy. Mikro-Väylä ei näytä varaustunnusta eikä asiakkaan henkilötietoja, mutta Lyngsoen automaateissa on ainakin optiona, että asiakas voi tarkistaa omat tiedot (nimi, osoite jne.). Irina mainitsi sivumennen myös, että kun asiakas kirjautuu lainatakseen Mikro-Väylän automaatilla, automaatti antaa tiedon noudettavista varauksista, muttei varausten sijaintikirjastoa. Sitä varten tulee kirjautua erikseen Tarkista varauksesi -toiminnolla. (Mietimme, tarvitseeko tätä kehittää.)

**Siilinjärvi**
* Ihmetelty yhden paljon varaavan asiakkaan tekstiviestejä: kaikki tekstiviestit näkyvät Kohassa epäonnistuneina, mutta asiakas kertoo saaneensa kaikki perille.
* Muuten ei mitään erikoista.

**Kirkes**
* Hankintapuoli mietiskellyt, vaikuttaako toimittajan nimen vaihtuminen johonkin haitallisesti.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2024#viikko-25) - [Palaa sivun alkuun](/paakayttajat2024)

## Viikko 24

Aika: 11.6.2024 klo 9.15<br />
Läsnä: Piia Semenoff ja Pirkko-Liisa Lauhikari (OUTI), Auli Rantasalo (Vaara), Maria Joona ja Pia Kusmin (Lappi), Reetta Pihlaja (Siilinjärvi), Kati Sillgren & Lotta Juvonen (Helle), Annika Helastila (Kirkes), Anneli Österman (Koha-Suomi)

**Asiat**
* [Viikon 24 päivitys](https://github.com/KohaSuomi/Koha/discussions/1281)
* [Huoltotiedote](https://github.com/KohaSuomi/Koha/discussions/1278)
* Uuteen [Päivystys-wikiin](https://github.com/KohaSuomi/Koha/wiki/P%C3%A4ivystys) kirjattu nyt, miten päivystys toimii. Tiedot päivitettiin Koha-Suomen palaverissa ja keväämmällä, mutta unohtui tehdä niistä erillinen sivu silloin.
  * muistattehan, että Koha-Suomen päivystysnumero on tarkoitettu vain kimppojen pääkäyttäjille ja sitä ei saa jakaa muille.
  * yhteydenpito Koha-Suomeen päin tapahtuu pääsääntöisesti pääkäyttäjien kautta. Ei suoria yhteydenottoja kirjastoista Koha-Suomeen.
* [Musiikin tiedonhaun koulutuksen ennakkokysely](https://github.com/KohaSuomi/Koha/discussions/1271)
* Version 24.05 tietovaranto ja [wiki](https://github.com/KohaSuomi/Koha-24.05/wiki)

Pohjoisesta etelään

**OUTI**
* OUTIn asiakkailla on yksityisoikeudellisia maksuja, jotka ovat vanhentuneet versiopäivityksen jälkeen. Ilmeisesti yöllinen vanhentuneiden maksujen mitätöintiajo ei ole toiminut versiopäivityksen jälkeen. Anneli tarkisti kehittäjiltä kokouksen aikana asian ja ilmeni, että triggerissä oli ollut jotain ongelmaa, joka on nyt korjattu. Ajot pitäisi toimia jatkossa kaikissa kimpoissa.

**Vaara**
* Ei mainittavaa.

**Lappi**
* Normaalia ylläpitoa.

**Siilinjärvi**
* Samoin Siilissä normimenoa.

**Helle**
* Ruotsinkielisessä Kohassa asiakashaku ei aina löytänyt asiakasta etunimi sukunimi -hakuehdolla. Johanna selvitti ongelman syyn: template cache oli jostain syystä jumissa. Tiketti #1268

**Kirkes**
* Henkilökunnalta tullut kyselyä, mitä tarkoittaa suojattu-tila uutta asiakasta luotaessa.
* Virheilmoituksia käsin lisätyissä hankinnoissa. Tiketti #1282.


[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2024#viikko-24) - [Palaa sivun alkuun](/paakayttajat2024)

## Viikko 23

Aika: 4.6.2024 klo 9.15<br />
Läsnä: Reetta Pihlaja (Siilinjärvi), Päivi Knuutinen, Auli Rantasalo, Irina Halminen (Vaara), Kati Sillgren (Helle), Anni Rajala (Vaski), Pia Kusmin (Lappi), Piia Semenoff (OUTI), Elina Uotila (Kirkes)

**Yhteiset asiat**
* [Uutiskirje 2/24 julkaistu](https://github.com/KohaSuomi/Koha/discussions/1267)
* [Viikon 23 päivitys](https://github.com/KohaSuomi/Koha/discussions/1266)
* [Totalissues-mäppäysten purku](https://github.com/KohaSuomi/Koha/issues/1175)
* [Uusi työkalu: Varausten viimeisen noutopäivän siirto eräajona #249 - kommentti patron_expiration_datesta](https://github.com/KohaSuomi/Koha/issues/249#issuecomment-2033568072)
* Yhteisö tehnyt versioon 24.05 tärkeän tietoturvapäivityksen, jonka tuonti meidän nykyiseen versioon on todella työlästä. Se on kuitenkin hyvin tärkeää saada myös meille, joten Koha-Suomen palaverissa päätettiin, että syksyllä päivitetään Koha versioon 24.05. Tarkempi aikataulu sovitaan asiantuntijaryhmässä.
* Muistutus: On sovittu, että jos jonkin nide- tai tietuemuutostarpeen voi tehdä erätyökaluilla, niin pääkäyttäjät (tai muut sovitut henkilöt kimpassa) tekevät sen itse sen sijaan, että niistä pyydetään tietokanta-ajo kehittäjiltä.
  * erätyökaluilla pystyy nykyään käsittelemään hyvinkin 10 000 tietuetta/nidettä kerralla, joten isojenkin joukkojen käsittelyssä ei mene mahdottoman kauaa.
  * erätyökalut tekevät automaattisesti tarvittavat uudelleenindeksoinnit, tietokanta-ajot eivät tee.
  * muutettavien joukkoja voi hakea myös raporteilla, tarvittaessa Koha-Suomen kehittäjät auttavat raporttien luonnissa.

Etelästä pohjoiseen

**Siilinjärvi**
* Mikroväylän automaatilla uusintapäivämäärä ei edelleenkään päivity ruudulle, Vaarassa sama ongelma.
* Kirjavälitys on nyt Storia Logistiikka, tarkistettu että toimittajan nimeä voi muokata hankinnassa.

**Vaara**
* Ei mainittavaa.

**Vaski**
* Kellutuksen hallinta -työkalun (Kellutin) käyttöönotto lähenee, koulutukset alkavat tänään.

**OUTI**
* Pyhäjoen kirjastosta kysyttiin kunnan varautumissuunnitelmaan apua kysymykseen: "Onko Koha-Suomi Oy:n kanssa sovittu toimimisesta poikkeusoloissa (pandemia, luonnonkatastrofit, sotilaallinen operaatio Suomen maaperällä)?" Annelin neuvoilla vastasin ja kerroin Koha-Suomen palvelimien varavirtalähteistä, Kohan yhteydettömän tilan lainauksesta sekä pandemia- eli korona-ajan kokemuksesta. Liitin mukaan linkin Koha-Suomi Oy:n tietosuoja- ja turvaperiaatteet-tiedostoon: https://koha-suomi.fi/dokumentaatio/tietosuojaperiaatteet/ Jos tulee lisäkysymyksiä, niin sovittiin, että välitetään kysymykset kehittäjien support-postiin.
* Suljettuja kirjastoja on poistettu tietokannasta.
* Varausjonojen siirtäminen tietueesta toiseen tilanteessa, kun tietueita ei voi yhdistää
  * Olisi hyvä olla työkalu varausjonojen siirtoon, jottei varauksia tarvitse siirtää yksitellen jonosta toiseen.
  * Piia tutkii löytyykö Bugzillasta tikettiä tähän liittyen ja tekee kehitysehdotuksen Githubiin

**Lappi**
* Normaalia ylläpitoa

**Kirkes**
* Normaalia ylläpitoa
* Toistaiseksi on ohjeistettu, että lapselle saa laittaa vain yhden takaajan. Nyt pohditaan, olisiko kahden takaajan mallissa etuja verrattuna nykyiseen. 

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2024#viikko-23) - [Palaa sivun alkuun](/paakayttajat2024)

## Viikko 22

Aika: 28.5.2024 klo 9.15<br />
Läsnä: Päivi Knuutinen, Auli Rantasalo, Irina Halminen, Hanna Hyttinen (Vaara), Pia Kusmin (Lappi), Anni Rajala (Vaski), Piia Semenoff ja Pirkko-Liisa Lauhikari (OUTI), Kati Sillgren (Helle), Janne Seppänen (Lastu), Roosa Väisänen (Kyyti), Annika Helastila ja Elina Uotila (Kirkes)

**Yhteiset asiat**
* [Viikon 22 päivitys](https://github.com/KohaSuomi/Koha/discussions/1250)
* [Testikantojen uusiminen 28.5.2024](https://github.com/KohaSuomi/Koha/discussions/1247)
* [Tietoturvatarkistus](https://github.com/KohaSuomi/Koha/discussions/1245)
* [Asiantuntijaryhmän muistio 7/2024](https://koha-suomi.fi/asiantuntijaryhma2024#asiantuntijaryhm%C3%A4n-muistio-72024) - vielä tarkistamatta ja julkaisematta
* Kesälomat ylös myös [Koha-yhteystiedot](https://github.com/KohaSuomi/Koha/wiki/Koha-yhteystiedot) -wikiin


Pohjoisesta etelään

**OUTI**
* Oulun kaupungin konsernihallinnon talouspuolelta on pyydetty selvittämään, jos hallituksen esitys arvonlisäveron nostosta 24% -> 25,5% menee läpi, mitä se vaatisi tietojärjestelmiltä. Anneli on testannut Kohan osalta, ja Koha tukee veroprosenttina 25,5%. Kirjastoissa pääsääntöisesti budjetit ovat verottomia. Kohan maksutyyppeihin alv-prosentteja ei määritellä. Finnan verkkomaksujen tuotekoodien ylläpito hoidetaan OUTIssa Ceeposin verkkomaksuportaalissa.

**Vaara**
* Mikroväylän lainausautomaatit eivät edelleenkään näytä uusinnoissa eräpäivää näytöllä, kuittiin tulee. Asiaa selvitetty Mikroväylän kanssa.
* Sähköavusteiset kuormapyörät laitettiin varattavaksi Kohan kautta torstaina ja perjantaina otettiin varausmahdollisuus pois päältä, kun tajuttiin, että lakimuutos mahdollisesti tarvittavasta liikennevakuutuksesta tulee voimaan 1.6.2024. Eilen saatiin kuitenkin tieto, että vakuutusta näille kuormapyörille ei tarvita.

**Lappi**
* Noutoryhmät/varausryhmät luotu.
* Normaalia ylläpitoa.

**Vaski**
* Pyydetty kirjastoja ilmoittamaan kesän kiinnioloajat, viedään tieto kirjastojen nimeen.
* Otettu viime viikolla käyttöön hankinnan kuvailupohja (järjestelmäasetus UseACQFrameworkForBiblioRecords). Pohjassa oli oletuksena valtava määrä turhia kenttiä, jotka piti testillä poistaa yksitellen, mutta tuotantoon onnistui viedä testiltä talteen otettu .ods-pohja. Sovittiin vielä palaverissa, että Vaski vie muokkaamansa pohjan jakoon TäTin ACQ-pohjan päälle.
* Hyllyvarausraportille pyydetty niteen viivakoodia, koska lehtivarausten osalta sen tarkistaminen tarvittaessa tietueen kautta on hidasta. Muualta ei ole kuulunut tälle tarvetta, mutta sovittiin että Vaski voi tehdä tästä tiketin. Vaski tarkastelee vielä miten paljon tarvetta on ennen tiketin twkoa. 
* Vaskin toive osittaisesta RDA-konversiosta virheiden välttämiseksi - keskustelunavaun. Sovittiin, että Vaski tekee tukipyynnön ja keskustelua jatketaan siellä. Tiketti: https://github.com/KohaSuomi/Koha/issues/1251

**Helle**
* Yhdessä kirjastossa ollut useampia Tili on lukittu -tapauksia. Kodolta tieto, että liittyvät automaattilainaukseen. Kodolta ohje pyytää automaattitoimittajalta muutos, jonka jälkeen automaatti kysyy joka kerta Kohasta lainausoikeuden.

**Lastu**  
* Suomi.fi-viestit käyttöön käyttöönoton yhteydessä, aloituspalaveri pidetty ja lupahakemus DVV:lle toimitettu. Lahti toimii välitoimijana.
* Raindance-määrittelypalaveri pidetty, tulee käyttöön Lahdessa vuoden 2025 alusta.
* Paikallinen varausryhmä-ominaisuutta testattu esinelainojen yhteydessä, joita ei voi kuljettaa pisteiden välillä. Vaikuttaa toistaiseksi lupaavalta.

**Kyyti**
* Normaalia ylläpitoa.
* Tehty yhdet uudet Koha-tunnukset ja käyty läpi vanhoja tunnuksia.

**Kirkes**
* Lähinnä normaalia ylläpitoa
* 0-vuotiaan hetun tallentamisessa oli samanlaista ongelmaa kuin OUTIssa edeltävällä viikolla. Tiketti asiasta on olemassa [täällä](https://github.com/KohaSuomi/Koha/issues/1252).

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2024#viikko-22) - [Palaa sivun alkuun](/paakayttajat2024)

## Viikko 21

Aika: 21.5.2024 klo 9.15<br />
Läsnä: Anneli ja Emmi (Koha-Suomi), Piia Semenoff ja Pirkko-Liisa Lauhikari (OUTI), Maria Joona, Leena Kinnunen ja Pia Kusmin (Lappi), Päivi Knuutinen, Auli Rantasalo, Irina Halminen, Hanna Hyttinen (Vaara), Reetta Pihlaja (Siilinjärvi), Hanna Ikonen (Lumme), Kati Sillgren (Helle), Annika Helastila ja Elina Uotila (Kirkes), Janne Seppänen (Lastu)

* [Käännöstoive: asiakastakaajan lisäys ja select-nappi #1014 ](https://github.com/KohaSuomi/Koha/issues/1014)
  * Päätös: otetaan käyttöön väliaikaisesti JS-rimpsu
* Tieteellisten Koha-pääkäyttäjien kokouksessa esille tullut CSS-toive: [MARC21-kenttien otsikot näkymään isoilla kirjaimilla](https://github.com/KohaSuomi/kohasuomi.github.io/blob/master/_docs/intranetusercss.md#muuta-marc21-kenttien-otsikot-n%C3%A4kym%C3%A4%C3%A4n-isoilla-kirjaimilla)
* [Viikon 21 päivitys](https://github.com/KohaSuomi/Koha/discussions/1229)
* Varausryhmä-termi hyllyvarausraportin ohjeistukseen, onko ok vai keksitäänkö jokin muu?
  * Poimintaryhmä - pickup group / pickup location group
* [Tiketti #447](https://github.com/KohaSuomi/Koha/issues/447) - otetaanko käyttöön js-rimpsu väliaikaisesti?
  * testataan vielä testeillä erilaisia katkaisuja ja tehdään lopullinen päätös maanantain asiantuntijaryhmässä.

Etelästä pohjoiseen

**OUTI**
* Viime viikolla 0-vuotiaalle lapselle korttia tehdessä ei Sotu-siilo huolinut hänen henkilötunnustaan vaan pyysi tarkistamaan hetun. Ilmeni, että siilon koodi on aluenpitäen kirjoitettu siten, että Sotu-siilo ei huoli 0-vuotiaiden eikä 100-vuotiaiden hetuja. Tämän asiakkaan kohdalla teimme niin, että hänen korttinsa tallennettiin ilman hetua ja kortille lisättiin viesti puuttuvasta henkilötunnuksesta. Kallisen Pasilla on ongelman ratkaisu työn alla.

**Lappi**
* Normaalia ylläpitoa + paljon pieniä korjauksia
* Muistutus Koha-Suomen seuraavasta uutiskirjeestä eli saammeko teiltä uutiset ja kuulumiset tähän pohjaan viimeistään 30.5. https://docs.google.com/document/d/1C1kP8jM8k47VGg_WCSmaeE29cL81IK5jimq2Dth9mbk/edit?usp=sharing

**Vaara**
* normaalia ylläpitoa, testausta ja asetusten tarkastelua
* Peruuta varaus-painikkeen tiketti ok, suljettu
* Varausjonon piilotuksesta tehdään tiketti

**Siilinjärvi**
* tämänaamuinen rajapintakorjaus palautti Siilinjärvi-kuntasovelluksen toimintaan
* työn alle tulossa hankintaportaaliin mahdollisuus tilata osa aineistosta muovitettuna, ainakin Lapissa ja Oulussa tämä tuntui toimivan

**Lumme**
* normaalia ylläpitoa.

**Helle**
* Asiakastieto oli lukittu-tilainen. Lukituksen syy ei ole ainakaan vielä löytynyt. Asiakastiedon lokitiedoissa ei ole merkintää yhdestäkään virheellisestä kirjautumisyrityksestä. Borrowers-taulun login_attempts=0
* Asiakkaan lainatiedot eivät latautuneet Kohassa eivätkä Finnassa. Latautumattomuuden syynä asiakkaalla lainassa olevan tietueen toinen nide, jonka Nidetyyppi-arvona oli ei-käytössä-oleva-arvo. Emmi lisäsi ongelman ratkaisutavan Ongelmatilanteita ja niiden ratkaisuja -dokumenttiin 
https://github.com/KohaSuomi/Koha/wiki/Ongelmatilanteita-ja-niiden-ratkaisuja#asiakkaan-lainat-eiv%C3%A4t-avaudu
* 20.5.2024 POSTPONED-tilainen EditX-sanoma. Sanoma sisällötön.

**Kirkes**
* Pieniä korjauksia ja henkilökunnan kysymyksiin vastaamista on vielä tehty versionvaihdon jäljiltä.
* Palautuskuitin kuittipohjaan ollaan lisäämässä tietoa asiakkaan anonymisoidusta lainahistoriasta. 

**Lastu**
* Pohdittu miten esinelainojen kuljetuksia voisi rajoittaa, Vaarasta vinkki "Oletusvaraussääntö nidetyypeittäin"-ominaisuudesta, jota aletaan testaamaan.
* Puppe-työkalu tulossa käyttöön Lahdessa, tarkka ajankohta ei vielä tiedossa mutta todennäköisesti heti käyttöönoton yhteydessä
* Palaverit Raindance-integraatiosta ja Suomi.fi - viestien käyttöönotosta tulossa

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2024#viikko-21) - [Palaa sivun alkuun](/paakayttajat2024)

## Viikko 20

Aika: 14.5.2024 klo 9.15<br />
Läsnä: Anneli, Kodo ja Pasi (Koha-Suomi), Maria Joona, Leena Kinnunen ja Pia Kusmin (Lappi), Hanna Ikonen ja Katja Valjakka (Lumme), Päivi Knuutinen, Irina Halminen, Hanna Hyttinen (Vaara), Tuomas Kunttu (Kyyti), Pirkko-Liisa Lauhikari ja Piia Semenoff (OUTI), Kati Sillgren ja Lotta Juvonen (Helle), Mikko Liimatainen (Vaski), Annika Helastila (Osan ajasta) ja Elina Uotila (Kirkes), Reetta Pihlaja (Siilinjärvi)

**Asiat**
* [Viikon 20 päivitys](https://github.com/KohaSuomi/Koha/discussions/1206)
* [Täti: Mitä JavaScript-rimpsuja Tätiin tarvitaan?](https://github.com/KohaSuomi/Koha/issues/1201)
* [Kohan omat auktoriteetit ja suurennuslasit teoksen perustiedot näytöllä #181](https://github.com/KohaSuomi/Koha-23x/issues/181)
  * Miten muissa kimpoissa asetukset? Tarviiko tehdä muutoksia?
* [Asiakasmääreen SSN haettavuus-ominaisuuden poistamisyrityksestä Virhe 500 #165 ](https://github.com/KohaSuomi/Koha-23x/issues/165)
  * OUTI, Lappi, Kyyti - tarviiko tehdä korjauksia? Jos ei, tiketin voisi sulkea.
* Uudet CSS-rimpsut: [Levennä otsikkokenttiä asiakkaan muokkauksessa](https://koha-suomi.fi/dokumentaatio/intranetusercss/#levenn%C3%A4-otsikkokentti%C3%A4-asiakkaan-muokkauksessa) tai [Levennä otsikkokenttiä](https://koha-suomi.fi/dokumentaatio/intranetusercss/#levenn%C3%A4-otsikkokentti%C3%A4)

Pohjoisesta etelään

**Lappi**
* Tarkistellaan vielä versionvaihdon muutoksia ja viimeisiä asetuksia kohdilleen.
* 15.5. pidetään Kysy Kohasta -tunti koko Lapin henkilökunnalle.
* Ranuan SmartBox on asennettu ja käyttöönottokoulutus pidetään 14.5.

**Lumme**
* Koha yskähteli aamulla, saatiin takaisin toimintaan.
* Käyty läpi henkilökunnan raportoimia bugeja ja viilattu asetuksia.
* Kohasta hävinnyt yksi vastaanotettu lehti. Näkyi vastaanotetuissa, mutta ei kuitenkaan tietueissa. Syy jäi toistaiseksi arvoitukseksi, tilannetta seurataan.

**Vaara**
* Hankinnan vastaanotosta tuli tieto, että ei pysty vastaanottamaan nidettä, kun Tilaaja: Tili on poistettu -teksti on näkyvissä. En tiedä, eikö käyttäjä oikeasti pystynyt vastaanottamaan, vai hämäsikö teksti vain käyttäjää, sillä Päivi sai niteen vastaanotettua. Tein tästä kaksi tikettiä, toisen käännöksen virheestä ja toisen siitä, että käyttäjän tunnus pitäisi näkyä. Tiketit #42 ja #1217
* Irina testannut Uusinta-painikkeen piilotusta Lainaus ja palautus-näytön vasemmasta valikosta ja myös varauksen peruutukseen liittyviä toimintoja.

**OUTI**
* Kohan palautuskehotusautomatiikasta oli tullut asiakaspalautetta. Asiakas oli närkästynyt, kun hän oli saanut arkipyhänä (helatorstaina) palautuskehotuksen. Harmillisesti kirjasto, jota asiakas käyttää, oli kiinni helatorstaina. Koha-tuessa totesimme, että vastaavia tapauksia tulee varmaan jatkossakin. Olisi aivan liian iso homma ottaa arkipyhät huomioon kirjastojen kalentereissa niin, ettei 1. ja 2. palautuskehotusten lähetyspäiviä sattuisi arkipyhille.
* OUTI-kirjastojen esihenkilöille on lähetetty koko kimpan henkilökunnan Koha-käyttäjätunnusten oikeuksien tarkistuslistat. Koha-tuki käy kesän aikana läpi tarkistetut listat ja päivittää tunnuksille tarvittavat oikeusmuutokset.

**Helle**
* Paikallinen kirjailija on pyytänyt pois syntymäaikansa teostensa tietueiden tekijätiedosta. Helle-tietueista on nyt poistettu ko. kirjailijan syntymäaika ja estetty tietueiden automaattinen päivitys (kenttä 942b).
Kirjailijaa on ohjeistettu ilmoittamaan muutostarve Toimijakuvailupalveluun.
* Tiedonhaun hakutuloksen fasetteihin on lisätty nämä kaksi tietueen YKL-luokka-arvoihin perustuvaa fasettia: 
YKL Kaunoluokat, YKL Tietoluokat
* Kuvailu-osioon on lisätty Tietuesiirtäjä-linkki

**Vaski**
* Sotu-siiloon tallentamisessa ollut epäselvyyttä. Asiakastietuetta ei huoata tallentaa hetun tallentamisen jälkeen, jolloin sotu-avain ei tallennu tietueeseen.
* Lainausta tehdessä aikakatkaisu voi aiheuttaa kirjautumisluupin, jossa Koha vaatii sisäänkirjautumisen jokaisen lainauksen jälkeen. Niteet menevät kuitenkin lainaan. Joissakin tapauksissa havaittu myös kirjautuneen käyttäjän kotikirjaston vaihtuneen samalla.
* Vaski-Finnaan on julkaistu kirjastonkäytön säästölaskuri.

**Kirkes**
* Tilauksen muokkausnäkymässä on havaittu arvo -1 "Ei lainattavissa" -sarakkeessa tekstiselitteen sijaan. Korvaushinta-kentästä on puuttunut sadasosan nolla ja desimaalierottimena on piste, vähittäishinnassa ja todellisessa hinnassa desimaalierottimena on pilkku. Sadasosat näkyvät vaihtelevasti. Seurataan tilannetta, esiintyykö omituisuuksia esim. tiettyjen aineistojen kohdalla.
* Sekä henk.koht että työkortin lainoissa on näkynyt valmiiksi uusi laina -täppä, mutta uusi valitut lainat -painike oli harmaana. Painike aktivoitunut, kun täpän on poistanut ja laittanut uudelleen päälle.
* Lauantaina lainatun aineiston "Ei uusintaa ennen" -päivä on mennyt seuraavalle tiistaille, joka on aiheuttanut hämmennystä.

**Siilinjärvi**
* Ei kai mainittavaa.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2024#viikko-20) - [Palaa sivun alkuun](/paakayttajat2024)

## Viikko 19

Aika: 7.5.2024 klo 9.15<br />
Läsnä:

**Asiat**
* Versionvaihdon kuulumiset

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2024#viikko-19) - [Palaa sivun alkuun](/paakayttajat2024)

## Viikko 18

Aika: 30.4.2024 klo 9.15<br />
Läsnä: Iina Niemi (Vaski), Piia Semenoff ja Pirkko-Liisa Lauhikari (OUTI), Anneli Österman ja Lari Strand (Koha-Suomi), Päivi Knuutinen, Auli Rantasalo, Hanna Hyttinen (Vaara), Annika Helastila ja Elina Uotila (Kirkes), Janne Seppänen (Lastu), Lotta Juvonen ja Vilgot Strömsholm (Helle), Tuomas Kunttu (Kyyti)

**Asiat**
* Testiversionvaihdon kuulumiset
  * Ei ehditty vielä tehdä. Tänään uusi yritys.
* [Tiedonhaussa nimekkeellä järjestämiseen tullut muutos, joka vaatii Elasticsearchin mäppäysten resetoinnin ja uudelleenindeksoinnin #93](https://github.com/KohaSuomi/Koha-23x/issues/93)
  * järjestettäviksi kentiksi määritettiin 245abp-kentät. Olisiko tarvetta määrittää myös 245n eli osan numero järjestettäväksi?
  	* Päätös: lisätään myös 245n
  * Esim. outi-nextillä Jukola-teokset menevät nyt osan nimen mukaan järjestykseen, ei numeron mukaan.
	![kuva](https://github.com/KohaSuomi/kohasuomi.github.io/assets/33121325/308961c8-eb9c-427b-98ae-94ee7fa4deb7)
* Osa onkin jo laittanut tikettiä viestityksen käynnistämisestä versiovaihdon jälkeen. Miten muut haluavat viestityksen käynnistyksen? Käytännössä ei voi valita, mitkä viestit lähtevät, vaan joko kaikki lähtee tai mitään ei lähde.
  * Tehkää Koha-23-tietovarantoon jokaisesta kimpasta oma tiketti, milloin haluatte viestien lähtevän versionvaihdon jälkeen. 
* [Erääntyneille varauksille asetettavaksi erikoistila varauksen vanhenemisen yhteydessä](https://github.com/KohaSuomi/Koha/issues/1100)
  * Käykää lisäämässä kimpan notforloan-arvot tikettiin, niin etsitään jokin sopiva varauksia varten.
* Onko kiinnostusta laittaa päälle [tiketin 129](https://github.com/KohaSuomi/Koha-23x/issues/129) asetusta?

Etelästä pohjoiseen

**Vaski**
* Ei raportoitavaa

**OUTI**
* Mietimme onko kiireetömän varauksen yhteydessä näkynyt teksti "Kiireetön varaus" myös nidevarausten kohdalla? Tällä hetkellä nextillä ja tuotannossa tieto kiireettömästä varauksesta näkyy vain tietueen varausjonossa ns. normaalin varauksen kohdalla. Kiireettömät varaukset eivät erotu normivarauksista asiakkaan varauksissa eivätkä kiireettömät nidevaraukset tietueen varausjonossa.

**Vaara**
* Hankintatilastot ihmetyttävät, ei saada samoja lukuja eri raporttien kautta. Jatketaan ihmettelyä versionvaihdon jälkeen.
* Testausta muiden töiden ohessa.

**Kirkes**
* Muutamalla asiakkaalla on varaus tarttunut vanhentuvien noutamattomien varausten ajoon, vaikka on todellisuudessa ollut jo pari päivää asiakkaalla lainassa. Tutkitaan asiaa tarkemmin varmaan versionvaihdon jälkeen. Tällä hetkellä versionvaihdon testaukset etusijalla. 
* Keravalla ollut tapaus, jossa aikakatkaisun jälkeen kirjautuessa virkailijan toimipiste on vaihtunut toiseksi. Seurataan tilannetta ja tehdään tarvittaessa tiketti.

**Lastu**
* Virkailijaoikeuksien tarkastelu ja käyttäjäryhmien luominen jatkuu

**Helle**
* Selvittellään ongelmaa joka alkoi viime viikon torstaina että koko Helle-Koha jumittuu silloin tällöin. Ongelma tulee Askolan alueen kirjastoista missä ei onnistu aineston uusiminen ja palautus/lainaus, joka lopuksi vie kaikki Helle-Kohan workerit.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2024#viikko-18) - [Palaa sivun alkuun](/paakayttajat2024)

## Viikko 17

Aika: 23.4.2024 klo 9.15<br />
Läsnä: Anneli Österman, Kodo Korkalo ja Pasi Kallinen (Koha-Suomi), Pirkko-Liisa Lauhikari ja Piia Semenoff (OUTI), Päivi Knuutinen, Auli Rantasalo ja Hanna Hyttinen (Vaara), Leena Kinnunen ja Pia Kusmin (Lappi), Hanna Ikonen (Lumme), Tuomas Kunttu (Kyyti), Annika Helastila ja Elina Uotila (Kirkes), Kati Sillgren (Helle), Reetta Pihlaja (Siilinjärvi), Janne Seppänen ja Lauri Hänninen (Lastu), Mikko Liimatainen (Vaski)

**Yhteiset**
* [Palautuskuitille tieto, jos asiakkaan lainahistoria on anonymisoitu](https://github.com/KohaSuomi/Koha/issues/1153) - testattu toimivaksi muutamassa kimpassa. Kuittipohjan voi muuttaa uudenlaiseksi kimpan päätöksen ja aikataulun mukaisesti.
* [Salasanan vanhenemistoiminto](https://github.com/KohaSuomi/Koha-23x/issues/98) - Miten toimitaan vanhentuneiden käyttäjätunnusten kirjautumisen estämisessä? Mennäänkö uudella salasanan vanhenemistoiminnolla vai pysytäänkö vanhassa tavassa?
  * Keskusteltiin aiheesta ja päätettiin viedä asia asiantuntijaryhmän päätettäväksi.
  * Useampi kannatti, että tämä koskisi vain virkailijatunnuksia.
* [Viikon 17 päivitys](https://github.com/KohaSuomi/Koha/discussions/1164)

Pohjoisesta etelään

**OUTI**
* Testaajat olivat huomanneet nextillä, kun olivat testanneet varauksen noutoaikoja:
  * Jos varaukselle on annettu sen tekovaiheessa joku viimeinen voimassaolopäivä tai jos varauksella on järjestelmän antama oletusvoimassaoloaika, niin järjestelmä antaa ko. päivän myös varauksen viimeiseksi noutopäiväksi, jos varus jää kiinni esim. edellisnä päivänä, kun varauksen voimassaoloaika päättyy.
  * Jos varauksen viimeisen voimassaolopäivän käy vaihtamassa teoksen varausjonossa, varaus saa noutoajaksi normaalin järjestelmäasetuksessa määritellyn ajan, vaikka varaus olisi jäänyt kiinni edellisenä päivänä, kun varauksen voimassaolopäivä päättyy.
  * Toimii näin myös tuotannossa.
  * Tehdään tiketti githubiin.
* Onko muilla huomioita, että Tietuesiirtäjän valutuksen yhteydessä osakohteisiin ei muodostu aina aineistotyypit 942c-kenttään. Toimintoa on korjattu, mutta vieläkään tämä ei toimi kunnolla. Välillä valutuksen yhteydessä aineistotyypit muodostuvat 942c-kenttään ja välillä ei. Välillä tapahtuu niinkin, että osakohteilla jo olleet aineistotyypit lähtevät pois, kun tietue valuu uudestaan, koska siihen on tullut päivitys. Kommentoidaan tikettiin #915.
* Jäälin kirjasto menee kiinni 3.6.-6.8.2024. Jäälin monitoimitalossa tehdään korjaustöitä siinä siivessä, jossa kirjasto sijaitsee, joten kirjastoa ei voida pitää auki. Sulkutoimenpiteitä mietitty.

**Vaara**
* Tehty tukipyyntötiketti raportin laatimisesta hankintojen listaamisesta OKM-raporttia vastaavasti.
* Asiakkaalta verkkokirjastosähköpostiin tullut anonyymi ehdotus jäädytettyjen varausten erottamisesta normaaleista varauksista. 
Jäädytetyt varaukset näkyvät voimassa olevien varausten kanssa samassa lukumäärässä. Ongelma myös virkailijatyökalussa. Päivi tekee
tiketin GitHubiin ja myös kyselyn Finna-toimistoon.

**Lappi**
* Rovaniemen niteiden muutosajo jumitti kaikki Lapin varaukset. Ei voinut varata eikä lainata varauksia. Ajo keskeytettiin ja suoritettiin uudelleen yöllä, jolloin kaikki meni hyvin.
* Sotuteekin tunnuksia jumissa myös Lapissa. Saatu korjattua.
* Versionvaihtoon liittyviä töitä.
* Normaalia ylläpitoa.

**Lumme**
* Normaalia ylläpitoa.
* Finna-Nextille vietiin uudet API-avaimet ja saatavuustiedot alkoivat näkymään normaalisti.
* Laskuttajalta tuli kysymys siitä, että tuleeko Ilmoittaa palauttaneensa -tilassa olevat niteet laskuille. Kohassa kyseiset niteet näkyvät olevatn normaalisti lainassa, mutta niteen tiedoissa näkyy "Ilmoittaa palauttaneensa". Tässä tilassa olevat niteet näyttävät tulevan laskutustyökalun listalle. Tehdään kehitysehdotus, että LOST-tilassa oleva aineisto voitaisiin rajata laskutuksen ulkopuolelle niin halutessa.

**Kyyti**
* Kyytiin on tekeillä muutama nidepaketti. Kun nidepakettiasetukset laittaa päälle, tulee Nextillä näkyviin kaikille asiakkaille reklamaatiot-välilehti. Nykyisessä versiossa ei tule. Koska nidepakettien käyttö on hyvin vähäistä, näkyy uusi välilehti turhaan kaikilla asiakkailla. Tehty tiketti, josko saisi välilehden piiloon jollain IntranetUser-rimpsulla.
* Kyytissä otettu tuotannossa käyttöön anonymisoitujen lainojen palautuskuitti
* Tietuesiirtäjä otettu tänään käyttöön. Heti tuli kuvailijalta ilmoitus, että pari vanhaa tietuetta on valunut. Lisäksi toivottiin, että tietuesiirtäjän avaa-nappi vaihtaisi väriä painamisen jälkeen, kuten aiemmin.

**Kirkes**

* Järvenpäässä on huomattu, että omatoimikirjastoon pääsee kirjautumaan vanhentuneella kirjastokortilla. Kirjautuminen näkyy omatoimikirjaston hallinnassa onnistuneena, mutta asiakkaan lokilla ei ole Kohassa sip-kyselyä ollenkaan. Elina selvittää asiaa Lyngsoelta. 
* Tuplamaksuja saaneen asiakkaan tapaus on edelleen selvityksessä (tiketti [#1157](https://github.com/KohaSuomi/Koha/issues/1157)), mutta siihen liittyen päätettiin selkiyttää maksujen kertymistä vaihtamalla ChargeFinesOnClosedDays-järjestelmäasetuksen arvoksi "laskuta".

**Siilinjärvi**
* Ei mainittavaa. Yritetään ottaa loppukiri versionvaihtotöissä.

**Lastu**
* Virkailijaoikeuksia ja niiden pohjalta käyttäjäryhmiä pohtiessa heräsi ajatus, voisiko asiakasmääreitä hyödyntää virkailijaoikeuksien asettamisen automatisoinnissa. Tämä sai kannatusta, joten tästä on palaverin jälkeen tehty kehitysehdotus [#1169](https://github.com/KohaSuomi/Koha/issues/1169)

**Vaski**
* Automaattiverkkoon tehdään muutoksia ja toivomme automaattien toimivan vielä aamullakin.
* Atk-ajot Turussa to-pe ja kaikki pääkäyttäjät osallistuvat.
* Nextin testaus etenee hyvin.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2024#viikko-17) - [Palaa sivun alkuun](/paakayttajat2024)

## Viikko 16

Aika: 16.4.2024 klo 9.15<br />
Läsnä: Anneli Österman, Kodo Korkalo, Lari Strand (Koha-Suomi), Pirkko-Liisa Lauhikari ja Piia Semenoff (OUTI), Leena Kinnunen ja Pia Kusmin (Lappi), Kati Sillgren ja Lotta Juvonen (Helle), Hanna Ikonen ja Katja Valjakka (Lumme), Annika Helastila ja Elina Uotila (Kirkes), Päivi Knuutinen ja Irina Halminen (Vaara), Reetta Pihlaja (Siilinjärvi), Mikko Liimatainen (Vaski)

**Yhteiset**
* Versionvaihdon tarkempi aikataulu
  * palvelut laitetaan kiinni su 5.5.2024 klo 19 ja aloitetaan päivitysskirptien ajo. Ne on toivottavasti saatu ajettua läpi noin klo 22.
  * ma-aamuna 6.5.2024 jatketaan töitä ja jos kaikki on mennyt hyvin, päästään jo aamusta testaamaan.
  * Kaikki toiminnot ja palvelut on tarkoitus saada toimimaan ti 7.5.2024 puoleen päivään mennessä.
  * [Versionvaihdon tiedote 3](https://github.com/KohaSuomi/Koha/discussions/1154)
  * Pidetään ma 6.5.2024 klo 10 väliaikapalaveri, jossa käydään läpi, missä mennään ja miltä näyttää.
* [Nextiltä tuotantoon kopioitavat tiedot](https://github.com/KohaSuomi/Koha-23x/issues/121)
* [Tarkka haku -toimintoon paluu hakutuloksen Muokkaa hakua -linkistä muuttaa tehdyn haun hakutyypin](https://github.com/KohaSuomi/Koha/issues/663)
  * Ehdotuksena, että viimeisimmissä kommenteissa mainitut rimpsut laitettaisiin nexteille ja sieltä sitten tuotantoon.
* IntranetUserJS-rimpsut ja niiden plugarisointi - käydään läpi Larin keräämä listaus [intranetuserjs_22x.ods](https://github.com/KohaSuomi/kohasuomi.github.io/files/14978767/intranetuserjs_22x.ods).
* [Pääkäyttäjien versionvaihdon muistilistaa](https://github.com/KohaSuomi/Koha-23x/wiki/P%C3%A4%C3%A4k%C3%A4ytt%C3%A4jien-muistilista) voi täydennellä aina, kun hoksaa jotain.
* [Palautuskuitille tieto, jos asiakkaan lainahistoria on anonymisoitu](https://github.com/KohaSuomi/Koha/issues/1153)


Etelästä pohjoiseen

**OUTI**
* Ei mitää erityistä, ollut normaalia tukityötä.
* Versionvaihdon testausta.

**Lappi**
* Uuden version testailua.
* Lapissa oli 5.4. e-kirjeet jumittaneet ja huomattiin vasta eilen. Korjattiin varaukset ja myöhästymismaksut. Miten Faild-tilalliset saa pois listoilta? Voidaan poistaa kehittäjän toimesta, mutta poistuvat samalla myös asiakkaan viesteistä.

**Vaara**
* Yhteisöasiakkailla ei ollut pääsyä Ellibsiin. Havaittu syyksi se, että heillä ei ole asiakastiedoissa ikätietoa (ajettu pois). Ei ole Vaaran osalta enää suuri ongelma, sillä siirtyminen uuteen e-kirjastoon tapahtuu viikon päästä. Muille Ellibsiä pitempään käyttäville tiedoksi.
* Noutamaton varaus ja saatavana-tila  aiheuttanut hämminkiä omatoimikirjastossa viikonloppuna (asiakas katsonut Finnasta, että nide on hyllyssä ja löytyikin varaushyllystä). Keskusteltiin, että tiketti [#1100 ](https://github.com/KohaSuomi/Koha/issues/1100) on menossa asiantuntijaryhmään ja mahdollisesti saataisiin korjaus/muutos asiaan.
* Sotuttomia asiakkaita siivottu ja yhdistelty.

**Lumme**
* Perusylläpitoa.
* Ei-aktiivisten asiakkaiden poistoajo aloitettu ja jatkuu vielä.
* Törmättiin tilanteeseen, jossa asiakkaan kahden kortin yhdistämisessä toisella kortilla ollut taattava ei siirtynyt korttien yhdistämisessä aktiiviseksi jätetyn kortin alle. Ongelmasta tarkoitus tehdä tiketti yhteisöön.

**Kirkes**
* Käyty läpi intranetuserjs- ja intranetusercss-rimpsuja Nextillä ja samalla testattu/räätälöity Vaskin jakamaa "Lisää käyttäjäoikeudet" -rimpsua, joka vaikuttaa oikein toimivalta.
* Ihmetystä herättänyt tapaus, jossa asiakkaalle on muodostunut maksimimäärä myöhästymismaksua samasta lainasta kahteen kertaan. Tiketti tehty [#1157](https://github.com/KohaSuomi/Koha/issues/1157)

**Siilinjärvi**
* Ei mainittavaa
* Palvelinpäivityksestä 10.4. aiheutunut aamulla pitkä Koha-katko. Tilanteesta selvittiin.

**Vaski**
* Versiopäivityksen aloitusajankohdasta olisi toivottu saatavan tieto hieman aiemmin, kun olimme ehtineet tiedottamaan katkosta ennen kuin tiesimme päivityksen alkavan jo sunnuntaina.
* Nextin tiketöintiin toivottu paremmin tietoa kenen vastuulle testaaminen kuuluu, jotta tikettiten läpikäynnissä ei tarvitse jatkuvasti käydä läpi samoja tikettejä.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2024#viikko-16) - [Palaa sivun alkuun](/paakayttajat2024)

## Viikko 15

Aika: 9.4.2024 klo 9.15<br />
Läsnä: Anneli Österman ja Johanna Räisä (Koha-Suomi), Leena Kinnunen, Pia Kusmin (Lappi), Anni Rajala (Vaski), Hanna Ikonen (Lumme), Piia Semenoff ja Pirkko-Liisa Lauhikari (OUTI), Tuomas Kunttu (Kyyti), Irina Halminen ja Hanna Hyttinen (Vaara), Annika Helastila ja Elina Uotila (Kirkes)

**Yhteiset**
* [Pääkäyttäjän tehtävät](https://github.com/KohaSuomi/Koha/wiki/P%C3%A4%C3%A4k%C3%A4ytt%C3%A4j%C3%A4n-teht%C3%A4v%C3%A4t) -listaus. Puuttuko jotain tai pitäisikö jotain poistaa?
* [Huoltoikkuna ke 10.4.2024](https://github.com/KohaSuomi/Koha/discussions/1144)
* [Bugi-perjantai 26.4.2024](https://github.com/KohaSuomi/Koha/discussions/1148)
* Kohan ohje suomeksi -päivitysvastuut, pohjaksi [edellisen versionvaihdon tiketti](https://github.com/KohaSuomi/Koha/issues/549)
  * [Kohan ohje suomeksi -muotoiluohjeistus](https://github.com/KohaSuomi/kohasuomi.github.io/wiki/Kohan-ohje-suomeksi--muotoiluohjeistus)
  * Päivitysvastuut kirjattu [tikettiin](https://github.com/KohaSuomi/Koha/issues/1150)
  * tavoitteena saada ohjeet päivitettyä syyskuun 2024 loppuun mennessä.
* [Nextiltä tuotantoon siirrettävät tiedot](https://github.com/KohaSuomi/Koha-23x/issues/121)
  * käydään läpi viikon 16 palaverissa, miettikää sitä ennen, tuleeko muita ehdotuksia/tarpeita mieleen ja kirjatkaa ne tikettiin. 

Pohjoisesta etelään

**Lappi**
* IntranetuserJS- ja IntranetuserCSS-asetukset verrattu tuotannosta ja versiopäivityksen ohjeesta. Käydään läpi vielä, lisätäänkö jotain vapaaehtoisia säätöjä. 
* Käyttäjäryhmä aloittanut nextin testaamisen
* Pääkäyttäjät Lapin kirjastopäivillä 10.-11.4., hoidetaan vain kiireeliset tehtävät

**Vaski**
* Elokuvien Vaski-tasoisen kellutuksen valmisteluun liittyen on päätetty ottaa käyttöön yhteiset kokoelmakoodit. Tällä hetkellä Vaskissa elokuvien erinäiset tarkemmat sijoittelutiedot on olleet konversion jäljiltä "Yleinen huomautus" -nidekentässä.
* Jaetaan nextin osoite koko henkilökunnalle, yleensä tosin aika harva innostuu testaamaan.
* Turun pk:n palautusautomatiikan uusiminen käynnistyy, iso projekti. Pääkäyttäjät menossa tutustumiskäynnille pääkaupunkiseudulle 19.4.

**Lumme**
* Normaalia ylläpitoa.
* Finnan kautta oli tullut paljon vääriä kirjautumisyrityksiä huollettaville, vaikka tunnukset ovat oikein. OUTI on tehnyt tästä tiketin.
* Gmail-osoitteita käyttäville asiakkaille oli mennyt myöhästymismuistutuksia roskapostiin. Henkilökuntaa opastettu tämän asian ohjeistamisessa asiakkaille.

**OUTI**
* OUTIn Finna-tuella selvityksen alla miten saadaan Finna-nextillä Kooste: -teksti piilotettua. Nykyinen Kooste-kohtien piilotus pakottaa Kooste-kohtiin ruksit, mutta noutoviestien kooste-ominaisuus ei tuohon pakotukseen OUTIssa käy. 
* Omatoimi-kirjasto otetaan käyttöön kesällä Muhoksella. Muhoksen lapsiasiakkaille on sallittu omatoimikäyttö uusia kortteja tehdessä. Huoltajien viesteihin on tarkoitus lisätä ajona hoksautus, että lapsella on omatoimikäyttö sallittu. Huoltajia on noin 500. Viesti tulisi näkymään myös verkkokirjastossa. 16 vuotta täyttäneiden asiakkaiden huoltajilta, joille tuo viesti on lisätty, otetaan viesti pois. Viestien poistamisen työkaluna käytetään sitä varten tehtyä raporttia.
* 776-kentän (useita ulkoasuja) tiedot näkyvät Kohassa hassusti tietueen perusnäytöllä esim: Useita ulkoasuja: Ei otsikkoa; Ei otsikkoa.. 776i tai 776z- kenttien piilotus ei auttanut. Finnassa kyseinen kohta näkyy siten, että ISBN:n perässä lukee FENNI KEEP. Anneli tutkaili palaverin aikana, että ehkä 776t-kentän täyttäminen auttaisi. OUTIssa jatkamme asian tutkimista Nextillä.
* Käyttäjätunnuksen lukkiutuminen, kun Finnassa liitetyn kortin PIN on vaihdettu. Tarkempi ongelman kuvaus tiketissä: 5 https://github.com/KohaSuomi/koha-plugin-rest-di/issues/5
  * Samaa ongelmaa on havaittu myös muissa kimpoissa.
* Laskutuksen keskeytys viikolla 19 (versiovaihdosviikko). Laskutuksen pitäisi toimia ihan ok versionvaihdon jälkeen, joten laskutuksen voi aloittaa jo viikolla 20, mutta pienesti.
  
**Vaara**
* Normaalia ylläpitoa, ei ongelmia.
* OUTIn mainitsema käyttäjätunnuksen lukkiutuminen huomattu myös Vaarassa (ks. OUTIn tiketti 5).

**Kyyti**
* Eräällä paljon tarroja tulostavalle on tarratulostustyökalun Itse tulostetut -listaan kertynyt niin paljon niteitä, että selain hyytyi niitä ladatessa. Tiketti [1146](https://github.com/KohaSuomi/Koha/issues/1146). Asiaan on jo tehty korjaus.
* Asiakkaan valitusta muuttuneesta sijasta varausjonossa selvitellessäni ihmettelin, että nimeketietueen varausjonossa voi muuttaa myös varauksen teko päivämäärää. Varausjonoa tarkastellessa ei siis voi mistään päätellä koska varaus on alunperin tehty, jos päivämäärää ja sijaa jonossa on muutettu. Myöskään suoraan reserves-taulusta ei sitä tietoa löydy. Ilmeisesti nämä muutokset eivät kuitenkaan näy lokeilla, joten varauslokeja tarkastellessa näkee alkuperäisen varauksen tekopäivän ja sijan. Mutta jos varauksia on kymmeniä tai satoja, on sieltä tällaisen muutetun varauksen löytäminen todella työlästä.
* Pyhtään uuden automaatin lainojen uusinta -ongelmaa on lähdettu ratkomaan automaattitoimittajalta. Toistaiseksi ei ole saatu vastausta. Tiketti [1137](https://github.com/KohaSuomi/Koha/issues/1137)

**Kirkes**
* Kuvailijoilta tullut kyselyjä kiinteämittaisten kenttien ja aineistotyypin vastaamattomuudesta. Tällaista ei pääsääntöisesti pitäisi olla, koska konversiossa aineistotyyppi määritettiin nimenomaan kiinteämittaisten kenttien mukaan. Ilmeisesti ongelma koskee lähinnä moniviestimiä, joissa osassa on toistettu 007-kenttää ja osassa ei.  

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2024#viikko-15) - [Palaa sivun alkuun](/paakayttajat2024)

## Viikko 14

Aika: 2.4.2024 klo 9.15<br />
Läsnä: Päivi Knuutinen ja Irina Halminen (Vaara), Pirkko-Liisa Lauhikari ja Piia Semenoff (OUTI), Lotta Juvonen (Helle), Kati Sillgren (Helle), Leena Kinnunen (Lappi), Tuomas Kunttu (Kyyti), Mikko Liimatainen (Vaski), Annika Helastila ja Elina Uotila (Kirkes)
 
**Yhteiset**
* Nextien laajempi testailu alkakoon
* Ensimmäinen [uutiskirje julkaistu](https://github.com/KohaSuomi/Koha/discussions/1139)

Etelästä pohjoiseen

**Vaara**
* ei mitään erityistä mainittavaa

**OUTI**
* Palaverin aikana tuli tieto, ettei Koha-Ceepos-maksurajapinta toimi, tulee virheilmoitus:
  ![image](https://github.com/KohaSuomi/kohasuomi.github.io/assets/98814860/b05765f2-49a4-4f36-aeb9-fdc1314b4fc7)
  
  Ongelmasta laitettu sekä CPU:lle että Koha-Suomen support-sähköpostiin.
* Githubissa on suljettu tiketti https://github.com/KohaSuomi/Koha/issues/280 eli siinä meillä on ollut ongelmana, kun niteen hankintapäivä on 0000-00-00, asiakkaan varaukset eivät näy Finnassa.  OUTIssa tuli vastaan tapaus, jossa yhden lehtiniteen viimeksi lainattu pvm. oli 0000-00-00, joka esti myös parilla asiakkaalla varausten näkymisen Finnassa. Sovittiin, jos tapauksia tulee vastaan enempi, avataan tiketti uudestaan.
* OUTIssa mennään kahdella pääkäyttäjällä varmaan ainakin kesään asti.

**Lappi**
* Rovaniemen pääkirjastossa on alkanut pakkaus väistöön siirtymistä varten.
* Muuten rauhallista.

**Helle**
* Uudessa versiossa otetaan käyttöön taattavan sähköpostiviestin lähetys myös takaajalle, jos ominaisuus toimii (RedirectGuaranteeEmail-järjestelmäasetus). Meneekö viesti kaikille taattavan takaajille? Tehty tiketti palaverin jälkeen [#127](https://github.com/KohaSuomi/Koha-23x/issues/127#issuecomment-2031968332)

**Kyyti**
* Pyhtään uuden automaatin ongelma [tiketti 1137](https://github.com/KohaSuomi/Koha/issues/1137)

**Vaski**
* Muutamia remontteja menossa/valmisteilla

**Kirkes**
* Ei mainittavaa

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2024#viikko-14) - [Palaa sivun alkuun](/paakayttajat2024)

## Viikko 13

Aika: 26.3.2024 klo 9.15<br />
Läsnä: Iina Niemi (Vaski), Lotta Juvonen (Helle), Maria Joona, Leena Kinnunen ja Pia Kusmin (Lappi), Anneli Österman ja Pasi Kallinen (Koha-Suomi), Päivi Knuutinen ja Irina Halminen (Vaara), Kati Sillgren (Helle), Pirkko-Liisa Lauhikari ja Piia Semenoff (OUTI), Hanna Ikonen (Lumme), Tuomas Kunttu (Kyyti), Annika Helastila ja Elina Uotila (Kirkes)

**Yhteiset**
* Viikolla 14 voi päästää muitakin kuin pääkäyttäjiä testaamaan nextejä.

Pohjoisesta etelään

**Vaski**
* Normaalia ylläpitoa

**Lappi**
* Rovaniemen remontin vuoksi kirjasto siirtyy Asemakirjastoon (entinen linja-auto-asema). Varausten siirtoon liittyen on tehty kolme tikettiä : 1132, 1133 ja 1134. Näissä on määräpäivänä 12.4. sekä 30.4. (tiketti 1132). 
* Omatoimikirjastoissa sallitut asiakaslajit ovat vain henkilö, huollettava (muu kuin lapsi), lapsi ja lapsi omatoimi. Kotipalveluasiakkaiden pääsy pitää lisätä omatoimikirjastoihin. 
* Käyttäjäryhmä on jonkin verran käynyt jo tutkimassa nextiä, ja pääkäyttäjät ovat hoitaneet asetuksia kuntoon.

**Vaara**
* Tietuesiirtäjä otettu käyttöön tänä aamuna.
* Työn alla huoltajalle lähetettävä viesti, kun lapsen tiedoista puuttuu henkilötunnus. (tiketti https://github.com/KohaSuomi/Koha/issues/865)
* Kuunteluoppilaana aloitti Hanna Hyttinen, josta tulee uusi pääpääkäyttäjä Vaaraan Päivin jälkeen

**OUTI**
* Muhoksen ja Pyhäjoen kirjastoissa otetaan käyttöön omatoimilaitteistot. Sip-tunnukset tehty ja toimitettu Koha-Suomelle ja laitetoimittajille.
* Anneli kysyy tieteellisiltä, tuleeko heille lainaustilanteessa sinistä huomautusilmoitusta, jossa tällä hetkellä näkyvät Koha-Suomen kimpoilla asiakkaan yksityisoikeudelliset maksut. Jos asiakkaalla on myös julkisoikeudellisia maksuja, ilmoituksen teksti antaa virheellisen tiedon asiakkaan maksuista. Jos tieteellisille sopii, Koha-Suomessa muutetaan huomautuksen tekstiksi: "Asiakkaalla on maksamattomia maksuja, jotka eivät vaikuta lainauskieltoon: XX,XX €". Tiketti: https://github.com/KohaSuomi/Koha-translations/issues/39

**Lumme**
* Normaalia ylläpitoa.
* Hyllyvarausraportissa värikoodaus on todettu toimivaksi, kun poimitaan varauksia ja varattu nide sijaitsee varauksentekokirjastossa. Nyt toivottiin värikoodausta, kun varaus sijaitsee saman seudun alueella kuljetusten helpottamiseksi. Tästä tehdään kehitysehdotus. 

**Kyyti**
* Tiedonhaku kokoelmatyössä koulutukseen raportit laitettu Kyytiin.
* Muutama tulevan version testitiketti testattu toimivaksi.
* Pyhtään uuden automaatin lainojen uusinta -toiminnossa on jokin ongelma. [Tiketti 1137](https://github.com/KohaSuomi/Koha/issues/1137)

**Kirkes**
* Yhden kunnan tietohallinnossa on ollut halua Firefoxista luopumiseen, ja luopumista on perusteltu tietoturvasyillä. Mitään todellista, tiedossa olevaa uhkaa ei Firefoxissa ole, joten keskusteluja jatketaan ko. tietohallinnon kanssa. 
* Kirkesin valutus siirretään broadcast biblios -liitännäiselle 27.3.
* Annika on käynyt läpi ja lisännyt kokoelmatyön tiedonhaku -koulutuksessa tarvittavia raportteja. 

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2024#viikko-13) - [Palaa sivun alkuun](/paakayttajat2024)

## Viikko 12

Aika: 19.3.2024 klo 9.15<br />
Läsnä: Anneli Österman ja Lari Strand (Koha-Suomi), Tuomas Kunttu (Kyyti), Anni Rajala (Vaski), Päivi Knuutinen ja Auli Rantasalo (Vaara), Hanna Ikonen (Lumme), Piia Semenoff (OUTI), Reetta Pihlaja (Siilinjärvi), Noora Suvanto (Lappi), Kati Sillgren ja Lotta Juvonen (Helle), Annika Helastila ja Elina Uotila (Kirkes)

**Yhteiset**
* [Kori-toiminnosta nidetyyppi-sarakkeen piilotus](https://github.com/KohaSuomi/Koha/issues/411#issuecomment-1976349820)
* [Asiantuntijaryhmän muistio 4/24](https://github.com/KohaSuomi/Koha/discussions/1123)

Etelästä pohjoiseen

**Kyyti**
* Uuden version ominaisuudesta kysyin, että voiko Varauksen teosta vahvistusviesti (EmailPatronWhenHoldIsPlaced) -toiminnon päälle laittaminen aiheuttaa mitään kuormaongelmaa sähköpostipalvelimella? - Ei kuulemma aiheuta.
* Testasin Ennakkovaraukset-ominaisuutta. Ei oikein vaikuta vielä toimivalta. Tein ennakkovarauksen. Sen jälkeen lainasin toiselle asiakkaalle ongelmitta, vaikka meni ennakkovarauksen päälle. Toisella kertaa antoi lainata ennakkovarauksen alkuun asti. Siinäkin tapauksessa antoi kuitenkin uusia lainan huolimata ennakkovarauksesta.
* Nextillä asiakkaan tiedoissa näkyy Reklamaatiot-välilehti. Tuotannossa ei näy. Johtuu ilmeisesti nextin BundleLostValue-asetuksesta, joka on päällä, koska nidepaketit ovat käytössä. Tuotannossa sama asetus on myös päällä, mutta silti reklamaatiot-välilehti ei näy. Asetuksen toiminta on siis muuttunut.

**Vaski**
* Mietitty pitäisikö Othernames-kentän kielikäännös muuttaa Muu nimi -> Kutsumanimi. Palaverissa todettiin, ettei ole tarpeen.
* Kirjastojen atk-ihmisten kokoontumisajot Turussa 25.-26.4.2024. Vaskin pääkäyttäjille voi huikata, jos ei ole saanut kutsua ja haluaisi osallistua.

**Vaara**
* Kysymys tarpeettomien aineistotyyppien poistosta tarkan haun näkymästä sai kielteisen vastauksen. Kehittäjien mielestä voi aiheutua ongelmaa, jos aineistotyyppejä poistaa auktorisoiduista arvoista. Harmi kun ei ole mitään muuta tapaa piilottaa tästä hakunäkymästä näitä tarpeettomia aineistotyyppejä.

**Lumme**
* Normaalia ylläpitoa.

**OUTI**
* Puppe on alustavasti otettu Oulussa käyttöön vuoden 2024 loppuun.
* Uuden version käyttöönottovalmisteluja tehty.
* Normaalia ylläpitoa
* Vaskista saatu raportti, jolla haetaan kannasta asiakkaan vahingossa poistamat varaukset. Raportin avulla voimme OUTIssa luopua käytännöstä, että etsimme lokilta varaukset ja tallennamme ne yksi kerrallaan asiakkaalle takaisin. Nyt voimme toimittaa listan poistetuista varauksista asiakkaalle ja hän voi halutessaan tallentaa ne itse verkkokirjastossa. Suurkiitos raportista!

**Siilinjärvi**
* Kohassa ei mainittavaa, kunnan yt-neuvottelut mietityttävät.

**Lappi**
* Asiakkaiden viesteissä otettu käyttöön kirjastokortinnumeron osittainen piilotus.
* Normaalia ylläpitoa.

**Helle**
* Uudet varapääkäyttäjät Lotta Juvonen ja Vilgot Strömsholm ovat aloittaneet.
* Uudessa versiossa on Niteiden erämuokkaus -toiminnossa uusina ominaisuuksina: Jätä pois paikallisten varausten jonosta JA Palauta niteet. Ehdotettu ominaisuuksien poistamista käytöstä (piilottamista). Palaverissa todettiin, että toteutukselle on tarve. Tiketti [#123](https://github.com/KohaSuomi/Koha-23x/issues/123)

**Kirkes**
* Käyty läpi Nextin järjestelmäasetuksia.
* Kirkes-johtoryhmä harkitsee noutamattomien varausten maksun poistamista lapsiasiakkailta, mutta päätöstä ei ole vielä tehty. Varaudutaan kuitenkin poistoajon käyttöönottoon.
* Salasananvaihtoviestit laitettaneen päälle jollain aikataululla. 

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2024#viikko-12) - [Palaa sivun alkuun](/paakayttajat2024)

## Viikko 11

Aika: 11.3.2024 klo 9.15<br />
Läsnä: Anneli Österman ja Emmi Takkinen (Koha-Suomi), Päivi Knuutinen ja Auli Rantasalo (Vaara), Annika Helastila (Kirkes), Leena Kinnunen, Pia Kusmin, Maria Joona (Lappi), Reetta Pihlaja (Siilinjärvi), Pirkko-Liisa Lauhikari ja Piia Semenoff (OUTI), Hanna Ikonen ja Katja Valjakka (Lumme), Kati Sillgren (Helle), Mikko Liimatainen (Vaski)

**Yhteiset**
* [Viikon 11 päivitys](https://github.com/KohaSuomi/Koha/discussions/1115)
* [Huoltokatko keskiviikkona](https://github.com/KohaSuomi/Koha/discussions/1108)
* String freeze viikosta 12 lähtien eli viikkopäivityksiä ei tehdä tästä lähtien ja keskitytään versiovaihdon ominaisuuksien valmistelemiseen.
* [Tiketti #336](https://github.com/KohaSuomi/Koha/issues/336#issuecomment-1968753873)
  * "Jos valitsi hyllypaikan, hyllytarkenteen ja kokoelmakoodin siten, ettei sellaisella kombinaatiolla entuudestaan ollut yhtään nidettä, niin kenttään tuli tyhjä arvo. Voisikohan tässä käyttää tuota osakentän oletusarvoa, vai onko parempi jättää kenttä tyhjäksi, jotta se täytetään sitten asianmukaisesti?" - Miten kannattaisi toimia?

Pohjoisesta etelään

**Vaara**
* normaalia ylläpitoa ja versionvaihdon tikettien testausta
* lisäksi PowerBI:n raportin muokkaamista

**Kirkes**
* selvitellään lehtien vastaanottamisessa ilmenneitä epäjohdonmukaisuuksia.

**Lappi**
* Normaalia yläpitoa

**Siilinjärvi**
* ei erityistä, intranetuser- ja järjestelmäasetusten läpikäynti vihdoin aloiteltu nextillä

**OUTI**
* Oulun luetteloinnissa ja hankinnassa oli huomattu, että jos tekee itse hankintoja Kohassa ja poimii valmiin tietueen ulkoisesta lähteestä, muodostuu tietueelle kaksi 000-kenttää, varsinainen 000-kenttä ja ”nam a22 8i 4500” -kenttä. Sama tilanne muodostuu myös, jos Hankinnan lomakkeella tekee tyhjästä uuden tietueen. Annelin neuvon mukaan, kannattaa käydä poistamassa ACQ-kuvailupohjan 000-kentän oletusarvo "nam a22 8i 4500", jottei tietueelle synny kahta 000-kenttää. Tarkemmin tiketissä: https://github.com/KohaSuomi/Koha/issues/1114  
* OUTIssa poistetaan myös lakkautetut kirjastot/toimipisteet tietokannasta, koska kirjastojen poistot eivät ole aiheuttaneet ongelmia muissakaan kimpoissa. Poiston voi tehdä sen jälkeen, kun kirjaston vuositilastot on otettu talteen, eikä kirjastolla ole enää asiakkaita, niteitä yms.
* OUTIssa otetaan käyttöön 13.3.2024 maksujen jaottelu julkis- ja yksityisoikeudellisiin maksuihin asiakkaan tiedossa.

**Lumme**
* Normaalia ylläpitoa. Tulevan version järjestelmä- ja IntranetUser-asetusten läpikäyntiä.

**Vaski**
* Pääkirjaston remontin osalta yllättäviä muutoksia

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2024#viikko-11) - [Palaa sivun alkuun](/paakayttajat2024)

## Viikko 10

Aika: 5.3.2024 klo 9.15<br />
Läsnä: Anneli Österman ja Pasi Kallinen (Koha-Suomi), Anni Rajala (Vaski), Leena Kinnunen (Lappi), Päivi Knuutinen ja Auli Rantasalo (Vaara), Hanna Ikonen (Lumme), Pirkko-Liisa Lauhikari, Piia Semenoff ja Veli-Pekka Marjoniemi (OUTI), Tuomas Kunttu (Kyyti), Kati Sillgren (Helle), Annika Helastila ja Elina Uotila (Kirkes)

**Yhteiset asiat**
* [HOLDDGST eli varausten koosteviesti](https://github.com/KohaSuomi/Koha-23x/wiki/Uudet-viestipohjat#holddgst) -uusi toiminnallisuus versiossa 23.11 - toiminnallisuuden hyvät ja huonot puolet.
  * toimii vain sms/email-pohjilla
  * asiakaskohtaisesti valittavissa, mutta pitäisikö pakottaa tai piilottaa kaikilta?
  * Päätös: Piilotetaan koostetäppä kaikilta
* Valmistautumista kokoelmatyön koulutukseen:
  * Onko teillä kimpoissa hyviksi havaittuja kokoelmiin liittyviä SQL-raportteja, joita ei vielä löydy Raporttikirjastosta?
    * Jos löytyy, niin lisäilettekö niitä Raporttikirjastoon Kokoelma-osioon parin viikon sisällä?
  * Nidehaku ja räätälöidyt hakukentät, joista tullaan puhumaan ja kannattaa lisätä nidehaun hakukenttiin ylläpidossa:
    * Luokka (084$a)
    * Aineistotyyppi (942$c) [auktorisoiduksi arvoksi MTYPE]
    * Kielikoodit eri MARC-kentistä (041$adhjp)
    * Asiasanat (655$a, 650$a)
    * Yleinen huomautus (952$z)
    * Huomautus virkailijalle (952$x) 
* [Viikon 10 päivitys](https://github.com/KohaSuomi/Koha/discussions/1107)
* [Huoltoikkuna 13.3.](https://github.com/KohaSuomi/Koha/discussions/1108) - katko tiedossa

Etelästä pohjoiseen

**Vaski**
* Otettu käyttöön mahdollisuus muokata jopa 10 000 nidettä erämuokkauksessa
* Tehty nideraportteja kirjastojen remonttisulkemisia varten, pääkirjaston kirjallisuus ja taiteet -osasto suljetaan lohkoittain joten tarvitaan useampi raportti.
* Pupen tilausten kohdentamisen parantamiseksi Broomworks pyytänyt lisäoikeuden vendors_manage. Sovittiin, että laitetaan vielä viestiä tästä Matrixin kautta. Jos/kun asia ok niin Anni huolehtii integraatiot-sivun ja OUTIn tiketin päivityksestä.
* Turun lainauskaappi alkanut antaa eräpäiväksi kuluvan päivän. Ongelma alkanut viime viikon päivityksessä tehdyn muutoksen seurauksena. Käydään vielä katsomassa automaatin asetuksia ennen kuin tehdään tiketti.

**Lappi**
* Kimpan johtoryhmä päätti luopua kirjastokortin kuntatunnuksesta ja siirtyä LAPPI-alkuisiin kortteihin. 
* Rovaniemen pääkirjasto väistötilassa 2.5. eteenpäin vuoden (siirtymä vaiheittain jo huhtikuun aikana). Perustetaan yksi uusi kirjasto aineiston käsittelyä varten, mutten mennään melko pitkälti toissavuoden väistötilan säännöillä. 
* Käyttäjäryhmän päätösten mukaisesti tehty pieniä muutoksia asetuksiin.

**Vaara**
* Viime viikolla saatiin Ceepos-kassat toimimaan, kun vaihdettiin vanha IntranetUserJS-rimpsu paikoilleen.
* Oli unohdettu tallentaa Kohan kalenteriin pääsiäisen poikkeusaukiolot, joten eräpäiviä tuli pääsiäisen pyhille. Onneksi erämuokkauksella sai korjattua eräpäivät oikeaan päivään ja kalenteri päivitetty vaihtuvilla pyhäpäivillä.
* Vaarassa on raportti, jolla saa kiinni asiakkaat, joiden rekisteröitymispäivämäärä on tulevaisuudessa. Tänä aamuna raportilla löytyi kaksi yhteisöasiakasta, joiden rekisteröitymispäivämäärä oli elokuussa 2024. Ilmeisesti se ei aiheuta onneksi muuta kuin tilastovirheen, jos tutkailee uusia asiakkaita. Harmillista silti, että tarpeettomasti muokataan tuota päivämäärää.

**Lumme**
* Tehty Finnaan pieniä käännösmuutoksia asiakasliittymään. Tilaa PIN-koodi vaihdettu "Vaihda PIN-koodiksi", Kohasta tulevat käsin lisätyt asiakasrajoitukset näkyvät jatkossa "Kirjastokortillasi on rajoitus. Ole yhteydessä kirjastoosi kirjaston palveluaikana."
* Nalkutin saatu toimimaan tuotantonnossa, nyt Marc-virhelistauksen raportti on pienentynyt n. 95 000 tietueesta 17 500 tietueeseen.
* Yhteiset käyttösäännöt tulivat voimaan 1.3. ja noutamattoman varauksen maksu nousi kahteen euroon.

**OUTI**
* Poistettu kirjastokorttinumerot s-postiviesteinä menevistä palautuskehotuksista ja eräpäivämuistutuksista. Jatkossa viesteissä näkyy vain kortin kolme viimeistä numeroa.
* Pystytäänkö Koha-Suomella arvioimaan, milloin nextille olisi saatu siirrettyä kaikki Koha-Suomen omat muutokset, jotta kimpassa voitaisiin toteuttaa isommat testaukset? Anneli lupaili aikataulua viikon 11 alkupuolella.

**Kyyti**
* Uuden version uudet asetukset käyty läpi
* Löytyi teos, jolla oli kaksi tietuetta: toiseen ei päässyt (Tietuetta 1500602 ei ole tietokannassa), mutta siinä oli kiinni nide ja toinen tietue toimi normaalisti ja siinä oli edellisen tietueen niteen hankintatiedot. Neuvottiin liittämään nide toimivaan tietueeseen (Muokkaa | Liitä nide). Tämä toimi hyvin. Sitten piti vielä pyytää kehittäjää poistamaan toimimaton tietue pois indeksistä [#1112](https://github.com/KohaSuomi/Koha/issues/1112)

**Helle**
* AutoFrameCode-liitännäisen käyttöönotossa olin unohtanut vaihtaa musiikkiäänitepohjalle oikean tunnuksen (tunnus ei ole sama kuin TäTin vastaavalla kuvailupohjalla). Väärästä määrityksestä johtuen ko. kuvailupohjaan liittyvän tietueen niteet eivät näkyneet oikein eivätkä olleet muokattavissa.
* Kausijulkaisut-toiminnossa tehtyjen toimintojen myötä muutamista käsitellyistä tietueista on muodostunut tuplatietueita. Tietueiden niteiden nidevarauksessa havaittu haasteita. (Helle-Finnassa varauksenteko onnistunut normaaliin tapaan.)
[#1041](https://github.com/KohaSuomi/Koha/issues/1041)
* Noudettavissa olevat varaukset -toiminnon Asiakas-sarake piilotettu.
* Tänä aamuna Kohan kirjautumisnäytöllä lisätekstinä Virhe: Tili lukittu. Kohaan kirjautuminen onnistui. Anneli lisäsi tapaustiedon Ongelmatilanteita-koosteeseen.
Ongelman syy: Todennäköisesti jollain tunnuksella on cardnumber/userid tyhjä ('') ja kyseisen tunnuksen epäonnistuneiden kirjautumisten määrä on ylittänyt sallitun maksimin.

**Kirkes**
* Ei mainittavaa. 


[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2024#viikko-10) - [Palaa sivun alkuun](/paakayttajat2024)

## Viikko 9

Aika: 27.2.2024 klo 9.15<br />
Läsnä: Anneli Österman (Koha-Suomi), Päivi Knuutinen ja Irina Halminen (Vaara), Pirkko-Liisa Lauhikari, Piia Semenoff ja Veli-Pekka Marjoniemi (OUTI), Pia Kusmin ja Maria Joona (Lappi), Kati Sillgren (Helle), Hanna Ikonen (Lumme), Mikko Liimatainen (Vaski)

**Yhteiset**
* [Varauksen keskeytyksen ja aktivoinnin käännösmuutosehdotukset](https://github.com/KohaSuomi/Koha-translations/issues/19#issuecomment-1954070069)
* [Viikon 9 päivitys](https://github.com/KohaSuomi/Koha/discussions/1098)
* Pääkäyttäjäryhmän vuosisuunnitelma: [paakayttajatvuosisuunnitelma2024.docx](https://github.com/KohaSuomi/kohasuomi.github.io/files/14416128/paakayttajatvuosisuunnitelma2024.docx)
* Asiantuntijaryhmästä tehtäväksi:
  * [Waitingreserves.pl-sivulle mahdollisuus näyttää asiakkaan tiedoista vain varaustunniste #367](https://github.com/KohaSuomi/Koha/issues/367)
    * Koha-Suomen asiantuntijaryhmä 26.2.2024: Suositus, että Asiakas-sarake piilotetaan sarakeasetuksissa. Pääkäyttäjien tehtävissä.
  * [Ylläpito/Kirjastot ja ryhmät: mahdollisuus lisätä Nimi-arvo suomen lisäksi ruotsiksi ja englanniksi #448](https://github.com/KohaSuomi/Koha/issues/448)
    * Koha-Suomen asiantuntijaryhmä 26.2.2024: Yhteisössä on avoinna aiheesta parikin bugia. Pyydetään pääkäyttäjiä käymään kommentoimassa tiketteihin, että toiminto olisi tärkeä, jotta saadaan yhteisöä aktivoitumaan. 

Pohjoisesta etelään

**Vaara**
* Ceepos-kassan testailut jatkuu, kun asetuksiin on muutettu sääntöä. Auli palaa lomalta huomenna, jolloin päästään testaamaan eri maksuvirityksiä ja niiden toimintaa.
* Muuten normaalia ylläpitoa, ei mainittavaa.

**OUTI**
* Pyhäjoella on poistettu käytöstä Monelan ja Pirttikosken kirjastot.
* Kutsumanimikentän saaminen näkyville tuotanto-Finnaan. Asia työn alla Larilla ja Erellä.
* Mietinnässä OUTIn Koha-ryhmässä uusien kokoelmien Dekkari, Helppolukuinen ja Selko lyhenteet ja kuvailut.
* Puppe otettiin perjantaina kehden viikon koekäyttöön. Koha-tukeen ei ole ainakaan vielä kuulunut miten menee. Palataan asiaan myöhemmin, kun kuullaan käyttökokemuksia.
* OUTIssa  on paljon hyväksytty varaustunnisteita, joissa on erikoismerkkejä. Pohdittiin voisiko muut kirjastot ottaa Vaskin validoinnin käyttöön, mutta koska OUTIn Finna-tuki oli tehnyt tästä jo kehitysehdotuksen Kansalliskirjastoon, päätettiin odottaa sen etenemistä.

**Lappi**
* Normaalia ylläpitoa.

**Helle**
* Kirjastoista kysytty Webkaken kaukolainojen näkymistä Kohaan.
* Tiedonhaun kirjasto + hyllypaikka -haku ei anna oikeaa hakutulosta Kohassa eikä Finnassa. Palaverissa saatu tieto/kertaus siitä, että hakuun tarvittavia indeksointeja puuttuu.
* Finnan Aikuiset-fasetin JA Lapset ja nuoret -fasetin käyttöä varten olisi tarpeellistsa saada tietueiden kiinteämittaiseen kenttään 008/22 massatäydennystä esim. tietueiden niteiden hyllypaikka-arvojen perusteella. Tämän mahdolliseen toteutukseen lienee parempi ajankohta joskus myöhemmin.

**Lumme**
* Perusylläpitoa.

**Vaski**
* Timeout-asetuksen muuttaminen puoleen tuntiin herättänyt paljon keskustelua. Aika koetaan hyvin lyhyeksi monissa kirjastoissa. Lisäksi uloskirjautumisen näkymättömyys aiheuttanut hämmennystä, kun uudelleenkirjatuminen saattaa alkaa niteen palautuksesta ja kirjautumisen jälkeen palautuu samaan tilanteeseen, johon edellinen käyttäjä oli Kohan jättänyt. Saisikohan Kohan oikeasti kirjaamaan käyttäjän pihalle, kun aika tulee täyteen, jolloin se näkyisi paremmin seuraavalle käyttäjälle? Tässä toki riskinä, että sama käyttäjä menettää jotain tekemäänsä, jos Koha ei palauta käyttäjää takaisin samalle sivulle.
* Käyttäjille, jotka vaihtavat työskentelypaikkaa usein, on ajateltu helpotusta arkeen selainliitännäisestä, joka tarjoaisi kirjautumisessa aina kyseisen toimipisteen, jossa kone sijaitsee. Tällä saataisiin käytännössä muutettua kirjautuminen toimipistekohtaiseksi nykyisen käyttäjäkohtaisen sijaan. Liitännäisestä on tehty prototyyppi, johon voi asettaa haluamansa kirjaston kirjastolyhenteen perusteella ja tallentaa tiedon selaimeen. Tähän olisi suunnitteilla hakea kirjastotiedot rajapinnasta.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2024#viikko-9) - [Palaa sivun alkuun](/paakayttajat2024)

## Viikko 8

Aika: 20.2.2024 klo 9.15<br />
Läsnä: Anneli Österman, Kodo Korkalo ja Lari Strand (Koha-Suomi), Anni Rajala (Vaski), Pia Kusmin ja Maria Joona (Lappi), Päivi Knuutinen ja Auli Rantasalo (Vaara), Hanna Ikonen (Lumme), Pirkko-Liisa Lauhikari ja Piia Semenoff (OUTI), Annika Helastila ja Elina Uotila (Kirkes), Tuomas Kunttu (Kyyti), Kati Sillgren (Helle), Reetta Pihlaja (Siilinjärvi)


**Yhteiset**
* [Viikon 8 päivitys](https://github.com/KohaSuomi/Koha/discussions/1087)
* Pääkäyttäjäryhmän vuosisuunnitelma 2024 työn alle: [paakayttajatvuosisuunnitelma2024.docx](https://github.com/KohaSuomi/kohasuomi.github.io/files/14331227/paakayttajatvuosisuunnitelma2024.docx)
  * käsitellään ensi viikon kokouksessa, kun kaikki ovat ehtineet katsoa dokumentin läpi ja Anneli pyytänyt Arilta tarkempaa ohjeistusta.

Etelästä pohjoiseen

**Vaski**

* Seinäjoelle (Eepos-kimpalle) pidetään tänään Koha-esittely.
* Turun pääkirjaston Kirjallisuus ja Taiteet -osasto menee remonttiin. Palautuvan aineiston sijoittelu mietinnässä.
* Myös kaksi Turun lähikirjastoa menossa remontin vuoksi kiinni.
* Kysyttiin onko mieltä sellaisessa ehdotuksessa, että nidehaun tuloksissa voisi näyttää 1000 nidettä (=saisi vietyä 1000 niteen joukon erämuokkaukseen). Selvisi, että Kohassa voi nykyään MaxItemsToDisplayForBatch... -asetuksilla määrittää paljonko niteitä esikatselussa näytetään ja paljonko niteitä voidaan kerralla muokata/poistaa. Kirkeksellä display-asetuksissa 1000 ja process 10000, ja toiminut hyvin. Vaskissa testataan samaa, helpottaa niteiden erämuokkauksia.

**Lappi**
* Rovaniemen remontti ja kiinnimeno lähenee. Eräpäivät ylitettiin ja samalla selvisi ongelma verkkokirjaston uusinnoissa. Finna käyttikin uusinnoissa Finna-API kirjaston kalenteria, jolloin nyt kaikkien kirjastojen eräpäivät siirtyivät 13.5. asti. Vika korjattiin circcontrol asetusta muuttamalla.
* Maksniemen kirjasto suljetaan kevään aikana. Suunnittelut sulkemisesta aloitettu.
* Ranualla otetaan toukokuussa käyttöön Smartbox.
* Tiketin #1083 tietueet korjattu, koska aiheuttivat indeksointi ongelman (saatavuus tieto näytti eri paikoissa eriä).
* Tuli vastaan varauksia, jotka olivat varaussijalla 0, mutta asiakas ei niitä ole saanut. Selvisi, että automaateilta menee osa varauksista suoraan hyllyyn, koska asiakkaat laittavat niteet väärään paikkaan. Tiedotetaan henkilökuntaa ja vinkataa automaateista saaravaan raporttiin tarkistettavista niteistä. 
* Kysy Kohasta -koulutus tulossa 19.3.

**OUTI**
* Uuden Tietuesiirtäjän säätöä (Antti ja Johanna). Tiketti #915
* Muhoksen Hyrkin alakoulu aloittaa lainaamisen. Lisätty hyllytarkenne.
* Tyrnävän kirjakaapin eräpäiväkuittiongelma. Lainauskuittiin ei tulostunut eräpäivää. Ennen versiopäivitystä 12-paluuviestissä on tullut eräpäivä AH-kentässä normaalisti. Versiopäivityksen jälkeen tilanne muuttui. Jos lähetetään 11-viestissä "no block" = ”Y”, niin AH-kenttä tulee tyhjänä, vaikka Koha ilmoittaa lainauksesta tai uusinnasta. Lainalla on myös Kohasta katsottuna eräpäivä, mutta AH-kentässä se ei tule. Oulun automaateilla ei tätä ongelmaa ollut vaan ainoastaan Tyrnävän kirjakaapissa.
  * Tiketti #1084
  * Yhteisössä on korjaus, joka on tuotu OUTI-testille ja Lappi-testille. Näyttää toimivan Lappi-testillä, mutta OUTIssa testataan vielä tällä viikolla. Jos kaikki menee hyvin tuodaan tuotantoon ensi tiistaina.
* OUTI Koha-ryhmän päätöksiä: 
  * uudet kokoelmat Dekkari, Selko, Helppolukuiset
  * uusi nidetyyppi laina-aika-7 vrk, myöhästymismaksu 0,40 e/pv, ei uusittava, ei varattava
  * asiakkaiden s-postiviesteistä (eräpäiväilmoitukset ja palautuskehotukset) jätetään koko kirjastokortin numero pois, vain kolme viimeistä merkkiä jätetään viesteihin.
  * Sotu-avaimettomille asiakkaille lisätään huomautusviesti (joka näkyy myös verkkokirjastossa) henkilötunnuksen puuttumisesta. Poistetaan mahdolliset siihen liittyvät rajoitukset.
  * Maksujen erottelu julkis- ja yksityisoikeudellisiin asiakkaan tiedoissa otetaan OUTIssa käyttöön:
Maksu-näkymän tekstimuutosehdotus asiakkaan Lainat- ja Tiedot näytöllä, jos mahdollista toteuttaa: "Asiakkaalla on lainauskieltoon vaikuttavia maksuja €16.00. Yhteensä (sis. maksut, jotka eivät vaikuta lainauskieltoon): €34.00.
     Anneli kysyy tieteelliseltä voiko lausetta muuttaa, vaikuttaako se tieteellisten kirjastojen toimintaan?
     OUTI tekee tästä tiketin. Tiketti: https://github.com/KohaSuomi/Koha/issues/1089
* Tullut kysymyksiä tilastoista.

**Vaara**
* Viime viikolla Outista Pirkko-Liisa kertoi raportista, jolla saa 245$h-kentän tiedot haettua. Pyysin raportin myös Vaaraan ja ajoin sen. Tuloksena oli yli 300 riviä erilaisia "yleismääreitä". Osa voidaan poistaa RDA-konversiossa suoraan, mutta osa sisältää tekijätietoja ym. jotka kuuluvat ihan toiseen osakenttään. Korjaan noita, missä on säilytettävää tietoa.
* Viime viikon päivityksessä Ceepos-kassan toiminnossa havaittiin ongelma, että osittain maksuja maksettaessa kassa näyttää eri summan kuin mitä Kohassa näkyy (virkailija syöttää esim. 2.00 euroa, Ceepos näyttää 2,30). Tätä nyt pallotellaan Meitan ja Ceepoksen välillä. Viimeisin tieto on, että Koha toimii väärin. Miksi se toimisi vain Joensuussa väärin?

**Lumme**
* Perusylläpitoa, pienten asioiden selvittämistä.
* Maaliskuussa otetaan käyttöön myös sähköpostimuistutus vaihtoehdoksi asiakkaille lähtevään 1. muistutusilmoitukseen.

**Kirkes**
* Mana-tietämyskanta on otettu käyttöön.
* Yksittäinen Suomi.fi-viesti lähtenyt useamman kerran, mistä DVV on ilmoittanut. Kyse on luultavasti silkasta vahingosta. 

**Kyyti**
* Käyty läpi uuden version IntranetuserCSS-rimpsu.  Löytyi yksi lisäys, jota tarvitaan jos käytössä ovat nidepaketit. Anneli lisäsi sen ohjeisiin: https://github.com/KohaSuomi/Koha-23x/wiki/IntranetUserCSS

**Siilinjärvi**
* Ei mainittavaa
* Tilastojen teko oli tällä kertaa helppoa ja mukavaa, koska tilastotyökalun antamat luvut olivat selkeitä ja loogisia. Kiitos kehittäjät!

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2024#viikko-8) - [Palaa sivun alkuun](/paakayttajat2024)

## Viikko 7

Aika: 13.2.2024 klo 9.15<br />
Läsnä: Anneli Österman ja Pasi Kallinen (Koha-Suomi), Pirkko-Liisa Lauhikari, Piia Semenoff, Veli-Pekka Marjoniemi (OUTI), Päivi Knuutinen, Auli Rantasalo, Irina Halminen (Vaara), Reetta Pihlaja (Siilinjärvi), Kati Sillgren (Helle), Tuomas Kunttu (Kyyti), Roosa Väisänen (Kyyti), Annika Helastila (Kirkes), Elina Uotila (Kirkes)

**Yhteiset**
* [Redusointi ja sip-tunnukset](https://github.com/KohaSuomi/Koha/issues/838#issuecomment-1931608560) - ehdotus toimintatavasta
  * kaikki tekevät testitunnukset ja toimittavat joko supportiin tai Larille Matrixissa.
* [Viikon 7 päivitys](https://github.com/KohaSuomi/Koha/discussions/1071)
  * Kuvailupohjan liitännäiseen pitää käydä lisäämässä asetukset, jotka löytyvät tiketistä.
* [Integraatiot-wikiin](https://github.com/KohaSuomi/Koha/wiki/Integraatiot) lisätty ohjeistusta rajapintojen avaamista ja sulkemista varten sekä mitä käyttäjäoikeuksia tunnukset tarvitsevat.
* Ei huoltokatkoa helmikuussa.
* [Pupen esittely 21.2.2024 klo 10](https://github.com/KohaSuomi/Koha/discussions/1068)
* Lari kysyy: Testi-Finnat ja kutsumanimi, oletteko ehtineet tarkistamaan?
  * sama muutos pitää pyytää myös nextien Finnoille.
  * Käykää testaamassa ja kuittaamassa [tikettiin Finna-kehitysehdotukset #22](https://github.com/KohaSuomi/Finna-kehitysehdotukset/issues/22) viimeistään pe 16.2.2024.

Pohjoisesta etelään

**OUTI**
* Otettu käyttöön uusi Tietuesiirtäjä. Tänä aamuna ensimmäiset tietueet siirtyneet Kohaan.
* Oulu ottaa kahdeksi viikoksi koekäyttöön Puppe-tilaustenvastaanottotyökalun 23.2.2023. Jos työkalu toimii, se jää ilmeisesti käyttöön.
* Oulun luetteloinnista tuli tiedoksi, että RDA-konversiossa poistuu kokonaan 245h-kenttä (Aineiston yleismääre). Ilmeisesti kentän tietojen annetaan hävitä konversiossa.
* Tehty varauksen keskeytykseen liittyvät tekstimuutokset Finnaan.

**Vaara**
* Joensuu-apin päivityksessä otettu käyttöön HionDigitalin tekemä sovellus, jolla Vaarojen asiakkaat pääsevät apin kautta uusimaan lainojaan, tekemään varauksia ja keveitä tiedonhakuja.
* Vaara-Finnassa muokattu maksunäkymää lisäämällä sinne tiedotusta maksamiseen liittyvissä asioissa.
* Cineast-elokuvapalvelu tulossa kuun vaihteessa käyttöön Vaarassa asiakkaille (nyt henkilökunnalla demokäyttö kokeiltavana)

**Siilinjärvi**
* Vuorelan kirjaston lainaus/palautusautomaatti seisahtelee itsekseen omatoimiaikana. Kohan päästä ei löytynyt vikaa, jatketaan selvittelyä Tieran ja Mikroväylän kanssa.
* Hetu/hetuavain näyttäisi puuttuvan n. 600 henkilöasiakkaalta, osa näistä käyty jo läpi aiemmin ja huomautus lisätty. Lisätään lopuillekin ja muistutellaan taas hetun tallentamisesta oikein.
* Emottomien osakohteiden poisto vielä vaiheessa, PasiK:n toimittama listaus vaatii vielä lisäselvittelyä.

**Helle**
* Poistettu massana 17269 emotonta osakohdetta. Listaus poistettavista Pasi Kalliselta.
* Niteelle tullut lainatessa eräpäiväksi lainauspäivä. Syynä kirjastokortillisen lainaajatiedon virheellinen Takaaja-asiakastyyppi. Takaaja-asiakastyyppi ei sisälly Hellen laina- ja maksusääntöihin.
* Kaukolaina-asiakastyypin salasanan generointiin tuli muutos. Lari Strand teki tarvittavat ylläpitomuutokset.

**Kirkes**
* E-kirjaston Cineast-elokuvapalvelu otettu käyttöön Viddlan sulkeuduttua, päivitelty integraatiolistaan.
* Kirjastokortittomille asiakkaille on muodostunut KIRKON-tunnus asiakastietojen kirjastokorttikenttään konversion seurauksena. Siivotaan nämä hiljalleen pois.
* Järvenpäässä vaihdettu tulostimien toimittaja Canoniin. Mahdollisuus rakentaa rajapinta Kohaan.
  

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2024#viikko-7) - [Palaa sivun alkuun](/paakayttajat2024)

## Viikko 6

Aika: 6.2.2024 klo 9.15<br />
Läsnä: Anneli Österman ja Lari Strand (Koha-Suomi), Iina Niemi (Vaski), Päivi Knuutinen, Auli Rantasalo, Irina Halminen (Vaara), Leena Kinnunen ja Pia Kusmin (Lappi), Tuomas Kunttu (Kyyti), Pirkko-Liisa Lauhikari (OUTI), Reetta Pihlaja (Siilinjärvi), Annika Helastila ja Elina Uotila (Kirkes), Kati Sillgren (Helle)

**Yhteiset**
* [Viikon 6 päivitys](https://github.com/KohaSuomi/Koha/discussions/1057)
* [Asiantuntijaryhmän muistio 2/24](https://koha-suomi.fi/asiantuntijaryhma2024#asiantuntijaryhm%C3%A4n-muistio-224) - keskeneräinen kirjoitushetkellä
* [Indeksointi- ja tiedonhakuryhmän muistio 1/2024](https://github.com/KohaSuomi/Koha/discussions/1047)
* Muistutuksena, että torstaina jatketaan uudemman version [ominaisuuksien läpikäyntiä](https://github.com/KohaSuomi/Koha/discussions/1054)
* 23.11-version IntranetUserCSS:t käyty läpi ja korjattu tarvittaessa. Kannattaa tyhjentää asetus kokonaan (ota talteen vanhat vaikka muistioon) ja lisäile sitten tarvittavat uudelleen. Näin mukaan ei jää vahingossa vanhoja/toimimattomia rimpsuja.
  * JS:t työn alla.

Etelästä pohjoiseen

**Vaski**

* Ei mainittavaa

**Vaara**
* Edellisellä viikolla kertomani emottomien osakohteiden korjausajo vaati lopulta neljä yritystä, ennen kuin raportti oli sellainen, että tietueet saattoi poistaa. Samalla korjattiin myös 001-kentän kontrollinumerot vastaamaan biblionumberia ja trimmattiin 003-kentistä tyhjiä merkkejä pois.
* Eilen kesken iltapäivän meni vaara.finna.fi:ssä rikki jotain: lainoja ei voinut uusia, niteiden saatavuus ei näkynyt, tapahtumien kuvat ja tiedot eivät näkyneet eikä myöskään uutiset. Selvisi, että vika oli lopulta Smileen chat-palvelussa, joka rikkoi jotain Finnassa. Muilla kimpoilla ei ollut samaa ongelmaa kuin Vaaralla ja Outilla. Finna-tuesta neuvottiin kommentoimaan chat-palvelu pois päältä, kunnes se on korjattu.

**Lappi**
* noreply-toiminnon käyttöönotto ei Lapissa aiheuttanut ilmeisesti mitään ongelmia. Noreplyä on ollut odottamassa 2. palautuskehotuksen salliminen sähköpostilla, otetaan se nyt työn alle.
* Sotuttomia asiakkaita käyty läpi ja merkitty näille rajoitus ja tieto sotun lisäämisestä. Kolmesta kirjastosta tullut palautetta, että sotut olisi heidän mielestään laitettu asiakkaille, ja ne olisivat nyt jotenkin kadonneet. Keskusteltiin, onko muualla havaittu samaa ja mikä voisi olla syynä. Lappi tekee kehitysehdotuksen sotun tallennuksen kehittämisestä niin, että sotua ei vahingossa jäisi tallentamatta. 

**Kyyti**
* Viime viikon kirjastojen sähköpostiosoitteiden muutos vaikutti laajasti Kyytin viesteihin. Tekstiviesteihin ilmestyi yksi yhteinen lähettäjänimi (Hamina), kun aiemmin lähettäjä oli oman kunnan nimi. Tekstiviestien osalta selvittely on vielä kesken. PDF-viestien tulostus meni myös sekaisin. Näiden viestien käsittely onnistuu uusilla ohjeistuksilla. Tiedottamista on riittänyt.

**OUTI**
* Oulun luetteloinnista Heikkisen Antilta tullut huomio, että jostakin syystä Mikropalvelu ei näytä ymmärtävän venäjänkielisen aineiston tietueissa olevia 9-osakentän sisältäviä kenttiä, vaan tuplaa ne, vaikka niiden sisältö on täysin sama. Tiketti: https://github.com/KohaSuomi/KohaSuomiServices/issues/13

**Siilinjärvi**
* ei mainittavaa Kohassa, muuten kiirettä.

**Kirkes**
* Keravan kirjastossa ei ollut nide tärpännyt Mäntsälän kirjastoauton varaukseen. Kirjastoautojen lainasäännöissä on muutenkin epäjohdonmukaisuuksia, mutta tutkitaan aina, kun tulee jotain ilmi.
* Järvenpäässä mietitään raportteja, joita lähettää Raportterin kautta kaupungin tietovarantoon. Elina tutkailee Oulun päivitettyä BI-raporttia, josko sitä voisi hyödyntää (Raportti täällä: https://github.com/KohaSuomi/Koha/issues/1051).

**Helle**
* Kehittäjä Lari Strand löysi ratkaisun siihen, miksi Helle-Finnan saatavuusnäkymässä tietueen kaikki niteet näkyvät Varattu-tilaisina, vaikka saatavilla olevia niteitä on enemmän kuin varauksia. Liittyy Kohan asetukseen AllowItemsOnHoldCheckoutSIP. Tiketti https://github.com/KohaSuomi/Koha/issues/1035
* Yhdestä Hankintaportaalin tilauksesta ei ole muodostunut tilausta Helle-Kohaan. Ilmoitusta virheellisestä tilaussanomasta ei ole tullut, eikä tilauksesta ole jälkeä EDIFACT-sanomissa. Hankintaportaalissa tilauksen tehnyt on saanut aineistotoimittajan vahvistusviestin tilauksesta.
* Ennakkoilmoitus-asiakasviesteissä on otettu käyttöön tieto lainaajakirjastosta. Tiketti https://github.com/KohaSuomi/Koha/issues/299


[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2024#viikko-6) - [Palaa sivun alkuun](/paakayttajat2024)

## Viikko 5

Aika: 30.1.2024 klo 9.15<br />
Läsnä: Leena Kinnunen (Lappi), Päivi Knuutinen, Auli Rantasalo, Irina Halminen (Vaara), Iina Niemi (Vaski), Hanna Ikonen (Lumme), Annika Helastila (Kirkes), Piia Semenoff ja Pirkko-Liisa Lauhikari (OUTI), Kati Sillgren (Helle), Tuomas Kunttu ja Roosa  Väisänen (Kyyti), Anneli Österman, Lari Strand, Johanna Räisä (Koha-Suomi)

**Yhteiset**
* [Yksiselitteinen ilmaisu varauksen keskeytyksen viimeiselle voimassaolopäivälle #19](https://github.com/KohaSuomi/Koha-translations/issues/19#issuecomment-1883024818)
  * Käydään Matrixin Finna-Yleinen-kanavan ehdotukset läpi
  * Pohdittiin erilaisia vaihtoehtoja päädyttiin tällaiseen vaihtoehtoon jäädytystä lisättäessä: Valitse päivä, jolloin varaus aktivoituu automaattisesti (vapaaehtoinen):
  * Kun varaus on jäädytetty/keskeytetty: Jäädytetty (väliaikaisesti keskeytetty) / Keskeytetty. Varaus aktivoituu xx.xx.xxxx (tai jos teksti paikkaan ei voi vaikuttaa, niin xx.xx.xxxx varaus aktivoituu)
  * Muutokset pystynee tekemään itse käännöksiin, joten jokainen kimppa voi tehdä ne itse.
* RenewAccruingItemInOpac ja RenewAccruingItemWhenPaid -asetuksia testattu OUTIssa.
  * asetukset toimivat kuvauksensa mukaisesti eli vain myöhässä olevien lainat uusitaan maksun jälkeen, jos ne on uusittavissa. Lastenaineistoa, joista ei kerry maksuja, ei uusita.
  * kimppakohtaisesti päätettävä, otetaanko käyttöön
  * Finnan maksusivua kannattaa joka tapauksessa parantaa ja selkeyttää, jotta asiakkaan hoksaavat käydä uusimassa lainansa.
* [Viikon 5 päivitys](https://github.com/KohaSuomi/Koha/discussions/1044)
* Bugi-perjantait harvennetaan joka toiseen kuukauteen, koska testattavia ei ole tarpeeksi.
* [Mana-testausten kokemukset](https://github.com/KohaSuomi/Koha/issues/677#issuecomment-1911734442)

Pohjoisesta etelään

**Lappi**
* Posion ja Sodankylän koulukirjastojen kanssa säätöä nidetyyppien, budjettien ja hankintaportaalin kanssa
* Edit-tilit näkymässä ei ole mahdollisuutta järjestää sarakkeita aakkosiin eikä suodatusta. Sovittiin, että Lappi tekee tästä kehitysehdotuksen yhteisöön
* Jos nide on poistettu, Finnan lainahistoriassa teos näkyy lainahistoriassa, mutta nimekkeenä on ei tietoa. Tehdään tiketti, jos niteen tiedot saisi näkyville esim. poistettujen tauluista tms.
* Kysytty, saisiko viivakoodin tilalle 2D-koodin, jättäisin tarralle lisää tilaa muulle tiedolle: ei tällä hetkellä mahdollista.

**Vaara**
* Päivi testannut Manan kuten yhteisissä asioissa mainittu
* Pasi Kallinen teki tiketin [#348](https://github.com/orgs/KohaSuomi/projects/4/views/1?filterQuery=348&pane=issue&itemId=17340272) toiveen mukaisesti viime yönä ajon, jonka tuloksena saatiin virhelista Vaaran emottomista osakohteista. Lista sisälsi myös virheilmoituksia tyyliin ERROR:Missing 001 [https://vaara.koha-suomi.fi/cgi-bin/koha/catalogue/detail.pl?biblionumber=151219] ja ERROR:003 needs trimming ( FI-BTJ) [https://vaara.koha-suomi.fi/cgi-bin/koha/catalogue/detail.pl?biblionumber=11298936]. Noiden virheiden korjaus täytynee tehdä muihinkin tietokantoihin, joten Pasi tekee sen tietokanta-ajona. 
Emottomien osakohteiden tietuelistauksen kohdalla on tapahtunut muutos, sillä siihen listaukseen tuli myös tietueita, jotka eivät olleet emottomia. Pasi korjaa skriptin tänään ja huomenna pääsen uudelleen testaamaan emottomien poistoa ajosta tulevan raportin avulla.

**Lumme**
* Täti-luetteloijat ovat alkaneet käydä läpi tietokannan tuplia ja triploja. Indeksiin jää edelleen roikkumaan poistettuja tietueita ja ongelma on selvittelyn alla.
* Kimpalla ja Lumme-Energialla oli sama lähettäjätunnus, minkä vuoksi kirjaston ja sähköyhtiön viestit alkoivat mennä samaan ketjuun. Ongelma poistui, kun kirjaston lähettäjätunnukseksi vaihdettiin "Kirjasto".

**Kirkes**
* Eri kimpan kaukopalvelija on ollut ihmeissään, kun Kirkes-Finna näyttää niteen havaintokirjaston kotikirjaston sijaan. Jos tarvetta, voidaan tehdä sääntö, joka sallii nidevaraukset kaukopalvelu-asiakasryhmälle. 
* MARC-virheraporttien käyttöönottoa odotellaan edelleen (tiketti https://github.com/KohaSuomi/Koha/issues/1015).

**OUTI**
* Ma 30.1. ajettu saapumisilmoitus tekstiviestinä täppä asiakkaille, joilla on puhelin numero Tekstiviesti numeroon -kentässä ja joilla ei ollut viestiasetuksissa valittuna mitään saapumisilmoitusten lähetystapaa ts. heillä oli sekä tekstiviesti- että sähköpostivalinnat tyhjinä. Liittyy tikettiin: https://github.com/KohaSuomi/Koha/issues/848.
* Oulun luetteloinnissa oli huomattu, että jos tilataan aineistoa, jolla ei ole varsinaista standardinumeroa, jolla yhdistää tietueen jo tietokannassa olevaan saman nimiseen tietueeseen, niin uusi hankintatietue ei tietenkään osaa yhdistyä siihen jo olemassa olevaan tietueeseen, vaan muodostaa uuden tuplatietueen. Sen päälle valuu sitten TäTistä oma, uusi täystietue osakohteineen. Mutta koska tietokannasta löytyi jo saman nimekkeen täystietue osakohteineen, niin Mikropalvelu hylkää kokonaan uuden tietueen valuvat osakohteet ja osakohteet olivat kadonneet myös tietueelta, joka oli jo ennestään tietokannassa. Olisikohan mitään keinoa täsmäyttää tietueita, joilla ei ole 020- tai 024-kentässä mitään tunnuksia, jotta vastaavaa ei tapahtuisi? Tiketti: https://github.com/KohaSuomi/KohaSuomiServices/issues/12
* OUTIin vanhojen lainassa olevien lainojen vanhentuneita myöhästymismaksuja on vanhennettu writeoff-ajona pariin kertaan. Ensimmäisen ajon 24.1. jälkeen maksut kertyvät asiakkaille uudestaan, mutta ajo tehtiin 29.1. uudestaan korjatulla skriptillä, eivätkä vanhennetut maksut ole enää kerääntyneet uudestaan.
* OUTIn Finna-testillä näkyy nyt oikein kutsumanimi ja varaustunniste. Tehdään tiketti, johon kirjataan kaikki tarvittavat toimenpiteet, jotka on tehtävä, jotta varaustunniste tulee jatkossa Finnaan oikein holdid-kentässä ja kutsumanimi calling_name-kentässä niille kirjastoille, jotka ottavat kutsumanimi-kentän käyttöön.

**Helle**
* Huomattu kausijulkaisutietueita, jotka tulevat tiedonhakuun tuplana. Nyt palaverissa saatu tieto, että tämä liittyy indeksointivirheeseen. Helle-tiketti (tehty pe 26.1.2024) https://github.com/KohaSuomi/Koha/issues/1041

**Kyyti**
* Kotkassa avattiin syksyllä uusi Lastenkulttuurikeskus, jonne meni pieni kokoelma lastenkirjoja. Niteiden oli tarkoitus olla vain Lakussa paikan päällä luettavissa, joten niiden tilaksi laitettiin "Ei lainattavissa (Ei varattavissa eikä lainattavissa)" ja yleiseksi huomautukseksi tieto niiden sijainnista Lakussa. Nyt on pohdittu, että jos näitä niteitä voisikin lainata Lastenkulttuurikeskukselta. Tämän seurauksena Kotkassa on alettu testaamaan Kohan itsepalvelulainausta.

**Vaski**

* Ei mainittavaa


[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2024#viikko-5) - [Palaa sivun alkuun](/paakayttajat2024)

## Viikko 4

Aika: 23.1.2024 klo 9.15<br />
Läsnä: Päivi Knuutinen, Auli Rantasalo, Irina Halminen (Vaara), Reetta Pihlaja (Siilinjärvi), Piia Semenoff ja Pirkko-Liisa Lauhikari (OUTI), Hanna Ikonen (Lumme), Annika Helastila ja Elina Uotila (Kirkes), Kati Sillgren (Helle), Tuomas Kunttu (Kyyti), Roosa Väisänen (Kyyti), Anneli Österman, Kodo Korkalo ja Lari Strand (Koha-Suomi), Mikko Liimatainen (Vaski), Leena Kinnunen ja Pia Kusmin (Lappi)

**Yhteiset**
* [SQL-raporttien jakaminen Koha-yhteisön Mana-tietokantaan #677](https://github.com/KohaSuomi/Koha/issues/677) tiketissä on ohjeet, kuinka käyttöönotto tapahtuu Kohan päässä ja kuinka raportteja jaetaan ja haetaan.
  * Päivi testaa ensin ja kertoo kokemuksia. Katsotaan sen jälkeen muut.
* [Tikettien tekeminen ja kommentointi](https://github.com/KohaSuomi/Koha/wiki/Tikettien-tekeminen-ja-kommentointi) -wikiä päivitetty.
  * lisätty tähdennys, että tikettejä saa tehdä vain pääkäyttäjät, koska ilmeisesti Github antaa nykyään kaikkien rekisteröityneiden käyttäjien lisätä tikettejä.
* [Viikon 4 päivitys](https://github.com/KohaSuomi/Koha/discussions/1025)
  * käännösmuutos myös Finnaan?
    * jokainen kimppa tekee itse muutoksen Finnan käännöksiin.
* Finnassa tänään päivitys, jossa mukana varaustunnus/kutsumanimi-muutos
    * muutos on tehtävä kaikkiin kimppoihin yhtä aikaa, koska vaatii Kohan päivityksen.
    * Finnaan tarvitaan uusi lomakepohja käyttöön, jotta tiedot menevät oikeisiin kenttiin Finnasta Kohaan.
    * OUTI tekee Finna-toimistoon pyynnön kaikkien puolesta. Kutsumanimi-kenttä halutaan vain OUTIssa ja Vaskissa käyttöön eli muissa kimpoissa sitä ei haluta näkyviin.
    * Vaski on pyytänyt testille lomakkeiden korjauksen. OUTI odottaa, miten ne lähtee toimimaan ja pyytää sitten itselle testille. 
* Vanhentuneet maksut -ajossa muodostunut myöhässä olleille lainoille uudet myöhästymismaksut
  * Muutetaan vanhentamisskirpti writeoffaamaan, noteen tieto mitätöinnistä.
  * muutetaan accountlines-taulusta expired-maksurivit writeoff-maksuriveiksi. 
  * OUTIssa ja Kyytissä date-kenttä päivittynyt 2021 tehdyn myöhästymismaksumuutoksen vuoksi, jolloin lainassa olleiden niteiden maksurivit päivittyi. Tuolloin ei vielä ollut erillistä timestamp-kenttää. Nyt kun date on päivittynyt, maksurivit eivät tulleet mukaan vanhentamisajoon.
  * OUTI ja Kyyti tekee tiketit päivämäärien korjauksista Vaskin skriptillä ja sen jälkeen maksut vanhennetaan korjatulla vanhentamisskriptillä
* Alla olevilla raporteilla voi hakea asiakkaat, joilla on maksut muodostunut uudelleen. Ne joutuu käymään läpi käsin ja writeoffaamaan ylimääräiset maksut.
```
SELECT DISTINCT i.borrowernumber
FROM issues i
INNER JOIN accountlines al ON i.itemnumber = al.itemnumber AND i.borrowernumber = al.borrowernumber
INNER JOIN (SELECT borrowernumber from accountlines
			 WHERE credit_type_code = 'EXPIRED') as exp ON exp.borrowernumber = al.borrowernumber
WHERE al.debit_type_code = 'OVERDUE'
AND date(i.date_due) < '2019-01-01'
ORDER BY 1 ASC
```

* Kannattaisiko ottaa käyttöön RenewAccruingItemInOpac ja RenewAccruingItemWhenPaid -asetukset? Testattava ennen käyttöönottoa.
  * asetuksissa rajoitteena se, että jos tietueeseen liittyy varaus tai uusimiskerrat täynnä, niin uusintaa ei voida tehdä
  * miten käy, jos maksaa maksun vain osittain? Järjestelmäastuksen kuvauksen mukaan uusinta tehdään vain, jos kaikki maksut maksetaan.
  * OUTIssa Pirkko-Liisa testaa ja katsotaan sen jälkeen, kannattaako ottaa käyttöön. 
* Uusien ominaisuuksien esittely suurelle yleisölle ke 17.4.2024 klo 13 - tallennetaan
* Pääkäyttäjille esittely to 1.2.2024 klo 10 - tallennetaan

Etelästä pohjoiseen

**Vaara**
* Joensuun kaupungin tilaama Koha-appi on osa Joensuun kaupungin mobiilisovellusta. Toimitettu testitunnukset kehittäjille.
* Päivi korjaillut musiikkiaineistojen koodausta mm. musiikkitallenne-aineistotyypiltä eli tarkentanut 007-kentän koodausta ja vaihtanut oikean aineistotyypin osakohteelle. Kaikki tähtää RDA-konversion parempaan onnistumiseen, kun lähtödata on paremmassa kuosissa. Odotellaan myös kehittäjien tekemiä massakorjauksia tietyille kentille, jotka (miltei) kaikissa kimpoissa kaipaavat korjausta.
* Eilen saatiin Vaaran next-kanta käyttöön ja Päivi on testannut jo muutaman tiketin kautta toimintoja. 
 
**Siilinjärvi**
* OPACPrivacy-asetus oli Älä salli, nyt korjattu Salli eli Yksityisyysasetus käännösmuutoksineen näkyy virkailijaliittymässäkin.
* [#1018](https://github.com/KohaSuomi/Koha/issues/1018) ongelmana Siilissä, sen sijaan mitätöityjen vanhentuneiden maksujen uudelleen kertyminen [#804](https://github.com/KohaSuomi/Koha/issues/804) ei koske meitä

**OUTI**
* OUTIssa oli syntynyt ainakin Oulun lasten- ja nuorten kirjatilauksille ylimääräisiä haamuniteitä maalis-toukokuun aikana 2023. Tapauksia oli tullut vastaan n. kymmenkunta. Ylimääräiset niteet oli huomannut hankintaa tekevä henkilö, kun hän oli käynyt läpi Oulun osalta raporttia "Nimekkeet, joissa on niteitä tilattu-tilassa". Ylimääräinen tilattu-tilassa oleva nide oli syntynyt eri välilehdelle missä olivat kirjaston muut oikeasti tilatut niteet. Haamunide oli syntynyt tietokantaan muutamaa tuntia aiemmin kuin varsinaiset tilatut niteet. Tiketti: https://github.com/KohaSuomi/Koha/issues/1024
* Finna-tukeen laitettu maksujen maksimimäärärajasta, joka ei aivan toimi lainojen uusinnassa. Eli Finna sallii sentin enemmän maksuja kuin Kohan järjestelmäasetuksiin on määritelty maksujen maksimäärästä. Varausten teossa maksuraja toimii eli varauksia ei pysty tekemään, jos maksujen maksimimäärä on ylittynyt.
* Oulun Ceepos-palvelin siirretty viime viikonloppuna (la-su välisenä yönä) Istekille. Siirto ei työllistänyt Koha-tukea. Ceepos oli saatu toimimaan ennen kirjaston asiakaspalvelun alkua. Verkkomaksupalvelu oli pois käytöstä siirron ajan.
* Selvisi miksi kaikilla asiakkailla ei näy Finnassa Lainat-näytöllä "Uusi kaikki"-nappi. Kun lainoja on 26 tai sitä enemmän, niin silloin nappi katoaa, sillä lainat näkyvät tuolloin useammalla sivulla kuin yhdellä. Laitoimme Finna-tukeen viestiä, että katoaako nappi sen vuoksi ettei sillä voi uusia kaikkia lainoja, jos lainat jakautuvat usealle sivulle? Ehdotimme, että voisivatko kaikki lainat näkyä yhdellä sivulla, jolloin nappi näkyisi kaikille asiakkaille eikä katoaisi välillä?

**Lumme**
* Asiakasrekisterin läpikäynti ja sen siivous on mennyt vähän eteenpäin. Tällä hetkellä tehty raportteja ei-aktiivisista asiakkaista.
* Henkilökunnalla on välillä vaikeuksia muistaa tallentaa sotua sotusiiloon. Tähän toivottiin jonkinlaista ratkaisua tai muistutusta. Myöhemmin mahdollisesti tulossa kaksivaiheinen asiakkaan lisääminen: ensin lisätään mahdollinen sotu ja vasta sen jälkeen pääsee lisäämään asiakkaan tietoja.

**Kirkes**
* Koska järjestelmä vaihtui kesken vuoden, nyt yritetään yhdistää Auroran ja Kohan aikana kertyneitä tilastoja niin, että lopputulos olisi OKM-tilastoja varten mahdollisimman oikea.

**Helle**
* Integraatiot-listaan tehty yksi päivitys (tarkennus) Helleen liittyen
* Helle-Finnassa saatavuustiedot saattavat edelleen näkyä väärin, kun nimekkeeseen kohdistuu varaus/varauksia. Keskustelua käyty Finna-toimiston kanssa, mutta ratkaisua ei ole löytynyt. Olisiko tähän ratkaisu Kohan puolella? Tiketti tehty https://github.com/KohaSuomi/Koha/issues/1035

**Kyyti**
* Kovasti nyt kiirettä muidenkin kuin Koha-asioiden kanssa
* Kysyin, että haittaako kun "Hallinnoi välivarastoituja MARC-tietueita"-osiossa on 20 sivua vanhoja (2018) Btj:n ennakkolistoja vai pitäisikö niitä poistaa. - Eivät kuulemma haittaa.
* Kotkassa tehty uusi Koha-tunnus ja asennettu varmenne ja kuittitulostimen asetukset.

**Vaski**
* Finnassa varaukset ja lainat sivuilla on valintaruutu kaikkien lainojen tai varausten valitsemiseen ilman selitettä. Tästä aiheutuu ongelmia, koska asiakkaat voivat helposti peruuttaa kaikki varauksensa tietämättä tekevänsä niin. Mietitään tähän ratkaisua esimerkiksi peruttavien varausten määrän näyttämistä poiston vahvistus ruudussa.

**Lappi**
* RDA-muutosta varten kuvailutiimi kokoaa korjausajolistaa
* Varmistettiin perustelut asiakkaalle, miksi henkilötunnus on tallennettava myös lapsiasiakkaalle. 

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2024#viikko-4) - [Palaa sivun alkuun](/paakayttajat2024)

## Viikko 3

Aika: 16.1.2024 klo 9.15<br />
Läsnä: Piia Semenoff, Pirkko-Liisa Lauhikari ja Veli-Pekka Marjoniemi (OUTI), Päivi Knuutinen (Vaara), Anni Rajala (Vaski), Kati Sillgren (Helle), Hanna Ikonen (Lumme), Anneli Österman ja Pasi Kallinen (Koha-Suomi), Tuomas Kunttu (Kyyti), Reetta Pihlaja (Siilinjärvi), Leena Kinnunen, Pia Kusmin ja Maria Joona (Lappi)

**Yhteiset**
* Onko [Integraatiot-lista](https://github.com/KohaSuomi/Koha/wiki/Integraatiot) oman kimpan osalta ajantasalla? Uusia, poistuneita?
* [Yksiselitteinen ilmaisu varauksen keskeytyksen viimeiselle voimassaolopäivälle #19](https://github.com/KohaSuomi/Koha-translations/issues/19#issuecomment-1883024818)
  * Anneli muuttaa until-tekstit niin, että valitaan ensimmäinen päivämäärä, jolloin varaus jatkuu.
  * Anneli tekee tiketin yhteisöön until-sanan epämääräisyydestä
  * Finnan käännökset kannattaa myös katsoa läpi ja jos joku keksii hyvät käännökset, voi niitä ehdottaa Finna-kanavalla Matrixissa. Käydään läpi ensi viikolla ja päätetään, mitkä niistä olisi hyvä ja laitetaan sitten Finna-toimistoon pyyntö muuttaa teksti kaikille kerralla.
* [Vkon 3 päivitys](https://github.com/KohaSuomi/Koha/discussions/1010)
* Muistutus: [Useamman samanaikaisen varauksen varaamisessa valinnan poisto tietueelta ei vaikuta ja varaus tehdään silti #780](https://github.com/KohaSuomi/Koha/issues/780) - CSS:n lisäys
* Sovittiin, että kimpoissa kerätään lista yleisimmin käytetyistä kielikoodeista, jolta puuttuu vielä selkokielinen käännös, joka näkyy faseteissa. Lisätään niille sitten käännös tietokannan tauluun. Ei lisätä käännöstä kaikille mahdollisille yli 400 kielikoodille. Tällä hetkellä käännös löytyy 116 kielikoodille. Listat kirjataan [tikettiin #885](https://github.com/KohaSuomi/Koha/issues/885).

Pohjoisesta etelään

**OUTI**
* Kempeleen liikuntalainaamolle on tehty uusi nidetyyppi, joka on muutoin sama kuin meidän lyhytlainat, mutta laina-aika on 3 vrk.
* Vaalan kirjastosta on tullut myös toive, että haluaisivat saman tyyppisen uuden nidetyypin, mutta jossa laina-aika olisikin 7 vrk.
* Muhoksen kirjasto on mennyt remontin vuoksi kokonaan kiinni eilen 15.1. ja on loppukuun kiinni. Kirjaston niteet muutettu Muuttolaatikossa-tilaan.
* OUTIssa maksujen maksimimäärä on Finnassa sentin isompi kuin Kohassa. 
  * OUTIssa lainauskiellon raja on 11,99 euroa.
  * Jos asiakkaalla on maksuja 12,00 euroa, asiakas on Kohassa lainauskiellossa, mutta Finnassa raja tulee vastaan, kun asiakkaalla on maksuja 12,01 euroa.
  * Finnaan tulee kyllä ilmoitus, että kirjastokorttisi on lainauskiellossa, mutta asiakas pystyy uusimaan lainansa.
  * Tätä ei ole havaittu muissa kimpoissa.
    * Sovittiin, että muissa kimpoissa tätä testataan ja kirjataan asiasta Matrixin Finna-kanavalle ja Pirkko-Liisa ottaa lopuksi yhteyttä Finna-tukeen.
   
**Vaara**
* ei mitään erityistä mainittavaa, paitsi tiedustelu Firefox esr-versiosta, mikä muilla kimpoilla on käytössä. Suurimmalla osalla Firefox 115.6.0esr tai 115.3.1esr. Vaarassa vanhempia versioita. Pitää pyytää päivittämään.

**Vaski**
* Pidemmät pin-koodit otettu virallisesti käyttöön (muutokset automaateille, ovilukijoille ja verkkokirjastoon tehty jo aiemmin, mutta tästä viikosta eteenpäin aletaan varsinaisesti tarjoamaan 4-10 numeroa pitkää koodia).
* ATK-ihmisten kokoontumisajot Turussa 25.-26.4.2024, vanhalla jakelulistalla lähtenyt ennakkotieto eilen. Esitys-ehdotuksia otetaan vastaan. Ohjelma ja ilmoittautumislinkki tulossa, kunhan valmistuvat.
* Seinäjoki pyytänyt Koha-esittelyä helmikuulle.

**Helle**
* Asiakastiedon avausyrityksesta Koha antanut Virhe 500 -ilmoituksen. Syy: asiakastiedossa oli syntymäaika-arvona kesäaikaan siirtymispäivä. Tiketti #624
* Marc-mäppäysmuutos tehty sovitusti 15.1.2024 (biblio.copyrightdate-sarakkeeseen MARC-kentät 264c ja 260c).

**Lumme**
* Normaalia ylläpitoa.

**Kyyti**
* Ei erityistä, vasta töihin palattu.

**Siilinjärvi**
* Ei erityistä
* Joudutaan ehkä tekemään uusi nidetyyppi konsolipeleille, jotta niille saadaan tiukempi lainarajoitus. Tämä yksittäisen asiakkaan vuoksi.

**Lappi**
* Kemin kassa saatu toimimaan päivityksen jälkeen.
* Posion koulukirjastoa varten tehty uusi nidetyyppi 56 vrk:n aineistoille. 

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2024#viikko-3) - [Palaa sivun alkuun](/paakayttajat2024)

## Viikko 2

Aika: 9.1.2024 klo 9.15<br />
Läsnä: Anneli Österman, Kassu Pohto, Lari Strand (Koha-Suomi), Reetta Pihlaja (Siilinjärvi), Kati Sillgren (Helle), Pirkko-Liisa Lauhikari ja Piia Semenoff (OUTI), Leena Kinnunen ja Pia Kusmin (Lappi), Päivi Knuutinen, Auli Rantasalo, Irina Halminen (Vaara), Hanna Ikonen (Lumme), Mikko Liimatainen (Vaski), Annika Helastila, Elina Uotila (Kirkes)

**Yhteiset**
* Etenemisaikataulu [tiketille 693 eli publicationyear/copyrightdate -mäppäysmuutos](https://github.com/KohaSuomi/Koha/issues/693)
  * [Mäppäysmuutoksen teko-ohje](https://koha-suomi.fi/dokumentaatio/asetukset/#19-kohan-marc-m%C3%A4%C3%A4ritykset)
  * Porrastetaan niin, että ajetaan kaksi kimppaa/yö. Mäppäysmuutos pitää tehdä ennen ajoa. Peukuta tiketissä seurantakommenttia, kun mäppäysmuutos on tehty. Lari täppäilee biblio-ajon täpät.
    * 9.1. Lappi ja OUTI
    * 10.1. Siili ja Vaara
    * 11.1. Lumme Kyyti
    * 15.1. Helle ja Kirkes
    * 16.1. Vaski
* Miten kannattaa edetä [tiketin #780](https://github.com/KohaSuomi/Koha/issues/780) suhteen?
  * Riittääkö raksien piilotus vai pitäisikö raksit saada vaikuttamaan.
    * Päätös: piilotetaan raksit
* [Haluaako joku testata](https://github.com/KohaSuomi/Koha/issues/628)?
* [Vkon 2 päivitys](https://github.com/KohaSuomi/Koha/discussions/999)
* [Huoltoikkuna keskiviikkona 10.1.2024](https://github.com/KohaSuomi/Koha/discussions/993)
  * [Redmine suljetaan](https://github.com/KohaSuomi/Koha/discussions/994)

Etelästä pohjoiseen

**Siilinjärvi**
* Ei mitään merkittävää
* Paitsi edelleen ihmetellään Finna-toimiston kanssa, miksi lainaushistoria Finnassa näkyy tietokoneella, mutta ei mobiililaitetta käytettäessä. Lainaushistoria tuntuu olevan asiakkaille kuitenkin tärkeä asia. Keskusteltiin laajemminkin lainaushistoriasta, esim. poistettujen niteiden puuttumisesta lainaushistoriassa.

**Helle**
* Asiakkaan maksujen poistosta muodostunut maksuihin hyvitettävää poistettavien maksujen arvosta. Voisiko johtua siitä, että ko. maksuja on poistettu kahdessa kirjastossa lähes samaan aikaan (maksutapahtumissa sekunnin aikaero accountlines-taulussa).

**OUTI**
* Muutamilla asiakastunnuksilla hävinnyt verkkokirjastosta Lainat-sivulta ”Uusi kaikki” toimintapainike. Ongelmasta laitettu Finna-tukeen.
* Ilmoitetaan Finna-tukeen, että kaikille Koha-Suomen kimpoille voivat laittaa tuotantoon palautuskehotusten tekstit ja käännökset.
* Koha-jumit 8.1. n. klo 9.37 ja 9.1. n. klo 9.32. Aiheuttajana OUTIa vaivanneet tietokantataulujen lukkiutumiset. Yritetään tehdä koha-suomimuutos, jolla näistä ongelmista päästäisiin eroon.
* Oulun kaupungin laskutusjärjestelmä muuttuu Intimestä Unit4:een.
* Teoksen varaukset sivulla ”Saatavana, ei lainattavissa” (damaged-arvo) olevilla niteillä näkyy Varaus-sarakkeessa ”Nide vaurioitunut”. Edellisessä versossa käännöksenä oli ”Ei varattavissa”. Päätettiin, ettei tehdä käännöstä tälle.

**Lappi**
* kysyttiin miten niteiden tilat vaikuttavat OKM:n lainatilastoihin. Tieto löytyy OKM-raportin asetuksista.
* Kemissä päivitetty CPU:n kassa ja yhteydet Kohaan katkenneet, asia ilmeisesti CPU:lla ja Kodolla hoidossa.
* Lapin henkilökunnan Kysy Kohasta -tilaisuus suunnnittelussa, samoin käyttäjäryhmän kokous.

**Vaara**
* Tilastotietojen keruu alkanut
* Päivi yritti saada Vaskin viikolla 51 kertoman tyylisen nidetyypin käyttöön. Nidetyypissä voi varata esineen vain niteen kotikirjastosta
lainattavaksi. Testi-Finnassa varauspainike ei tullut ollenkaan näkyviin, jos asiakkaan kotikirjasto oli muu kuin ko. esineen kotikirjasto. Kun 
asiakas oli samasta kirjastosta kuin esine, varauspainike tuli näkyviin. Kysyin neuvoa myös Vaskista, mutta ei sielläkään keksitty mikä olisi eri tavalla
asetuksissa meidän järjestelmissä.
* Hyllyvarauslista on joidenkin mielestä epäselvä, mikä kummastuttaa.

**Lumme**
* Lumpeissa ollut syksyllä usein indeksointivirheitä tietueiden poistojen jälkeen. Ongelma näyttää johtuvan siitä, että Koha luo indekseille replikan, joka ei toimi. Nyt nämä replikat on tiputettu pois.
* Asiakas toivoi Finnaan tulostettavaa versiota lainaushistoriasta. Tämä ei ole käytännöllistä listan jatkuvan päivittymisen takia, joten asiaa ei viedä eteenpäin.

**Vaski**
* Varauksen keskeytyksessä viimeistä päivää ei lasketa keskytykseen mukaan. Tämä on toisin aiempaa käsitystä, jonka takia käänösteksteissä ja verkkokirjastossa puhutaan keskeytyksen viimeisestä voimassaolopäivästä
* Järjestelmänvaihdon ajalta huomattiin maksuja, joissa maksun muodostumispäivä on virheellisesti 4.6.2021. Nämä maksut eivät nyt poistu automaattisesti niin kuin pitäisi.
* Puppe ollut käytössä muutaman viikon ajan. Tunnelmat olleet positiivisia. Voidaan järjestää esittely muillekin Pupen käytöstä.

**Kirkes**
* Sarastian mukaan zip-tiedostona tulevat yksittäiset laskut ovat liian työläiltä. Kuitenkin Vaskista lähtevät laskut samalla tavalla. Jatketaan asian selvittelyä ensi viikolla, kun Emmi palaa lomalta.
* Lisätty Tarramuutos -tila käyttöön ohjeen (https://github.com/KohaSuomi/Koha/issues/799) mukaisesti. Ihmetellään sen toimintaa vielä.
* Toivottiin Videopelien lainamäärät -raportin korjausta ja kyseltiin mahdollisuutta selvittää seutulainojen lukumäärää.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2024#viikko-2) - [Palaa sivun alkuun](/paakayttajat2024)

## Viikko 1

Aika: 2.1.2024 klo 9.15<br />
Läsnä: Anneli Österman, Emmi Takkinen ja Lari Strand (Koha-Suomi), Reetta Pihlaja (Siilinjärvi), Leena Kinnunen ja Pia Kusmin (Lappi), Hanna Ikonen (Lumme), Päivi Knuutinen ja Irina Halminen (Vaara), Pirkko-Liisa Lauhikari ja Piia Semenoff (OUTI), Mikko Liimatainen (Vaski)

**Yhteiset**
* Kuittaus [tikettiin 459](https://github.com/KohaSuomi/Koha/issues/459), kun järjestelmäasetus muutettu.

Pohjoisesta etelään.

**Siilinjärvi**
* Maksujen mitätöinnit näyttäisivät menneen ainakin päällisin puolin ok.
* Unohtunut mainita: joulukuussa esitelty Kangasniemelle pienen kirjaston Koha-pääkäyttäjän tehtäviä.

**Lappi**
* Korjattu BTJ:n vanhat kirjankansilinkit (72376 kpl).
* Muita pieniä korjauksia
* Joissakin tietueissa Koha ja Finna ei osaa näyttää oikein &-merkkiä, vaan ne näkyvät tekstinä &amp;. Koskee lähinnä hankintatietueita, korjaantuu todennäköisesti, kun tulee täysi tietue.

**Lumme**
* Ei mitään mainittavaa.

**Vaara**
* Ei mitään mainittavaa.

**OUTI**
* Asiakkaalta tullut palautetta, että Finnan lainaus- ja varaussivuilla olevat toimintopainikkeet ”Uusi valitut”, ”Uusi kaikki”, ”Muokkaa valittuja” ja ”Peru valitut” ovat niin harmaita ja huomaamattomia, että niitä on hankala huomata sivuilta. OUTIn Finna-tuki reklamoinut asiasta Finnaan.
* Asiakkaalta tuli palautetta, että hänen kahdesta lainasta vain toisesta oli tullut lainakuitti sähköpostiin.Tiketti: [OUTI: Kaikki asiakkaan lainat eivät muodostuneet "Lainasit tänään"-viestiin · Issue #991 · KohaSuomi/Koha (github.com). ](https://github.com/KohaSuomi/Koha/issues/991)
* Finnassa näkyvien palautuskehotusten otsikon ja selitteiden tekstimuutokset. Tiketti: [Finnassa näkyvien palautuskehotusten otsikon ja selitteiden muutokset · Issue #21 · KohaSuomi/Finna-kehitysehdotukset (github.com).](https://github.com/KohaSuomi/Finna-kehitysehdotukset/issues/21) Voisiko kimpat, joissa ruotsinkieliset sivut käytössä, tarkistaa, että palautuskehotusten tekstit näkyvät myös ruotsiksi oikein. Pyydetään sitten Finna-tukea laittamaan käännökset kaikille kimpoille tuotantoon.
* Raahen pieni Haapajoen kirjaston toiminta laikkaa 1.2.2024. Tehtävänä lakkautukseen liittyviä toimenpiteitä.

**Vaski**
* Ei mitään mainittavaa.
  
[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2024#viikko-1) - [Palaa sivun alkuun](/paakayttajat2024)
