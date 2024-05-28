---
layout: single
permalink: /asiantuntijaryhma2024
hidden: true
header:
  overlay_color: '#5e616c'
  overlay_image: /assets/images/cropped-pexels-photo-113850.jpeg
toc: true
title: 'Koha-Suomen asiantuntijaryhmä 2024'
---

Tältä sivulta löydät Koha-Suomen asiantuntijaryhmän vuoden 2024 muistiot. Uusin muistio on aina ylimmäisenä.

Koha-Suomen asiantuntijaryhmään kuuluvat Leena Kinnunen (Lapin kirjasto), Noora Valkonen (OUTI-kirjastot), Päivi Knuutinen (Vaara-kirjastot), Hanna Ikonen (Lumme-kirjastot), Tuomas Kunttu (Kyyti-kirjastot), Katri Sillgren (Helle-kirjastot), Susanna Sandell (Vaski-kirjastot) sekä Riikka Mustajärvi (Kirkes). Koha-Suomesta mukana on puheenjohtajana Ari Mäkiranta ja asiantuntijoina Anneli Österman ja Kodo Korkalo.

Asiantuntijaryhmän valitsee kerran vuodessa Koha-Suomen hallitus.

## Asiantuntijaryhmän muistio 7/2024

Aika: 27.5.2024 klo 13<br />
Läsnä: Päivi Knuutinen (Vaara), Ari Mäkiranta, Piia Semenoff (OUTI), Roosa Kyllönen (Kyyti), Pia Kusmin (Lapin kirjasto), Riikka Mustajärvi (Kirkes), Susanna Sandell (Vaski), Anneli Österman, Katja Valjakka, Kodo Korkalo

### 1. Arin ajankohtaiset

Versiopäivitys meni melko hyvin.
Suomi.fi viesteihin on tulossa käyttöön REST-rajapinta.

### 2. Tiekartan tarkistus

Käydään läpi tiekartta ja päivitetään tarpeen mukaan.

