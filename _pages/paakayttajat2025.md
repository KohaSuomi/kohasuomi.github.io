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

## Viikko 32

Aika: 5.8.2025 klo 9.15<br />
Läsnä: Päivi Knuutinen, Irina Halminen, Auli Rantasalo, Hanna Hyttinen (Vaara)

**Yhteiset**
* [Viikon 32 päivitys](https://github.com/KohaSuomi/Koha/discussions/1924)
* [Varauksen viimeiseksi noutopäivämääräksi muodostuu varauksen viimeinen voimassaolopäivä, jos pvm muuttaa tallentaessaan varausta #1174](https://github.com/KohaSuomi/Koha/issues/1174)
  * Tarkistatteko oman kimpan tilanteen ja jos on tarvetta, niin muuttakaa Finnassa varauksen teossa päivämäärävalinta valinnaiseksi (eli tyhjäksi).
  * Anneli sulkee tiketin, jos ei tule esille muuta korjattavaa.
* Miten edettäis [tiketin #1790](https://github.com/KohaSuomi/Koha/issues/1790) kanssa?

Pohjoisesta etelään

**Vaara**
* ei erityisempää, loman jälkeen vähän testausta

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-32) - [Palaa sivun alkuun](/paakayttajat2025)

## Viikko 31

Aika: 29.7.2025 klo 9.15<br />
Läsnä: Auli Rantasalo ja Hanna Hyttinen (Vaara), Elina Uotila ja Erika Miettinen (Kirkes), Anneli Österman (Koha-Suomi), Pirkko-Liisa Lauhikari, Katariina Pohto ja Piia Semenoff (OUTI), Pia Kusmin (Lappi), Tuomas Kunttu (Kyyti), Hanna Ikonen (Lumme), Lauri Hänninen (Lastu)

**Yhteiset**
* Viikon 31 päivitys
  * Ei päivitettävää
* [Raportit: Monivalintavalikon valinnan arvo monistuu myös seuraavaan ajonaikaiseen parametriin](https://github.com/KohaSuomi/Koha/issues/1912)
  * Tuodaanko korjaus myös meille vai odotetaanko versionvaihtoon?
  * Päätös: Tuodaan
* [TäTissä on tunnistetalkoot tehty](https://github.com/KohaSuomi/Koha/issues/1841). Talkoot voi aloittaa myös paikalliskannoissa.
  * Muistakaa vaihtaa apuraportin numero ja tietokannan osoite Tätin numerosta ja osoitteesta omaksi
  * [Lisätietoja Finnan tunnistetalkoista](https://mailchi.mp/helsinki.fi/finnan-tunnistetalkoot-kynnistyvt?e=f6d8dcb728). Osallistuminen on vapaaehtoista.
* Uusi raportti kirjastossa: [Tietueet, joissa on useampi nide samassa kotikirjastossa](https://koha-suomi.fi/dokumentaatio/raporttikirjasto/#tietueet-joissa-on-useampi-nide-samassa-kotikirjastossa), liittyy [tikettiin #1918](https://github.com/KohaSuomi/Koha/issues/1918)
* Testikantojen redusoinnissa huomattua: Luokitusoppaista ei saa poistaa vaihtoehtoja generic, lcc ja dewey, koska se aiheuttaa ongelmia redusoinnissa ja myöskin Kohassa, koska niillä on riippuvuuksia muualla Kohassa. Tieto lisätty [Asetukset-ohjeeseen Tekniseen dokumentaatioon](https://koha-suomi.fi/dokumentaatio/asetukset/#222-luokitusoppaat).
* [Asiakasvarmenteiden vaihto 2025](https://github.com/KohaSuomi/Koha/issues/1920)
  * Uusi varmenne jakoon viimeistään ma 11.8.2025
* Tiketin [Koha #1681](https://koha-suomi.fi/dokumentaatio/intranetusercss/#hyllyvaratun-teoksen-lainatapahtuman-viestien-muokkaus) rimpsu dokumentoitu CSS-kirjastoon.

  **Vaara**
  * ei mainittavaa, rauhallista ollut
  
   **Kirkes**
* Asiakas on poistanut varauksen Finnan kautta 15 sekunnin kuluessa siitä, kun virkailija on tärppäyttänyt varauksen Kohassa. Henkilökunnalta tullut kysymys, miksi Finna antaa poistaa noudettavissa olleen varauksen. Erikan testien perusteella varauksen poisto Finnan kautta onnistuu, vaikka varaus olisi jo Kohan mukaan noudettavana, jos Finnaan kirjautuneella asiakkaalla on omien varausten sivu auki varauksen tärpätessä ja sen jälkeen. Finnan toiminta saattaa johtua siitä, että Kohan omassa verkkokirjastossa noudettavan varauksen poisto on mahdollista. Jos Finnan varaussivua päivittää tai käy millä tahansa muulla sivulla, varausten tilanne päivittyy Finnaan reaaliaikaisesti. Koska kyseessä ei kokemusten perusteella ole laaja ongelma, ei asiaan tällä erää puututa enempää.
* Kirkes-kirjastoilla ei ole varauksen noutomuistutusta käytössä, koska siitä, että viesti tulee sulkupäivinä joka päivä, on tullut palautetta. Vaski-kirjastoilla varauksen noutomuistutus on käytössä sähköpostivaihtoehtona, tekstiviestivaihtoehto on mahdollista piilottaa. Voidaan miettiä, otetaanko myös Kirkes-kirjastoille käyttöön Vaskin malli.
* Elina tehnyt signum-muutoksen edellyttämät tarrapohjamuutokset Järvenpäälle ja Erika Tuusulalle. Tarrapohjamuutokset ja automaattien säännöt ohjeistetaan vielä muille Kirkes-kirjastoille.
* Mäntsälässä näkynyt kahdeksan laskukopiota, vaikka vain seitsemän pitäisi olla lähdössä. Elina tarkistanut, että vain seitsemän laskua näkyy pending-tilaisena. Ylimääräinen laskukopio on marraskuulta 2024. Jos tällaisia tapauksia tulee lisää, tehdään tiketti.

**OUTI**
* On ollut rauhallista, ei erityistä mainittavaa.

**Lappi**
* Normaalia ylläpitoa, rauhallista on.

**Kyyti**
* Kysyin Kohan rajapinnan osoitetta, jonka Anneli lähetti kokouksen jälkeen Matrixissa
* Lomilta palattu, ei muuta mainittavaa

**Lumme**
* Ei mainittavaa.

**Lastu**
* Normaalia ylläpitoa, rauhallista
* Tekstiviestien lähdöstä palautuva epäonnistuminen ja uudelleen yritykset mietitytti

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-31) - [Palaa sivun alkuun](/paakayttajat2025)

## Viikko 30

Aika: 22.7.2025 klo 9.15<br />
Läsnä: Anni Mäki-Mantila (Vaski), Pirkko-Liisa Lauhikari ja Piia Semenoff (OUTI), Elina Uotila ja Erika Miettinen (Kirkes), Pia Kusmin (Lappi), Anneli Österman ja Emmi Takkinen (Koha-Suomi), Hanna Ikonen (Lumme), Ville Kivioja (Kyyti-kirjastot), Lauri Hänninen (Lastu-kirjastot), Lotta Juvonen & Vilgot Strömsholm (Helle)

**Yhteiset**
* [Viikon 30 päivitys](https://github.com/KohaSuomi/Koha/discussions/1915)

Pohjoisesta etelään

**Vaski**

* Vaskille lisätty uudet hakufasetit Kaunokirjallisuus ja Tietokirjallisuus. Lisäksi lisätty js-koodi, joka järjestelee itse lisätyt hakufasetit haluttuun järjestykseen: https://github.com/KohaSuomi/Koha/issues/1908.
* Vaski-testi meni nurin perjantaina 18.7. ja ainakin maanantaina 21.7. havaittiin hidastelua aina silloin, kun raporttia ajettiin ja raportin ei tarvinnut ole edes mitenkään erityisen raskas. Laitetaan viestiä tämän tiimoilta, jos ongelma edelleen jatkuu.
* Ihmetelty, miksi asiakkaan lisäyksessä näkyy pari itsepalveluun liittyvää asiakasmäärettä ja virkailijan käyttöoikeuksien muokkauksessa borrowers-oikeuksien alla tyhjiä rivejä. Tehty tiketti https://github.com/KohaSuomi/Koha/issues/1916.

**OUTI**
* Kun Oulun kuvailija oli palauttanut TäTissä Lokien katselu -toiminnossa tietueita, palautuksen jälkeen hän oli huomannut, että toistetut osakentät 100e, 700e, 505t katoavat, myös 880-kentistä katoaa tietoa ja kentistä kopioituu tietoja kokonaan vääriin kenttiin. Lisäksi hän oli huomannut, että osassa 700-kentissä olleet t- ja l-osakenttä hyppäävät kaikkiin 700-kentän toistumiin. Tiketti: https://github.com/KohaSuomi/Koha/issues/1913
* Saatiin palautetta, että Kohassa ja Finnassa kun klikkaa tekijän nimikenttää, hakutulokseen tulee myös muiden saman nimisten henkilöiden teoksia, vaikka klikatussa tekijäkentässä on käytetty Asterin auktoriteettimuotoa. Esimerkkinä oli Eino Leino. Koha hakee tekijäkentästä ei auktoriteettikentästä.
* Oulussa Myllyojan kirjastossa oli asiakkaan kaksi vanhentunutta noudettavaa varausta vielä seuraavana päivänä noudettavissa tilassa. Eli varaukset olivat vanhentuneet 17.7., mutta yöllisessä varausten vanhentumisajossa oli ollut ilmeisesti joku kupru, kun nämä kaksi varausta olivat jääneet vanhentamatta. Muita vastaavia OUTIsta ei löytynyt. Tiketti: https://github.com/KohaSuomi/Koha/issues/1914
  
**Kirkes**
* Suomi.fi-REST-rajapinnan käyttöönotto odottaa lomakauden päättymistä. Otetaan käyttöön elokuussa, jotta ehditään tiedottaa henkilökuntaa ja mahdollisesti asiakkaitakin.

**Lappi**
* Normaalia ylläpitoa, rauhallista on.
* Raporttien päivitykseen tarvitaan varmaan kehittäjien/Annelin apua.

**Lumme**
* Juhannusviikolla sattunut kaupungin laskujen lähetys OmaPostiin kirjaston nimissä on selvinnyt. Ongelma paikallistettiin OmaPostiin ja tätä selvittelevät yhdessä Meitan kanssa.
* Muuten rauhallista.

**Lastu**
* Normaalia ylläpitoa.
* Laskutusasiat edelleen selvityksessä.
  
[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-30) - [Palaa sivun alkuun](/paakayttajat2025)

## Viikko 29

Aika: 15.7.2025 klo 9.15<br />
Läsnä: Emmi Takkinen (Koha-Suomi Oy), Pia Kusmin (Lappi), Auli Rantasalo klo 9.15-9.20 (Vaara). Erika Miettinen (Kirkes), Kati Sillgren (Helle), Pirkko-Liisa Lauhikari ja Piia Semenoff (OUTI), Reetta Pihlaja (Siilinjärvi)

**Yhteiset**
* Viikon 29 päivitys

Etelästä pohjoiseen

**Lappi**
* Normaalia ylläpitoa

**Vaara**
* Hiljaista on, ei mainittavaa

**Kirkes**
* Erika käynyt läpi signum-muutoksen edellyttämiä toimia, mm. raporttien tarkistusta.
* Toinen Kirkes-pääkäyttäjä Elina palaa lomalta tällä viikolla.

**OUTI**
* Kuvailija oli tehnyt Finnan tietuetalkoiden tietueita TäTissä ja hän oli vahingossa laittanut väärät muokkaussäännöt 130 tietueelle. Tietueet pitäisi palauttaa takaisin edelliseen versiooon. Muokatut tietuenumerot ovat tallessa excelissä. Kehittäjän kanssa tulimme siihen tulokseen, että paras ja varmin ratkaisu on, että Oulussa palautetaan muokatut tietueet itse manuaalisesti.
* Oulun Finvoice-laskutusajolla "testataan" uutta SFTP-moduulia keskiviikkona 16.7. Jos laskujen lähetys toimii ongelmitta uudella lähetystavalla, moduuli otetaan käyttöön myös muissa kimpoissa.

**Siilinjärvi**
* Signum-muutokseen liittyvät tiketit käyty (toivottavasti) läpi ja kommentoitu Siilin osalta. Muutoksen aikataulusta ei kai ole vielä mitään tietoa?
* Muuten rauhallista.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-29) - [Palaa sivun alkuun](/paakayttajat2025)

## Viikko 28

Aika: 8.7.2025 klo 9.15<br />
Läsnä: Erika Miettinen (Kirkes), Kati Sillgren (Helle), Noora Suvanto (Lappi), Iina Niemi (Vaski), Janne Seppänen (Lastu), Auli Rantasalo (Vaara), Pirkko-Liisa Lauhikari (OUTI), Piia Semenoff (OUTI), Roosa Väisänen (Kyyti), Hanna Hyttinen (Vaara), Kati Sillgren (Helle), Pasi Kallinen (Koha-Suomi)

**Yhteiset**
* Ei päivitystä
* [Ke 9.7. huoltokatko](https://github.com/KohaSuomi/Koha/discussions/1904)

Pohjoisesta etelään

**Lastu**
* DNA saanut korjattua [ongelman](https://github.com/KohaSuomi/Koha/issues/1895) jossa osa tekstiviesteistä päättyi erikoiseen virheeseen.
* Muuten hiljaista, perusylläpitoa.

**OUTI**
* Kirjastojen kesäsulkutoimenpiteet ovat aiheuttaneet vielä säätöä.
* Väistökirjastona toiminut Pekurin kirjasto on mennyt kiinni heinäkuun alusta alkaen ja muutto peruskorjattuun pääkirjastoon eli keskustakirjasto Saareen on alkanut. Ma 7.7. niteille, joiden havaintokirjasto oli Pekuri, muutettiin havaintokirjastoksi Saaren kirjasto ja niteet vielä muuttolaatikossa-tilaan.

**Vaski**
* Perusylläpitoa

**Helle**
* Porvooseen tulossa pilottikäyttöön EnvisionWare varausjärjestelmä Cloud 9 (asiakaskoneille/-laitteille). [Helle, Porvoo: Envisionwaren varausjärjestelmän Cloud 9 käyttöönotto](https://github.com/KohaSuomi/Koha/issues/1903)

**Kirkes**
 * Perusylläpitoa

**Lappi**
 * Perusylläpitoa

**Vaara**
 * ei mainittavaa, rauhallista

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-28) - [Palaa sivun alkuun](/paakayttajat2025)

## Viikko 27

Aika: 1.7.2025 klo 9.15<br />
Läsnä: Leena Kinnunen (Lappi), Päivi Knuutinen ja Hanna Hyttinen (Vaara), Emmi Takkinen (Koha-Suomi), Janne Seppänen (Lastu), Erika Miettinen (Kirkes), Reetta Pihlaja (Siilinjärvi), Piia Semenoff (OUTI)

**Yhteiset**
* Viikon 27 päivitys

Etelästä pohjoiseen

**OUTI**
* Oulun keskustassa olevan Pekurin kirjaston sulkutoimenpiteitä ja siihen liittyen Oulun keskustakirjasto Saaren avaustoimenpiteitä tehty. Saari aukeaa marraskuussa 2025, mutta se on jo nyt valittavissa varausten noutopisteeksi ja sen varauksia voi hakea Saaren lähettyvillä pysäköivästä kirjastoauto Onnelista avautumiseen saakka.
* kirjastojen kesäkiinniolot työllistävät edelleen.
* muutoin on rauhallista.

**Lappi**
* Uusia omatoimikoneita Rovaniemelle pääkirjastoon ja Korkalovaaraan
* Kittilän remontti alkaa elokuussa
* Raportit käyty läpi ja siivottu tarpeettomat pois
* Raportilla 544 löytyy asiakkaita, joiden sotu on kiinni useammassa asiakastiedossa. Näissä on asiakkaita, joilla ei näytä olevan tapahtumia 5 vuoteen, mutta eivät ole poistuneet 23.6. asiakkaiden poistoajossa, johtuneeko asiakkaille merkitystä rajoituksesta. Tehdään tiketti ja selvitetään, voiko asiakastiedot poistaa.

**Vaara**
* Viime viikolla keskiviikkoaamuna Joensuun pääkirjaston tunneloitu palautusautomaatti ei halunnut toimia, herjasi vain SIP-virhettä. Soitin Koha-kehittäjien päivystysnumeroon, jossa Johanna selvitti asiaa välikätenä Bittigurun ja Meitan kanssa. Lopulta palautusautomaatti saatiin toimimaan vasta torstaina iltapäivällä juuri ennen klo 15. Kesäloma-ajalla lienee osittain vaikutus ongelman ratkaisun kestämiseen.
* Samaan aikaan huomattiin myös Ceepos-kassojen yhteysongelma Kohaan eli maksut eivät päivittyneet kuten piti vaan ne piti hoitaa käsin. Johanna epäili, että asialla olisi jotain tekemistä tuon tunnelin kanssa, mutta ilmeisesti ongelma on kuitenkin jossakin muualla (Meitalle tehty tikettejä asiasta), sillä kassaongelma on edelleen.

**Lastu**
* [Tekstiviesteissä epäonnistuneita viestien lähetyksiä](https://github.com/KohaSuomi/Koha/issues/1895), selvitys menossa mistä johtuu. Myös Vaskissa vastaava ongelma.
* Muuten perusylläpitoa

**Kirkes**
 * Erika saanut tarrapohjia muokattua signum-muutoksen edellyttämiksi
 * Suomi.fi-REST-rajapinnan käyttöönotto olisi sovittavissa, mutta odotellaan lomakauden loppua, jotta pystytään paremmin tiedottamaan henkilökuntaa ja asiakkaita.

**Siilinjärvi**
* Aika kuluu asiakaspalvelussa, Kohassa ei mainittavaa.
* Testiltä puuttuvat nidetiedot: Jotain meni pieleen taulua ladattaessa. 500: Internal Server Error. 

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-27) - [Palaa sivun alkuun](/paakayttajat2025)

## Viikko 26

Aika: 24.6.2025 klo 9.15<br />
Läsnä: Johanna ja Lari (Koha-Suomi), Leena Kinnunen (Lappi), Päivi Knuutinen ja Hanna Hyttinen (Vaara), Katariina Pohto ja Piia Semenoff (OUTI), Janne Seppänen (Lastu), Erika Miettinen (Kirkes), Kati Sillgren (Helle)

**Yhteiset**
* Viikon 26 päivitys
* Raportteja:
  * [Verkkomaksujen jako kirjastoittain tai kunnittain](https://koha-suomi.fi/dokumentaatio/raporttikirjasto/#verkkomaksujen-jako-kirjastoittain-tai-kunnittain). [Liittyy tikettiin #1845](https://github.com/KohaSuomi/Koha/issues/1845)
  * [Finnan tunnistetalkoiden apuraportti](https://github.com/KohaSuomi/Koha/issues/1841#issuecomment-2955619706), löytyy Tätistäkin ja jota kuvailijat toivottavasti osaavat hyödyntää Finnan tunnistetalkoissa.
     * Kassu lisää raporttikirjastoon. 

Pohjoisesta etelään

**Lappi**
* Asiakkaiden poistoajo 23.6. poisti reilut 66000 asiakasta
* Automaattien AO-viestit kuntoon kolmelle automaatille, pyydetty muutos toimittajilta
* Väistöjen varauksiin ja eräpäiviin liittyvät ylläpidot

**Vaara**
* rauhallista pääkäyttäjätöiden osalta, yhden kirjastoauton varausten siirto kun ei muistettu ilmoittaa ajoissa kesälomaa
* raporttien ajoa ja testausta

**OUTI**
* Hiljaista on, joskin kesäsulut ja siirrettävät varaukset työllistävät.
* Testaamme tuotannossa CSS-variaatiota, jossa piilotetaan varauksen poistamisen vaihtoehto myös lainatessa kuljetetus- ja käsittelytilaisia varauksia. [#1681](https://github.com/KohaSuomi/Koha/issues/1681)

**Lastu**
* Normaalia ylläpitoa
* Lastun osalta asiakkaiden poistoajoa ei tarvitse tehdä tänä tai ensi vuonna, asiakasrekisteri siivottiin kesällä 2024

**Kirkes**
  * Kirkes-kirjastoilla on asetuksessa FailedLoginAttempts "10", kuten usealla muullakin, osalla asetukseen on asetettu "12". Erika huomannut muiden testausten ohessa, että Finna-käyttäjätili ei mennyt lukkoon kymmenellä epäonnistuneella kirjautumisella, vaikka sen pitäisi lukittua kuudennella kirjautumisyrityksellä. HUOM. Finna ei ilmoita tilin lukittumisesta, mutta huomautuksen pitäisi näkyä Kohassa. Muilla tilin lukittautuminen toimi oikein. Todennäköisesti ongelma koskee siis vain Erikan testauksia, eikä asiaa tarvitse tutkia enempää.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-26) - [Palaa sivun alkuun](/paakayttajat2025)

## Viikko 25

Aika: 17.6.2025 klo 9.15<br />
Läsnä: Leena Kinnunen ja Maria Joona (Lappi), Päivi Knuutinen (Vaara), Susanna Sandell (Vaski), Erika Miettinen (Kirkes), Anneli Österman ja Pasi Kallinen (Koha-Suomi), Hanna Ikonen (Lumme), Lauri Hänninen (Lastu), Piia Semenoff (OUTI), Roosa Väisänen (Kyyti)

**Yhteiset**
* [Viikon 25 päivitys](https://github.com/KohaSuomi/Koha/discussions/1886)
  

Etelästä pohjoiseen

**Lastu**
* Perusylläpitoa.

**Vaski**
* Omatoimikirjastoissa ajoittain levotonta. Mietimme voisiko lasten omatoimisuuden rajoittamisesta asiakastyypeillä olla apua puuttumiseen. Asiakastyyppi on kuitenkin tarkoitettu lapsen suojelemiseksi, eikä ongelmiin puuttumiseen.
   
**Lappi**
* Perusylläpitoa, kesälomasijaisten tunnuksia, väistöihin liittyviä tukitöitä
* 23.6. ajetaan asiakkaiden poistoajo

**Vaara**
* ei mainittavaa, perusylläpitoa

**Kirkes**
 * Kirkes-kirjastoissa havaittu hitautta lainausautomaateissa asiakkailla, joilla on paljon (kymmeniä tai noin sata) varausta tai lainaa. Muilla tällaista ei ole havaittu.

**Lumme**
* Perusylläpitoa.

**OUTI**
* Virheellisistä tekstiviesteistä ei ole tullut ilmoituksia raportille, viimeisin tullut 1.6. Seuraillaan tilannetta.

**KYYTI**
* Perusylläpitoa.
  

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-25) - [Palaa sivun alkuun](/paakayttajat2025)

## Viikko 24

Aika: 10.6.2025 klo 9.15<br />
Läsnä: Anneli, Emmi ja Olli (Koha-Suomi), Leena Kinnunen, Pia Kusmin ja Maria Joona (Lappi), Janne Seppänen ja Lauri Hänninen (Lastu), Elina Uotila ja Erika Miettinen (Kirkes), Päivi Knuutinen ja Hanna Hyttinen (Vaara), Anni Mäki-Mantila (Vaski), Katariina Pohto ja Piia Semenoff (OUTI), Kati Sillgren (Helle), Hanna Ikonen (Lumme), Reetta Pihlaja (Siilinjärvi), Roosa Väisänen (Kyyti)

**Yhteiset**
* [Viikon 24 päivitys](https://github.com/KohaSuomi/Koha/discussions/1869)
* voidaanko siirtää 19.8.2025 palaveri keskiviikolle 20.8.2025?
  *  siirretään ke 20.8.2025 klo 9.15

Pohjoisesta etelään

**Lappi**
* EDItX tilaussanomien käsittelyssä ongelmia 9.6. klo 23.05 ja 6.6. klo 23.05. Aamulla viestit tulleet perille. 
* Rovaniemen remonttien aiheuttamat muutokset työllistävät (varausten noutopisteiden muutoksia, eräpäivien massamuutoksia...). Remontteja yms. menossa tai alkamassa myös Posiolla ja Kittilässä. 
* Käyttäjätunnusten puolivuotistarkistus johtajilla
  
**Lastu**
* Testailtu Kohan automatiikkaa (decreaseLoanHighHolds) laina-ajan automaattisessa lyhentämisessä, ja toiminto vaikuttaa toimivan kyllä kuten se lupaakin. Ainoa selkeä puute on se, ettei toiminto osaa jättää huomiotta jäädytettyjä varauksia.
* Raindance-laskutusjärjestelmään muodostunut liian suuria laskutuslisiä, mutta laskutettavan aineiston tiedot lähtevät Kohasta ilman laskutuslisää ja se lisätään myöhemmin mukaan laskulle.

**Kirkes**
* Suomi-fi-viestien REST-rajapinnan käyttöönotto etenee ja testaukset ovat onnistuneet
* Kirkes-henkilökunnalta tullut kysymys laskusta, jonka Erika vienyt Matrixiin. Ongelma on todennäköisesti ollut Provincian päässä.
* Elina ja Erika tekevät kesän aikana tarrapohjiin signum-muutoksen edellyttämiä muutoksia.
* Kirkes-kirjastoissa ollut jälleen esillä henkilöllisyystodistusten käyttö asiakaspalvelussa, ja Erika kirjoittanut tästäkin Matrixiin. Henkilöllisyystodistusta aiotaan alkaa käyttää asiakkaan yksilöimiseen tilanteessa, jossa hänelle opastetaan kirjastokortin hakeminen verkkokirjastosta.
* Elina lomalla 16.6.-16.7.

**Vaara**
* Ihmetelty asiakkailla olevia miinussaldoja. Erilaisia tilanteita, osa verkkomaksuja tuplasti. Niihin ei vaikuta edes asiakkaan tiedoissa olevat hyvitykset. Joensuun kaupungin ohjeistuksia noudatettava palautusten suhteen.
* Genreluokista luovutaan, siirrytään kokoelmakoodeihin varmaan syksyllä, kunhan saadaan päätettyä menettelytavat.

**Vaski**
* Kesän kiinnioloja työn alla.
* Kelluttimen (kelluvan kokoelman hallinnan työkalu) jatkokehitys käynnistynyt, sen ohessa Turkuun lähivuosina tulevan aineistohotellin suunnittelua.
* Turun pääkirjaston palautusautomaation kilpailutus edennyt, sopimukset vielä allekirjoittamatta.
* Lisäksi luvattiin huolehtia Ohita-toiminnon lisäämisestä kausijulkaisuohjeeseen.

**OUTI**
* Kesän sulut ja muutot työllistävät.
* Tuotantoon on laitettu CSS, joka piilottaa turhia nappeja hyllyvarausilmoituksesta lainaustapahtuman yhteydessä. [Tiketti #1681](https://github.com/KohaSuomi/Koha/issues/1681)
* Tiedonhaun fasetteihin on otettu käyttöön hakurajaus tieto- tai kaunoluokkiin.
* Pirkko-Liisa lomalla 6.7. asti.

**Helle**
* Koha-aikakatkaistuu -ilmoitus otettu käyttöön.

**Lumme**
* Perusylläpitoa.

**Siilinjärvi**
* Tekstiviestirajapinnan muutos 2.6. sujui kivuttomasti. Ei muuta mainittavaa.

**KYYTI**
* Alettu suunnittelemaan tarvittavia muutoksia automaatin lajittelusääntöihin, joita signum-muutoksesta seuraa.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-24) - [Palaa sivun alkuun](/paakayttajat2025)


## Viikko 23

Aika: 3.6.2025 klo 9.15<br />
Läsnä: Päivi Knuutinen, Auli Rantasalo ja Irina Halminen (Vaara), Anneli Österman (Koha-Suomi), Katariina Pohto ja Pirkko-Liisa Lauhikari (OUTI), Erika Miettinen ja Elina Uotila (Kirkes), Anni Mäki-Mantila (Vaski), Hanna Ikonen (Lumme), Kati Sillgren (Helle), Janne Seppänen ja Lauri Hänninen (Lastu), Tuomas Kunttu (Kyyti)

**Yhteiset**
* [Viikon 23 päivitys](https://github.com/KohaSuomi/Koha/discussions/1863)
* [Kesäkuun huoltotiedote](https://github.com/KohaSuomi/Koha/discussions/1862)
* [Tuomaksen kysymys](https://github.com/KohaSuomi/Koha/issues/1737)
* Koha-Suomen kesäharjoittelija Olli aloittanut
* [Versionvaihdon tietovaranto](https://github.com/KohaSuomi/Koha-25x/wiki) jo perustettu ja wikiin kerätty alustavasti tietoja

Etelästä pohjoiseen

**Vaara**
* Aikakatkaisuliitännäinen laitettu päälle (JS-versiota ei ollut, joten ei tarvinnut poistaa käytöstä)
* Vaaran Koha on viime aikoina kaatunut muutaman vuorokauden välein öisin, kun plack ei ole käynnistynyt yöllisten ajojen ja uudelleenkäynnistyksen jälkeen. Tämä on todella ongelmallista, sillä omatoimikirjastot avautuvat normaalisti klo 7 eikä siihen mennessä yleensä kukaan kehittäjä ole ollut töissä. Myös kuvailutietojen valutus jää tulematta Vaaraan, koska siihen ei saada yhteyttä. Verkkokirjaston kautta asiakkaat eivät pääse aikaisin aamulla hoitamaan asioitaan. Toivottavasti kehittäjät saavat selville ongelman syyn ja korjattua sen.
* Pyhäselän kirjasto on mennyt kiinni muuttoa varten. Uusi kirjasto avataan Hammaslahden kirjaston nimellä elokuussa. Irina on tehnyt tarvittavia muutostöitä ja muuttoa.

**OUTI**
* Nyt kun kaikkiin Koha-maksuihin tule aiheuttajaperusteinen kirjastotieto ja maksut saadaan jyvitettyä raportilla kirjastokohtaiseksi, vertasimme Kohan antamia raporttitilastoja verkkomaksuportaalin antamiin maksutilastoihin. Maksutilastoissa on pientä eroa niin, että verkkomaksuportaalin maksutilastot ovat muutamia kymppejä pienempiä kuin Kohan vastaavalta ajalta olevat maksutilastot. Ero ei ollut kuukausitasolla merkittävä kokonaissummaan nähden. Kysytty kaupungin verkkomaksuportaalin pääkäyttäjiltä, missä vaiheessa maksut tilastoituvat varkkomaksuportaalin tilastoihin, joka voisi selittää pienen tilastoeron.
* OUTIssa on päätetty ottaa käyttöön lasten ja nuorten lyhytlainan nidetyyppi eli vastaava kuin aikuisilla on, mutta niin, ettei nidetyypille kirjaudu myöhästymismaksuja myöskään silloin, jos lainaaja on aikuinen.
* Oulun aineistoa on kellunut pääkirjaston perusparannusremontin ajan yksipuolisesti Iin, Limingan, Lumijoen, Pyhäjoen ja Pudasjärven kirjastoissa. Nyt kun remontti alkaa olla loppusuoralla, kellutussäännöt on poistettu Kohasta, jotta aineisto palaa automaattisesti kotikirjastoon Ouluun.

**Kirkes**
* Suomi.fi-viesteissä selvitetään REST-rajapinnan käyttöön siirtymistä.
* Ei muuta mainittavaa.

**Vaski**
* Huomattu, että tietueiden aikaleimat eivät ehkä muuttuneet taannoin tehdyssä asiasanakenttien korjauksessa, koska muuttuneista tietueista ei tullut Raportterin kautta tietoa Kelluttimeen. Tässä tapauksessa muuttuneilla tiedoilla ei ollut Kelluttimen kannalta merkitystä, mutta sovittiin että Vaski kyselee kuitenkin Pasilta muuttuivatko aikaleimat vai eivät.
* Mietitty niteiden erämuokkausten tekoa silloin, kun muutettavia niteitä kymmeniä tuhansia. Aiheuttavat hiukan viivettä indeksointeihin, taustatöihin tulee näistä sen verran ruuhkaa. Palaverissa annettiin suositus, että ei kannata tehdä kaikista ruuhkaisimpina aikoina suuria määriä erämuokkauksia.

**Lumme**
* MyLink-rajapinta otettu käyttöön.
* Normaalia ylläpitoa.

**Helle**
* Ylläpidossa kunnankirjastojen Vastausosoite-kenttään lisätty kirjaston sähköpostiosoite.

**Lastu**
* Pohdittu decreaseLoanHighHolds - asetusta, voisiko kenties siirtyä käyttämään sitä nykyisen manuaalisen laina-aikojen lyhentämisen sijaan. On ollut käytössä muissa kimpoissa, esim. Hellessä joskus aikoinaan, mutta toiminta ollut puutteellista. Jatketaan testailuja miltä toiminto vaikuttaa nykypäivänä ja onko ongelmia saatu ratkottua.

**Kyyti**
* Ei mainittavaa

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-23) - [Palaa sivun alkuun](/paakayttajat2025)

## Viikko 22

Aika: 27.5.2025 klo 9.15<br />
Läsnä: Leena Kinnunen ja Pia Kusmin (Lappi), Hanna Ikonen (Lumme), Anneli Österman ja Pasi Kallinen (Koha-Suomi), Kati Sillgren (Helle), Elina Uotila ja Erika Miettinen (Kirkes), Katariina Pohto, Piia Semenoff ja Pirkko-Liisa Lauhikari (OUTI, Päivi Knuutinen, Auli Rantasalo, Hanna Hyttinen (Vaara), Janne Seppänen ja Lauri Hänninen (Lastu)

**Yhteiset**
* [Viikon 22 päivitys](https://github.com/KohaSuomi/Koha/discussions/1852)
* Ehdotus: Voisiko kaikissa kimpoissa laittaa ylläpidossa kirjastojen vastausosoitteisiin kirjaston sähköpostiosoitteen, jotta jos asiakas syystä tai toisesta vastaa noreplystä tulevaan viestiin, ohjautuu vastaus kirjastolle. Nyt ne eivät mene minnekään.
  * [Kirjasto-osion ohjeistus Asetukset-sivulla](https://koha-suomi.fi/dokumentaatio/asetukset/#1-kirjastot)
* Uusi raportti: [Asiakkaat, joilla on useampi varaus samaan tietueeseen tietyllä aikavälillä](https://koha-suomi.fi/dokumentaatio/raporttikirjasto/#asiakkaat-joilla-on-useampi-varaus-samaan-tietueeseen)
* [Hyllyvaratun teoksen lainatapahtuman viesti valinnaiseksi](https://github.com/KohaSuomi/Koha/issues/1681#issuecomment-2854321162) - kuinka edetään tämän kanssa?
  * Kokeillaan laittaa Mikon has-muotoiset CSS-rimpsut käyttöön ja jos ne eivät toimi jollakulla, suositellaan selaimen päivittämistä uudempaan. Se olisi tietoturvankin kannalta paras ratkaisu. Kannattaa ensin testata testillä ja vasta sitten laittaa tuotantoon.


Pohjoisesta etelään

**Lappi**
* Yksi epäonnistunut verkkomaksu muodostunut. Selvitellään, mistä tullut.
* Remontit ja aukiolopoikkeukset työllistävät.
* Pääkäyttäjien lomat alkavat.

**OUTI**
* Toivottiin Annelilta ohjevideota offline-lainaamisesta.
  * Anneli alkaa tekemään ohjevideoita testikantojen redusoinnin jälkeen. Listalla ovat mmm. offline-lainaus ja varausten muokkaus eräajona-työkalun käyttö.
* Kimpan kirjastojen kesäkiinniolot, Pekurin kirjaston sulketuminen ja Keskustakirjasto Saaren ottaminen käyttöön työllistävät nyt kesän aikana.
* OUTIn pääkäyttäjien lomat alkavat pyörimään tällä viikolla.

**Lumme**
* Normaalia ylläpitoa.
* Ainoa Lumpeiden Toveri-ovikone on saatu vaihdettua.

  **Kirkes**
  * Järvenpään koulukirjastoilla ei ole kirjastoyksiköiden ylläpidossa sähköpostiosoitetta, johon asiakas voisi vastata. Elina selvittää, minkä osoitteen siihen voisi laittaa.
  * Erikalta kysytty, miksi (uusien) niteen tiedoissa on "Laskun numero" -kenttä. Kyseessä ilmeisesti tieto, joka niteelle automaattisesti tulee nidettä vastaanotettaessa.
  * Kohan yhteystietoihin päivitetään Kirkes-pääkäyttäjäksi Annikan sijasta Erikan tiedot.

**Vaara**
* Ihmettelyä testitietokannan asetuksista (recall päällä, vaikka tuotannossa ei)
* Kysymys, onko notloan-arvoa ei lainattavissa tai vain lukusalikäyttöön käytössä jossain kimpassa rinnakkain. Lastussa käytetään termiä Käytettävissä kirjastossa. Otetaan harkintaan meiläkin.
  
    


[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-22) - [Palaa sivun alkuun](/paakayttajat2025)

## Viikko 21

Aika: 20.5.2025 klo 9.15<br />
Läsnä: Leena Kinnunen (Lappi), Elina Uotila & Erika Miettinen (Kirkes), Päivi Knuutinen, Auli Rantasalo, Hanna Hyttinen (Vaara), Pirkko-Liisa Lauhikari, Katariina Pohto ja Piia Semenoff (OUTI), Reetta Pihlaja (Siilinjärvi; alkuosan), Hanna Ikonen (Lumme), Kati Sillgren (Helle), Tuomas Kunttu (Kyyti), Janne Seppänen ja Lauri Hänninen (Lastu)

**Yhteiset**
* [Viikon 21 päivitys](https://github.com/KohaSuomi/Koha/discussions/1836)
* Uusi raportti: [Tietueet, joissa on useampi nide kahdessa eri sijaintikirjastossa samalla kotikirjastolla](https://koha-suomi.fi/dokumentaatio/raporttikirjasto/#tietueet-joissa-on-useampi-nide-kahdessa-eri-sijaintikirjastossa-samalla-kotikirjastolla)
* [Kuvailupohjien tarkistus](https://github.com/KohaSuomi/Koha/issues/1835) - olematon 973-kenttä
* Muistattehan käydä sulkemassa itse kirjaamanne [Ratkaisu ehdotettu](https://github.com/orgs/KohaSuomi/projects/4/views/15) -tilaiset tiketit

Etelästä pohjoiseen

**Lappi**
* Ikuisuusprojekti Saamelaisbibliografian poiminta valmistumassa, eli Bibsysiin poimintaa varten korjattu saamelaisbibliografian tietueet. Haravointi uudelleen testauksessa tulevana yönä. Linkki bibliografiaan https://bibsys-almaprimo.hosted.exlibrisgroup.com/primo-explore/search?vid=SAPMI 
* Korjattu ja tarkistettu kaikkien kirjastojen tuplatilaukset 16.5. ongelmien jälkeen
* Muuten rauhallista, normaalia ylläpitoa

**Kirkes**
* Asiakkaalta tulleen palautteen mukaan palautusautomaatista tulostuneesta palautuskuitista puuttui viimeisenä palautettu nide, mutta sähköpostiin saapuneessa palautuskuitissa oli kaikki niteet. Jos asiakkaan palauttamissa niteissä olisi muiden asiakkaiden lainoja, ne voisivat puuttua sähköpostiin lähetettävästä palautuskuitista, mutta tässä tapauksessa tutkimme palautusautomaatin lokeja. Kyseessä ei todennäköisesti ole laajempi ongelma.
* Kirkes-kirjastoissa on käytössä Suomi.fi-viestit, mutta uuden rajapinnan käyttöönottoa on mietitty. Githubista löytyy tähän ohje: https://github.com/KohaSuomi/koha-suomi-messaging/wiki
 
**Vaara**
* Normaalia ylläpitoa ja tikettien testausta, etenkin signummuutokseen liittyvien asioiden testaus ja selvittely.

**OUTI**
* Käyty läpi OUTIn SIP-tunnuksia, joita on lähes 200. Käytöstä poistettuja tunnuksia ei ole poistettu koskaan. Listataan poistettavat tunnukset tikettiin poistettavaksi SIP-palvelimelta.
* 15.5. OUTIn kuvailijoilta tuli tieto, että 14.5. Kirjapalvelun paketti on jäänyt valumatta, mutta että pakettia ei kannattanut valuttaa enää jälkeenpäin, kun ei tiedetty mitä kaikkia tietueita oli korjattu valuneeseen pakettiin. Tehdään kehitysehdotustiketti siitä, että olisiko mahdollista valuttaa paketit aikajärjestyksessä, jotta tietueiden korjaukset eivät menisi hukkaan. 

**Siilinjärvi**
* Ei mainittavaa, hankintaportaali näyttäisi nyt toimivan ok.

**Lumme**
* Ei mainittavaa.

**Kyyti**
* Testikantojen testiasiakkaiden kirjastokorttien pseudonymisointi https://github.com/KohaSuomi/Koha/issues/1832. Onko mahdollista jättää pseudonymisoimatta? - On kuulemma mahdollista.
* Hallinnoi taustatöistä oli keskiviikon Kohan kaatumisen jäljiltä oli 14 epäonnistunutta taustatyötä. Aiheuttaako puutteellinen indeksi ongelmaa niteiden poistossa? - Voi aiheuttaa, koska niteiden poiston yhteydessä päivitetään myös indeksiä.
* Kuvailupohjien testaus ilmoittaa, että itemtype ei ole määritetty. Onko ongelma? - Ei ole, liittyy meidän MTYPEen.

**Helle**
* Voisiko käyttöön saada ominaisuuden, joka ilmoittaa kehittäjille kimppaan/kimppoihin siirtymättömistä kuvailutietue-paketeista?

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-21) - [Palaa sivun alkuun](/paakayttajat2025)

## Viikko 20

Aika: 13.5.2025 klo 9.15<br />
Läsnä: Leena Kinnunen, Pia Kusmin ja Maria Joona (Lappi), Päivi Knuutinen, Auli Rantasalo, Irina Halminen, Hanna Hyttinen (Vaara), Hanna Ikonen (Lumme), Lauri Hänninen (Lastu), Kati Sillgren ja Lotta Juvonen (Helle), Anneli Österman Lari Strand ja Emmi Takkinen (Koha-Suomi), Reetta Pihlaja (Siilinjärvi), Roosa Väisänen (Kyyti), Erika Miettinen ja Elina Uotila (Kirkes), Pirkko-Liisa Lauhikari ja Piia Semenoff (OUTI)

**Yhteiset**
* LocalCoverImages-asetus pois päältä tuotannoista
  * Kun kyseinen asetus on päällä, Koha yrittää hakea kaikille hakutuloksille paikallista kansikuvaa. Jos hakutuloksien joukossa on tietue, joka on poistettu, mutta se ei ole poistunut indeksistä, Koha näyttää 500 virhettä. 
  * Asetus on suositeltavaa ottaa pois päältä tuotannoista.
* [Viikon 20 päivitys](https://github.com/KohaSuomi/Koha/discussions/1826)
* [Toukokuun kuukausihuollon tiedote](https://github.com/KohaSuomi/Koha/discussions/1827)

Pohjoisesta etelään

**Lappi**

* Laskujen ulkonäkö on muuttunut, teksti on pienempää ja marginaalit kapeampia
* Muutettiin varausten noutopäiviä, ja kirjastot ottivat uusia kuitteja : jos otetaan uusi kuitti, siihen tulee alkuperäinen viimeinen noutopäivä.
* Hankintaportaalista ei siirry kaikki tilaukset Kohaan. 
* Circcontrol- asetus noudatti kirjautuneen käyttäjän kirjastoa, joka oli määritetty kirjastoon, jossa oli ohitettu eräpäivät. Testattu ja vaihdettu CircControl Koha Suomen suosituksen mukaiseksi "niteen kotikirjaston säännöt".
* Ranualla sijaitseva Japani-talo lakkaamassa, mietinnässä mitä niteille (n. 1600 kpl) tehdään
* Lapin käyttösäännöt uudistuivat huhtikuussa, ja sen seurauksena tarvitaan tieto poistajakirjastosta. Asia ratkesi hakemalla poistajatiedot lokien katselulla. 
* Kodo maininnut jossain asiantuntijapalaverissa mahdollisuudesta saada ns. virheraporttien tietoja Kohan about-sivulle, ei ilmeisesti edennyt?

**Vaara**
* normaalia ylläpitoa, vähän testausta ja yksi SIP2-tunnusten tekopyyntö
* Pyhäselän kirjasto muuttaa, Irinalla tehtäviä sen kanssa. Kirjasto sulkeutuu tämän kuun lopussa ja avataan heinäkuussa uudessa tilassa uudella nimellä eli Hammaslahden kirjasto.

**Lumme**
* Normaalia ylläpitoa.
* Kuortin kirjasto on nyt virallisesti suljettu.

**Lastu**
* Normaalia ylläpitoa.
* Montaa teosta varatessa eroavaisuuksia yhden varauksen tekemiseen nähden, esim. noutopiste tyhjänä ja kiireetöntä varausta ei voi tehdä.
  * Molemmista löytyi jälkikäteen tiketit yhteisöstä, [36871](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=36871) ja [38638](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=38638).
 
**Helle**
* otettu käyttöön Varauksen noutomuistutus -toiminto [Tiketti 1812](https://github.com/KohaSuomi/Koha/issues/1812)

**Siilinjärvi**
* Laskujen lisäksi Tulosta ilmoituksia -työkalussa fontin koko oli pienentynyt, mutta se on nyt korjaantunut [Tiketti 1828](https://github.com/KohaSuomi/Koha/issues/1828)
* Hankintaportaalin tiedonsiirto-ongelmat jatkuivat, mutta ne on nyt ilmeisesti korjattu ja sanomat tulevat perille Kohaan.

**OUTI**
* Testattu, mille kirjastolle accountlines-tauluun Koha-maksut kirjautuvat. Testien perusteella näyttäisi menevän seuraavasti:
  * Palautuskehotusmaksut: kirjastolle, josta lainat oli lainattu tai jos asiakkaalla on samalle eräpäivälle lainoja useammasta kuin yhdestä kirjastosta, maksu kirjautuu kirjastolle, josta asiakas oli lainannut lainan ensimmäiseksi.
  * Myöhästymismaksut voi määrittää järjestelmäasetuksella OverdueFineBranch, mille kirjastolle maksut kirjautuvat.
  * Noutamattoman varauksen maksu kirjautuu kirjastolle, jossa varauksen noutopaikka.
  * Kadonneen aineiston maksu kirjautuu kirjastolle, jossa nide asetettu kadonneeksi.
  * Manuaalisesti lisätty maksu kirjautuu kirjastolle, jossa maksu lisätty asiakkaan maksuihin.
  

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-20) - [Palaa sivun alkuun](/paakayttajat2025)

## Viikko 19

Aika: 6.5.2025 klo 9.15<br />
Läsnä: Anni Mäki-Mantila (Vaski), Päivi Knuutinen, Irina Halminen, Hanna Hyttinen (Vaara), Anneli Österman, Johanna Räisä ja Lari Strand (Koha-Suomi), Pirkko-Liisa Lauhikari, Katariina Pohto ja Piia Semenoff (OUTI), Reetta Pihlaja (Siilinjärvi), Tuomas Kunttu ja Roosa Väisänen (Kyyti), Hanna Ikonen (Lumme), Kati Sillgren ja Vilgot Strömsholm (Helle), Leena Kinnunen, Pia Kusmin ja Maria Joona (Lappi), Janne Seppänen ja Lauri Hänninen (Lastu)

**Yhteiset**
* [Viikon 19 päivitys](https://github.com/KohaSuomi/Koha/discussions/1819)
* Kohan ohje suomeksi - Työkalut-osioon lisätty osiot [Eräpäivien siirto eräajona](https://koha-suomi.fi/dokumentaatio/tyokalut/#126-er%C3%A4p%C3%A4ivien-siirto-er%C3%A4ajona) ja [Varausten muokkaus eräajona](https://koha-suomi.fi/dokumentaatio/tyokalut/#127-varausten-muokkaus-er%C3%A4ajona)
* Testikannat luodaan uusiksi touko-kesäkuun vaihteessa, kunhan palvelinten käyttöjärjestelmäpäivitys on ohi.

Etelästä pohjoiseen

**Vaski**
* Kyseltiin [Hakutulosnäytön muutoksia koskevan tiketin](https://github.com/KohaSuomi/Koha-23x/issues/157) perään. Koha-Suomi käsittelee omassa palaverissaan, keskusteltiin että mahdollisesti voisi olla hyvä käydä toiveiden ajantasaisuus vielä läpi tiedonhaku- ja indesointiryhmässä.
* Kyseltiin myös [kehitysehdotuksesta, joka liittyy hyllyvaratun teoksen lainatapahtuman tekstiin](https://github.com/KohaSuomi/Koha/issues/1681). Todettiin, että Annelin version ongelmana on se, että noudettavissa olevaa varausta ei saa kokonaan peruutettua tilanteessa jossa toinen asiakas noutaa varauksen puolesta. Vaski tarkistaa ja kommentoi oliko tämä Mikon versiossa huomioitu. Sen lisäksi sovittiin, että muutkin testaavat Mikon versiota (joka toimii Firefox ESR 128-versiosta eteenpäin) ja mietitään sitten testausten jälkeen mennäänkö sillä vai onko tarvetta harkita esimerkiksi javascript-pluginia.

**Vaara**
* ei erityistä, normaalia ylläpitoa

**OUTI**
* Oulussa on testattu Lyngsoen automaatin offline-ohjelmaa. Testaushavainnot laitettu Matrixin Automaatti-kanavalle.
* OUTIn Koha-pääkäyttäjät ovat koulutuksessa ke 7.5. koko päivän. Päivystyspuhelin on mukana, johon voi käyttäjät soittaa kiireellisissä asioissa esim. jos Koha ei toimi.

**Siilinjärvi**
* Kohan taannoisista kaatumisista aiheutui tarve kerrata henkilökunnan kanssa, kuinka poikkeustilanteessa toimitaan ja varsinkin että poikkeustilanteen jälkeen odotetaan kärsivällisesti käyttölupaa.
* Havaittiin tiedonhakuongelma eli jotain vikaa indeksissä. Korjaantui kun LocalCoverImages-järjestelmäasetukset otettiin pois päälltä. Siilissä ei edes ole käytössä omia kansikuvia.
* MyLink-tekstiviestirajapinta on tarkoitus ottaa käyttöön ma 2.6. Kuunneltiin tarkasti Lapin ongelmat.

**Kyyti**
* Henkilökunnalta tullut palautetta, kun tiedonhaun tuloksissa fasettien sisällöt eivät ole aakkosjärjestyksessä. Järjestelmäasetuksella FacetOrder saa määriteltyä näytetäänkö fasetit esiintymismäärän mukaisessa järjestyksessä, vai aakkosjärjestyksessä.

**Lumme**
* Normaalia ylläpitoa.

**Lappi**
* LinkMobilityn uusi rajapinta otettiin käyttöön 2.5., mutta 6.5. selvisi, että MyLink-ohjelma, jossa uudet tiedot ovat, oli demotilassa, eikä siksi lähettänyt viestejä. Demo poistettiin, ja viestit lähetettiin uudelleen, lisättiin varauksille noutoaikaa 9.-12.5. -> 16.5.


[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-19) - [Palaa sivun alkuun](/paakayttajat2025)

## Viikko 18

Aika: 29.4.2025 klo 9.15<br />
Läsnä: Anneli Österman ja Emmi Takkinen (Koha-Suomi), Leena Kinnunen ja Pia Kusmin (Lappi), Hanna Ikonen (Lumme), Tuomas Kunttu ja Roosa Väisänen (Kyyti), Reetta Pihlaja (Siilinjärvi), Irina Halminen (Vaara), Kati Sillgren (Helle), Janne Seppänen ja Lauri Hänninen (Lastu), Piia Semenoff ja Pirkko-Liisa Lauhikari (OUTI)


**Yhteiset**
* [Tuotantojen suhteen palattu normaaliin tilanteeseen ja testit ovat myös pystyssä](https://github.com/KohaSuomi/Koha/discussions/1806).


Pohjoisesta etelään

**Lappi**
* Normaalia ylläpitoa.

**OUTI**
* OUTIin on tullut asiakaspalautetta Finnan lainaushistorian järjestämisestä otsikon mukaan. Nythän Finnassa lainahistoria järjestyy ensin poistettujen niteiden mukaan eivätkä ne mene aakkosjärjestykseen ja vasta poistettujen niteiden jälkeen järjestyvät aakkosiin kokoelmasta edelleen löytyvät niteet. Tästä on tikettejä auki ja mietimme pääkäyttäjäpalaverissa miten asiassa nyt edetään?
  * Päätimme ottaa asian puheeksi seuraavassa Finna-kehitysehdotusten tapaamisessa toukokuussa (21.5.25025).
* Kaukopalveluohjelma Webkaken ja Kohan välinen yhteys katkesi OUTIssa la 26.4. Yhteys oli edellen poikki tiistaina aamulla.
  * Vika saatiin korjattua palaverin aikana. Syytä yhteyskatkolle ei ole OUTIlla tiedossa.

**Vaara**
* Normaalia ylläpitoa.
* Hankintaportaalissa palvelinvirheitä ja hidastelua.

**Lumme**
* Normaalia ylläpitoa.

**Kyyti**
* Hankintaportaalin tilauksissa on toisen aineistovälittäjän hinnoissa välillä nidekohtaisesti sentin heittoja lähetyslistassa ja Kohassa olevassa hinnassa. Tarkistin vielä EditX-sanoman ja siinä on sama hinta kuin Kohassa. Asia huomattu tänä vuonna. Lapissa havaittu sama asia.

**Siilinjärvi**
* Hankintaportaalin kanssa takuttu, jotain saatu jo korjattua.
* Muuten ei mainittavaa.

**Lastu**
* Pohdittu pitäisikö virkailijatunnuksia säilyttää järjestelmässä deaktivoituina vielä työsuhteen loppumisen jälkeen, sillä poistaminen vaikuttaa myös asiakastietojen katselun lokitietoihin
  * Palaverin jälkeen kysytty kaupungin tietosuojavastaavalta, jonka näkemys oli että tunnuksia on hyvä säilyttää deaktivoituina 6kk, jonka jälkeen tunnukset voi poistaa

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-18) - [Palaa sivun alkuun](/paakayttajat2025)


## Viikko 17

Aika: 22.4.2025 klo 9.15<br />
Läsnä: Pirkko-Liisa Lauhikari ja Piia Semenoff (OUTI), Leena Kinnunen (Lappi), Päivi Knuutinen ja Hanna Hyttinen (Vaara), Elina Uotila (Kirkes), Lauri Hänninen (Lastu), Susanna Sandell (Vaski), Pasi Kallinen ja Lari Strand (Koha-Suomi), Päivi Knuutinen ja Hanna Hyttinen (Vaara)

**Yhteiset**
* [Raportti tietueista, joissa on sama asiasana kahdessa eri MARC-kentässä #1787](https://github.com/KohaSuomi/Koha/issues/1787)
  * raportin voi lisätä omaan kantaan, jos haluatte siivota asiasanoja pois

Etelästä pohjoiseen

**VASKI**
* Asiakkaiden vanhenemispäivän siirtoajo tehty
* Testien käynnistystä odotellaan eri kehitysprojektien testauksen takia

**LASTU**
* Lastussa aiemmin tyhjänä tullut EditX-sanoma ilmoitellut itsestään pääsiäisen yli. Poistettu palvelimielta jo aiemmin, ja pitäisi olla nyt arkistoitunut. poistettu EDIFACT-sanoma uudelleen. Muuten normaalia ylläpitoa.

**OUTI**
* OUTIssa hyllyvarauksia 22.4. aamulla 3279 kpl. Pääsiäisen jälkeinen viikko on ollut perinteisesti yksi vuoden vilkkaimmista viikoista, joka voi näkyä myös Kohan käytössä hidasteluna.
* Oulussa on nyt loppu kevään ja kesän aikana menossa monta kirjastoa väliaikaisesti kiinni, joko remontin tai kesäkiinniolon vuoksi. Kaikki kiinni menot vaativat myös Kohaan muutoksia. Ensimmäisenä kiinni menee Tuiran kirjasto 30.4., joka muuttaa uusiin tiloihin ja avataan elokuussa uudestaan. Toukokuun lopussa alkaa ensimmäisten kirjastojen kesäsulut eli eivät ole auki edes omatoimella. Myös meidän pääkirjaston väistötila Pekurin kirjasto suljetaan kesäkuun lopussa ja remontoitu pääkirjasto avataan ehkä marraskuussa. Tämän väliajan asiakkaat voivat noutaa varaukset kirjastoauto Onnelista, joka parkkeeraa joka päivä entisen pääkirjaston (uusi nimi Oulun keskustakirjasto Saari) edessä. Kaikki kiinniolot vaativat jonkinlaisia muutoksia ja muutosten aikataulutusta Kohaan.

**Vaara**
* Ei erityistä mainittavaa. Vaarassa myös tyhjä hankintaportaalisanoma poistettava (lisätty tikettiin 1798).

**Lappi**
* Kohan Työkalut - Varausten muokkaus eräajona - ohje puuttuu Kohan ohjeesta.
* Rovaniemellä kesällä 1.6. lähtien Asemakirjaston (pääkirjaston väistö) paluu pääkirjastoon / Konttikirjastoon, Korkalovaaran muutto Vaaramon monitoimitaloon sekä Saarenkylän muutto väistöön remontin ajaksi. Paluu "normaaliin" kaikissa ajoittuu noin syyskuulle. Tiedossa siis muutoksia Kohaan, mm varausten noutopisteen siirtoja (ei ilmeisesti voi pääkäyttäjä itse tehdä).
* Kulunut viikko rauhallinen.

**Kirkes**
* Järvenpään kirjasto ottaa tällä viikolla käyttöön Canonin kirjastotulostuksen. Tieto on päivitetty integraatiolistaan. 

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-17) - [Palaa sivun alkuun](/paakayttajat2025)


## Viikko 16

Aika: 15.4.2025 klo 9.15<br />
Läsnä: Leena Kinnunen ja Pia Kusmin (Lappi), Hanna Ikonen (Lumme), Piia Semenoff ja Pirkko-Liisa Lauhikari (OUTI), Päivi Knuutinen, Auli Rantasalo, Irina Halminen, Hanna Hyttinen (Vaara), Annika Helastila ja Elina Uotila (Kirkes), Kati Sillgren, Lotta Juvonen, Vilgot Strömsholm (Helle), Anneli Österman, Pasi Kallinen ja Lari Strand (Koha-Suomi)

**Yhteiset**
* ei viikkopäivitystä palvelimien tiedostojärjestelmäongelman vuoksi

Pohjoisesta etelään

**Lappi**
* Vuoden 2024 budjetit ja tilit on suljettu.
* Normaalia ylläpitoa.

**OUTI**
* OUTIin tullut asiakkaalta toive: "Voisiko Finnaankin tulla käyttöön kaksivaiheinen kirjautuminen? Kirjautuminen pelkällä pin-koodilla ei ole turvallista. Finna-käyttäjän takana on kuitenkin runsaasti henkilötietoja." Kansalliskirjaston Yleisten kirjastojen Finna-tapaamisessa oli kerrottu, että tämä on jo Finna-kehityslistalla. Linkki sivulle: https://www.kiwi.fi/display/Finna/Yleisten+kirjastojen+Finna-tapaaminen+1.4.2025
* Asiakaspalvelutilanteessa ei oltu voitu lainata asiakkaalle varausta, kun hänellä oli liikaa lainoja ko. kirjastossa ja ilmeni, että asiakkaalla oli yli 200 lainaa (useasta eri kirjastosta). Asiakastyyppikohtainen lainaraja ei toimi ja laina- ja maksusäännöt toimivat kirjastokohtaisesti. Nidetyyppikohtainen lainaraja toimii ja hieman hillitsee asiakkaan lainamäärää. OUTI tekee tiketin tästä ja linkkaa siihen Larin löytämän Bugzilla-tiketin (https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=8137)

**Lumme**
* Ei mainittavaa.

**Vaara**
* Ei erityisempää. Tietojärjestelmäongelma aiheutti tietenkin oman hässäkkänsä.

**Kirkes**
* Edellisviikon käyttökatkoista selvittiin tällä tietoa ihan hyvin, ja ilmeisesti varalainausohjelman käyttö sujui kirjastoissa.

**Helle**
* Vanhentuneiden asiakastietojen poistoajo tehty [Tiketti 1572](https://github.com/KohaSuomi/Koha/issues/1572#issuecomment-2771492169)

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-16) - [Palaa sivun alkuun](/paakayttajat2025)

## Viikko 15

Aika: 8.4.2025 klo 9.15<br />
Läsnä: Iina Niemi (Vaski), Päivi Knuutinen, Auli Rantasalo, Irina Halminen (Vaara), Katariina Pohto, Pirkko-Liisa Lauhikari ja Piia Semenoff (OUTI), Hanna Ikonen (Lumme), Anneli Österman, Emmi Takkinen, Pasi Kallinen ja Lari Strand (Koha-Suomi), Maria Joona ja Pia Kusmin (Lappi), Janne Seppänen (Lastu), Reetta Pihlaja (Siilinjärvi, alkuosan), Kati Sillgren (Helle), Annika Helastila ja Elina Uotila (Kirkes)

**Yhteiset**
* [Viikon 15 päivitys](https://github.com/KohaSuomi/Koha/discussions/1784)
* [Huoltotiedote 9.4.2025](https://github.com/KohaSuomi/Koha/discussions/1783)
* [Varaustunnuksen boldaus -rimpsu lisätty IntranetUserCSS-kirjastoon](https://koha-suomi.fi/dokumentaatio/intranetusercss/#lihavoi-asiakasm%C3%A4%C3%A4re-varaustunnus-asiakkaan-yhteenveto-osiossa-vasemmalla), sen voi ottaa kimpassa tarvittaessa käyttöön. Liittyy [tikettiin 1753](https://github.com/KohaSuomi/Koha/issues/1753)

Etelästä pohjoiseen

**Vaski**
* Normaalia ylläpitoa.

**Vaara**
* Signummuutoksen tarvitsemia muutoksia testattu mm. tarratulostukseen ja palautusautomaatin toimintaan. Nämä muutokset tulevat viemään aikaa, monenlaisia kysymyksiä ja ongelmia.
* Niteen havaintohistorian ihmettelyä, miten sama nide voi olla samaan aikaan monen eri kirjaston listalla.

**OUTI**
* Muutamassa Oulun koulukirjastossa on ollut ongelmana Kohan itsepalvelulainauksessa, että CSRF-token on vanhentunut monta kertaa päivässä ja tästä syystä itsepalvelulainaus on kirjautunut ohjelmasta ulos ja lakannut toimimasta. Viikon 14 Koha-päivityksessä tuli itsepalvelulainaukseen pari korjausta, joista toinen ehkä korjasi ko. ongelman. Päivityksen jälkeen kouluilta ei ole tullut valituksia ongelmasta.

**Lumme**
* Normaalia ylläpitoa.
* Toivottiin, että tarrapohjiin saataisiin kopiointimahdollisuus tarratulostustyökalussa. Asiasta tehty tiketti.

**Lappi**
* Aiemmin mainittu Kysy Kohasta-koulutus- ja kyselytunti siirretään syksyyn.
* Normaalia ylläpitoa.

**Lastu**
* Kyseltiin oliko muualla havaittu ongelmaa, että varaustunnuksella haku ei onnistu jos tunnuksessa on väli. Oli havaittu, Vaskissa ohjeistettu toimimaan näin.
  > Valitse hakukentäksi "Varaustunnus" ja hakutyypiksi "Alkaa". Jos varaustunnuksessa on välilyönti, korvaa se alaviivalla, esim. 12_345
* Asiakkailta tullut toiveita näyttää laina-aika myös Finnassa, mutta nidetyypit sellaisenaan eivät välttämättä tähän taivu sellaisenaan. Laina-aika voi myös muuttua varauksen tekohetkestä lainaushetkeen.
* Kehitelty toimintoa, joka luo tietueen Niteet-välilehdelle kunkin niteen tietoihin linkin niteen havaintohistorian listaavalle raportille. JS-rimpsu löytyy [tältä tiketiltä](https://github.com/KohaSuomi/Koha/issues/1788), palaverin jälkeen pohdittu tehdäänkö tuosta plugari vai lisätäänkö IntranetUserJS-kirjastoon.

**Siilinjärvi**
* Korjailtu hankintaportaalin tilauksen 1.4. jälkiä, tilauksen tietueista ja niteistä tuli Kohaan vain osa, aiheutti vähän selvittelyä.
* Tiera ja Mikro-Väylä päivittävät 9.4. uudet DNS-osoitteet automaateille, ei pitäisi aiheuttaa Kohan päässä muutoksia.
* Jatketaan signum-muutostöitä. Ei pitäisi Siilissä olla mitään ylivoimaista.

**Kirkes**
* Toinen pääkäyttäjä on vaihtumassa toukokuun alusta, joten lähinnä on valmisteltu perehdyttämistä. 
* Signum-muutostöihin ryhdytään toden teolla sitten, kun uusi työpari on mukana remmissä.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-15) - [Palaa sivun alkuun](/paakayttajat2025)

## Viikko 14

Aika: 1.4.2025 klo 9.15<br />
Läsnä: Anneli Österman (Koha-Suomi), Janne Seppänen ja Lauri Hänninen (Lastu), Leena Kinnunen ja Pia Kusmin (Lappi), Päivi Knuutinen ja Auli Rantasalo (Vaara), Hanna Ikonen (Lumme), Katariina Pohto ja Piia Semenoff (OUTI), Reetta Pihlaja (Siilinjärvi)

**Yhteiset**
* [Viikon 14 päivitys](https://github.com/KohaSuomi/Koha/discussions/1772)
* Koha-seminaarin striimin tallenteet katsottavissa 2 viikkoa. Linkit löytyy [tapahtuman tiedotteesta](https://github.com/KohaSuomi/Koha/discussions/1665).
* Koha-seminaarista tulossa palautekysely
* Seuraava [Bugi-perjantai 4.4.2025 klo 13](https://github.com/KohaSuomi/Koha/discussions/1771)
* [Signumiin luokka ja pääsana](https://github.com/KohaSuomi/Koha/issues/923) - lisätty alitiketit tehtäville asioille. Puuttuukko vielä jotain?
  * Tuli toive, että kaikki laittaisivat esimerkkitiedoston (pdf) tarrapohjista tarrapohja-tikettiin. Tiedostoon voi kerätä esimerkit monenlaisista aineistoista.

Pohjoisesta etelään

**Lastu**
* Ei mainittavaa

**Lappi**
* Normaalia ylläpitoa.
* Suunnitellaan signum-muutosta ja Kysy Kohasta -koulutus- ja kyselytuntia.

**Vaara**
* Hion Digitalin kaupunkisovellus on korjattu lainauskiellossa olevien asiakkaiden kohdalta eli lainauskiellon ylittävät maksut estävät uusimasta lainoja. Varausten näyttämisessä on vielä ongelmaa.

**Lumme**
* Normaalia ylläpitoa.
* Näillä näkymin Kuortin kirjasto lopettaa toimintansa, asia on menossa vielä valituskierrokselle.

**OUTI**
* Oulun Ceepos-kassaympäristö siirtyi 1.4.2025 Oulun Monetran kassaympäristöön. https://github.com/KohaSuomi/Koha/issues/1718
* OUTI siirtyi käyttämään 1.4.2025 LinkMobilityn uutta MyLink APIa Kohassa. https://github.com/KohaSuomi/Koha/issues/1381

**Siilinjärvi**
* Kysytty aiheuttaako YSO-konversion lokitiedosto toimenpiteitä omassa Kohassa; ei toistaiseksi. Seurataan teamsia ja muita keskusteluja.
* Ei muuta mainittavaa.


[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-14) - [Palaa sivun alkuun](/paakayttajat2025)

## Viikko 13

Aika: 25.3.2025<br />
Läsnä: Leena Kinnunen (Lappi), Anni Mäki-Mantila (Vaski), Roosa Väisänen ja Tuomas Kunttu (Kyyti), Päivi Knuutinen ja Irina Halminen (Vaara), Hanna Ikonen (Lumme), Annika Helastila ja Elina Uotila (Kirkes), Janne Seppänen ja Lauri Hänninen (Lastu), Kati Sillgren ja Lotta Juvonen (Helle), Piia Semenoff ja Pirkko-Liisa Lauhikari (OUTI)

**Yhteiset**
* [Viikon 13 päivitys](https://github.com/KohaSuomi/Koha/discussions/1760)
* [Uutiskirje 1/2025](https://github.com/KohaSuomi/Koha/discussions/1762) julkaistu
* [Indeksointi- ja tiedonhakuryhmän muistio 1/2025](https://koha-suomi.fi/indeksointiryhma2025#muistio-12025)
* Koha-seminaari to-pe
* [Libriksen Z39.50-palvelimelle voi määrittää käyttöön sääntötiedoston](https://koha-suomi.fi/dokumentaatio/asetukset/#35-z3950sru-palvelimet), jossa tiputetaan ruotsalaisia kenttiä, kun tietue tuodaan omaan kantaan. Sääntö on käytössä TäTissä, mutta sen pystyy halutessaan laittaa myös käyttöön paikalliskantaan.
* Signum-muutoksen valmistelua: Onko signumbuilderin määrittelyt oikein [tiketissä #1759](https://github.com/KohaSuomi/Koha/issues/1759)?

Etelästä pohjoiseen

**Vaski**
* Asiakastietueiden poistoajoa valmistellaan ja kyseltiin miten muut ovat asiasta tiedottaneet. Kyytin verkkokirjaston tiedotearkistosta löytyy hyvä tiedote, josta OUTIssakin oli otettu mallia.
* Aurora-Koha-konversiossa asiakastietueiden vanhenemisia porrastettiin alkamaan vuoden 2025 alusta ja asiakkaat ottavat nyt vanhenemisviestien seurauksena yhteyttä. Vaski tutkii pystyykö asiakkaiden erämuokkauksella tekemään vanhenemisajan muutoksen järkevästi itse vai tarvitseeko ajosta tehdä tiketti Githubiin.
* Puolen tunnin aikakatkaisu sekä aikakatkaisua varten tehty javascript-rimpsu olleet samaan aikaan käytössä nyt viikon. Toistaiseksi henkilökunnalta ei ole tullut palautetta, tiedotus onnistui ehkä paremmin kuin edelliskerralla asetusta muutettaessa ja toisaalta 5 minuuttia ennen aikakatkaisua tuleva varoitus voi myös auttaa asiaa.

**Lappi**
* Kielifasetit päällä ja indeksointi tehty 23.3.
* Kimpan uudet käyttösäännöt voimaan 1.4., joten aletaan valmistella käyttämättömien kirjastokorttien poistoajoa
* Lapin Kysy Kohasta-koulutus- ja kyselytunti tulossa 15.4.: vastataan tulleisiin kysymyksiin, kerrataan ja nostetaan esille uusia ja muuttuneita Kohan toimintoja.
* Muutoin tukipostissa hyvin rauhallista

**Vaara**
* Kysymykseen voiko tilapäisessä kirjaston remonttikiinniolotapauksessa estää tietyn kirjaston (noutoilmoitus)viestien lähteminen tuli vastaus, että ei voi, koska lähettäminen on kimppakohtaista (ei ollut yllätys).
* Kaupunkisovelluksen lainauskieltorajan toimintaa kehitetään, pyydetty testitunnusta, jolla maksuja testausta varten. Toivotaan pikaista korjausta- asiaan.

**Kyyti**
* Muutimme Kouvolassa kelluvan aineiston kotikirjaston pääkirjastoksi.
* Kysyin voiko kuvailupohjan muuttaa massamuokkauksella esim. oletuspohjasta lehtipohjaksi tietyille tietueille? - Ei voi, joko tietokanta-ajona tai käsin.

**Lumme**
* Tietueiden yhdistämisessä mahdollisesti kadonnut varauksia. Asiaa selvitellään.
* Ei muuta mainittavaa.

**Kirkes**
* Yhdestä kirjastosta on tullut kyselyä, miksi Finnassa näytetään niteet sijainti- eikä kotikirjaston mukaan. Finnan Koha-ajuri antaa valita jommankumman, ja koska kimpasta osa kelluttaa, kotikirjasto ei ole vaihtoehto. Muutenkin niteen reaaliaikainen sijaintikirjasto on asiakkaalle informatiivisempi tieto kuin kotikirjasto.

**Lastu**
* Normaalia ylläpitoa, alettu tarkemmin tutustumaan datan visualisointiin Power BI:llä

**Helle**
* Tiedonhaussa Korin lähetykseen liittyvän CART-ilmoituksen pohja on Hellessä oletuskielen lisäksi suomeksi, ruotsiksi, englanniksi. Oletuskieli-pohjassa viesti on nyt vain englanniksi. Korin lähetystä testatessa viesti muodostui aina suomeksi. Korin lähetys testattu kaikilla Koha-kielillä (Svenska, English, Suomi). Kohaan kirjautuneen käyttäjätunnuksella on mm. arvo lang=fi-FI. Viestipohjaksi on vielä testaamatta tapa, jota on käytetty varauksen noutomuistutukseen Vaskissa: [HOLD_REMINDER eli varauksen noutomuistutus](https://koha-suomi.fi/dokumentaatio/kuititjaviestit/#hold_reminder-eli-varauksen-noutomuistutus)

**OUTI**
* Toimme Tätistä kuvailupohjan OUTIn tuotantoon 21.3. ja sen jälkeen Huomautus virkailijalle kenttään tallennettu teksti ei näy niteen Perustiedot -näytöllä niteen saatavuustiedot rivillä ja, kun menee katsomaan niteen tietoja muokkauksen kautta, niin kenttään tallennettu teksti on kadonnut. Jos tiedon tallentaa Niteet -sivulla Huomautus virkalijalle-kenttään, niin tieto näkyy myös Perustiedot -näytöllä, eikä tieto katoa Niteet -sivulta. Tiketti: https://github.com/KohaSuomi/Koha/issues/1768

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-13) - [Palaa sivun alkuun](/paakayttajat2025)

## Viikko 12

Aika: 18.3.2025<br />
Läsnä: Anneli Österman, Emmi Takkinen, Pasi Kallinen ja Lari Strand (Koha-Suomi), Iina Niemi (Vaski), Päivi Knuutinen, Auli Rantasalo, Irina Halminen (Vaara), Katariina Pohto (OUTI), Annika Helastila (Kirkes), Kati Sillgren (Helle), Reetta Pihlaja (Siilinjärvi), Roosa Väisänen (Kyyti), Tuomas Kunttu (Kyyti), Janne Seppänen ja Lauri Hänninen (Lastu)

**Yhteiset**
* [Viikon 12 päivitys](https://github.com/KohaSuomi/Koha/discussions/1749)
* [Asiantuntijaryhmän muistio 3/2025](https://koha-suomi.fi/asiantuntijaryhma2025#muistio-32025)
* [Niteiden muokkaus eräajossa: Signum ei muodostu klikatessa kolmea pistettä. #585](https://github.com/KohaSuomi/Koha/issues/585)
  * Kokeillaan ensin ilmoituksen lisäämistä kentän viereen, jos signumin muodostamista varten tarvittavia tietoja ei ole saatavilla. Ei piiloteta kolmea pistettä.
* Jos olette ilmoittautuneet Koha-seminaarin iltaohjelmaan, käyttehän vastaamassa sähköpostiin lähetettyyn ruokakyselyyn tämän viikon aikana.

Pohjoisesta etelään

**Vaski**
* Meillä pohdittu miten toimia tapauksissa jossa varauksia pitää siirtää isoissa määrin tietueelta toiselle. Otimme Bugzillan tiketin seurantaan.
* Aikakatkaisu palautettu tänään 30 minuuttiin. Katsotaan, miten henkilökunta reagoi aikakatkaisun selkeytykseen.

**Vaara**
* Ilomantsin kirjaston ilmoitus kadonneista sotutunnuksista. Keskustelun jälkeen tein tiketin https://github.com/KohaSuomi/Koha/issues/1752
* Poistettavan tilauksen laskunumeron poisto ei onnistu, tiketti https://github.com/KohaSuomi/Koha/issues/1751
* Varaustunnuksista käyty keskustelu johti tikettiin https://github.com/KohaSuomi/Koha/issues/1753

**OUTI**
* Finnassa isompien lainahistorioiden lataaminen ei ole onnistunut. Tällä viikolla pitäisi tulla päivitys, jolla rajoitetaan ladattavien osien koko 400 tulokseen.
* Virkailijoiden käyttäjäoikeuksia ryhminä lisäävä valikko lisätty skriptinä tuotantoon.

**Kirkes**
* Mietiskelty asiakkaan omien tietojen päivittämiseen liittyvää toimintaa ts. saako asiakas vahvistuksen, jos Finnassa muutetut tiedot hyväksyy tai hylkää Kohassa.

**Helle**
* Kirjastosta ihmetelty, kun Hyllyvarausraportti-toiminto ei ole näyttänyt 13.3.2025 aamulla heti kaikkia hyllyvarauksia. Hyllyvarausraportin päivitys oli tuonut näkyviin aiempina päivinä tehtyjä varauksia. (Esimerkiksi mainittu tietue 181972. Tietueeseen tehty voimassa oleva varaus Helle-Finnassa 11.03.2025 19:11 (varauksen ID 1513170). Tietueella on vain yksi nide (ID 120681). Niteelle ei lokitietoja (hankittu v. 2004).) Vastaavaa on tapahtunut myös aiemmin.
* Vaski-kimpassa tehdylle Koha-aikakatkaisun selkeyttäminen -ominaisuudelle on kiinnostusta myös Helle-käyttöön. [Koha-aikakatkaisun selkeyttäminen](https://github.com/KohaSuomi/Koha/issues/1357)

**Siilinjärvi**
* Ei mainittavaa

**Kyyti**
* Aloitimme kuvatallenteiden kellutuksen. Niteiden kotikirjastot jäivät ennalleen. Nyt kun muista kirjastoista palautuu lähikirjastojen aineistoa pääkirjastoon, jää kuljetustila päälle, vaikka ei tarvitsisi. Miten on toimittu muualla? Kaikissa vastanneissa toimittiin niin että niteiden kotikirjasto oli pääkirjasto ja kaikki muiden kuntien palautukset tulivat pääkirjastoon.
On myös olemassa tiketti [973](https://github.com/KohaSuomi/Koha/issues/973), joka ei ole edennyt.

**Lastu**
* Normaalia ylläpitoa

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-12) - [Palaa sivun alkuun](/paakayttajat2025)


## Viikko 11

Aika: 11.3.2025<br />
Läsnä: Anneli Österman, Kodo Korkalo, Emmi Takkinen, Lari Strand (Koha-Suomi), Anni Mäki-Mantila (Vaski), Leena Kinnunen ja Pia Kusmin (Lappi), Annika Helastila (Kirkes), Päivi Knuutinen ja Irina Halminen (Vaara), Janne Seppänen ja Lauri Hänninen (Lastu), Kati Sillgren (Helle), Katariina Pohto ja Pirkko-Liisa Lauhikari (OUTI), Hanna Ikonen (Lumme), Tuomas Kunttu (Kyyti), Reetta Pihlaja (Siilinjärvi)

**Yhteiset**
* [Viikon 11 päivitys](https://github.com/KohaSuomi/Koha/discussions/1734)
* [Maaliskuun kuukausihuolto 12.3.2025](https://github.com/KohaSuomi/Koha/discussions/1726)
* [Koha-seminaarin ilmoittautuminen](https://github.com/KohaSuomi/Koha/discussions/1665) päättyy perjantaina, ilmoittauduthan ajoissa.
* Nidetyyppi-kenttä 952$y kaikkiin kuvailupohjiin pakolliseksi sekä oletusarvon lisääminen samaiseen kenttään /Emmi
  * Ei lisätä oletusarvoa, koska se on esim. Lapissa määritettynä ja virheellisiä nidetyyppejä on silti tallentunut.
  * Kaikki voisi tarkistaa, että 952$y on merkitty pakolliseksi. Sekään ei tosin näytä aina auttavan, koska vääriä nidetyyppejä on senkin kanssa syntynyt.
  * Jatketaan tutkimista.
* Nidetyypin generointiin käyttöön permanent_location-sarake location-sarakkeen sijaan /Emmi
  * tehdään muutos, että käytetään permanent_location-saraketta
* Hellessä testattu [MaxSearchResultsItemsPerRecordStatusCheck -järjestelmäasetusta](https://github.com/KohaSuomi/Koha-translations/issues/58#issuecomment-2700020701) hyvin tuloksin. Seuraava kimppa voisi nyt testata sitä.
  * Kati ehdottaa, että saatavana-tekstiä ei muutettaisi, kuten yllä linkatussa tiketissä on alunperin ehdotettu.
  * Päätös: ei tehdä lisää käännösmuutoksia
* [Ratkaisu ehdotettu](https://github.com/orgs/KohaSuomi/projects/4/views/15) -tyyppisiä tikettejä parikymmentä. Muistattehan käydä sulkemassa itse tekemänne tiketit, kun olette todenneet niiden olevan kunnossa. 

Etelästä pohjoiseen

**Vaski**
* Emottomien osakohteiden raporttia kyselty, valutuksen seurauksena tullut välillä orpoja osakohteita.
  * Ei mahdollista raporttina. Skripti olemassa, mutta poistoa ei kannata automatisoida vaan toimittaa raportti ennemmin pääkäyttäjille ja poistot tehtäisiin eräpoistotyökalun kautta. Vaski tekee tästä vielä tiketin.
* Vuosittainen tietoturvakoulutus tällä viikolla henkilökunnalle, pidetty viimeksi vuosi sitten ja tarkoituksena järjestää koulutus säännöllisesti.

**Lappi**
* Epäonnistuneita tekstiviestejä muodostui 10.3. katkon aikana erikoisella virheilmoituksella. Kodo laittoi kaikki epäonnistuneet tekstiviestit takaisin "pending"-tilaan, jolloin ne lähtivät uudelleen seuraavassa viestienlähetyserässä. Tiketti #1736
* Normaalia ylläpitoa lomien keskellä.

**Kirkes**
* Hyllyvarausraportissa ollut häiriö, mutta korjaantunut.
* Jokunen epäonnistunut tekstiviesti 10.3. sekä tuplia.

**Vaara**
* Tukipyyntö lähettämättömien palautuskehotusten kanssa ratkaistu siten, että raportti otettu Annelin ohjeen mukaan ja asiakkaille on lähetetty sähköposti tai sen puuttuessa tekstiviesti kehottaen palauttamaan erääntyneet lainat. Näistä ei mene palautuskehotusmaksua, normaali myöhästymismaksu vain.
* Kesälahden lainausautomaattiasia on edelleen kesken. Laitteen IP-osoitteen vaihto aiheutti sen, että laitetta ei ole saatu toimimaan, vaikka Koha-Suomen kehittäjät, konesalioperaattori ja Meita tehneet töitä.
* Hionin tekemä kaupunkiappi on osoittautunut ainakin Joensuussa ongelmalliseksi, koska ei osaa huomioida asiakkaan lainauskieltoa (maksuja yli lainauskieltorajan) vaan antaa uusia myöhässä olevia lainoja niin kauan kuin uusintamahdollisuuksia on käyttämättä. Maksut eivät näy apissa ollenkaan asiakkaalle. Appi pitäisi saada pois käytöstä siihen saakka, kunnes puutteet on korjattu.

**Lastu**
* Omatoimien yhteysongelmia selvitelty nyt yhteispalaverissa kaikkien toimijoiden kanssa. Selkeää ratkaisua ei löytynyt, mutta monta pientä korjausta joita lähdetään koittamaan.
* Lehtitilauksiin joissakin tapauksissa valittu vahingossa väärä tietue, kysyttiin onko mahdollista siirtää niteitä ja kausijulkaisutilausta toiselle tietueelle. Niteet saa, mutta tilausta ei, joten ohjeistetaan näissä tapauksissa kirjastoja poistamaan tilaus ja tekemään uusi.
* Kyseltiin mahdollisuutta rajata hakutuloksia sellaisiin tietueisiin jotka eivät ole käännöksiä, mutta tämä ei ole mahdollista.
* Muistuteltiin taas uutiskirjeestä, jonka deadline on ensi viikon perjantaina.

**OUTI**
* Kehitysehdotus palautussivun kuljetusmodaalin käytettävyyden parantamiseksi: [tiketti #1741](https://github.com/KohaSuomi/Koha/issues/1741)

**Lumme**
* Normaalia ylläpitoa.

**Kyyti**
* Ei erityistä.

**Siilinjärvi**
* Ei mainittavaa täälläkään.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-11) - [Palaa sivun alkuun](/paakayttajat2025)


## Viikko 10

Aika: 4.3.2025<br />
Läsnä: Johanna Räisä (Koha-Suomi), Pirkko-Liisa Lauhikari ja Piia Semenoff (OUTI), Päivi Knuutinen ja Irina Halminen (Vaara), Leena Kinnunen (Lappi), Janne Seppänen ja Lauri Hänninen (Lastu), Kati Sillgren (Helle), Reetta Pihlaja (Siilinjärvi)

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

**Siilinjärvi**
* Pitkään vireillä ollut myös muovitetun aineiston tilaamista koskeva muutos Hankintaportaalissa on vihdoin edennyt, testitilauksia on jo lähetetty.
* Vanhentuneiden asiakkaiden poistoajo on pyydetty ti 11.3.
* YSO-konversion valmistelu on työn alla

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-10) - [Palaa sivun alkuun](/paakayttajat2025)


## Viikko 9

Aika: 25.2.2025<br />
Läsnä: Janne Seppänen (Lastu), Päivi Knuutinen ja Auli Rantasalo (Vaara), Hanna Ikonen (Lumme), Leena Kinnunen, Pia Kusmin, Maria Joona (Lappi), Pirkko-Liisa Lauhikari, Katariina Pohto ja Piia Semenoff (OUTI), Susanna Sandell (Vaski), Anneli Österman ja Emmi Takkinen (Koha-Suomi), Annika Helastila ja Elina Uotila (Kirkes), Kati Sillgren (Helle), Roosa Väisänen (Kyyti), Reetta Pihlaja (Siilinjärvi)

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

**Siilinjärvi**
* La 22.2. tehty fasettien nollaus huolimattomasti ja saatu tiedonhaku jumiin. Uudelleenindeksointi hoitui onneksi nopeasti ja ma-aamuna se jo toimi, kiitos!
* Tarkistettu vielä, että fasettien uudelleen järjestäminen ei aiheuta uudelleen indeksoinnin tarvetta.
* Kysytty myös Koha-Suomen "hinnastosta", se on vielä vaiheessa. Toistaiseksi tapauskohtaiseen harkintaan perustuva hinnoittelu.

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
