---
title: 'Koha-Suomen vuoden 2024 muistiot'
header:
  overlay_color: '#5e616c'
  overlay_image: /assets/images/cropped-pexels-photo-113850.jpeg
permalink: /kohasuomi2024
redirect_from:
  - /theme-setup/
toc: true
layout: single
hidden: true
---

Koha-Suomen henkilökunta kokoontuu kerran viikossa pidempään palaveriin ja päivittäin 15 minuutin pikapalaveriin. Muistio kirjoitetaan vain maanantain pidemmästä palaverista. Uusin muistio on aina ylimmäisenä.

## Viikko 25

Aika: Tistai 18.6.2024 klo 12<br />
Läsnä:

**Asiat**
* pääkäyttäjäpalaverit ja päivitystiedotteet Annelin loma-aikana


## Viikko 24

Aika: Maanantai 10.6.2024 klo 9<br />
Läsnä: Ari, Lari, Johanna, Pasi, Lasse, Kodo, Anneli

**Asiat**
* Palvelimen OCFS-levyjärjestelmän ongelmat kuntoon, reklamaatio.
  * Kodo ja Johanna kirjoittavat viestin, jonka Ari välittää palvelinsalin ylläpitäjälle. Ei tehdä vielä varsinaista reklamaatiota, mutta pyritään selvittämään ongelmia.
* Viikon 24 päivitykseen 5 tikettiä
* Scrumm
  * Kodo: Tietuemätsäyksiä, sähköinen ilmoittautuminen, suomi.fi viestien palaveri rest-rajapinnasta ma
  * Johanna: Tikettejä, suomi.fi viestien palaveri rest-rajapinnasta ma
  * Anneli: Release notesien läpikäyntiä ja tietojen vientiä 24.05:n wikiin, julkaisuvuosihaun testausta nidehaussa
  * Lari: omia tikettejä käsitellyt ja jatkaa niistä, JS-plugareiden teon jatkaminen
  * Pasi: Redusoinnit tehty ja plugarit asennettu testeille, dna:n lähtemättömien viestien uudelleenlähetys Vaskissa, redusointiskriptiin vielä pieniä muutoksia, omien tikettien läpikäyntiä
  * Lasse: tikettejä vastuutettu loman aikana

## Viikko 23

Aika: Maanantai 3.6.2024 klo 9<br />
Läsnä: Emmi, Anneli, Pasi, Johanna, Kodo, Lari, Ari

**Asiat**
* Versioon 24.05 ja backportattuna 23.11.04 tulee uusi REST-endpoint, jolla saa yhdisteltyä tietueita http://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=33036. Kannattaisiko tuoda meillekin KaTia varten?
  * Emmi tuo tämän meidän versioon.
* Tehdään syksyllä versiopäivitys, siirrytään versioon 24.05. Seuraavassa versiossa tulee paljon bugikorjauksia, jotka me tarvitaan.
* Päivystysvuorot viikosta 24 eteenpäin
* Viikon 23 päivitys
* Vastuuttomien tikettien vastuutus
  * Vastuutettiin osa  

## Viikko 22

Aika: Maanantai 27.5.2024 klo 9<br />
Läsnä: Lasse, Emmi, Anneli, Pasi, Johanna, Kassu, Kodo, Lari

**Asiat**
* Viikon 22 päivitys
  * Uutta käyttäjätunnusta tehdessä Kopioi asiakastiedot-kysymys palauttaa kirjastovalinnan oletukseksi
  * Kohan itsepalvelutoiminnon Palautus-kentässä käännösvirhe
  * Kyyti: tarratulostuksen Itse tulostetut -listalla liikaa niteitä
  * EDItX-hankinta: Käyttäjätilin näkyminen tilausta vastaanotettaessa
* Testikantojen uudelleenluonti ja redusointi

## Viikko 21

Aika: Maanantai 20.5.2024 klo 9<br />
Läsnä: Lasse, Emmi, Kassu, Ari, Lari, Johanna, Kodo, Anneli