Päivitetty toukokuun tiekartta: [Tiekartta2024touko.xlsx](https://github.com/KohaSuomi/kohasuomi.github.io/files/15456347/Tiekartta2024touko.xlsx)

### 3. Varausten priorisointi

Kohassa on järjestelmäasetus [LocalHoldsPriority](https://koha-community.org/manual/23.11/en/html/circulationpreferences.html#localholdspriority-localholdsprioritypatroncontrol-localholdspriorityitemcontrol), jolla voi priorisoida varauksia niin, että palautuskirjastossa olevat varaukset jäävät kiinni, vaikka niiden edellä olisi varauksia muualla. Yksittäisiä niteitä ja asiakastyyppejä voi määrittää toiminnon ulkopuolelle.

Kannattaisiko toimintoa kokeilla jossain tai voisiko ajatella, että tuo asetus/toiminto otettaisiin pohjaksi, kun varausten priorisointia lähetään joskus kehittämään Kohassa.

Mahdollisia ongelmia:
* niteeseen voi jäädä kiinni varaus, joka on esim. sijalla 350.
* pienessä kirjastossa noudettavaksi haluttu varaus voidaan ohittaa periaatteessa rajattomasti, jos joku asiakas ei satu palauttamaan nidettä juuri sinne.

**Pohdittavaksi seuraavaan kokoukseen:**

Minkälaisia ehtoja toimintoon tarvittaisiin?
* kannattako höydyntää jotenkin suhdelukua niteitä/varauksia, saman tyylisesti kuin Varauksia per nide -raportilla, jonka jälkeen esim. aletaan vasta priorisoimaan. 
* kuinka usein ohitetaan asiakas max?
* kuinka iso joukko varauksia jonon alusta otetaan huomioon? Numeerinen raja vai prosenttiosuus vai jotain muuta?

### 4. JavaScript-rimpsuja

Otetaanko tuen piiriin seuraavat JS-rimpsut?

* [Nidehaun julkaisuvuosi-hakuun ennen/jälkeen -toiminnot #447](https://github.com/KohaSuomi/Koha/issues/447) - Väliaikainen korjaus
  * Päätös: Ei oteta, viedäänkin korjaus yhteisöön ja asennetaan myös meille.
* [Käännöstoive: asiakastakaajan lisäys ja select-nappi #1014 ](https://github.com/KohaSuomi/Koha/issues/1014) - siirretään Select-nappi ja poistetaan Osoite-sarakkeesta ylimääräinan kirjastotieto.
  * Päätös: Ei oteta, viedäänkin korjaus yhteisöön ja asennetaan myös meille.
* [Asiakastietojen suojattu-valinta näkyviin vain pääkäyttäjille](https://github.com/KohaSuomi/Koha/issues/1232) - Vaskin rimpsu, jonka useampi haluaa käyttöön. Kannattaako plugarisoida ja ottaa Koha-Suomen vastuulle?
  * Päätös: Tehdään liitännäiseksi ja asennetaan kaikkiin kimppohin. Pääkäyttäjät voivat tarvittaessa aktivoida liitännäisen käyttöön sen jälkeen. 

### 5. Kuulumisia Suomi.fi Viesti -rajapinnan uudistuksista

Kodo kertoi Suomi.fi Viestit -rajapinnan uudistuksista. Hän ja Strandin Lari osallistuivat Valtion integraatioalustan tiedotustilaisuuteen viikolla 21.

* REST-rajapinta tulossa. Se mahdollistaa viestien välittämisen Suomi.fi Viesteihin niin, että varsinaiseen viestiinkin saadaan enemmän sisältöä, eikä asiakkaan tarvitse lukea kirjaston viestiä liitteenä olevasta pdf-tiedostosta. Viestit tulevat olemaan enemmän sähköpostin/pikaviestin kaltaisia jatkossa, mutta päästä päähän salattuja. Jos asiakkaalla on käytössä puhelimessa Suomi.fi-sovellus, voi hän saada ilmoituksia saapuvista viesteistä kuten sähköposteista/pikaviesteistä.
* Tähän mennessä viestejä on voinut lähettää vain sellaisille henkilöille, joilla on suomalainen henkilötunnus. Tähän on tullut muutos ja viestit voidaan lähettää jo nyt pelkän osoitteen perusteella, eli periaatteessa kaikki kirjeviestintä voitaisiin siirtää Suomi.fi Viesteihin.

Tarkempi tiedote (linkki tulossa)

Kimpoissa selvitykseen:
* Pystyisikö kimpat siirtyä käyttämään Suomi.fi Viestit -palvelua kirjeiden osalta ja luopua nykyisistä kirjeviestirajapinnoista?
  * Suomi.fi Viestit käytössä tällä hetkellä Vaarassa ja Kirkeksessä. Tulossa myös Lastuun.

### 6. Kehitysehdotusten läpikänti

* [Virkailijaoikeuksien muodostuminen automaattisesti asiakasmääreen perusteella #1169](https://github.com/KohaSuomi/Koha/issues/1169)
  * Versioon 24.05 on tulossa mahdollisuus kopioida käyttäjäoikeudet käyttäjältä toiselle
  * **Päätös**: Versioon 24.05 tulee ominaisuus, jossa käyttäjoikeudet voidaan kopioida käyttäjältä toiselle. Seurataan, tuoko yhteisö ominaisuutta aikaisempiin versioihin ja tuodaan se sitten mahdollisesti meidän nykyiseen versioon. Muuten ominaisuus tulee käyttöön vuoden päästä, kun päivitetään versioon 24.xx. Ei tehdä automaatiota, mutta tarvittaessa kimpoissa voi hyödyntää asiakasmääreitä ja auktorisoituja arvoja kertomaan, mitkä käyttäjäoikeudet käyttäjällä on.
* [Jäädytetyjen ja aktiivisten varausten erottaminen lukumäärässä #1170 ](https://github.com/KohaSuomi/Koha/issues/1170)
  * Pitääkö ottaa huomioon myös tulevaisuudessa voimaan tulevat varaukset?
  * Korjaus tarkoittaisi syvälle meneviä koodimuutoksia. Mielellään yhteisön kautta.
  * Finna-kuvio pitää miettiä erikseen, koska huomioitava Finna-rajapinta ja Finnan käyttöliittymä.
    * Päivi on kysynyt Finna-toimistosta asiasta ja he ovat tehneet varausten näkyvyydestä muutosehdotuksen.
  * **Päätös**: Tutkitaan, olisiko Kassun ehdotus taulukon yläreunan lisätekstistä mahdollinen ratkaisu. Sinne voisi siis koota tietoja tyyliin
Aktiivisia 5, Keskeytettyjä 3, Ei vielä voimassa 2
* [Tiettyjen LOST- ja NOT_LOAN arvojen jättäminen laskutuksen ulkopuolelle #1171](https://github.com/KohaSuomi/Koha/issues/1171)
  * Riittäisikö, että kaikki LOST-tilat jätettäisiin laskutuksen ulkopuolelle?
  * **Päätös**: Muutetaan laskutustyökalua niin, että LOST-tilaiset niteet eivät tule mukaan laskutettavien listalle. Ei lisätä mahdollisuutta määritellä, mitkä LOST-tilaiset otetaan huomioon, vaan kaikki LOST-tilat jätetään pois listalta.
* [Takaajan tietoihin muutosehdotus taattavan maksunäkymistä, ehdotus 2. #1173](https://github.com/KohaSuomi/Koha/issues/1173)
  * Ehdotus: toteutus yhteisössä
  * **Päätös**: Toteutetaan itse ja tarjotaan yhteisölle muutos. Edellinen vastaava on mennyt siellä läpi.
* [Nalkuta eri kentistä luettelointipohjan mukaan #1](https://github.com/KohaSuomi/koha-plugin-nalkutin/issues/1)
  * Ehdotus: toteutetaan
  * **Päätös**: Viedään Indeksointi- ja tiedonhakuryhmään päätettäväksi.
  Asiantuntijaryhmän huomioita:
  * Nalkutin muutettaisiin sellaiseksi, että jokaiselle/halutuille kuvailupohjalle voidaan määrittää omat säännöt, joiden mukaan nalkutetaan.
* [Kiireetön varaus: Asiakkaan tiedoissa olevasta varausjonosta ei erotu, jos jokin varauksista on kiireetön varaus #1187](https://github.com/KohaSuomi/Koha/issues/1187)
  * Ehdotus: toteutus yhteisön kautta
  * **Päätös**: Ei toteuteta, koska kiireettömiä varauksia tehdään lähinnä työkorteille. Piia tekee yhteisöön kehitysehdotuksen.
*  [Myöhemmin voimaan tulevan varauksen erottuminen varausjonossa #1214](https://github.com/KohaSuomi/Koha/issues/1214)
   * Ehdotus: toteutus yhteisön kautta
   * **Päätös**: Tiketissä #1170 päätettiin tutkia, saisiko varaustaulukkoon lisättyä jonkinlaisen tiedon, kuinka monta aktiivista, keskeytettyä ja ei-aktiivista varausta tietueella on. Se riittänee tämänkin tiketin osalta. 
* [Takaajan tiedoissa Taattavan maksut -välilehden maksunäkymään muutosehdotus](https://github.com/KohaSuomi/Koha/issues/1239)
  * **Päätös**: Tehdään korjaus ja tarjotaan sitä yhteisöön.

### 7. Muut asiat

Kimpoissa selvitykseen seuraavaan kokoukseen, ketä ehdotetaan jäseniksi seuraavaan asiantuntijaryhmään. Koha-Suomen hallitus valitsee uuden asiantuntijaryhmän syksyllä.

### 8. Seuraavat kokoukset

Kesän kokoukset:

Ke 19.6.2024 klo 13
Ma 26.8.2024 klo 13

## Asiantuntijaryhmän muistio 6/24

Aika: 29.4.2024 klo 13<br />
Läsnä: Ari Mäkiranta, Tuomas Kunttu , Piia Semenoff, Päivi Knuutinen, Hanna Ikonen, Janne Seppänen (kohta 2), Leena Kinnunen, Susanna Sandell, Riikka Mustajärvi, Tove Selkälä, Kodo Korkalo, Anneli Österman

### 1. Arin ajankohtaiset

Tilinpäätös valmistumassa.

### 2. Sähköinen ilmoittautuminen

Lastu-kirjastoista Janne Seppänen kertoi heidän sähköisen ilmoittautumisen prosessista.
  * [epalvelun](https://epalvelu.fi/) kautta voi tehdä vahvan tunnistautumisen vaativan lomakkeen, joka ei pakota hyväksymään suomi.fi-viestien käyttöönottoa.
  * Lastussa käytetään [Heinolan kunnan lomaketta](https://heinola.epalvelu.fi/services/heinola/10565/revision/19/)
  * Webprobolilla on vastaava toteutus, mutta se vaatii hyväksymään suomi.fi-viestien käyttöönoton.
  * Lomakkeen tiedot tallennetaan palvelimelle xml-muodossa (jokaisesta asiakkaasta oma xml-tiedosto), josta ohjelmistorobotti ottaa ne yksi kerrallaan käsittelyyn yöllä. Robotti kirjautuu Auroran käyttöliittymään ja lisää asiakkaat sitä kautta.
  * Robotti myös poistaa sellaiset asiakastiedot, joita ei ole otettu käyttöön tietyn ajan kuluessa.
  * Lisätyistä ja poistetuista asiakastiedoista (määrä) sekä virheistä saavat päivittäin tiedon sähköpostiin.

Miten Kohan osalta kannattaisi mahdollisesti edetä?
* Kannattanee hyödyntää samalla tavalla valmista lomakepalvelua, johon on liitetty jo vahva tunnistautuminen
* Kohan REST-rajapinnassa on mahdollista viedä asiakastietoja JSON-muodossa tietokantaan.
* Lomakkeen ja rajapinnan väliin tarvittaneen todennäköisesti jokin "konvertteri", joka muuttaa datan oikeaan muotoon ja vie ne rajapinnan kautta Kohaan.
* Sotu-siiloon ei ole yhteyttä, joten hetut pitänee lisätä sitten, kun asiakas tulee noutamaan kortin.
* Sähköisille ilmoittautujille kannattaisi tehdä Kohaan oma asiakastyyppi, joka muutetaan sitten joksikin muuksi, kun asiakas tulee noutamaan kortin.
* Ajastetulla ajolla voidaan poistaa asiakkaat, joiden asiakastyyppi ei ole muuttunut toiseksi tietyn ajan sisällä rekisteröimispäivästä.

Jatko: Kodo on yhteyksissä Heinolan tietohallintoon henkilöön, joka on ollut mukana Heinolan lomakkeen käyttöönotossa.

### 3. Signum-työryhmän perustaminen

Edellisessä kokouksessa päätettiin perustaa työryhmä, joka miettii ja testaa, voisiko signumeihin tehdä sellaisen muutoksen, että ne sisältäisivät vain luokan ja pääsanan. Mitä kaikkea pitää ottaa huomioon, jos muutos tehdään. Jokaisesta kimpasta pyydettiin etsimään yksi jäsen mukaan ryhmään.

[Kohan signumiin vain luokka ja pääsana #923](https://github.com/KohaSuomi/Koha/issues/923)

Jäsenet kimpoista:

OUTI: Anu Seilonen ja Mari Vesala (ouka.fi)<br />
Lappi: Pia Kusmin<br />
Kirkes: Sani Kuosmanen, Tuusula<br />
Vaara: Päivi Knuutinen<br />
Helle: Kati Sillgren<br />
Lumme: Katja Valjakka<br />
Kyyti: Tuomas Kunttu<br />
Vaski: Anni Rajala<br />
Koha-Suomi: Anneli Österman ja Pasi Kallinen

Kokoonkutsujana toimii Anneli.

### 4. Kehitysehdotusten läpikäynti

* [Ilmoitukset-sivun viestit ladattavaksi sivu kerrallaan #691](https://github.com/KohaSuomi/Koha/issues/691)
  * Jatketaan käsittelyä.
  * Päätös: Edistetään kahta ratkaisua rinnakkain:
    1. Viestejä poistetaan jatkossa määrän mukaan. Viestien määrärajaksi 500. Lisäksi viestit-sivulle lisätään JavaScript-liitännäinen, jolla kerrotaan, että vanhemmat viestit löytyvät raportilla ja nappi/linkki, jolla saa ajettua kyseisen raportin (samalla tavalla kuin lainamäärä-raportti perustiedot-näytöllä tiedonhaussa).
    2. Tiketin avaajana Mikko Liimatainen tekee yhteisöön tiketin, jossa ehdotetaan yhteisöön viesteille api-endpoint, jolloin sivu voidaan ladata asynkronisesti.
* [Hetun tallennukseen painikkeen siirto tai muistutus tallentamattomasta hetusta #1066](https://github.com/KohaSuomi/Koha/issues/1066)
  * Ehdotus: Kommenteissa olevan Larin vaihtoehto
  * Päätös: Tutkitaan, saisiko asiakkaan muokkaus/lisäyssivun yläreunan Tallenna-napin "epäaktiiviseksi" kunnes on painettu Lisää hetu -osiossa joko Tallenna tai Ohita. Jonkinlainen ohjeistus myös, jos yritetään tallentaa ilman hetun tallennusta tai ohitusta.
* [Erääntyneille varauksille asetettavaksi erikoistila varauksen vanhenemisen yhteydessä #1100](https://github.com/KohaSuomi/Koha/issues/1100)
  * Ehdotus: Toteutettavissa. Halutaanko tarjota yhteisöön?
  * Päätös: Toteutetaan ja tarjotaan yhteisöön. Niteen tila pitää olla ajastetussa ajossa määriteltävissä, jotta ratkaisu kelpaa yhteisölle. Pääkäyttäjät: Listatkaa tähän tikettiin kimpassa käytössä olevat NOT_LOAN-tilat, niin koitetaan löytää jokin, jota voisi käyttää kaikissa kimpoissa. Tarvittaessa luodaan uusi arvo kaikille, jolloin se olisi sama.
* [Hyllyvarausraportissa värikoodaus seudun mukaan #1138](https://github.com/KohaSuomi/Koha/issues/1138)
  * Ehdotus: Toteutus kirjastoryhmien kautta.
  * Päätös: Toteutetaan hyödyntäen kirjastoryhmiä. Kokeillaan riittäisikö yksiköiden tunnusten lihavointi sarakkeessa, jotta ei tulisi liikaa hankalasti toisistaan erottuvia värejä.

### 5. Muut asiat

#### 5.1 Salasanojen vanhenemistoiminto

[Salasanan vanhenemistoiminto](https://github.com/KohaSuomi/Koha-23x/issues/98) - Miten toimitaan vanhentuneiden käyttäjätunnusten kirjautumisen estämisessä? Mennäänkö uudella salasanan vanhenemistoiminnolla vai pysytäänkö vanhassa tavassa?

Asiasta keskusteltiin pääkäyttäjäpalaverissa ja päätettiin, että asia viedään asiantuntijaryhmän päätettäväksi.

Päätös: Otetaan käyttöön virkailijatunnuksilla uusi salasanan vanhenemistoiminto niin, että salasanan vanhentumispäivä seuraa tunnuksen vanhentumispäivää. Triggeri hoitaa, että ne ovat samat ja että muutos koskee vain asiakastyyppiä VIRKAILIJA. Kaikissa kimpoissa asiakastyypin tunnus on sama.

##### 5.2. Ehdokkaat seuraavaan asiantuntijaryhmään

Selvitelkää kimpoissa (myös Lastu) ehdokkaat seuraavaan nimettävään asiantuntijaryhmään.

### 6. Seuraava kokous

Sovitaan seuraavan kokouksen / seuraavien kokousten ajankohta.

Ma 27.5.2024 klo 13.

Sovitaan toukokuun kokouksessa kesän ja syksyn kokoukset.

## Asiantuntijaryhmän muistio 5/2024

Aika: 8.4.2024 klo 13<br />
Läsnä: Ari Mäkiranta, Anneli Österman, Kodo Korkalo, Leena Kinnunen, Irina Halminen, Susanna Sandell, Tuomas Kunttu, Riikka Mustajärvi, Kati Sillgren, Hanna Ikonen

### 1. Arin ajankohtaiset

Uuden version esittely 17.4.
Seuraava bugiperjantai 26.4.

### 2. Kehitysehdotukset

* [Paperiselle palautuskuitille niteiden tiedot myös silloin kun asiakas on valinnut ettei lainahistoriaa tallenneta #441](https://github.com/KohaSuomi/Koha/issues/441)
  * Ehdotus uudelleen käsittelyyn tutkinnan jälkeen.
  * Ei ole teknisesti toteutettavissa. Lainatiedot jäävät statisticsiin, mutta niiden pitäisi oikeastaan anonymisoidessa poistua sieltäkin.
  * Tapaukset luultavasti todella harvinaisia ja lienee hoidettavissa selittämällä asiakkaalle, että tieto lainasta katoaa saman tien kun palautus tapahtuu silloin kun lainahistoriaa ei säilytetä.
  * Päätös: Ei toteuteta. Tutkitaan, saisiko kuitille tulostumaan Template Toolkitin avulla jotain tyyliin "Ei lainahistoriaa" tai "Lainahistoria anonymisoitu, ei voida tulostaa palautuksia".
  * Pitäisi kirjoittaa myös anonymisointiskripti, joka anonymisoi sähköpostiin lähetetyt palautus/lainakuitit, jos asiakas on valinnut, ettei lainahistoriaa tallenneta.
  * Kodo tekee tiketit kuittipohjasta ja anonymisoinnista.
* [Varaustunnus-asiakasmääre näkyville mm. Noudettavissa olevat varaukset -toiminnossa #514](https://github.com/KohaSuomi/Koha/issues/514)
  * Päätös: Tiketissä [Waitingreserves.pl-sivulle mahdollisuus näyttää asiakkaan tiedoista vain varaustunniste #367](https://github.com/KohaSuomi/Koha/issues/367) on päätetty, että asiakastiedot piilotetaan. Noudatetaan sitä päätöstä, eikä tuoda varaustunnusta näkyville.
* [Ilmoitukset-sivun viestit ladattavaksi sivu kerrallaan #691](https://github.com/KohaSuomi/Koha/issues/691)
  * Ehdotus: Ratkaisu yhteisön kautta, toteuttamalla viesteille api-endpoint, jolloin sivu voidaan ladata asynkronisesti.
  * Päätös: Jatketaan asian pohdintaa seuraavassa kokouksessa tikettiin kirjattujen tietojen pohjalta.
* [Laskutustyökalun toiminnot Luo Finvoice/Luo e-lasku mahdollistavat tuplalaskujen syntymisen #734](https://github.com/KohaSuomi/Koha/issues/734)
  * Ehdotus: Toteutettavissa oleva esim. niin että nappulan painamisen jälkeen ei voi klikata uudelleen. Tai piilottamalla laskutetut näytöltä.
  * Päätös: Epäaktivoidaan nappulat, koska piilotus voi olla käyttäjän kannalta hämäävää. Tulee helposti tunne, että jotain meni pieleen, jos ruudulta katoaa sisältöä.
* [Tekstiviestivalinnan estäminen noutomuistutukselta #861](https://github.com/KohaSuomi/Koha/issues/861)
  * Ehdotus: Tutkittava, onko mahdollista esim. tiputtamalla sms-message_transport (tjsp.) noutomuistutukselta.
  * Päätös: Tutkitaan, katoavatko tekstiviestivalinnat Finnasta ja Kohasta, jos poistetaan noutomuistutukselta sms-mahdollisuus.
* [Kohan signumiin vain luokka ja pääsana #923](https://github.com/KohaSuomi/Koha/issues/923)
  * Ehdotus: Keskustellaan aiheesta, voi olla tiedossa iso remontti.
  * Päätös: Selvitetään, olisiko muutos toteutettavissa. Tutkitaan, miten lajittelusäännöt ja tarrapohjat saadaan toimimaan kuten ennenkin tai halutulla tavalla. Perustetaan ryhmä tutkimaan muutosta. Ehdokkaat jäsenistä seuraavaan asiantuntijaryhmän kokoukseen. Mukaan toivotaan myös automaattien lajitteluja ymmärtäviä kirjastolaisia. Yksi jäsen/kimppa.

### 3. Muut asiat

#### 3.1 JavaScriptien muuttaminen liitännäisiksi

Strandin Larille on annettu tehtäväksi käydä läpi kaikki Koha-Suomen JavaScriptit ja millä kimpoilla ne on käytössä. Sen jälkeen pohditaan Koha-Suomen palaverissa, mitkä niistä kannattaisi muuttaa liitännäiseksi. Pääkäyttäjät pystyvät aktivoimaan ja epäaktivoimaan liitännäiset tarpeen mukaan. Osaan liitännäisistä tulee myös mahdollisuus tehdä määrittelyjä, esim. jos se koskee vain tiettyjä asiakastyyppejä tai käytetään jotain tiettyä tallennettua raporttia. Sen myötä IntranetUserJS-järjestelmäasetuksen sisältö vähenee ja JavaScriptien ylläpito helpottuu. Käsitellään ehdotus liitännäiseksi muutettavista JavaScripteistä myös pääkäyttäjien viikkopalaverissa ennen toteutusta.

#### 3.2 Asiakasvarmenteiden jakelun aikataulu

Asiakasvarmenteet vanhenevat 31.8.2024. Sertifikaatti voi olla voimassa maksimissaan 390 päivää, jolloin uutta varmennetta ei voi tehdä kovin aikaisin. Uusi varmenne tulee jakoon elokuun alussa viikolla 32, jolloin käyttäjille ja kuntien IT-väelle jää vajaa kuukausi aikaa asentaa uusi varmenne.

#### 3.3 Sähköinen ilmoittautuminen ei saanut rahoitusta, miten jatketaan?

Oulu haki hankerahoitusta sähköoisen ilmoittautumisen suunnitteluun, mutta rahoitusta ei saatu. Pohditaan, miten asiaa voitaisiin edistää itse. Tutustutaan pikaisella aikataululla Lastun käyttöprjoketissa heillä käytössä olevan [vahvan tunnistautumisen vaativan e-lomakkeen toimintatapaan](https://heinola.epalvelu.fi/services/heinola/10565/revision/19/). Lomakkeen toteutus on tultava jostain muualta kuin Koha-Suomesta, joka toimittaa REST-rajapinnan Kohaan. Palataan asiaan asiantuntijaryhmässä, kun Lastusta on saatu tarkempia tietoja.

#### 3.4 Viestitaulun säilytysaika kuluva vuosi

Viestitaulun säilytysaika on nykyään kuluva vuosi.

### 4. Seuraava kokous

Ma 29.4.2024 klo 13.

## Asiantuntijaryhmän muistio 4/24

Aika: 18.3.2024 klo 13<br />
Läsnä: Kodo Korkalo, Anneli Österman, Ari Mäkiranta ja Emmi Takkinen (kohta 3) (Koha-Suomi), Päivi Knuutinen (Vaara), Hanna Ikonen (Lumme), Noora Valkonen (OUTI), Susanna Sandell ja Anni Rajala (Vaski), Leena Kinnunen (Lappi), Tuomas Kunttu (Kyyti), Kati Sillgren (Helle), Anu Järvi (Kirkes)

### 1. Arin ajankohtaiset

Harjoittelija aloitti maaliskuun alussa Oulussa. Harjoittelu jatkuu toukokuun loppuun saakka.

### 2. Varausjono vs. Hyllyvarausraportti

Keskustellaan Varausjono- ja Hyllyvarausraporteista. Taustalla on toiveita raportin ja kuljetusten optimointiin. Varausjono-raporttiin pystyy kytkemään Kohan kuljetusten painomatriisin, hyllyvarausraporttiin ei pysty. Hyllyvarausraporttiin on taas tehty paljon muutoksia, joita Varausjonossa ei ole. Samat muutokset pitäisi todennäköisesti tehdä myös Varausjono-raporttiin, jotta se olisi käytettävyydeltään samaa luokkaa. Onko järkevää ylläpitää molempia? Anni Rajala alustaa aihetta.

Päätös: Pysytään toistaiseksi Hyllyvarausraportissa, mutta pidetään varausten optimointi mielessä. Muun kuin hyllyvarausten osalta optimointi pitää olla reaaliaikaista, kun asiakas palauttaa niteen automaattiin. Tämä on haastavaa, eikä siihen ole tällä hetkellä ratkaisua.

Vaski on yhteydessä Broomworks Oy:hyn, olisiko heillä kiinnostusta tutkia lainasta palautuvan aineiston kuljetusten optimointia.

### 3. Kehitysehdotusten läpikäynti

* [Noutamattoman varauksen maksun määräytyminen nidetyypin mukaan #404](https://github.com/KohaSuomi/Koha/issues/404)
  * Päätös: Toteutetaan. Kehittäjät tutkivat, mikä on paras tapa toteuttaa muutos. Vanha tapa asiakastyypin mukaan pitää säilyttää.
* [Ylläpito/Auktorisoidut arvot: mahdollisuus lisätä Kuvaus-arvo suomen lisäksi ruotsiksi ja englanniksi #450](https://github.com/KohaSuomi/Koha/issues/450)
  * Päätös: Yhteisössä on avoinna aiheesta parikin bugia. Pyydetään pääkäyttäjiä käymään kommentoimassa tiketteihin, että toiminto olisi tärkeä, jotta saadaan yhteisöä aktivoitumaan.
* [Tilaustietueet eivät yhdisty aina oikein, kun 024a-kentästä tarkistetaan vain ensimmäinen osakenttä #454](https://github.com/KohaSuomi/Koha/issues/454)
  * Päätös: Toteutetaan sekä isbn että ean-kentille. EDItX:ään muutos, joka osaa pilkkoa putkimerkillä erotetut koodit toisistaan ja tekee vertailun sitten kaikkiin koodeihin. Lisäksi pudotettava triggeri, joka pudottaa osakenttien toistumat biblioitems-taulusta. ISBN:n osalta pitää huomioida moniosaisten teosten ISBN sekä osan ISBN. Huolehdittava, ettei yhdisty väärin.  Voi olla, että ISBN:n osalta tätä ei voi toteuttaa
* [Hae asiakkaat -toimintoon esto hakea Haku-painikkeella kaikki asiakastiedot #456](https://github.com/KohaSuomi/Koha/issues/456)
  * Päätös: Tutkitaan, saako estettyä tyhjä haku. Yritetään saada mahdollinen muutos myös yhteisöön.
* [Kaikki verkkokirjastossa tehdyt toimenpiteet eivät lokitu #473](https://github.com/KohaSuomi/Koha/issues/473)
  *  kirjautuminen verkkokirjastoon -lisäys olisi hyvä. Lokituksen kokonaismäärä pitää pitää mielessä.
  *  Päätös: Lisätään lokiin sisäänkirjautuminen Finnaan.
* [Työkaluliitännäiset/Tulosta ilmoituksia - viestin poistomahdollisuus tulostussivulle #505  ](https://github.com/KohaSuomi/Koha/issues/505)
  * Todettiin bugiksi.
* [Asiakkaan Ilmoitukset-välilehteen liittyvä käännösmuutos #513](https://github.com/KohaSuomi/Koha/issues/513)
  * Päätös: Ei muuteta tekstiä.
* [Varauksen kuljetustilan peruuttaminen jättää nidekuljetuksen voimaan #672](https://github.com/KohaSuomi/Koha/issues/672)
  * Päätös: Tarjotaan yhteisölle ratkaisu.

### 4. Muut asiat

#### 4.1 Uutiskirjeen vastuutus

1. kirjeen koonti Vaskin vastuulla, deadline 29.3.2024, julkaisu viikolla 14.<br />
2. kirjeen koonti Lapin vastuulla, deadline 30.5.2024, julkaisu vkolla 23.<br />
3. kirjeen koonti OUTIn vastuulla, deadline 30.9.2024, julkaisu vkolla 41.<br />
4. kirjeen koonti Vaaran vastuulla, deadline 6.12.2024, julkaisu vkolla 50.
   
#### 4.2 JavaScriptien ylläpito ja vastuutus

Mitkä JavaScriptit ovat jatkossa Koha-Suomen ylläpidolla ja vastuulla ja mitkä kimppojen omalle vastuulle? JavaScriptien määrä lisääntyy jatkuvasti ja niiden ylläpito on työlästä.

Jatkossa asiantuntijaryhmän päätöksellä uudet JavaScriptit otetaan Koha-Suomen tukeen mukaan. Kimpat saavat jatkossakin tehdä omia skriptejä, mutta vastaavat niiden toimivuudesta esim. versionvaihdon aikaan itse.

#### 4.3 Kokoelmatyön tiedonhaun koulutuksen ajankohta

To 4.4.2024 klo 9-11.

### 5. Seuraava kokous

Ma 8.4.2024 klo 13.

## Asiantuntijaryhmän muistio 3/24

Aika: 26.2.2024 klo 13<br />
Läsnä: Päivi Knuutinen (Vaara), Susanna Sandell (Vaski), Ari Mäkiranta (Koha-Suomi), Hanna Ikonen (Lumme), Pia Kusmin (Lappi), Noora Valkonen (OUTI), Riikka Mustajärvi (Kirkes), Kati Sillgren (Helle), Anneli Österman (Koha-Suomi)

### 1. Arin ajankohtaiset

LASTU-konversio on edennyt hyvin, jatkassa käyttöönottoprojektit voidaan viedä läpi tiiviimmässä aikataulussa.
Osakassopimus on lähdössä kuntiin kommmentoitavaksi.

### 2. Asiantuntijaryhmän vuosisuunnitelma 2024

Käydään läpi asiantuntijaryhmän oma vuosisuunnitelma.

Vuosisuunnitelma: [Asiantuntijaryhmän_vuosisuunnitelma2024_valmis.docx](https://github.com/KohaSuomi/kohasuomi.github.io/files/14405118/Asiantuntijaryhman_vuosisuunnitelma2024_valmis.docx)



### 3. Uutiskirjeen vastuuvuorot

Syksyn Koha-seminaarissa tuli esille ajatus kaikille Kohaa käyttäville kohdistetusta uutiskirjeestä. Kirjeen koonnista olisi vastuussa aina yksi kimppa kerrallaan. He koostavat muilta tulleet uutiset ja voivat itse nostaa esille esim. hyviä käytänteitä. Julkaistaan Githubin keskustelupalstalla (Discussions eli sama, missä tulee esim. viikkopäivitysten tiedotteet). Matrixissa voi kysellä muilta kimpoilta sisältöjä uutiskirjeeseen.

Sovitaan kimppojen järjestys uutiskirjeen kirjoittamiselle.

1. kirjeen koonti Vaskin vastuulla, deadline 29.3.2024, julkaisu viikolla 14.<br />
2. kirjeen koonti xx vastuulla, deadline 30.5.2024, julkaisu vkolla 23.<br />
3. kirjeen koonti xx vastuulla, deadline 30.9.2024, julkaisu vkolla 41.<br />
4. kirjeen koonti xx vastuulla, deadline 6.12.2024, julkaisu vkolla 50.

Sovitaan loput vastuut seuraavassa kokouksessa.

### 4. Tekstiviestisopimusten irtisanomisajat

Siilinjärvi: 3 kk<br />
Vaara: Link mobility, toistaiseksi voimassaoleva, irtisanomisaika 3 kk.<br />
Kyyti: Tekstiviestipalvelussa (Arena Interactive) on 90 päivän irtisanomisaika.<br />
Lappi: Link Mobilityn irtisanomisaika on 3 kuukautta, toistaiseksi voimassa oleva sopimus. <br />
Vaski: Vaski-kirjastojen televiestisopimus on DNA Oy:n kanssa tehty laaja sopimus, jossa kaupungin kaikki puhepalvelut. Toistaiseksi voimassaoleva. Todennäköisesti erittäin vaikea päästä eroon.<br />
Lumme: Link Mobility, toistaiseksi voimassaoleva, irtisanomisaika 3kk.<br />
OUTI: Link Mobility, toistaiseksi voimassaoleva, irtisanomisaika 3kk.<br />
Helle: ei irtisanomisaikaa.<br />
Kirkes: ei vielä tiedossa.

### 5. Kehitysehdotusten läpikäynti

* [Waitingreserves.pl-sivulle mahdollisuus näyttää asiakkaan tiedoista vain varaustunniste #367](https://github.com/KohaSuomi/Koha/issues/367)
  * Koha-Suomen asiantuntijaryhmä 26.2.2024: Suositus, että Asiakas-sarake piilotetaan sarakeasetuksissa. Pääkäyttäjien tehtävissä. 
* [Hankintaportaalista tilatulle teokselle tieto: muovitettu/muovittamaton #386](https://github.com/KohaSuomi/Koha/issues/386)
  * Koha-Suomen asiantuntijaryhmä 26.2.2024: Tälle ei ole enää tarvetta, joten ei toteuteta. 
* [Saisiko muutoksen popuptekstiin? Kun nide palauttaessa tärppää noudettavaksi varaukseen, lukee popupissa mm. Asiakasta ei ole huomautettu. #6](https://github.com/KohaSuomi/Koha-translations/issues/6)
  * Koha-Suomen asiantuntijaryhmä 26.2.2024: Muutetaan meidän omiin po-tiedostoihin muotoon Ilmoitus: Kirje. Alkuperäisteksti: Patron is not notified
* [Noutamattoman varauksen maksun määräytyminen nidetyypin mukaan #404](https://github.com/KohaSuomi/Koha/issues/404)
  * Siirretään käsittely seuraavaan kokoukseen.
* [Kohan Kori-toiminto #411](https://github.com/KohaSuomi/Koha/issues/411)
  * Koha-Suomen asiantuntijaryhmä 26.2.2024: Aineistotyypin saaminen näkyviin olisi Koha-Suomen oma koodimuutos, jota ei kannata ylläpidollisesti tehdä. Piilotetaan sarake. 
* [Paperiselle palautuskuitille niteiden tiedot myös silloin kun asiakas on valinnut ettei lainahistoriaa tallenneta #441](https://github.com/KohaSuomi/Koha/issues/441)
  * Koha-Suomen asiantuntijaryhmä 26.2.2024: Koha-Suomalaiset ehdottava yhteisön tikettiin ratkaisua, jossa palautuskuitin sisältö kerättäisiin uuteen viestityyppiin ja kun palautuskuitti tulostetaan, haetaan tieto message_queue-taulusta old_issues-taulun sijaan. Eli samantyyppisesti kerättäisiin tiedot lennossa kuitille kuin mitä sähköpostikuitissa. 
* [Nidettä poistaessa huomautus, kun poistettavalla niteellä on voimassa oleva tilaus #445](https://github.com/KohaSuomi/Koha/issues/445)
  * Koha-Suomen asiantuntijaryhmä 26.2.2024: Ei toteuteta, koska käytettäessä Kohan hankinnat-toimintoa, ongelmaa eli roikkumaan jääviä tilauksia ei esiinny kuin virhetilanteissa.
* [Ylläpito/Kirjastot ja ryhmät: mahdollisuus lisätä Nimi-arvo suomen lisäksi ruotsiksi ja englanniksi #448](https://github.com/KohaSuomi/Koha/issues/448)
  * Koha-Suomen asiantuntijaryhmä 26.2.2024: Yhteisössä on avoinna aiheesta parikin bugia. Pyydetään pääkäyttäjiä käymään kommentoimassa tiketteihin, että toiminto olisi tärkeä, jotta saadaan yhteisöä aktivoitumaan. 

### 6. Muut asiat

Kokoelmatyöhön liittyvät haut ja nidehaku -koulutus. [Ennakkokyselyn sisältö](https://forms.gle/LfRce1cWHAwNr3nY7).
* lisätään kyselyyn kimppa-tieto
* aikataulu: koulutus maaliskuun lopulla
* toiveiden esittämiselle aikaa maaliskuun puolivälin seutuville
* asiantuntijaryhmä: kyselettekö omista kimpoisa, löytyisikö Annelille kaveriksi joku henkilö, joka tekee paljon kokoelmatyötä ja olisi valmis tulemaan mukaan kouluttamaan? Deadline vko 10 loppuun. Tieto Annelille.

### 7. Seuraava kokous

Ma 18.3.2024 klo 13.

## Asiantuntijaryhmän muistio 2/24

Aika: 5.2.2024 klo 13<br />
Läsnä: Päivi Knuutinen, Kati Sillgren, Ari Mäkiranta, Hanna Ikonen, Noora Valkonen, Riikka Mustajärvi, Susanna Sandell, Leena Kinnunen, Tuomas Kunttu, Kodo Korkalo, Anneli Österman

### 1. Arin ajankohtaiset

* Hallitus näki viestien keskittämisselvityksen jatkamisen tärkeänä.
  * Minkälaiset irtisanomisajat/ehdot sms-viestien sopimuksilla on - selvitettävä kimpoissa seuraavaan kokoukseen.
* Siilinjärven kanssa pilotoidaan VTJ:n muutosrajapintaa ja koeponnistetaan lupahakemus sen käyttämiseen. Todennäköisesti jokainen kunta joutuu erikseen tekemään lupahakemuksen. Siilinjärven pilotista saadaan toivottavasti malli muiden käytettäväksi.

### 2. Kehitysehdotusten läpikäynti

Päätökset kirjattiin tiketteihin.

* [Laskutusliitännäinen: laskun jäljennökseen laskun numero ja viitenumero #296](https://github.com/KohaSuomi/Koha/issues/296)
* [Asiakkaan Ilmoitukset-välilehden Toimitushuomautus-sarakkeeseen oikea tieto epäonnistumisen syystä #329](https://github.com/KohaSuomi/Koha/issues/329)
* [Koha-Ceepos-maksurajapintaa käytettäessä Hyväksy-painike epäaktiiviseksi #351](https://github.com/KohaSuomi/Koha/issues/351)
* [Saisiko Kohan ilmoittamaan oikein niteen mahdollisen saatavuuden mm. hakutuloksen Rajoita saatavilla oleviin niteisiin -fasettirajauksella #359](https://github.com/KohaSuomi/Koha/issues/359)
* [Waitingreserves.pl-sivulle mahdollisuus näyttää asiakkaan tiedoista vain varaustunniste #367](https://github.com/KohaSuomi/Koha/issues/367)
  * Siirretään tämän tiketin käsittely seuraavaan kokoukseen, jotta voidaan tarkistaa sen tarpeellisuus.
* [Finto-liitännäinen Metatietosanastosta #373](https://github.com/KohaSuomi/Koha/issues/373)
* [Mikropalveluun mahdolliseksi 4-tason tietueen vienti 3-tason Melinda-tietueen päälle #9](https://github.com/KohaSuomi/KohaSuomiServices/issues/9)
* [Hankintaportaalista tilatulle teokselle tieto: muovitettu/muovittamaton #386](https://github.com/KohaSuomi/Koha/issues/386)
  * Siirretään tämän tiketin käsittely seuraavaan kokoukseen, jotta voidaan tarkistaa sen tarpeellisuus.

### 3. Seuraavien kokousten ajankohdat

* ma 26.2.2024 klo 13
* ma 18.3.2024 klo 13
* ma 8.4.2024 klo 13
* ma 29.4.2024 klo 13
* toukokuun kokous sovitaan huhtikuussa

### 4. Muut asiat

* Sähköpostin lähettäjäosoitteen aiheuttamat muutokset kirjeiden tulostuksessa ja SMS-laskutuksessa. [Tiedote muutoksesta](https://github.com/KohaSuomi/Koha/discussions/1052).
  * Googlen (ja jatkossa muiden sähköpostioperaattoreiden) kiristyneistä viestien toimitusvaatimuksista johtuen on tarpeen vaihtaa Kohasta lähtevien viestien lähettäjäosoitteeksi koha-suomi.fi -loppuinen osoite. Muutos aiheuttaa sen, että jatkossa viestit päätyvät viestitauluun koha-suomi.fi lähettäjäosoitteella. Lähettäjäosoitteen varaan on Koha-Suomessa rakennettu sähköposteihin liittymätöntä toiminnallisuutta, joka ei enää muutoksen jälkeen toimi aiotusti.
  * Paperikirjeiden tulostaminen kirjastossa käyttää lähettävän kirjaston sähköpostiosoitetta tulostettavien viestien lajitteluun kirjastoyksiköittäin. Lajittelu ei toimi muutoksen jälkeen. Paperikirjeiden tulostusliitännäiseen on lisätty mahdollisuus lajitella tulostettavat viestit viestin vastaanottajan kotikirjaston mukaan.
  * Tekstiviestilaskujen jakaminen kunnittain operaattoripäässä on toteutettu lähettävän kirjaston sähköpostiosoitteen varaan. Toiminnallisuus on ollut ainoastaan Arenan sähköpostiajurissa ja yhden kimpan käytössä. Jatkossa jakaminen kunnittain "aiheuttajaperusteisesti" ei ole mahdollista ja kustannukset on jyvitettävä muulla perusteella.
  * Edistetään yhteisöön ehdotusta, että viesti-tauluun saataisiin lähettäjäkirjaston branchcode, jolloin sitä voidaan hyödyntää raporteilla.
  * Koosteviestien osalta soveltuvaa kirjastoyksikköä pitää vielä selvittää.
  * Kirjeiden tulostukseen ja SMS-viestien lähetykseen ei tehdä tässä vaiheessa muita muutoksia.


## Asiantuntijaryhmän muistio 1/24

Aika: 15.1.2024 klo 13<br />
Läsnä: Ari Mäkiranta, Anneli Österman, Kodo Korkalo, Leena Kinnunen, Noora Valkonen, Päivi Knuutinen, Tuomas Kunttu, Kati Sillgren, Susanna Sandell, Riikka Mustajärvi, Hanna Ikonen

### 1. Arin ajankohtaiset

Lastun dumppi saatiin joulun alla ja nyt päästään tekemään ensimmäistä koekonversiota.

### 2. Tiekartan päivitys

Tiekartan päivitys, viimeksi päivitys on tehty lokakuussa 2023.

[Tiekartta2023lokakuu.xlsx](https://github.com/KohaSuomi/kohasuomi.github.io/files/13872461/Tiekartta2023lokakuu.xlsx)

Päivitetty tiekartta: [Tiekartta2024tammikuu.xlsx](https://github.com/KohaSuomi/kohasuomi.github.io/files/13939514/Tiekartta2024tammikuu.xlsx)

### 3. Kotipalvelutyöryhmän perustaminen

Edellisessä kokouksessa päätettiin perustaa kotipalvelutyöryhmä, joka miettii, miten Finnaa voisi hyödyntää paremmin kotipalvelutyössä. Hyvät niksit ja käytännöt jakoon kaikkien kesken.

Ryhmään on ilmoittautunut mukaan seuraavat henkilöt:
* Lastu: Susanna Partanen, Lahti
* Vaara: Heli Itkonen, Joensuu ja Tero Paasu, Juuka
* OUTI: Katja Isokääntä, Oulu ja Laila Jakonen, Muhos
* Lumme: Jenni Häkkinen, Pieksämäki
* Lappi: Soile Arkivuo, Rovaniemi
* Kirkes: Rebecca Hopkins, Tuusula
* Helle: David Thiry, Askola (eduaskola.fi)

Kokoonkutsujaksi pyydetään Heli Itkosta. Päivi kysyy. Mukaan pääsee vielä myöhemminkin.

### 4. Versionvaihdon ominaisuuksien läpikäyntiä

[Versionvaihdon 23.xx tiketit](https://github.com/KohaSuomi/Koha-23x/issues)

Kaikki tiketit on nyt käyty läpi ja päätökset kirjattiin tiketteihin siirretään/ei siirretä -tiloina.

### 5. Kehitysehdotusten läpikäyntiä

* [Asiakkaan lainatietoihin uusinta-sarakkeeseen oletuksena rasti myös tänään erääntyville #261](https://github.com/KohaSuomi/Koha/issues/261)
* [Asiakkaan eräpäiväkuittiin lainat eräpäiväjärjestykseen #218](https://github.com/KohaSuomi/Koha/issues/218)
* [Palautusten määrä näkyviin kuitille/sähköpostiin #227](https://github.com/KohaSuomi/Koha/issues/227)
* [Luettelointioikeuksiin erillinen tietueiden poisto-oikeus #221](https://github.com/KohaSuomi/Koha/issues/221)
* [Uusi työkalu: Varausten viimeisen noutopäivän siirto eräajona #249](https://github.com/KohaSuomi/Koha/issues/249)
* [Siirtoraportti-toimintoon tieto, onko siirtoraportin tietue uusi täydellisesti kuvailtu tietue VAI jo olemassa olevan täydellisesti kuvaillun tietueen muutostietue #286](https://github.com/KohaSuomi/Koha/issues/286)

Päätökset kirjattiin tiketteihin.

### 6. Muut asiat

Ei muita asioita.

### 7. Seuraava kokous

5.2.2024 klo 13
