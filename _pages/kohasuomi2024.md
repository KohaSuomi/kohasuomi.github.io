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

## Viikko 50

Aika: 9.12.2024 klo 9<br />
Läsnä:

* Loppujen vastuuttomien tikettien vastuutus

## Viikko 49

Aika: 2.12.2024 klo 9<br />
Läsnä: Ari, Lari, Anneli, Pasi, Kodo ja Emmi

* Vastuuttomien tikettien vastuutus
  * Osa tiketeistä vastuutettu, jatketaan vastuutusta ensi viikolla 
* Viikon 49 päivitys
  * [[Kehitysehdotus] Saisiko muutoksen Koha-popuptekstiin? Kun olemassa olevan asiakastiedon asiakastyypin vaihtaa, kysyy Koha-popup: Vaihda viestiasetukset oletukseksi tälle ryhmälle? ](https://github.com/KohaSuomi/Koha-translations/issues/3)
  * [Tätiin Tietuesiirtäjän käyttäjätunnuksiin järjestystä](https://github.com/KohaSuomi/Koha/issues/1494)
  * [Kohan itsepalvelutoiminnon Palautus-toiminnossa aloitussivu ei tyhjene](https://github.com/KohaSuomi/Koha/issues/1518)
  * ["Tyhjennä suodatin" -painike ei toimi tietueen perusnäytöllä](https://github.com/KohaSuomi/Koha/issues/1522)
  * [Varausta tehdessä kohdistin menee väärään kenttään](https://github.com/KohaSuomi/Koha-24.05/issues/187)
  * [Hankinnan muokkaa-napin toimimattomuus](https://github.com/KohaSuomi/Koha-24.05/issues/181)
  * [Lainauksen Määrittele eräpäivä -toiminnon ominaisuus Muista istunnolle](https://github.com/KohaSuomi/Koha-24.05/issues/186)
* Pitäisikö kaikki keskeneräiset version 24.05-tietovarannon tiketit siirtää Koha-tietovarantoon? Helpottaisi seurantaa, kun ei tarvitse seikkailla kahden välillä.
  * Kehittäjät käyvät tikettinsä läpi ja tarkistavat, mitkä niistä voi jo sulkea. Loput siirretään Koha-tietovarantoon. 
  
## Viikko 48

Aika: 25.11.2024 klo 9<br />
Läsnä: Johanna, Anneli, Ari, Pasi ja Lari

* [Versionvaihdon keskeneräiset tiketit](https://github.com/KohaSuomi/Koha-24.05/issues)
 * Tilat tarkistettu ja lisätty tekijät. 
* Viikon 48 päivitys
 * [Aikakauslehtien julkaisutiheyden poistaminen ei onnistu](https://github.com/KohaSuomi/Koha-24.05/issues/159)
 * [Finna-liitännäinen: Lisätään liitännäiselle puuttuva versionumero](https://github.com/KohaSuomi/koha-plugin-rest-di/issues/9)
* Mitä uutiskirjeeseen?
 * Miksi päivitettiin nyt ja testauksen tärkeys.
* Päivystysvuorot vko 48 eteenpäin
 * Lisätty

[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-48) - [Palaa sivun alkuun](/kohasuomi2024)

## Viikko 46

Aika: 11.11.2024 klo 9<br />
Läsnä: Emmi, Kodo, Lari, Ari, Anneli

* Testien päivitys tänään

## Viikko 45

Aika: 4.11.2024 klo 9<br />
Läsnä: Emmi, Kodo, Johanna, Ari, Anneli

Ei erityistä.

## Viikko 44

Aika: 28.10.2024 klo 9<br />
Läsnä: Anneli, Kodo, Lari, Ari, Emmi

* Versionvaihto
  * Tikettien läpikäyminen
  * Mitä otettava huomioon vielä ennen h-hetkeä? 

## Viikko 43

Aika: 21.10.2024 klo 9<br />
Läsnä: Ari, Pasi, Johanna, Lari, Anneli, Kodo ja Emmi

* Päivystysvuorot viikosta 44 alkaen
  * Lari ja Kodo
  * Anneli ja Johanna
  * Emmi ja Kodo
  * Pasi ja Lari
* Kolmansien osapuolten pääsyt testeille? Ja tuotantoihin(!?) Miten linjataan, mitä suositellaan?
  * Viedään tämä asiantuntijaryhmään keskusteltavaksi 
* Käyttäjävirheiden korjaamisen linjaus. Milloin kehittäjät korjaavat, milloin jätetään korjaamatta?
  * Esimerkiksi tiketti [#1455](https://github.com/KohaSuomi/Koha/issues/1455)
  * Ari miettii asiaa ja keskustellaan lisää jossain myöhemmässä palaverissa
* Suomi.fi REST-pilotointi. Kuka aloittaa ja milloin?
  * Johanna hoitaa
* VTJ kehitys
  * Kodo

## Viikko 42

Aika: 14.10.2024 klo 9<br />
Läsnä: Johanna, Emmi, Pasi, Lari, Kodo, Anneli

**Asiat**
* Viikonlopun käyttöhäiriöt
* olisiko tarvetta laittaa päälle RecordStaffUserOnCheckout-järjestelmäasetus kaikissa kimpoissa?
  * This system preference determines whether the staff account who checks out an item to a patron is recorded along with the checkout. When set to ‘record’ the staff account will be displayed in the staff interface in the patron’s circulation history as well as the record’s checkout history.
  * Käytännössä asetuksen ollessa päällä issues-tauluun kirjautuun issuer_id-kenttään lainan tehneen virkailijan borrowernumber
  * Lainaaja näkyy asiakkaan lainahistoriassa (ei näkyvillä) ja tietueen lainahistoria-sivulla, josta sarakkeen voisi piilottaa niin, ettei käyttäjät saa sitä näkyville.
  * Esimerkki, jolloin tieto olisi ollut tarpeellinen: Virkailija unohti vaihtaa kirjautumiskirjaston ja lainat tallentuivat väärälle kirjastolle. Jos asetus olisi ollut päällä, olisi issues-tauluun kirjautunut issuer_id-kenttään virkailijan borrowernumber ja lainat olisi voinut muuttaa helposti toisen kirjaston lainoiksi. (Mites statistics?)
  * Mahdolliset ongelmat?
  * Päätös: Suositellaan käyttöön. Keskustellaan pääkäyttäjien kanssa tiistaina.
* Kolmansien osapuolten pääsyt testeille? Ja tuotantoihin(!?) Miten linjataan, mitä suositellaan?
  * Siirretään käsittely viikolle 42
* Lassen tikettien läpikäyminen ja uudelleenvastuutus
  * Käyty läpi.

## Viikko 41

Aika: 7.10.2024 klo 9<br />
Läsnä: Johanna, Anneli, Ari, Emmi, Pasi ja Lari

**Asiat**
* Asiantuntijaryhmän palaverin asioiden läpikäynti
* onko huoltokatkoa?
  * Ei ole
* versionvaihdon tilanne
  * Ei ole vähään aikaan tullut uusia.

## Viikko 40

Aika: 30.9.2024 klo 9<br />
Läsnä: Johanna, Pasi, Lari, Ari, Anneli

**Asiat**
* Plugarisioitavien JS-rimpsujen läpikäynti
  * Päätettiin mitkä rimpsut olisi vielä plugarisoitava, mitä ei plugarisoida ja mitkä rimpsut ovat ylipäänsä enää tarpeellisia 

## Viikko 39

Aika: 23.9.2024 klo 9<br />
Läsnä: Johanna, Kodo, Lari, Emmi, Pasi, Lasse, Ari, Anneli

**Asiat**
* Päivystysvuorot viikosta 40 eteenpäin
  * Vko 40 Emmi ja Kodo
  * Vko 41 Lari ja Johanna
  * Vko 42 Anneli ja Pasi
  * Vko 43 Emmi ja Johannna
* Versionvaihdossa enää kaksi vastuutonta tikettiä
  * vastuutettu loputkin

## Viikko 38

Aika: 16.9.2024 klo 9<br />
Läsnä: Johanna, Pasi, Emmi, Lari, Ari, Anneli

**Asiat**
* Viikon 37 keskeiset
  * Torstaina 12.9. tuotantojen indeksit olivat rikki ja ne piti palauttaa dumpeista.
* Päivitys
  * Viimeinen päivitys ennen tuotantojen jäädytystä.
* RDA-konversion aikataulut. Voidaan tehdä useampia yhtäaikaa, hyvä ajankohta on viikonloppu, kun ei silloin muokata kuvailutietoja.

## Viikko 37

Aika: 9.9.2024 klo 9<br />
Läsnä: Johanna, Pasi, Emmi, Lari, Kodo, Ari, Anneli

**Asiat**
* Vastuuttomien tikettien vastuutus
  * Tiketit käytiin läpi ja vastuutettiin jos pystyttiin
* Versionvaihdon vastuuttomat tiketi
  * Jokainen käy nimeämässä itselleen edellisessä versionvaihdossa tekemänsä tiketit
  * Loput katsotaan läpi jossakin tämän viikon scrummissa   
* Ei päivitystä viikolla 37


## Viikko 36

Aika: 2.9.2024 klo 9<br />
Läsnä: Ari, Emmi, Johanna, Pasi, Lari, Kodo, Anneli

* Asiantuntijaryhmästä:
  * ketkä kehittäjistä alkavat tutkimaan, miten varauksia voisi priorisoida
    * Johanna ja Lari. Anneli tekee tikettiin yhteenvedon toiveista/tarpeista.
  * [Items-tauluun on_shelf-sarake kertomaan onko nide hyllyssä #1297](https://github.com/KohaSuomi/Koha/issues/1297)
    * Koha-Suomen asiantuntijaryhmä 26.8.2024: Edistetään yhteisön kautta. Koha-Suomen kehittäjä tekee tiketin yhteisöön ja haistellaan, minkälaisen vastaanoton se saa. Koha-Suomi juttelee jatkotoimenpiteistä 27.8.2024 palaverissa.
    * Kodo kirjaa speksejä ja Emmi tutkii, mihin kaikialle muutos vaikuttaisi.
* Vastuuttomien tikettien vastuutus
* Viikon 36 päivitys
  * [Hetun tallennukseen painikkeen siirto tai muistutus tallentamattomasta hetusta #1066 ](https://github.com/KohaSuomi/Koha/issues/1066)
  * [Henkilötunnuksen tallennus ei onnistu 0-vuotiaalle #1252](https://github.com/KohaSuomi/Koha/issues/1252)
  * [000-kentän editorissa on vanhat suomennokset merkkipaikkojen 07 ja 17 arvoille #51](https://github.com/KohaSuomi/Koha-translations/issues/51)
  * [Tietokannan aikaleiman tarkistus täsmäämään 005-kentän aikaleiman kanssa. #9](https://github.com/KohaSuomi/koha-plugin-broadcast-biblios/issues/9)
* Versionvaihdon tikettien tilanne
* Päivystysvuorot viikosta 37 eteenpäin

## Viikko 35

Aika: 26.8.2024 klo 9<br />
Läsnä: Johanna, Anneli, Ari, Lasse ja Lari

* Viikon 34 keskeiset
  * RDA-konversiomäppäykset alkavat olla kunnossa, suunnitellaan konversioiden käynnistys. 
* Viikon 35 päivitys
  * Kaikki verkkokirjastossa tehdyt toimenpiteet eivät lokitu [#473](https://github.com/KohaSuomi/Koha/issues/473) 
 

[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-35) - [Palaa sivun alkuun](/kohasuomi2024)

## Viikko 34

Aika: 19.8.2024 klo 9<br />
Läsnä:

* Viikon 33 keskeiset
  * käyttökatkot ke-to 14.-15.8.2024
  * käyttökatkoista tiedottaminen
    * päivystysaikana 8-16
    * ensisijainen tieto katkoksesta edelleen matrixissa pääkäyttäjille
    * kun alkaa näyttämään, että kyseessä on pidempiaikainen ongelma, laitetaan häiriötiedote, jossa kerrotaan että on ongelma ja sitä selvitellään. Täydennetään tiedotetta sitten, kun asioita selviää.
    * alkutiedotuksen voi tehdä kuka tahansa meistä, koska kaikki ei kuitenkaan pysty osallistumaan / tarvitse osallistua ongelmaselvittelyihin.
      * Anneli luo tiedotepohjan, jonka kaikki voi sitten tallentaa Githubissa omiin saved replies -asetukseen.
      * Koha-kirjastojärjestelmissä on xxx-kimpoissa tällä hetkellä tekninen häiriö, minkä vuoksi ne eivät toimi. Selvitämme ongelmaa ja päivitämme tätä tiedotetta, kun tiedämme ongelman syystä ja sen korjauksesta enemmän.
Pahoittelemme häiriöstä aiheutuvaa haittaa.
* Tehtäväjaon suunnittelua
  * Roolitukset?
    * työparit
    * vanhempien kehittäjien erityisvastuut?
  * Tikettien priorisointisysteemi
    * Huolehditaan siitä, että myös matalan prioriteetin tikettejä tulee tehtyä. Määräajat?
  * Kehityksen seuranta
  * Suunnitteluhackaton, kvartaaleittain, pari kertaa vuodessa?
    * KohaConin yhteydessä vai kokonaan erillinen tapahtuma?
  * Otetaanko käyttöön scrummin sprintit?
    * No ei varmaan oteta, T. Kodo :D Varma keino saada työtyytyväisyys tipahtamaan nollaan ja työstressitasot 100% koko revohkalla.
* Tallennusjärjestelmäremontti
  * ocfs:n ongelmat johtuivat lvm:stä
  * vielä tehtävä blokkikoon muutos
  * Mitenkäs se lokitus? Nyt ei todennäköisesti enää ole tarvetta shm-lokitukselle, joten puretaanko seuraavassa huoltokatkossa se pois ja annetaan lokien mennä suoraan ocfs:lle?
  * elastictmpfs tarve jatkossa?
* Lastun tuotanto lähenee, konversiotauluihin vielä hieman muutoksia, joten tehdään kolmas koekonversio.
* Viikon 34 päivitys
  * Lisätään lokitusta
  * Muutetaan Melinda viennissä &lt; ja &gt takaisin hakasuluiksi
  * Takaajan tiedoissa Taattavan maksut -välilehden maksunäkymään muutosehdotus
  * Takaajan tietoihin tekstimuutosehdotus taattavan maksuista, ehdotus 2
  * Do not allow script-tags in systempreferences
  * Finna-pluginin ominaisuuden poisto: varausjonossa huomiodaan myös keskeytetyt varaukset

[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-34) - [Palaa sivun alkuun](/kohasuomi2024)

## Viikko 33

Aika: 12.8.2024 klo 9<br />
Läsnä: Lari, Ari, Lasse, Johanna, Kodo, Anneli

**Asiat**
* Viikon 32 keskeiset
  * Lokitiedostojen säilytysaikadokumentaatio. Vanha oli Redminessä, ja se luultavasti vaatii päivittämistä.
  * Tietoturvapaikan myötä niteiden vastaanotto meni rikki tiistaina. Ongelma korjattiin aluksi väliaikaisella paikalla ja sitten tuomalla keskiviikkona korjaus tuotantoihin. Väliaikaisen paikan käyttöönotto vaati palveluiden uudelleen käynnistykset kaikissa kimpoissa, tämä saattoi näkyä katkoina. 
* [Vastuuttomien tikettien vastuuttaminen](https://github.com/KohaSuomi/Koha/issues?q=is%3Aissue+is%3Aopen+no%3Aassignee)
  * jatketaan ensi viikolla
* Borrowers/status endpoint
  * lisätään lokitusta ja kirjoitetaan service-check
* Verkkolaskufoorumin kysely support-lootassa
  * Vastattu, ettei ole ongelmia. 
* finnaprefix-asetuksen kohtalo
  * Tarkoitus on ollut ilmeisesti ottaa käyttöön konfissa oleva finnaprefix-asetus, mutta sama asetus löytyy myös paikallisista asetuksista Kohasta ja koodissa käytetään nimenomaan sitä. Olisi päätettävä lopullisesti kumpi otetaan käyttöön ja kummasta luovutaan ja tehtävä siivoukset sekä mahdollinen koodimuutos sen mukaan.
  * Päätös: käytetään järjestelmäasetusten finnaprefix-asetusta. Siivotaan koha-config versionvaihdon yhteydessä.

[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-33) - [Palaa sivun alkuun](/kohasuomi2024)

## Viikko 32

Aika: 5.8.2024 klo 9<br />
Läsnä: Pasi, Johanna, Emmi, Lasse, Lari, Anneli

**Asiat**
* Viikon 31 keskeiset
  * Olisiko tarvetta pyytää Mattermostiin Koha-Finland -kanava (tai jopa Koha-Norcic), jonne saataisiin yleiset ja tieteelliset samalle alustalle? Keskustellaan pääkäyttäjien ja Arin kanssa.
  * Oraclen kanssa on nyt keskusteltu tuesta OCFS2:lle ja lisäksi muita mahdollisia vaihtoehtoja OCFS2:lle on selvitetty (Gluster tai GFS2).
  * Bittiguru toimittaa OCFS2 testiympäristön 2.8.
  * Yhteisöversio on nyt pystyssä meidän omilla palvelimilla, ongelmia normaalitapaan Plackin ja Elasticsearchin kanssa, mutta nyt kaikki vaikuttaisi toimivan. Yhteisöversiossa ei ole mitään Koha-Suomi spesifejä ominaisuuksia ja esimerkiksi indeksit ovat täysin yhteisöversion mukaiset.
  * Backuppaus ja dumppaus tuotannoista muutettu siten että tiedostot ovat oikeuksien ja omistajien suhteen paremmassa tallessa.
* Viikon 32 päivitys
  * Muutos tietuesiirtäjään [Koha #1249](https://github.com/KohaSuomi/Koha/issues/1249)
  * 4 tietoturvakorjausta
* Varmenteet jakoon tällä viikolla

[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-32) - [Palaa sivun alkuun](/kohasuomi2024)

## Viikko 31

Aika: 28.7.2024 klo 9<br />
Läsnä: Lasse, Pasi, Emmi, Johanna, Kodo, Anneli

**Asiat**
* Päivystysvuorot viikosta 32 alkaen
* Paljon asioita jää tällä hetkellä muistioista "pimentoon", koska iso osa asioista käsitellään päiväpalavereissa. Ryhdytään lisäämään keskeiset muutokset maanantaipalaverin esityslistalle ja todetaan maanantaisin että nämä tuli tehtyä viikon aikana.
* Viikon 30 keskeiset
  * Uusi muutokset kalenteri, merkkaillaan sinne merkittävät tehdyt muutokset, jotta voidaan mahdollisten ongelmien ilmetessä kalenteria apuna käyttäen haarukoita mikä ongelmia olisi mahdollisesti voinut aiheuttaa.
  * Canonicalin kanssa palaveerattu. Ubunto Pro:n hinta on jyrkähkö, mutta "educational" organisaatiot saavat hinnsata 90% alennuksen. Nyt odotellaan jännityksellä ovatko yleiset kirjastot Canonicalinkin mielestä "educational organization". Canonicalin suunnasta tukea olisi saatavilla Ubuntu main -repositorion paketeille, joihin sisältyy myös OCFS2.
  * Oraclea kontaktoitu OCFS2 tuen suhteen. Ovat yhteydessä jos kysymyksessä on heidän mielestään "Sales related question" ja kaihan tuen ostoaie on semmoinen.
* Viikon 31 päivitys
  * [LOST-arvojen jättäminen laskutuksen ulkopuolelle](https://github.com/KohaSuomi/koha-plugin-overdue-tool/issues/15)
  * [Libriksen Z39.50-säännöt](https://github.com/KohaSuomi/Koha/issues/977)
* Scrumm
  * Emmi: Koha-comm -palvelimen ongelmien korjausta ja miten sitä päivitellään
  * Anneli: käännösehdotuksien tarkistelua. Anonymisoitujen tietojen raporttia. Libris Z3950
  * Johanna: Suomi.fi -rajapinta. Yhteisöön taustatöiden filtteröintitikettiä
  * Lasse: Itsepalvelun palautus
  * Kodo: Libriksen pudotettavien kenttien kanssa säätämistä. Koha-commin pystyttelyä ja korjailua.
  * Pasi: Avointen tikettien loppuunvientiä, tietueiden palautusskriptiä

[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-31) - [Palaa sivun alkuun](/kohasuomi2024)

## Viikko 30

Aika: 22.7.2024 klo 9<br />
Läsnä: Lasse, Pasi, Emmi, Johanna, Kodo, Anneli

**Asiat**
* Bug [35604](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=35604) - ILL - Allow for automatic backend selection testaus   
  * laitetaan comm-kanta pystyyn ja testataan siellä
  * tehdään comm-kontissa päivitys tuoreempaan käyttöjärjestelmäversioon
  * Emmillä on yhteisöversion kanta, käytetään sitä
  * moduulit yhteisön pakettivarannosta, vanhat cpanit pois
* Viikon 30 päivitys
  * [Sarjajulkaisun hakeminen fasetin kautta #251](https://github.com/KohaSuomi/Koha/issues/251)
  * [Laskutusliitännäinen: Älä käytä saraketta "accounttype" jos asiakkaalle lisätään maksuja #8](https://github.com/KohaSuomi/koha-plugin-overdue-tool/issues/8)
  * [Template-cachen hakemiston vaihto #517](https://github.com/KohaSuomi/Koha/issues/517) (perjantain automaattikatkos liittyi tähän)
* Scrumm
  * Johanna: versionvaihtotikettien ihmettelyä (niteitä ei saa auki nidevälilehdellä)
  * Pasi: yhteisön tikettien katselua
  * Emmi: niteitä ei saa auki välilehdellä, varaustyökalun tutkiskelua, miten saa toimimaan apin kautta
  * Kodo: muutoksia build releaseen, ei tarvitse enää hakemistoa buildille (käyttää $KOHA_PATH:ia). korefreshiin remonttia, siinä on nyt -u vipu, jolla ajetaan updatedatabase. Ajatuksena oli ratkaista [#669](https://github.com/KohaSuomi/Koha/issues/669). Helpin saa korefresh -h.
  * Lasse: versionvaihtotikettejä
  * Anneli: lomailua ja viestien läpikäyntiä

[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-30) - [Palaa sivun alkuun](/kohasuomi2024)

## Viikko 29

Aika: Maanantai 15.7.2024 klo 9<br />
Läsnä: Lasse, Pasi, Johanna ja Emmi

**Asiat**
* Ei päivitystä tällä viikolla
* Muistutus ottaa omat versionvaihdon tiketit työn alle
* Scrumm:
  * Lasse: varaussivun kattelua
  * Pasi: tietokantojen siivousskriptejä
  * Johanna: suomi.fi-rajapinnan aloitus
  * Emmi: versionvaihdon tikettejä 

[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-29) - [Palaa sivun alkuun](/kohasuomi2024)

## Viikko 28

Aika: Maanantai 8.7.2024 klo 9<br />
Läsnä: Pasi, Emmi, Ari, Lasse, Lari

**Asiat**
* Ei Kohan päivitystä
* Perjantaiaamuna meg:llä olleet kohat kaatuivat, plack kaatui, reloadi/restartti ei auttanut, piti stopata/käynnistellä memcached ja apache2
* Scrumm:
  * Emmi: Yhteisötikettejä
  * Lasse: Varausssivun ongelmien korjausta
  * Lari: Toveri-ongelma, koosteviestien kieliongelma Finnan kanssa
  * Pasi: Tietueitten palautteluskriptin testausta

[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-28) - [Palaa sivun alkuun](/kohasuomi2024)

## Viikko 27

Aika: Maanantai 1.7.2024 klo 9<br />
Läsnä: Pasi, Lasse, Ari, Emmi, Lari

**Asiat**
* Otetaan "omat" tiketit työn alle [Koha-24.05](https://github.com/KohaSuomi/Koha-24.05/issues)-reposta
* Viikon 27 päivitys:
  * [Jäädytetyjen ja aktiivisten varausten erottaminen lukumäärässä #1170](https://github.com/KohaSuomi/Koha/issues/1170) 
* Scrumm:
  * Lari: js-plugarien viemistä seuraavaan versioon, loppujen versionvaihtotikettien läpikäymistä
  * Lasse: tikettejä
  * Pasi: metadatan timestampien oikaisuskripti, ajettu OUTIin ja Lappiin, loput illalla   
  * Emmi: tikettejä, Vaskin hankintahinnattomien ihmettelyä

[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-27) - [Palaa sivun alkuun](/kohasuomi2024)

## Viikko 26

Aika: Maanantai 24.6.2024 klo 9<br />
Läsnä: Ari, Emmi, Pasi, Kodo, Lari

**Asiat**
* [Vanhoja kuvalutietoja valuu uusien päälle #1298](https://github.com/KohaSuomi/Koha/issues/1298)
  * Päivitetään kimppojen metadatojen timestampit, jottei tietueita enää valu tätistä
  * Laitetaan valutus takaisin päälle
  * Tehdään ohjelmanpätkä jolla palautetaan actionlogsista muuttuneet tietueet
* Päivitys:
  * [Automaateilla ei päivity uusitun lainan eräpäivä](https://github.com/KohaSuomi/Koha/issues/1291)
  * [Käännös: Hankinnan vastaanoton väärä käännös](https://github.com/KohaSuomi/Koha-translations/issues/42)
  * [Käännös: Rajoita saatavilla oleviin niteisiin](https://github.com/KohaSuomi/Koha-translations/issues/37)

[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-26) - [Palaa sivun alkuun](/kohasuomi2024)

## Viikko 25

Aika: Tiistai 18.6.2024 klo 12<br />
Läsnä: Pasi, Anneli, Lasse, Ari, Kodo, Lari, Emmi

**Asiat**
* Pääkäyttäjäpalaverit ja päivitystiedotteet Annelin loma-aikana
  * Päivystäjät hoitaa
* Scrumm:
  * Anneli: päivitystiedotteen tekemistä, käännöksiä
  * Kodo: OCFS:stä keskusteltu operaattorin kanssa, pystyttävät testiympäristön, fix-yarn mukaan buildiin, service-checkin dokumentointi, Lastun tunnareiden tekoa
  * Lasse: tulevaisuudessa alkavien varausten näkyminen tietueen varaukset -näytöllä
  * Lari: automaattihommia, nidepakkettien varaus tiketti
  * Pasi: sotuteekkiin muutos, Siilin tuotannon MARC-kentät järjestetty, muihin tuotantoihin sama ajo
  * Emmi: versionvaihdon tiketöintiä, päivitys aamulla, tietokantasiivouksen pohdintaa     

[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-25) - [Palaa sivun alkuun](/kohasuomi2024)

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

[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-24) - [Palaa sivun alkuun](/kohasuomi2024)

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

[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-23) - [Palaa sivun alkuun](/kohasuomi2024)

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

[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-22) - [Palaa sivun alkuun](/kohasuomi2024)

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


[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-21) - [Palaa sivun alkuun](/kohasuomi2024)

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

[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-20) - [Palaa sivun alkuun](/kohasuomi2024)

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

[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-18) - [Palaa sivun alkuun](/kohasuomi2024)

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

[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-17) - [Palaa sivun alkuun](/kohasuomi2024)

## Viikko 16

Aika: Maanantai 15.4.2024 klo 9<br />
Läsnä: Lasse, Ari, Emmi, Anneli, Johanna, Pasi, Kassu, Lari, Kodo

* Miten toteutetaan [tiketti #467](https://github.com/KohaSuomi/Koha/issues/467) / Kassu
  * CSS-muutos ja käännös, koetetaan saada yhteisöön
* Versionvaihdon tarkempi aikataulu päätettävä ja tiedotettava.
  * Sunnuntai-iltana 5.5. klo 19
* JS-rimpsujen läpikäynti Larin listan pohjalta

[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-16) - [Palaa sivun alkuun](/kohasuomi2024)

## Viikko 15

Aika: Maanantai 8.4.2024 klo 9<br />
Läsnä: Pasi, Emmi, Lasse, Anneli, Lari, Ari, Kodo, Kassu

* Onko kaikki laittaneet kesälomansa kalenteriin?

[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-15) - [Palaa sivun alkuun](/kohasuomi2024)

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

[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-14) - [Palaa sivun alkuun](/kohasuomi2024)
  
## Viikko 13

Aika: 25.3.2024 klo 9<br />
Läsnä: Ari, Lari, Anneli, Kassu, Lasse, Johanna, Emmi, Pasi

* Vk 14 pääkäyttäjille pääsy nexteille testausta varten

[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-13) - [Palaa sivun alkuun](/kohasuomi2024)

## Viikko 12

Aika: 18.3.2024 klo 9<br />
Läsnä: Lari, Lasse, Kodo, Anneli, Pasi, Ari, Emmi

* [Yhteisöversion-testikannan pystytys](https://github.com/KohaSuomi/Koha/issues/1116) Joskus kesällä.

[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-12) - [Palaa sivun alkuun](/kohasuomi2024)

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

[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-11) - [Palaa sivun alkuun](/kohasuomi2024)

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

[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-10) - [Palaa sivun alkuun](/kohasuomi2024)

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

[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-9) - [Palaa sivun alkuun](/kohasuomi2024)

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

[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-8) - [Palaa sivun alkuun](/kohasuomi2024)

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


[Palaa viikon muistion alkuun](https://koha-suomi.fi/kohasuomi2024#viikko-7) - [Palaa sivun alkuun](/kohasuomi2024)

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