**Asiat**
* kuka kehittäjistä mukaan signum-työryhmään? Muut jäsenet jo tiedossa.
  * Pasi
* Koha-Suomen aiheet [seuraavaan uutiskirjeeseen](https://docs.google.com/document/d/1C1kP8jM8k47VGg_WCSmaeE29cL81IK5jimq2Dth9mbk/edit)?
  * Lapista tuli toive, voisiko versionvaihdosta kirjoittaa Koha-Suomen työntekijöiden näkökulmasta, "miten meillä meni" -tyyliin.
    * Lasse ja Emmi kokoaa tekstin
  * Anneli kirjoittaa varmenteesta 
* Milloin testit uusitaan?
  * ti 28.5.2024
  * sovitaan tiistaina scrummissa tekijät
* Viikon 21 päivitys
  * 11 muutosta
* Scrumm
  * Emmi: Uudelleenindeksointi?,
  * Kodo: service-checkiin dokumentaatio ja commit
  * Johanna: Melinda-replikoinnin korjaus, viestiprosessi
  * Kassu: Viime vuoden hankintojen kokoamisskripti
  * Lasse: elasticsearch päivitetty omalle koneelle?
  * Lari: varausryhmä, vanhimmasta päästä tikettin toteutusta
  * Anneli: to käännöksiä, tieteellisten pääkäyttäjäpalsu, aikakatkaisutiketin testausta
  * Ari: OUTIn ohjausryhmälle kuulumisia ja tiekarttaa

## Viikko 20

Aika: Maanantai 13.5.2024 klo 9<br />
Läsnä: Ari, Lasse, Emmi, Pasi, Kassu, Kodo, Lari, Anneli, Johanna

**Asiat**
* Miten edetään loppujen [Koha23-version tikettien](https://github.com/KohaSuomi/Koha-23x/issues) kanssa?
  * Tiketit käyty lävitse, suljettu/siirretty/vastuutettu 
* Vkon 20 päivitys
  * [Asiakkaan viivakoodin näyttäminen asiakastietonäytöllä -plugari](https://github.com/KohaSuomi/Koha/issues/671), käytössä Lapissa
  * [Käännös: Nide kuljetettavanana yksiköstä x lähtien pp.kk.vvvv](https://github.com/KohaSuomi/Koha-translations/issues/41)
  * [Tietuesiirtäjä: Valuneisiin osakohteisiin ei muodostu aineistotyyppiä](https://github.com/KohaSuomi/Koha/issues/1205)
* Konesalin yhteysongelma maanantai-aamuna ennen klo 7, kysellään Bittigurulta


## Viikko 18

Aika: Maanantai 29.4.2024 klo 9<br />
Läsnä: Pasi, Lasse, Emmi, Ari, Johanna, Lari, Anneli

* Hellessä käyttökatkos 25.4.2024 klo 10.19. Tokeni Plackin sulkemisella ja uudelleenkäynnistyksellä.
* Kesäprojektit
  * JS-rimpsut plugineiksi / Lari
  * committien tägitys / Emmi ja Johanna
  * branch-listan läpikäyminen ja siivoaminen / Emmi
  * branch-listan käsittelyn järkevöittäminen / joku
  * yhteisöversion pystytys / Emmi, Kodo
  * RDA-konversiot / Johanna ja Emmi
  * Tiedonhaun muutoksista video tms. / Anneli
* Pitää käydä läpi, onko meillä sellaisia alkuvuoden brancheja, joita ei ole viety 23:een
* Scrum
  * Anneli: Bugiton, Ellibsin kirjautumisten testailua, kun Lumpeissa ilmeisesti tulee moninkertaisia virhekirjauksia.
  * Emmi: bugiton, mattermostiin, laskutusnapin disabloinnin yrityksiä, tänään testien päivitys 23.11 versioon
  * Johanna: nappi sitä varten, että action logseista pytyy palauttamaan vanhemman version tietueesta, pikkuviilauksia Melinda-vientiin
  * Pasi: Kotkan lainaustilastosysteemi, kaikille javascript-plugin, joka korjaa Z39.50-hakua
  * Lari: Elasticsearchin tutkimista, miten saisi skandit aakkostumaan oikein hakutulosten järjestämisessä. Hakuviivebranch yhteisöstä omaan branchiin meille. Pari sms-driveria testattava, että skandit toimii.
  * Lasse: tekemättömien tikettien tutkimista

## Viikko 17

Aika: Maanantai 22.4.2024 klo 9<br />
Läsnä: Pasi, Johanna, Lasse, Anneli, Kassu, Lari, Kodo, Emmi

* Versionvaihdon tikettien tilannekatsaus / Anneli
  * Tiketit käytiin läpi 
* Päivitys vko 17
  * [Laskutus-liitännäinen: Merkitse lähetetyt finvoice-laskut sent-tilaisiksi heti lähetyksen jälkeen #12](https://github.com/KohaSuomi/koha-plugin-overdue-tool/issues/12)
  * [Raportti, joka laskee tietueen niteiden lainamäärät sekä JavaScriptillä nappi raportin ajoon. #1109](https://github.com/KohaSuomi/Koha/issues/1109)
    * päivitetään siis koha-plugin-intranetjs-checkout-report-link
* Scrumm:
  * Lari: js-rimpsu-plugarien kanssa säätöä
  * Anneli: yhteisön bugin testausta ja tekemistä, käsittelyerä-toiminnon ihmettelyä
  * Kassu: randomraija, brancheja nextille
  * Pasi: XSLT:n kattelua
  * Kodo: versionvaihdon tikettien testausta
  * Lasse: varaus-sivun kattelua nexteille
  * Johanna: Melinda-siirron korjausta
  * Emmi: käsittelyerä-toiminnon ja backgroundjobs korjaus

## Viikko 16

Aika: Maanantai 15.4.2024 klo 9<br />
Läsnä: Lasse, Ari, Emmi, Anneli, Johanna, Pasi, Kassu, Lari, Kodo

* Miten toteutetaan [tiketti #467](https://github.com/KohaSuomi/Koha/issues/467) / Kassu
  * CSS-muutos ja käännös, koetetaan saada yhteisöön
* Versionvaihdon tarkempi aikataulu päätettävä ja tiedotettava.
  * Sunnuntai-iltana 5.5. klo 19
* JS-rimpsujen läpikäynti Larin listan pohjalta

## Viikko 15

Aika: Maanantai 8.4.2024 klo 9<br />
Läsnä: Pasi, Emmi, Lasse, Anneli, Lari, Ari, Kodo, Kassu

* Onko kaikki laittaneet kesälomansa kalenteriin?

## Viikko 14

Aika: Tiistai 2.4.2024 klo 13<br />
Läsnä: Pasi, Emmi, Lasse, Lari, Kassu, Ari, Anneli

* Mitkä kaikki [JS-rimpsut](https://github.com/KohaSuomi/Koha-23x/wiki/IntranetUserJS) plugarisoidaan? [Tiketti 1121](https://github.com/KohaSuomi/Koha/issues/1121)
  * Lari käy läpi kaikki rimpsut, missä kaikkialla niitä käytetään ja mitkä kannattaisi plugarisoida.
  * Ehkä ainakin suositellut plugareiksi, vapaaehtoisista harkitaan tapauskohtaisesti.
  * Osa plugareista tarvitsee konfiguraation. Jos vaatii sen, niin plugarin kuvaukseen tieto, jolloin pääkäyttäjät tietävät tehdä sen.
* Pitäiskö päivittää ke? Tuotantoihin pitäisi viedä:
  * [Tarkka haku -toimintoon paluu hakutuloksen Muokkaa hakua -linkistä muuttaa tehdyn haun hakutyypin](https://github.com/KohaSuomi/Koha/issues/663#issuecomment-2020248402)
    * Tässä pitää siis lisätä Hellelle tämä: https://github.com/KohaSuomi/Koha/issues/663#issuecomment-1878400300
    * Kaikille tämä korjattu versio: https://koha-suomi.fi/dokumentaatio/intranetuserjs/#indeksointity%C3%B6ryhm%C3%A4n-tekem%C3%A4t-tiedonhaun-mukautukset
  * [Vaski: Kutsumanimen piilotus tietyiltä asiakaslajeilta](https://github.com/KohaSuomi/Koha/issues/1127)
  * Kokoelmatyökoulutusta 4.4. varten [Raportti, joka laskee lainamäärät ja linkki perustiedot-näytölle](https://github.com/KohaSuomi/Koha/issues/1109) kaikille kimpoille. Lari laittaa plugarin kaikkiin kimppoihin ti-iltana. Anneli tiedottaa pääkäyttäjiä lisäämään raportin ja käymään aktivoimassa plugarin sen jälkeen ja lisäämässä konfiguraatioon raportin numeron.
* Päivystäjät vko 16 eteenpäin
* scrumm
  * Pasi: versionvaihdon tikettejä
  * Lari: sip-ongelmia tutkinut: nextille vietynä meidän paikalliset muutokset. Omatoimen estot pitää testata tuotannossa. Uusi viesti tilin lukittuessa, helpottanee ongelmia selvitettäessä.
  * Kodo: ennen lomaa versionvaihdon tikettejä, loppuja tällä viikolla. RopoCapitalilta tullut viestiä.
  * Lasse: nexteillä vanha versio varaussivusta, kääntymättömiä tekstejä useampi.
  * Kassu: Kaikkien assiakastietojen haun blokkauksen selvittelyä. Piialle SQL-raporttia. Nextin laitto omalle koneelle.
  * Anneli: Vaskin aikakatkaisu -ongelman testausta, RedirectGuaranteeEmail-tiketin testausta, uutiskirje eetteriin, css:ine kanssa värkkäämistä.
  * Emmi: elastic 8:n saanut toimimaan, tietokantatriggereitä outi-nextille, Ceepos-häröilyt Oulussa ja Vaarassa.

  
## Viikko 13

Aika: 25.3.2024 klo 9<br />
Läsnä: Ari, Lari, Anneli, Kassu, Lasse, Johanna, Emmi, Pasi

* Vk 14 pääkäyttäjille pääsy nexteille testausta varten

## Viikko 12

Aika: 18.3.2024 klo 9<br />
Läsnä: Lari, Lasse, Kodo, Anneli, Pasi, Ari, Emmi

* [Yhteisöversion-testikannan pystytys](https://github.com/KohaSuomi/Koha/issues/1116) Joskus kesällä.

## Viikko 11

Aika: 11.3.2024 klo 9<br />
Läsnä: Pasi, Emmi, Kodo, Lasse, Lari, Johanna, Anneli, Kassu, Ari

* Versionvaihdon tilanne
  * koska pääsisi laajemmin kimpoissa testaamaan eli koska Koha-Suomen ominaisuudet kaikki tehty?
  * toimiviksi testatut tiketit sulki, niin helpompi seurata tilannetta ja löytää uutta testattavaa.
  * Keskiviikon scrummiin arvio, kuinka kauan omien tikettien tekoon menee.
  * Lisättiin uusi valinta Testaaja, jossa vaihtoehtoina Koha-Suomi/Pääkäyttäjät.
  * Testaussuunnitelma tikettiin, kun sen laittaa testattavaksi.
  * Tuotantoon freeze viikosta 12 lähtien. Vain kriittiset päivitykset tehdään sen jälkeen.
* Uutiskirjeen keräyspaikka?
  * Annelin Google Docsiin jaettu tiedosto
* Päivystyskäytännöt - rautalanka
  * Päivystysaikana 8-16 päivystetään puhelimitse kriittisissä asioissa (Koha ei toimi), muita kanavia (Matrix, sähköposti) seurataan mahdollisuuksien mukaan (oman työajan puitteissa, esim. klo 7-15). Muut kuin kriittiset asiat voidaan hoitaa myös seuraavana päivänä.
  * jos tulee yllättäviä poissaoloja/sairastumisia, sovitaan sijaistaja.
* Päivystysvuorot vko 12 eteenpäin
* Vkon 11 päivitys
  * neljä päivitystä/muutosta
* Keskiviikon huoltokatko
  * testit ja nextit käyvät alhaalla tiistaina.

## Viikko 10

Aika: 4.3.2024 klo 9<br />
Läsnä: Anneli, Kassu, Johanna, Emmi, Lasse, Pasi, Kodo

* Viikon 10 päivitys
  * Pelkkiä käännöksien muutoksia 
  * käännösmuutosten ajo aina myös testeille
* Scrumm
  * Emmi: Puuttuvat categorycodet statisticsissa
  * Lasse: Tikettien hoitamisia
  * Johanna: Ceepos-kassamksun napin korjausta
  * Kassu: SQL-kyselyiden ihmettelyä
  * Anneli: Lastun salasana-ongelma, kokoelmatyön tiedonhaun koulutuksen valmistelua raporttien osalta, muuta pientä sälää
  * Kodo: Lastun konversion siistimistä, vaara ropocapital
  * Pasi: z3950-haku välimerkkiongelma

## Viikko 9

Aika: 26.2.2024 klo 9<br />
Läsnä: Ari, Anneli, Emmi, Lasse, Pasi, Lari

* Päivystyskäytäntöjen päivitys ja kirjaus muuallekin kuin Redmineen.
  * Kopattu Redminestä:
    * Kehittäjät päivystävät puhelimitse virka-aikana ma-pe klo 8-16. Iltaisin ja viikonloppuisin ei ole päivystystä. Jos viikonloppuna tulee ongelmia Kohan kanssa, pitää toimintakäytännöistä sopia kimpan sisällä. Varalainausohjeet ja -ohjelmat kannattaa huolehtia kuntoon valmiiksi.
    * Kehittäjät päivystävät pareittain viikon kerrallaan. Päivystyajankohdat pyritään järjestämään niin, että muut käynnissä olevat projektit voidaan hoitaa sovitussa aikataulussa.
    * Päivystäjän tehtävät:
      * seuraa tikettejä ja huolehtii, että ne tulevat tarpeen tullen tehdyksi ajallaan
      * hoitaa viikon aikana tulevat tukipyyntö-tapahtumatyyppiä olevat tiketit, mikäli se on mahdollista
      * seuraa support-lootaan tulevia sähköposteja ja Matrixia ja hoitaa asiat tai huolehtii, että joku muu hoitaa
      * vastaa kehittäjien päivystyspuhelimeen ja huolehtii, että sitä kautta tulevat asiat tulee hoidetuksi
        päivystyspuhelinnumero on kimpan pääkäyttäjillä tiedossa ja heidän käyttöön tarkoitettu
    * Kiireelliset asiat (järjestelmä ei toimi) aina päivystyspuhelimeen, jolloin ne pyritään hoitamaan niin pian kuin mahdollista.
    * Ei-kiireelliset sähköpostiin ja Matrixiin tulleet asiat pyritään hoitamaan kiireettömämmällä aikataululla.
    * Tukipyynnöistä aina tiketti.
* Viestintäsuunnitelma ja sen toteuma
  * Suunnitelmassa virheellisesti Tieteelliset Koha-kirjastot -kohdassa "Kehittäjien yhteistyö on säännöllistä", kun sen pitäisi olla "Koha-Suomen ja tieteellisten kirjastojen yhteistyö on säännöllistä". Ari tekee tarvittavat korjaukset seuraavaan suunnitelmaan.
* Viikon 9 päivitys
  * Tarrapohjalle kokoelmatieto selkokielisenä
  * Automaattien lainausviestiparin 11-12 vastauksessa ei tule AH-kentässä eräpäivää, mikäli ”no block” -asetuksessa lähetetään ”Y”
  * Käännösvirhe niteiden erämuokkauksessa jos poistettavia niteitä enemmän kuin mitä sallitaan näytettäväksi

## Viikko 8

Aika: 19.2.2024 klo 9<br />
Läsnä: Pasi, Lasse, Johanna, Lari, Kodo, Anneli, Emmi

* Kesälomat suunnitteluun? / Anneli
  * Laitetaan kalenteriin toiveet ja sumplitaan sitten lisää
* Kommentoitu-tilaisten (plus muiden) vastuutus / Anneli
  * Käytiin läpi kommentoitu-tilaiset tiketit 
* Branchit 0104 ja 0105 eivät ole ajantasalla tuotannoissa /Emmi
  * Poistetaan 0105 ja päivitetään 0104 ajantasalle viikkopäivityksessä 
* Viikon 8 päivitys
  *  [Sarakevalinnat eivät käyttäydy aina oikein niteiden eräpoistossa/erämuokkauksessa #769](https://github.com/KohaSuomi/Koha/issues/769)
  *   [Rajoitteen tekstimuutosehdotus, kun asiakkaalla on yli 50 virheellistä kirjautumisyritystä #474](https://github.com/KohaSuomi/Koha/issues/474)
* Scrum:
  * Kodo: Lastussa hyllypaikkojen korjausta, pientä silppua
  * Anneli: tikettien läpikäyntiä
  * Pasi: pari päivistyjuttua
  * Lari: Finna-juttuja (poistetut niteet), versionvaihtoa
  * Johanna: uuden valutuksen testausta
  * Lasse: tikettien tekoa
  * Emmi: 0114 branchin kanssa ongelmia     


## Viikko 7

Aika: 12.2.2024 klo 9<br />
Läsnä: Johanna, Ari, Lari, Lasse, Kodo, Pasi, Anneli, Kassu

* Päivystysvuorot viikosta 8 eteenpäin
* Viikon 7 päivitys
  * [Koha-Ceepos-maksurajapintaa käytettäessä Hyväksy-painike epäaktiiviseksi](https://github.com/KohaSuomi/Koha/issues/351)
  * [Tietueen tuominen TäTistä Vaaraan ei tuo oikeaa tallennuspohjaa](https://github.com/KohaSuomi/Koha/issues/592)
  * [Hankinnan vastaanotossa haku ei pysy perässä tai väärä haku jää välillä voimaan](https://github.com/KohaSuomi/Koha/issues/826)
  * [Tietueiden eräpoisto: toiminnon käynnistyksen jälkeen ilmestyvässä ilmoituksessa mainitaan mm. Uusi niteiden poisto eräajona](https://github.com/KohaSuomi/Koha-translations/issues/34)
* OUTI siirtyy uuteen valutukseen tiistaiaamuna 13.2. /Johanna
* Scrum:
  * Kodo: Kassun kanssa tikettien selvittelemistä
  * Kassu: Sama juttu
  * Anneli: IntranetUserJS:n läpikäyntiä, ja niistä tikettejä
  * Pasi: Tietokantasiivouksien käpistelyä
  * Lari: Finna-plugarin parantelua
  * Lasse: Varauksen peruutusnapin ihmettelyä
  * Johanna: Valutusta


## Viikko 6

Aika: 5.2.2024 klo 9<br/>
Läsnä: Johanna, Ari, Lari, Emmi, Lasse, Kodo, Pasi, Anneli, Kassu

**Asiat**
* No status ja Tehtävä -tilaisten tikettien vastuutus /Anneli
* Viivakoodien generointi timestampilla - kuinka edetään? /Emmi
  * Ehdotetaan viivakoodeja tarjoavaa endpointia yhteisöön.
*Scrum:
  * Kodo: Varausten jäädytyssäätämistä Lastussa + pieniä korjauksia, automaattitunnarit puuttuu
  * Anneli: Hellen Finna-näkymään ratkaisu löytynyt, korjattu myös pluginiin
  * Kassu: randomraijaa ja tikettejä
  * Pasi: Tietokantakorjauksia/tarkistuksia ajossa viikonloppuna, raportteja pääkäyttäjille
  * Lasse: sivutusta
  * Johanna: Valutusta, RDA jäissä kansalliskirjaston githubin päivityksiä odotellessa
  * Emmi: CGI:lle toimitettu laskutuksen testiaineisto (Mäntsälä), pientä sälää

[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-6) - [Palaa sivun alkuun](/kohasuomi2024)

## Viikko 5

Aika: 29.1.2024 klo 9<br/>
Läsnä: Emmi, Pasi, Lari, Ari, Johanna, Anneli, Kassu, Lasse, Kodo

**Asiat**
* Bugittoman harvennus kahden kuukauden välein?
  * harvennetaan 
* Viikon 5 päivitys
  * [Käännöstoive: Mitätöidyn maksun status Forgiven -> Mitätöity #33](https://github.com/KohaSuomi/Koha-translations/issues/33)
  * [Manan ohje selkeämmäksi #32](https://github.com/KohaSuomi/Koha-translations/issues/32)
* Scrum:
  * Emmi: Lumpeiden kummittelavat tietueet
  * Johanna: korjauksia tietuesiirtäjään
  * Kodo: Lastun konversio, niteiden kanssa ongelmia
  * Anneli: indeksointi- ja tiedonhakuryhmä tänään
  * Kassu: maksuriviraportit, muita rapsoja OUTIlle
  * Lari: maksuriviongelma
  * Lasse: versionvaihdon testausta
  * Pasi: RDA:n valmistelua     

[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-5) - [Palaa sivun alkuun](/kohasuomi2024)

## Viikko 4

Aika: 22.1.2024 klo 9<br/>
Läsnä: Anneli, Lasse, Pasi, Johanna, Emmi, Ari, Kassu, Kodo

**Asiat**
* Versionvaihdon tikettien katsaus? /Emmi
  * otetaan katsaus keskiviikkona klo 10.30.
* [Käännöstoive: asiakastakaajan lisäys ja select-nappi](https://github.com/KohaSuomi/Koha/issues/1014)
  * Viedään koodimuutokset yhteisöön ehdolle, ei tuoda itselle väliaikaisesti.
* Vkon 4 päivitys
  * mukaan tulossa vain yksi käännösmuutos
* Scrum:
  * Kodo: Tiedot lastun konversiotauluja varten metsästelty dumpista (tietue-id:t), Lastu konversiota, Vaaran mobiiliappi testissä, Kotkan RFID-haravakuviossa ei vielä etenemistä
  * Emmi: Nextit redusoitu ja valmiina testattavaksi
  * Johanna: RDA-konversio, Kansalliskirjasto päivittänyt konversiosäännöt
  * Pasi: Odottavien tikettien tekoa
  * Lasse: Varaussivun sivutus ja versionvaihdon tikettejä
  * Anneli & Kassu: Vanhennettujen maksujen uudelleenkertymisongelman selvittelyä
  * Lari: Vanhennettujen maksujen uudelleenkertymisongelman selvittelyä

[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-4) - [Palaa sivun alkuun](/kohasuomi2024)

## Viikko 3

Aika: 15.1.2024 klo 9<br />
Läsnä: Ari, Anneli, Kodo, Pasi, Lari, Lasse, Johanna, Kassu

**Asiat**
* Vkon 3 päivitys
  * [Siirtoraportilla tiedot menevät päällekkäin](https://github.com/KohaSuomi/koha-plugin-exporter-report/issues/2)
  * [Hae tietokannasta -haku ei unohda haun rajaukseen käytettyä fasettivalintaa Nykyinen paikka, kun hakutulosnäytöllä tehdään uusi Hae tietokannasta](https://github.com/KohaSuomi/Koha/issues/667)
  * [Koriin linkki teokseen verkkokirjastossa](https://github.com/KohaSuomi/Koha/issues/883)
  * [Nimekkeen katkaisu laskutuksessa vain Finvoice-sanomille](https://github.com/KohaSuomi/koha-plugin-overdue-tool/issues/7)
  * [Käännösmuutostoive: asiakastietojen yhteenvedon alaotsikko Odottavat varaukset](https://github.com/KohaSuomi/Koha-translations/issues/31)
  * [Hyllyvarausraportista katosi julkaisuvuosi](https://github.com/KohaSuomi/Koha/issues/1009)
  * [Viestitaulun lukitus kaataa Kohan](https://github.com/KohaSuomi/Koha/issues/1002)
* Bugiperjantai /Anneli
  * Katsotaan tiistaina 
* Keskiviikon Järvenpään tietovarantopalsu, ketä osallistumassa?
  * Kodo selvittää 
* Statuksettomien tikettien läpikäynti
* Scrum
  * Kodo: Plack-workerien restart muutos --graceful-vipu testissä
  * Kassu: uusien tikettien selvittelyä
  * Anneli: versionvaihdon valmistelua, tiedote päivityksestä 
  * Pasi: MARC-virheraportti hakee Nalkuttimen asetuksista skipattavat kentät. Sanaston rapsat valmiit.
  * Lasse: varaussivun sivutus
  * Lari: selvittelyä miksi batchrebuildbiblios-ajot ei mene läpi
  * Johanna: RDA, ruotsinkielisten tietueiden erottelu

[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-3) - [Palaa sivun alkuun](/kohasuomi2024)

## Viikko 2

Aika: 8.1.2024 klo 9<br />
Läsnä: Lari, Kodo, Pasi, Ari, Johanna, Lasse, Kassu, Anneli

**Asiat**
* Statuksettomien tikettien läpikäynti
  * ehdittiin käydä noin puolet, loput ensi viikolla.
* Elasticsearch-päivitys
  * Elasticsearch-pluginit eivät päivity käyttöjärjestelmän päivityksessä. Lukitaan Elasticsearch-versio paketinhallinnassa tulevaisuudessa.
* Viikon 2 päivitys
  * 2 muutosta tulossa.  

[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-2) - [Palaa sivun alkuun](/kohasuomi2024)

## Viikko 1

Aika: Keskiviikko 3.1.2024 klo 12<br />
Läsnä: Emmi, Anneli, Kodo, Ari, Pasi, Lari, Lasse

**Asiat**
* [BTJ-linkkien korjaus](https://github.com/KohaSuomi/Koha/issues/982) / Anneli
  * jos työ on tehtävissä erätyökaluilla, kimpat tekevät työn itse 
* [005-kentän päivittyminen lainattaessa](https://github.com/KohaSuomi/Koha/issues/924) jäänyt vastuuttamatta / Emmi
  * Pasi hoitaa. 
* Kuinka usein nolla-branchiin päivitetään yhteisöön tulleet muutokset? Aina kun uusi stable release julkaistaan vai harvemmin? / Emmi
  * Seuraillaan vielä miten nolla-branchin kanssa pärjäillään ja tehdään sitten tarkempi päätös.
* Terrapin-paikat ja nykytilanne / Kodo
* Ensi viikon huolto, RedMinen sulkeminen, Multipath-murhe / Kodo
  * mm. tuotantojen käyttiksien päivitys, [huoltotiedotteessa](https://github.com/KohaSuomi/Koha/discussions/993) tarkemmin
  * [Redmine kiinni](https://github.com/KohaSuomi/Koha/discussions/994) samaan aikaan
* Varmuuskopioiden tarkistus pois päältä ajastusongelman vuoksi 
* Lastun kuulumiset ja dumppi / Kodo 
* [Nidehaun tulosten järjestäminen julkaisuvuoden mukaan ei toimi oikein](https://github.com/KohaSuomi/Koha/issues/693) aikataulutus vkon 2 pääkäyttäjäpalsua varten.
  * pääkäyttäjät hoitavat uudelleenmäppäykset (ja raporttien päivitykset)
* Scrum:
  * Kodo: ei ihmeempiä yllä olevien lisäks
  * Pasi: sanasto, nextien redusointi
  * Lasse: pluginien testailua versionvaihtoa varten
  * Lari: varausten noutomuistutusajo
  * Emmi: indeksistä poistumattomien tietueiden selvittelyä
  * Anneli: versionvaihdon ominaisuuksien kirjaamista ylös, tilastojen päivitystä    

[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-1) - [Palaa sivun alkuun](/kohasuomi2024)
