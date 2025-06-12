---
title: 'Asetukset'
permalink: /dokumentaatio/asetukset/
redirect_from:
  - /theme-setup/
toc: true
---

## 0. Yleistä

### 0.1 Ääkköset ja erikoismerkit erilaisissa tunnuksissa/tunnisteissa

Erilaisissa tunnuksissa ei saa käyttää erikoismerkkejä, sisältäen ääkköset ja esim. alaviivat. Käytä siis tunnuksissa vain kirjaimia A-Z ja numeroita 0-9. Myöskään välilyöntejä ei saa laittaa tunnuksiin.

Tunnuksilla tarkoitetaan esim. auktorisoitujen arvojen tunnisteita, käyttäjätunnuksia, kirjastolyhenteitä, nidetyyppejä, asiakasmääreitä, maksutyyppejä jne.

## 1. Kirjastot

Tietokantaan pitää luoda kirjastot. Se onnistuu Ylläpito -> Kirjastot -> Uusi kirjasto

<img src="/assets/files/docs/Asetukset/kirjasto.png" title="Kirjaston lisäyslomake" alt="Kuvakaappaus kirjaston lisäyslomakkeesta" style="width:90.0%" />
<img src="/assets/files/docs/Asetukset/kirjasto2.png" title="Kirjaston lisäyslomake" alt="Kuvakaappaus kirjaston lisäyslomakkeesta jatkuu" style="width:90.0%" />

**Kirjaston tunnus**

Yksilöivä tunnus, jossa ei kannata käyttää erikoismerkkejä tai ääkkösiä. Tunnusta ei pysty muuttamaan jälkikäteen.

Perinteisesti tunnus on muodostettu niin, että se alkaa ns. kuntaosiolla ja päättyy toimipistetunnukseen. Esim. Oulun pääkirjasto OUPK, jossa OU-viittaa Ouluun ja PK pääkirjastoon. Tässä muodostustavassa on omat hyvät puolensa, pystyy esimerkiksi raporteilla hakemaan tietyn kunnan kirjastoja alun perusteella (OU%), mutta huonona puolena on se, että jos kirjastoyksikkö muuttaa nimensä tai siirtyy toisen kunnan alaisuuteen, niin lyhenne ei enää vastaa kunta tai nimitietoa.

Tällä hetkellä Finna muodostaa organisaatio-fasetissa kunta/kirjastotason kirjastolyhenteen perusteella.

**Nimi**

Kirjaston nimi. Tätä pystyy muokkaamaan myöhemminkin.

**Osoiterivit**

Kirjaston lähiosoite.

**Kunta**

Tähän kirjataan postitoimipaikka. Englanniksi sana on City, jota käytetään muussakin yhteydessä kuntaan viittaavana, joten sanaa ei ole voitu suomentaa postitoimipaikaksi.

**Osavaltio**

Ei ole Suomessa tarpeellinen tieto.

**Postinumero**

Kirjaston postinumero.

**Maa**

Voi halutessaan kirjata, mutta ei välttämätön.

**Puh.**

Kirjaston puhelinnumero.

**Faksi**

Tähän voi kirjata faksin numeron tai käyttää luovasti ja kirjata esim. keskitetyn asiakaspalvelun numeron, jos se on eri kuin kirjastopisteen oma numero.

**Sähköposti**

Tähän laitetaan noreply@koha-suomi.fi, koska sähköpostiviestit lähetetään Koha-Suomen/Bittigurun sähköpostipalvelimelta Koha-Suomen nimissä. Erilaiset sähköpostipalvelut ovat tiukentaneet roskaposti- ja turvakäytäntöjään, joten tässä on tärkeää käyttää koha-suomi.fi-päätteistä osoitetta.

**Vastausosoite**

Tähän voi kirjata kirjaston oman sähköpostiosoitteen, jolloin asiakkaan vastaus tulee kirjaston osoitteeseen.

**Palautusosoite**

Tämä jätetään joko tyhjäksi tai laitetaan noreply@koha-suomi.fi. Tässä olevan osoitteen domain (eli @-merkin jälkeinen tieto) pitää olla sama kuin Sähköposti-kentässä olevassa osoitteessa. Jos ne ovat erit, sähköpostipalvelut tulkitsevat herkästi viestin roskapostiksi tai huijaukseksi.

**SMTP-palvelin**

Annetaan olla oletus-vaihtoehto.

**URL**

Tähän voi kirjata kirjaston tai verkkokirjaston osoitteen halutessaan. Ei tule automaattisesti näkyviin mihinkään, mutta voi käyttää hyväksi mm. viestipohjissa.

**Verkkokirjaston tiedot**

Tämä kenttä koskee Kohan omaa verkkokirjastoa, joka ei ole käytössä. Ei tarvitse täyttää.

**IP-osoite**

Tällä voisi rajata pääsyn tähän kirjastoon tiettyyn ip-osoitteeseen tai aliverkkoon. Rajaus ei ole tarpeellinen.

**MARC-yhteisökoodi**

ISIL-tunnus. Ei tarvitse täyttää, koska kuvailu tehdään erilliseen TäTi-tietokantaan.

**Huomautukset**

Lisätietokenttä, ei tarpeellinen.

**Noutopaikka**

Tällä asetuksella valitaan, onko kirjastoyksikkö varausten noutopaikka vai ei. Asetus vaikuttaa sekä virkailijaliittymään että Finna-verkkokirjastoon. Jos kirjaston määrittää ei-noutopaikaksi, niin virkailijat eivät pysty ohittamaan asetusta.

**Julkinen**

Liittyy Kohan omaan verkkokirjastoon, joka ei ole käytössä. Ei tarpeellinen.

**Aukioloajat**

Asetuksella voi määrittää kirjaston aukioloajat, joita hyödynnetään tuntilainojen eräpäiviä määritettäessä. Ei tarpeellinen.

**OPAC JS**

Asetuksella voi tehdä kirjastokohtaisia määrityksiä Kohan verkkokirjastossa, kun asiakas on kirjautuneena sisään. Ei tarpeellinen, koska ei vaikuta Finnaan.

**OPAC CSS**

Asetuksella voi tehdä kirjastokohtaisia määrityksiä Kohan verkkokirjastossa, kun asiakas on kirjautuneena sisään. Ei tarpeellinen, koska ei vaikuta Finnaan.

## 2. Kirjastoryhmät

Kirjastoryhmillä voi kirjastoja voi ryhmitellä eri tarpeiden mukaan esim. hakuryhmiin, kellutusryhmiin, yms. Kirjastoryhmät määritellään Ylläpito -> Kirjastoryhmät

OKM-tilastoja varten pitää perustaa ryhmä, jonka nimekkeessä mainitaan OKM. Esim. TUU_OKM. Tyypillisesti ryhmään lisätään yhden kunnan kirjastoyksiköt.

Uusi ryhmä tehdään Lisää ryhmä -painikkeella. Kun ryhmä on luotu, voi siihen lisätä kirjastoja Lisää kirjasto -nappulalla. Toiminnot-nappulan takaa voi lisätä alaryhmän, muokata ryhmän tietoja tai poistaa ryhmän. Alaryhmän tarvetta kannattaa harkita tarkkaan.

<img src="/assets/files/docs/Asetukset/ryhma.png" title="Kirjastoryhmän lisäyslomake" alt="Pop-up-ikkuna, jossa voi lisätä kirjastoryhmän" style="width:60.0%" />

**Nimeke**

Ryhmän nimi. Tieto on pakollinen, mutta sen voi muuttaa myöhemmin.

**Kuvaus**

Ryhmää voi kuvailla halutessaan, esim. mihin tarkoitukseen se on.

**Ominaisuudet**

- Rajoita muihin ryhmiin kuuluvien pääsyä tämä ryhmän asiakkaisiin
  - Ei tarpeellinen.
- Rajoita niteen muokkausta ryhmän mukaan
  - Asetuksella voi rajoittaa muihin kirjastoryhmiin kuuluvien niteiden muokkaamista käyttäjiltä. Tämän rajoituksen voi ohittaa, jos käyttäjällä on edit_any_item permission-käyttäjäoikeus.
  - Toiminnossa on ongelmana, että nimekkeen perustiedot-näkymässä katoaa kokoelmat-taulukossa niteiden valinta-mahdollisuus, jolloin ei pysty viemään niteitä esim. erämuokkaukseen tai tarratulostukseen. Ei siis suositella käyttöön vielä.
- Käytä verkkokirjaston hakuryhmille -> koskee Kohan omaa verkkokirjastoa, ei tarpeellinen
- Käytä virkailijaliittymän hakuryhmille -> tällä ryhmän saa näkymään tiedonhaussa kirjasto-rajausten osiossa ja hakua voi tällöin rajata ryhmän kirjastoihin.
- Paikallinen varausryhmä -> tätä toimintoa ei ole vielä testattu.
- Paikallinen kellutusryhmä -> tällä voi määrittää ryhmään kuuluvien kirjastojen kaiken aineiston kellumaan ryhmään kuuluvissa kirjastoissa.

## 3. Nidetyypit

Jotta mitään voisi lainata, pitää määritellä nidetyypit, koska laina- ja maksusäännöt perustuvat niihin. Nidetypit kuvaavat teoksen laina-aikaa ja myöhästymismaksuja, jotka perustuvat kimpan/kirjaston käyttösääntöihin, joten jokaisella Koha-kimpalla on hieman erilaiset nidetyypit. Toki yhteneväisyyttäkin on. Yleisiä nidetyyppejä on mm. "28 vrk" tai "28 vrk lastenaineisto".

Laina- ja maksusääntöjä voi tehdä kirjaston, asiakastyypin ja nidetyypin mukaan. Nidetyyppejä luodessa kannattaa siis miettiä, minkälaisia laina-aikoja ja myöhästymismaksuja tarvitsee olla, kuinka monta lainaa saa olla kerralla, tarviiko automaatilla tehdä lajitteluja nidetyypin (joka mäpätään sip-materiaalityypiksi), tarvitseeko pystyä tekemään nidevarauksia.

**Alla esimerkkinä OUTI-kirjastojen nidetyypit:**
Nidetyypin kuvaus | Nidetyypin tunnus | Selite
---|---|---
14 vrk - AV	| 14VRK |AV-aineistolle, joissa laina-aika on 14 vrk
14 vrk - 2 lainaa |	14VRK2LA | Konsolipeleille, joissa laina-aika on sama kuin muulla AV-aineistolla, mutta lainamäärä on rajoitettu kahteen
14 vrk - 40 snt/pv |	14VRK40SNT | Lyhytlainoille, joilla laina-aika on 14 vrk, mutta päivittäinen myöhästymismaksu on korkeampi kuin AV-aineistolla
14 vrk - LN - AV	| 14VRKLN | Lasten AV-aineisto, jolla laina-aika 14 vrk. Lastenaineistosta ei mene päiväkohtaista myöhästymismaksua, joten sitä varten tarvitaan oma nidetyyppi
14 vrk - LN - 2 lainaa |	14VRKLN2LA | Lasten konsolipeleille. Muuten sama kuin yllä oleva vastaava, mutta ei mene päiväkohtaista myöhästymismaksua
28 vrk | 28VRK | Yleisin nidetyyppi, jolle on määritetty laina-ajaksi 28 vrk ja myöhästymismaksuksi 15 snt/pv. Nidevaraukset eivät sallittuja verkkokirjastossa.
28 vrk - AV |	28VRKAV  | AV-aineistolle, joissa laina-aika on 28 vrk. Nämä pitää saada palautusautomaatilla lajiteltua muusta 28 vrk-materiaalista erilleen, minkä vuoksi oma nidetyyppi
28 vrk - Lehti	|  28VRKLEHTI | Aikuisten lehdille. Näille pitää pystyä tekemään nidevarauksia verkkokirjastossa, minkä vuoksi oma nidetyyppi
28 vrk - LN	| 28VRKLN | Lasten aineisto yleislaina-aika. Näistä ei saa mennä päiväkohtaista myöhästymismaksua, minkä vuoksi erillinen nidetyyppi 28 vrk:sta
28 vrk - LN - AV	| 28VRKLNAV | Lasten aineiston 28 vrk:n AV-aineiston nidetyyppi, joista ei saa mennä päiväkohtaista myöhästymismaksua
28 vrk - LN - Lehti	| 28VRKLNLEH | Lasten lehtiaineistolle oma nidetyyppi, koska ei saa mennä päiväkohtaista myöhästymismaksua ja pitää pystyä tekemään nidevarauksia verkkokirjastossa
7 vrk - 1 laina	| 7VRK1LA | Pikalainat/Sarjakortit, joilla laina-aika 7 vrk, lainamäärä 1 kpl ja myöhästymismaksu 40 snt/pv
Ei lainata	| EILAINATA | Ei lainattavan materiaalin nidetyyppi, joille määritetty lainamääräksi 0
Oppimateriaalipalvelut | OPPIMATER | Oulun koulukirjaston Oppimateriaalipalvelujen tarvitsema nidetyyppi. Muuten koulukirjaston niteet ovat lasten aineiston nidetyypeillä

### 3.1 Uusi nidetyyppi

<img src="/assets/files/docs/Asetukset/nidetyyppi1.png" title="Kirjaston lisäyslomake" alt="Kuvakaappaus kirjaston lisäyslomakkeesta jatkuu" style="width:90.0%" />
<img src="/assets/files/docs/Asetukset/nidetyyppi2.png" title="Kirjaston lisäyslomake" alt="Kuvakaappaus kirjaston lisäyslomakkeesta jatkuu" style="width:90.0%" />
<img src="/assets/files/docs/Asetukset/nidetyyppi3.png" title="Kirjaston lisäyslomake" alt="Kuvakaappaus kirjaston lisäyslomakkeesta jatkuu" style="width:90.0%" />

* **Nidetyyppi**: Nidetyypin tunniste, esim. 28VRK.
* **Emonidetyyppi**: Emonidetyypin määrittäminen ottaa käyttöön myös tälle nidetyypille emonidetyypille määritetyt laina- ja maksusäännöt.
* **Kuvaus**: Selkokielinen selite nidetyypille.
* **Hakutyyppi**: Asetuksella voi ryhmitellä nidetyyppejä. Vaihtoehdot on määritelty auktorisoidun arvon mukaan ITEMTYPECAT.
* **Valitse ikoni**: Nidetyypille voi halutessaan valita ikonin/kuvakkeen.
* **Piilota verkkokirjastossa**: Jos valittuna, tämän tyypin niteet suodatetaan pois Kohan verkkokirjaston tarkasta hausta. Ei koske Finnaa.
* **Ei lainattavissa**: Valinta estää tämän nidetyypin lainaamisen. Jos jätät tämän valinnan tyhjäksi, tätä nidetyyppiä voi lainata, ellei niteelle ole valittuna "ei lainata"-tila.
* **Automaattinen palautus**: Jos valittuna, niteet palautetaan automaattisesti eräpäivänä. Ominaisuus vaatii misc/cronjobs/automatic_checkin.pl cronjobin. Ei ole testattu.
* **Lainausmaksu**: Tähän voisi määrittää lainalle/uusinnalle maksu. Suomessa yleisten kirjastojen lainat ovat maksuttomia.
* **Päivävuokra**: Tämä maksu veloitetaan lainattaessa/uusittaessa jokaiselta päivältä lainauksen/uusinnan päivän ja eräpäivän välillä, jos laina-aika määritellään päivissä. Suomessa yleisten kirjastojen lainat ovat maksuttomia.
* **Käytä kalenteria päiväkohtaisille vuokrille**: Jos valitset tämän, päivittäinen veloitus lasketaan kalenterista kiinniolopäivät poislukien. Jos ei valintaa, maksu lasketaan suoraan päivien määrän mukaan eräpäivästä lähtien.
* **Tuntikohtainen lainausmaksu**: Tämä maksu veloitetaan lainattaessa/uusittaessa jokaiselta tunnilta lainauksen/uusinnan päivän ja eräpäivän välillä, jos laina-aika määritellään tunneissa.
* **Käytä kalenteria tuntikohtaisille lainoille**: Jos valitset tämän, tuntiveloitus lasketaan kalenterista kiinniolopäivät poislukien. Jos ei valintaa, maksu lasketaan suoraan tuntien määrän mukaan erääntymisestä lähtien.
* **Oletuskorvaushinta**: Nidetyypille voi määrittää oletuskorvaushinnan, jota käytetään, jos nide on kadonnut, eikä sillä ole nidekohtaista korvaushintaa määritettynä.
* **Käsittelykulut (kun kadonnut)**: Tämä maksu lisätään niteen korvaushintaan, jos asiakkaan laina merkitään kadonneeksi.
* **Palautusviesti**: Näkyy, kun tätä nidetyyppiä oleva nide palautetaan.
* **Palautusviestin tyyppi**: Tällä määritetään, onko yllä mainittu palautusviesti tyypiltään viesti vai huomautus. Ne ovat muuten samanlaisia, mutta viesti näytetään palautuksessa sinisellä pohjalla ja huomautus keltaisella pohjalla.
* **SIP-mediatyyppi**: Asetuksella määritetään, mikä "aineistotyyppi" välitetään SIP2-sanomissa. Kohan omat nidetyypit eivät välity sanomissa. SIP-mediatyypeillä voi tehdä esim. lajittelusääntöjä palautusautomaateilla tai määrittää aktivoidaanko tai deaktivoidaanko hälytyksiä.
  * Samoihin lajittelulaareihin haluttavat nidetyypit kannattaa määrittää samalle SIP-mediatyypille.
* **Kirjastorajoitus**: Nidetyypin voi määrittää kaikkien, yhden tai useamman kirjaston käyttöön. Jos nidetyyppi on rajoitettu esim. yhdelle kirjastolle, näkyy se vain kyseiseen kirjastoon kirjautuneille käyttäjille.
* **Yhteenveto**: Syötä kuvaus, jota käytetään oletuskuvauksen sijaan hakutuloksissa. Tätä käytetään vain ei-xslt-näytöillä.

*Tallenna muutokset* -napista saat tallennettua tekemäsi muutokset.

## 4. Auktorisoidut arvot

Auktorisoituja arvoja voi käyttää Kohan eri osioissa esim. alasvetovalikoissa. Ne ovat siis valmiita "listoja", joita halutaan käytettävän vapaan tekstin sijaan. Kaikki arvot ovat pääsääntöisesti kaikille kirjastoille/asiakastyypeille käytettävissä, mutta ne voidaan rajoittaa myös käytettäväksi tietyillä kirjastoilla tai asiakastyyypeillä. TäTi-tietokannassa on paljon RDA-kuvailuun liittyviä luokkia, joilla helpotetaan kuvailijoiden töitä. Näitä ei ole pääsääntöisesti paikalliskannoissa. Alla listattuna tärkeimmät paikalliskannoissa olevat auktorisoidut arvot:

**agelevel**

agelevel-luokalla ja sen arvoilla luodaan tiedonhakuun mahdollisuus rajata hakua elokuvan ikärajan mukaan. Luokan nimi on sama kuin ikäraja-indeksin nimi. Tähän on lisätty arvot
K3, K7, K12, K16, K18 ja S. Hakuehdon saa näkyville tarkan haun lomakkeelle AdvancedSearchTypes-järjestelmäasetuksella, johon lisätään arvo _agelevel_.

**AUTOMTYPE**

AUTOMTYPE-luokka on luotu asiakasmäärettä AUTOTYPE-varten, jolla taas voi määrittää SIP2-tunnuksiin, minkä tyyppinen automaatti on kysessä. Eli onko se lainausautomaatti, palautusautomaatti, lainaava ja palauttava vai ovikone. Tämä luokka on rajoitettu käytettäväksi vain asiakastyypille AUTOM/AUTOMAATTI

**bib-level**

bib-level-luokka on luotu sitä varten, että tiedonhakuun Tarkan haun lomakkeelle saadaan mahdollisuus rajata hakua emokohteen ja osakohteen mukaan. Hakuehdon saa näkyville tarkan haun lomakkeelle AdvancedSearchTypes-järjestelmäasetuksella, johon lisätään arvo _bib-level_.

**BOR_NOTES**

BOR_NOTES-luokan arvoilla voi luoda valmiita viestipohjia, jotka näkyvät, kun asiakkaalle lisää viestin.

**CCODE**

CCODE eli kokoelmakoodi. Tämän arvon voi määrittää niteelle. Näistä ei ole tehty Koha-Suomen laajuista yhteistä päätöstä, mutta monestikin kokoelmat ovat esim. Jännitys, Fantasia, Romantiikka yms.

**DAMAGED**

DAMAGED-luokan arvot näkyvät niteen ylläpidossa Vahingoittunut/Varattavuus-rivin valikossa. Tätä arvoa käytetään hieman luovasti estämään niteiden jääminen kiinni varauksiin. Arvoina voi olla esim. "Saatavana, ei varattavissa" ja "Saatavana oppilaille, ei varattavissa". Vaikka jonkin nidetyypin määrittäisi "ei varattavaksi", niin Koha noudattaa sitä vain varatessa, ei silloin kun varaukset jäävät palautettaessa kiinni. Eli jos tietueella on osa niteistä varattavia ja osa ei-varattavia, pystyy tietueeseen tekemään varauksia ja ilman damaged-tilaa niteet myös jäävät kiinni varauksiin. Lisäksi pitää laittaa järjestelmäasetukseen *AllowHoldsOnDamagedItems* vaihtoehto "Älä salli".

**LOC**

LOC-luokkaan määritetään niteiden hyllypaikat (eli osastot). Hyllypaikoista ei ole Koha-Suomen kimppojen yhteistä päätöstä, mutta yleisiä ovat mm. Aikuiset, Lapset (tai Lapset ja nuoret), Musiikki, Lehdet, jne. Hyllypaikat ovat kaikille kirjastoyksiköille yhteiset, mutta kuten muutkin auktorisoidut arvot, ne voidaan tarvittaessa rajoittaa käytettäväksi vain tietyille kirjastoille.

**LOST**

LOST-luokassa on niteiden kadonnut-arvot.

**MTYPE**

MTYPE-luokassa on tietueiden aineistotyypit, jotka vastaavat Finnan materiaalityyppejä. Arvo on kytketty MARC-kenttä 942c.

Koha-Suomen pääkäyttäjäryhmän 23.2.2021 ja 2.3.2021 päättämät aineistotyyppien tunnisteet
(1.11.2021 lisätty VIDEOPELI ja LAUTAPELI korvaamaan KONSOLIP):

|Finna-materiaalityyppi|MTYPE|Selite|
|---|---|---|
|Article|ARTIKKELI|Artikkeli|
|Atlas|ATLAS|Atlas|
|BluRay|BLURAY|Blu-ray|
|BookSection|KIRJANOSA|Kirjan osa|
|Book|KIRJA|Kirja|
|Braille|BRAILLE|Braille|
|CDROM|CDROM|CD-ROM|
|CD|CD|CD|
|ChipCartridge|PIIRIKOT|Piirikotelo|
|Drawing|PIIRROS|Piirros|
|DVD|DVD|DVD|
|eBook|EKIRJA|eKirja|
|Electronic|ELEKTRON|Elektroninen|
|Journal|ALEHTI|Aikakauslehti|
|Kit|MONIVIES|Moniviestin|
|Manuscript|KASIKIRJ|Käsikirjoitus|
|Map|KARTTA|Kartta|
|Microfilm|MIKROF|Mikrofilmi|
|MusicalScore|NUOTTI|Nuotti|
|MusicRecording|MUSATAL|Musiikkitallenne|
|Newspaper|SLEHTI|Sanomalehti|
|NonmusicalCassette|PUHEKAS|Kasetti, puhe|
|NonmusicalCD|PUHECD|CD, puhe|
|NonmusicalDisc|PUHELEVY|Äänilevy, puhe|
|NonmusicalRecording|PUHETAL|Äänitallenne, puhe|
|OnlineVideo|EVIDEO|eVideo|
|Painting|MAALAUS|Maalaus|
|Photo|VALOKUVA|Valokuva|
|PhysicalObject|ESINE|Esine|
|Print|MUUPAINATE|Muu painate|
|Serial|KAUSIJULK|Kausijulkaisu|
|Slide|DIA|Dia|
|SoundCassette|AANIKAS|Äänikasetti|
|SoundDisc|AANILEVY|Äänilevy|
|SoundRecording|AANITALL|Äänitallenne|
|TechnicalDrawing|TYOPIIR|Työpiirustus|
|VideoCassette|VIDEOKAS|Videokasetti|
|VideoDisc|VIDEOLEVY|Videolevy|
|Video|VIDEO|Video|
|TapeCartridge|NAUHAKAS|Nauhakasetti|
|DiscCartridge|OPTINEN|Optinen levykasetti|
|TapeCasette|DATKAS|DAT-kasetti|
|TapeReel|MAGNEETTI|Magneettinauha|
|FloppyDisc|LEVYKE|Levyke|
|Filmstrip|RAINA|Raina|
|Transparency|KALVO|Kalvo|
|Collage|KOLLAASI|Kollaasi|
|Photonegative|NEGATIIVI|Valokuvanegatiivi|
|Flashcard|KORTTI|Sana- tai kuvakortti|
|Chart|KAAVIO|Kaavio|
|MotionPicture|ELOKUVA|Elokuva|
|SensorImage|KAUKOKART|Kaukokartoituskuva|
|VideoCartridge|VIDEOSILM|Videosilmukkakasetti|
|VideoReel|VIDEOKELA|Videokela|
|Collection|KOKOELMA|Kokoelma|
|SubUnit|SARJANOSA|Sarjan osa|
|ContinuouslyUpdatedRecource|PAIVITTYVA|Päivittyvä julkaisu|
|Other|MUU|Muu aineisto|
|VideoGame|VIDEOPELI|Videopeli|
|BoardGame|LAUTAPELI|Lautapeli|


**NOT_LOAN**

NOT_LOAN-luokassa on niteen Ei lainata -arvot. Arvot voivat olla miinus- tai plusmerkkisiä. *SkipHoldTrapOnNotForLoanValue*-järjestelmäasetuksella määritetään, mitkä ei-lainata-arvot estää varausten kiinni jäämisen. *TrapHoldsOnOrder*-järjestelmäasetuksessa määritetään, ovatko miinusmerkkiset arvot varattavissa.

Arvoista -1 (Tilattu) ja -2 (Saapunut) ovat Kohan "sisäisiä" arvoja ja ne ovat yleensä kaikilla samat.

Laskutusta varten on yleisesti kimpoissa käytetty arvoa 6 (Laskutettu).

**PAYMENT_TYPE**

PAYMENT_TYPE-luokan arvot näytetään maksua maksettaessa Maksutyyppi-valikossa. Tämä on oleellinen arvo vain Ceepos-kassaliittymää käyttäville kimpoille, jolloin tähän luokkaan lisätään käytettävien kassojen tunnukset. [Ceepos-kassaliittymän käyttöönotto-ohje](https://github.com/KohaSuomi/koha-plugin-ceepos-integration/wiki/Ceepos%E2%80%90kassaliittym%C3%A4n-k%C3%A4ytt%C3%B6%C3%B6notto#maksutyyppi-jokaiselle-k%C3%A4ytett%C3%A4v%C3%A4lle-kassalle).

**REPORT_GROUP ja REPORT_SUBGROUP**

REPORT_GROUP ja REPORT_SUBGROUP -luokissa määritetään, minkä nimisiä välilehtiä näkyy Tallennetuissa raporteissa. Näitä voi luoda myös suoraan raportti-osion kautta. Jos luot ryhmän raportti-osiossa, muista **ettei tunnuksessa saa olla ääkkösiä tai muita erikoismerkkejä, koska ne rikkovat välilehtien toiminnan**.

**SIP_MEDIA_TYPE**

SIP_MEDIA_TYPE-luokassa on lueteltuna SIP-mediatyypit, jotka välittyvät SIP2-viestissä automaatille niteen "aineistolajina". Näiden perusteella voidaan tehdä esim. lajitteluja automaatin ohjelmistossa. Standardi on vanha, joten vaihtoehtoja ei ole kovin kummoisia. Nämä on kytkettävissä Kohan nidetyyppeihin niiden ylläpidossa.

**SUBLOC**

SUBLOC-luokka eli niteen hyllytarkenne. Tämä on alunperin Koha-Suomen oma lisäys, mutta se on löytyy nykyään myös yhteisön tietokantarakenteesta. Hyllytarkenteista ei ole Koha-Suomen kimppojen laajuista päätöstä ja niitä onkin käytetty hyvin eri tavoin. Niissä voi olla saman tyyppisiä arvoja kuin kokoelmissa tai esimerkiksi Koulukirjastojen kirjastoyksiköiden nimiä.

Hyllytarkenne näytetään virkailijaliittymässä tietueen perustiedot-näytöllä Kotikirjasto-sarakkeessa hyllypaikan perässä sulkeissa.

<img src="/assets/files/docs/Asetukset/hyllytarkenne.png" title="Kirjaston lisäyslomake" alt="Kuvakaappaus, jossa hyllytarkenne näkyy hyllypaikan yhteydessä sulkeissa" style="width:90.0%" />

**TOIMITTAJAT**

TOIMITTAJAT-luokka on aisapari AUTOMTYPE-luokalle eli tällä voi määrittää SIP2-tunnukseen, mikä toimittajan automaatista on kyse. Tämä arvo on rajoitettu vain asiakastyypille AUTOM/AUTOMAATTI.

## 5. Asiakastyypit

Koha-asiantuntijaryhmä on päättänyt yhteiset asiakastyypit 27.3.2017.

|Lyhenne/Tunnus|Selite|Asiakastyypin tyyppi|Huomautus|
|-----------|-------------|-----------|
|HENKILO|Henkilöasiakas|Aikuiset||
|LAPSI|Lapsiasiakas|Huollettava||
|YHTEISO|Yhteisöasiakas|Yhteisö||
|VIRKAILIJA|Kirjaston työntekijä| Henkilökunta| Tätä käytetään vain käyttäjätunnuksena, ei käytetä kirjastokorttina. Henkilökunnalla pitää olla erikseen kirjastokortti-tunnus. Tämän tunnuksen tyyppi pitää olla _Henkilökunta_, jotta virkailijatunnukset saadaan siirrettyä redusoinnissa testikantaan |
|KAUKOLAINA|Kaukolainakirjasto|Yhteisö||
|KOTIPALVEL|Kotipalveluasiakas|Aikuiset||
|EITILASTO|Ei tilastoitavat lainat|Ammattilainen|Käytetään ns. työlainojen ja -varausten tekemiseen.|
|MUUHUOL|Huollettava, muu kuin lapsi|Huollettava|Aikuinen, jolle pitää merkitä huoltaja.|
|AUTOM|Z Automaatti Z|Tilastoyksikkö|SIP2-automaattien/ovikoneiden/laitteiden käyttäjätunnukset. Selitteessä on Z-kirjaimet, jotta se asettuu valikossa loppuun.|
|API| Z API Z|Tilastoyksikkö|Erilaisten rajapintoja käyttävien järjestelmien/toimintojen käyttäjätunnukset. Selitteessä on Z-kirjaimet, jotta se asettuu valikossa loppuun. Päätetty ottaa käyttöön [Koha-Suomen asiantuntijaryhmän kokouksessa 4/21](https://tiketti.koha-suomi.fi/projects/mls/wiki/Asiantuntijat_-_Vuosi_2021#Muistio-421).|
|LAOMATOIMI|Lapsi, omatoimi sallittu|Huollettava|Tarvitaan lapsiasiakkaille, joilla on huoltajan antama lupa päästä omatoimeen. Lapsi-asiakkaiden pääsy estetään. Päätetty ottaa käyttöön [Koha-Suomen asiantuntijaryhmän kokouksessa 5/21](https://tiketti.koha-suomi.fi/projects/mls/wiki/Asiantuntijat_-_Vuosi_2021#5-Asiakastyyppi-omatoimiestoille) |
|HEOMATOIMI| Henkilöasiakas, omatoimi sallittu |Aikuinen| Tarvitaan henkilöasiakkaille, jotka ovat Vaarassa hyväksyneet omatoimen käyttösäännöt. Henkilö-asiakkaiden pääsy estetään. Päätetty ottaa mukaan yhteisiin asiakastyyppeihin [Koha-Suomen asiantuntijaryhmän kokouksessa 12/24](https://koha-suomi.fi/asiantuntijaryhma2024#4-vaarassa-k%C3%A4ytt%C3%B6%C3%B6n-uudet-heomatoimi-ja-yhomatoimi--asiakastyypit)|
|YHOMATOIMI| Yhteisöasiakas, omatoimi sallittu|Yhteisö| Tarvitaan yhteisöasiakkaille, jotka ovat Vaarassa hyväksyneet omatoimen käyttösäännöt. Yhteisö-asiakkaiden pääsy estetään. Päätetty ottaa mukaan yhteisiin asiakastyyppeihin [Koha-Suomen asiantuntijaryhmän kokouksessa 12/24](https://koha-suomi.fi/asiantuntijaryhma2024#4-vaarassa-k%C3%A4ytt%C3%B6%C3%B6n-uudet-heomatoimi-ja-yhomatoimi--asiakastyypit)|

### 5.1 Asiakastyyppien määritykset

<img src="/assets/files/docs/Asetukset/asiakastyypit.png" title="Asiakastyypin tiedot" alt="Asiakastyypin muokattavat kentät" style="width=100.0%" />


**Tyyppikoodi**

Tyyppikoodiin tulee yllä luetellut tunnukset. Pakollinen tieto.

**Kuvaus**

Selkokielinen kuvaus asiakastyypistä. Kuvausta voi muokata halutessaan muuksikin kuin yllä olevassa taulukossa.

**Voimassaoloaika**

Henkilöasikkaiden (aikuiset ja lapset) oletusvoimassaoloajaksi on sovittu Koha-Suomen asiantuntijaryhmän 9.5.2022 kokouksessa kymmenen vuotta (120 kk).

Muilla asiakastyypeillä voi olla tarvittaessa kimpan päätöksen mukaan lyhyempi voimassaoloaika.

**Vaadittu ikä ja Ikäraja**

Näillä asetuksilla määritetään asiakkaan minimi- ja maksimi-ikä. Lapsiasiakkaat muutetaan aikuiseksi tämän asetuksen perusteella, eli kun asiakas saavuttaa maksimi-iän, vaihdetaan hänen asiakastyyppi aikuisasiakkaaksi (henkilöasiakas).

HUOM! Tähän joutuu laittamaan maksimi-iäksi yhden vuoden enemmän kuin olisi tarpeen, koska ajastettu ajo, joka muuttaa lapsiasiakkaat aikuisasiakkaiksi tulkitsee luvun eri tavalla kuin Kohan käyttöliittymä. Eli jos asiakas pitää muuttaa aikuisasiakkaaksi hänen täytettyä 15 vuotta, pitää Ikärajaksi laittaa 15. Tästä seuraa se, että alla oleva väite siitä, että lomake tarkistaa, että asiakkaan ikä on asiakastyypille sallitussa ikähaarukassa ei toimi oikein.

Kun asiakasta lisätään, tarkistaa lomake, että asiakkaan ikä on asiakastyypille sallitussa ikähaarukassa.

**Rekisteröintimaksu**

Ei tarpeellinen Suomessa, merkitse/anna olla 0.00.

**Myöhästymisilmoitus**

Tällä asetuksella määritetään, lähteekö asiakastyypin asiakkaille OVERDUE_NOTICE-tyyppisiä viestejä eli palautuskehotuksia/myöhästymisilmoituksia. Esim. työkorteille (EITILASTO) ei kannata määrittää lähtemään myöhästymisilmoituksia.

**Näytetäänkö kadonneet niteet virkailijaliittymässä**

Valitse "Näytetään".

**Varausmaksu**

Ei sovellu suomalaiseen kirjastomaailmaan, koska varausmaksua ei saa lain mukaan periä. Laita/anna olla 0.00.

**Luokkatyyppi**

Luokkatyyppi määrittelee, minkälainen "lomake" näytetään asiakasta lisätessä ja muokatessa. Esim. lapsiasiakas-tyypeille pitää määrittää "Huollettava", ja aikuisasiakkaille Aikuiset. Yhteisöasiakkailla taas näkyy vain yksi nimikenttä. 

Huom! Tilastoyksikkö-valinta aiheuttaa sen, että lainatessa lainat eivät mene asiakkaalle lainaan.

**Voi olla taattava**

Asetuksella määritetään, onko asiakastyyppi taattava vai ei. Jos tähän valitsee _Kyllä_, näytetään asiakkaan lisäys/muokkauslomakkeella takaajatieto-osio. Jos taas valitaan _Ei_, asiakastiedoissa ei näytetä takaajatieto-osiota.

Kyllä kannattaa laittaa lapsiasiakas ja Huollettava, muu kuin lapsi -asiakastyypeille.

**Kirjastorajoitukset**

Asiakastyypin voi tarvittaessa rajoittaa myös tietyn kirjaston käyttöön, mutta pääsääntöisesti tämä ei ole tarpeen.

**Salasanan palautus verkkokirjastossa**

Jos tämä halutaan sallia, valitse järjestelmäasetuksessa OpacResetPassword, että käyttäjät saavat palauttaa unohtuneen salasanansa verkkokirjastossa ja valitse tähän kohtaan, että Noudata järjestelmäasetusta OpacResetPassword. Monella kimpalla toiminto on käytössä.

**Salasanan vaihto verkkokirjastossa**

Valitse järjestelmäasetuksessa OpacPasswordChange, että sallitaan salasanan vaihto verkkokirjastossa ja valitse tähän kohtaan "Noudata järjestelmäasetusta OpacPasswordChange".

**Salasanan minimipituus**

Asiakkaiden asiakastyypeille tähän laitetaan numero 4, koska omatoimikirjautumisessa ei voi käyttää kuin neljänumeroista pin-koodia.

VIRKAILIJA/AUTOM/API-asiakastyypeille määritetään joko 15 (Kyberturvallisuuskeskuksen suositus) tai jätetään tyhjäksi, jolloin noudatetaan järjestelmäasetusta  minPasswordLength. Muista käydä määrittämässä kyseiseen järjestelmäasetukseen silloin tuo 15.

Huom! Käytännössä Koha ei ehdota alle kahdeksan merkkisiä salasanoja, vaikka tähän asetukseen tai minPasswordLength-järjestelmäasetukseen laittaisikin 4. Meillä on erikseen JS-liitännäinen, jolla huolehditaan, että asiakkaille generoituu nelinumeroisia PIN-koodeja. Liitännäisen määrittelyssä määritetään, mille asiakastyypeille generoidaan nelinumeroinen PIN-koodi. [IntranetUserJS: Generate PIN codes -liitännäisen ohjeistus](https://github.com/KohaSuomi/koha-plugin-intranetjs-generate-pin/blob/master/README.md).

**Vaadi vahva salasana**

Asiakas-asiakastyypeille valitaan vaihtoehto "Ei". Asiakkailta ei voi vaatia vahvaa salasanaa, koska omatoimikirjautumisessa voi käyttää vain nelinumeroista pin-koodia.

VIRKAILIJA/AUTOM/API-asiakastyypeille määritetään "Kyllä". Tietoturvasyistä käyttäjätunnuksilta vaaditaan vahva salasana.

**Estä vanhentuneet asiakkaat**

Valitse vaihtoehto "Järjestelmäasetus BlockExpiredPatronOpacActions määrittää".

**Tarkasta edelliset lainat**

Tämä vaihtoehto on näkyvillä vain, jos  CheckPrevCheckout-järjestelmäasetuksessa on valittuna jokin muu kuin _Älä tarkista_. Kotipalvelu-asiakastyypille voi valita "Kyllä ja yritä ohittaa järjestelmäasetukset". Muille asiakastyypeille kannattaa valita "Ei ja yritä ohittaa järjestelmäasetukset.

Käytännössä järjestelmä tarkistaa lainatessa ja varatessa, onko saman tietueen nide ollut asiakkaalla jo lainassa. Jos asetus on päällä, pitää virkailijan kuitata huomautus. Lainaaminen ei onnistu automaateilla, jos teos on ollut jo asiakkaalla lainassa.

**Oletusarvo yksityisyydelle**

Tämä tarkoittaa lainahistorian säilytysaikaa. 

- Oletus tarkoittaa kirjaston määrittämän ajan. Koha-Suomen asiantuntijaryhmä on ehdottanut oletussäilytysajaksi kolme vuotta.
- Ei koskaan tarkoittaa, että lainahistoriaa ei tallenneta ja laina anonymisoidaan heti, kun nide palautetaan.
- Aina tarkoittaa, että lainahistoria säilyy aina, eikä sitä poisteta säännöllisissä poisto/anonymisointiajoissa.

**Jätä pois paikallisten varausten jonosta**

Valitse ei.

**Viestien oletusasetukset tälle asiakastyypille**

Asiakastyypille voi määritellä oletusasetukset viesteille. Nämä valinnat tulevat siis automaattisesti, kun luodaan kyseisen asiakastyypin asiakasta.

Koha-Suomen suositus on, että oletusarvoja ei lisättäisi, jotta viestiasetusten tarkistukseen liittyvät JavaScript-liitännäiset toimisivat oikein.

Ainoa poikkeus on Ennakkoilmoitus-kohta, johon kannattaa laittaa muu arvo kuin 0. Jos asiakkaalle tallentuu tähän arvo 0, hänelle ei käytännössä lähde ennakkoilmoitusta.

## 6. Laina- ja maksusäännöt

Laina- ja maksusäännöissä määritetään mm. laina-aika, sallittujen lainojen määrä, uusintojen määrä, varausten määrä, myöhästymismaksujen suuruus ja katto. Sääntöjä voi tehdä kirjaston, asiakastyypin ja nidetyypin mukaan. 

**Huomioitavaa:**

- Jos kirjastolle tekee yhdenkin oman säännön, oletussäännöt eivät enää koske kyseistä kirjastoa. Kirjastokohtaisiin sääntöihin pitää toistaa kaikki ne säännöt, jotka haluaa oletussäännöistä koskevan myös kirjastokohtaisesti.
- Vaikka olisi asettettu maksimi laina- ja varausmäärät asiakastyyppille, niin rajoitus koskee vain kirjastokohtaisesti. Eli jos lainojen maksimiksi on määritetty 50, saa asiakas lainata 50 kirjastosta A + 50 kirjastosta B + 50 kirjastosta C, jne.
- Jokainen lainasääntö sallii niin monta lainaa, kuin sille riville on määritetty. Käytännössä jos asiakas lainaa useampaan lainasääntöön kuuluvia niteitä, hän pystyy lainaamaan enemmän kuin yhden sääntörivin maksimissa määritetään.

Säännöt tarkistetaan tässä järjestyksessä, ja sääntönä käytetään ensimmäistä kirjaston, asiakastyypin ja nidetyypin mukaan osuvaa:

- sama kirjasto, sama asiakastyyppi, sama nidetyyppi
- sama kirjasto, sama asiakastyyppi, kaikki nidetyypit
- sama kirjasto, kaikki asiakastyypit, sama nidetyyppi
- sama kirjasto, kaikki asiakastyypit, kaikki nidetyypit
- oletus (kaikki kirjastot), sama asiakastyyppi, sama nidetyyppi
- oletus (kaikki kirjastot), sama asiakastyyppi, kaikki nidetyypit
- oletus (kaikki kirjastot), kaikki asiakastyypit, sama nidetyyppi
- oletus (kaikki kirjastot), kaikki asiakastyypit, kaikki nidetyypit

Kun nidetyypillä on emonidetyyppi, sääntö näytetään "Emo -> alatyyppi" ja sallittujen lainojen määrä rajoitetaan joko emon maksimiin (laskien mukaan "sisartyypit") tai nidetyypin erityissääntöön, siihen kummassa on pienempi luku.

Tarkentaaksesi sääntöä luo uusi sääntö, jolla on sama asiakastyyppi ja nidetyyppi.

### 6.1 Laina- ja maksusääntötaulukko

<img src="/assets/files/docs/Asetukset/lainasaannot.png" title="Laina- ja maksusäännöt" alt="Kuvakaappaus laina- ja maksusäännöt -sivulta. Näkymässä neljä sääntöriviä, joita voi muokata Muokkaa-napilla" style="width=100.0%" />

**Asiakastyyppi**

Valitse, mitä asiakastyyppiä sääntö koskee. Jos se koskee kaikkia, silloin ei valita asiakastyyppiä. Huomioitavaa on, että jos asiakastyypille tekee yhdenkin oman säännön, tällöin kaikkia asiakastyyppejä koskevat sääntö/säännöt eivät koske enää kyseistä asiakastyyppiä.

**Nidetyyppi**

Niidetyypin mukaisia sääntöjä voi tehdä joko koskemaan kaikkia asiakastyyppejä tai tiettyjä asiakastyyppejä.

**Huomautus**

Tähän voi halutessaan laittaa jotain sääntöä kuvaavaa tietoa.

**Sallittu lainamäärä**

Jokainen lainasääntö sallii niin monta lainaa, kuin sille riville on määritetty. Käytännössä jos asiakas lainaa useampaan lainasääntöön kuuluvia niteitä, hän pystyy lainaamaan enemmän kuin yhden sääntörivin maksimissa määritetään.

**On-site lainoja sallittu**

On-site -lainat ovat tilastolainoja. Tätä voi käyttää esim. silloin, kun haluaa tilastoida mitä kirjoja on vinkattu. Nämä lainat eivät mene asiakkaan lainoihin.

**Laina-aika**

Määritä tähän laina-aika. Yksikkö eli onko laina-aika päivä/tunti-perusteinen määritetään omassa sarakkeessa.

**Päivätila**

Tällä asetuksella määritetään, käytetäänkö oletusta eli useDaysMode-järjestelmäasetuksessa määritettyä sääntöä vai jotain muuta valikossa ehdolla olevaa sääntöä. Pääsääntöisesti kimpassa kannattaa noudattaa yhteistä oletussääntöä.

**Yksikkö**

Tässä määritetään, onko laina-aika tunteja vai päiviä.

**Eräpäivä**

Tällä voi määrittää kiinteän eräpäivän. Tätä käytetään todennäköisesti lähinnä oppilaitoskirjastoissa, joissa halutaan, että eräpäivät eivät mene lukukauden loppumispäivän yli ja halutaan niteet takaisin ennen lukukauden loppua.

**Lyhennetty laina-aika paljon varatuille (päivinä)**

Kohassa on toiminnallisuus/järjestelmäasetus decreaseLoanHighHolds, jolla voi määrittää lyhyemmän laina-ajan sellaisille tietueille, joihin kohdistuu paljon varauksia. Laina-ajan voi määrittää oletuksena decreaseLoanHighHolds-järjestelmäasetukseen tai sääntökohtaisesti laina- ja maksussäännöissä, jolloin ohitetaan järjestelmäasetuksen sääntö.

Huomioitavaa: Tähän toiminnallisuuteen liittyy jonkin verran epäjohdonmukaisuuksia, joten kannattaa testata ennen käyttöönottoa huolella, että logiikka sopii omaan toimintaympäristöön.

<img src="/assets/files/docs/Asetukset/lainasaannot2.png" title="Laina- ja maksusäännöt keskiosa" alt="Laina- ja maksusäännöistä keskiosa" style="width:100.0%" />

**Maksun määrä**

Maksun määrä -kohtaan määritetään päivä/tuntikohtainen maksun määrä.

**Maksun veloitusväli**

Maksun veloitusväli -asetuksessa määritetään minkälaisella veloitusvälillä maksu veloitetaan, esim. 1 päivän välein, 5 päivän välein, 3 tunnin välein jne.

**Veloitusaika**

Veloitusaika-asetuksella määritetään, missä kohtaa veloitusväliä maksu lisätään asiakkaan maksuihin, alussa vai lopussa. Jos veloitusväli on yksi päivä, tällä ei ole juuri merkitystä, mutta jos veloitusväli on pidempi, esim. 7 päivää, on sillä jo merkitystä.

**Maksut anteeksi -aika (päivinä)**

Maksut anteeksi -aika (päivinä) on aika, jonka laina voi olla myöhässä ennen kuin aletaan veloittamaan myöhästymismaksuja. FinesIncludeGracePeriod-järjestelmäasetuksella määritetään, otetaanko Maksut anteeksi -aika huomioon, kun maksuja lasketaan.

Huom! Tämä asetus voidaan asettaa vain päiviksi, ei tunneiksi.

**Maksimi myöhästymismaksu**

Maksimi myöhästymismaksulla määritetään, kuinka paljon korkeintaan veloitetaan nidekohtaista myöhästymismaksua kyseiselle asiakastyyppi/nidetyyppiyhdistelmälle (lainasääntöriville).

Huom! Jos laina on useamman kerran myöhässä, niin lainasta voi kertyä yli maksimimäärän, koska jokaisesta myöhässä olevasta "lainakerrasta" (laina tai uusinta) kertyy oma maksurivi, joka kertyy maksimissaan sitten tässä asetettuun summaan.

**Korvaushinnan katto**

Tällä asetuksella voidaan estää se, että niteen myöhästymismaksu ei ylitä niteen korvaushintaa.

**Keskeytys (päivää)**

Jos asiakkaita "sakotetaan" jäädyttämällä heidän tilinsä/kirjastokorttinsa, tähän määritetään, kuinka kauan päivissä jäädytys kestää.

Tätä ominaisuutta ei taideta Suomessa käyttää.

**Maksimikeskeytys (päivää)**

Tähän säädetään maksimimäärä päiviä, joita tilin/kirjastokortin jäädytys voi kestää.

**Keskeytyksen veloitusväli**

Keskeytyksen veloitusväli toimii kuten Veloitusaikaväli, mutta maksujen sijasta annetaan jäädytyspäiviä.

<img src="/assets/files/docs/Asetukset/lainasaannot3.png" title="Laina- ja maksusäännöt keskiosaa" alt="Laina- ja maksusääntöjen jatkoa" style="width:100.0%" />

**Sallitut uusintakerrat**

Asetuksella määritetään, kuinka monta kertaa asiakas voi uusia lainansa, mikäli siihen ei kohdistu varauksia, eikä asiakkaalla ole liikaa maksuja.

Huom! Jos tämän asetuksen muuttaa ns. lennossa pienemmäksi, voi asiakkailla olla uusintakertoja enemmän kuin sallitaan.

**Sallitut verkkokirjastouusintakerrat**

Asetuksella määritetään, kuinka monta kertaa asiakas saa uusia itse lainan verkkokirjastossa ennen kuin se pitää tehdä henkilökunnan toimesta. Tässä voisi olla esim. yksi vähemmän kuin Sallitut uusintakerrat -kohdassa, jolloin viimeisen uusinnan joutuisi tekemään henkilökunta. Tätä ei taida olla käytössä missään kimpassa.

**Uusinta-aika**

Asetuksella määritetään, kuinka monta päivää lisää annetaan laina-aikaa. Tyypillisesti tässä on sama luku kuin laina-ajassa.

**Ei uusintaa ennen**

Asetuksella määritetään, koska lainan saa aikaisintaan uusia ennen eräpäivää. Tyypillisesti jos laina-aika on 28 vrk, niin tähän tulisi 27 vrk. Asetuksen tarkoituksena on estää asiakasta/virkailijaa uusimasta samaa lainaa monta kertaa saman päivän aikana ja kuluttamasta turhaan uusintakertojen määrää.

Huom! Jos tämä asetus on päällä ja asiakas vahingossa lukee automaatilla lainatessaan niteen uudelleen (kaksi kertaa peräkkäin, koitetaan nide silloin uusia. Jos tämä asetus on päällä, uusiminen ei onnistu ja asiakas saa automaatilta virheilmoituksen, että lainaaminen ei onnistunut. Nide on kuitenkin jo mennyt lainaan ensimmäisellä lukukerralla, mutta asiakas saa kuvan, että näin ei ole käynyt. Tämä on ongelmallista varsinkin omatoimiaikaan, jolloin asiakas ei voi tarkistaa tilannetta henkilökunnalta ja pahimmassa tapauksessa jättää itsellään lainassa olevan niteen automaatille/hyllyyn/tiskille.

Osalla kimpoista tämä asetus on käytössä, osassa siitä on luovuttu automaateilla tulevien ongelmien vuoksi.

**Automaattinen uusinta**

Asetuksella valitaan, onko kyseiselle lainasäännölle voimassa automaattinen uusinta vai ei. Tämä sääntö pelkästään ei riitä vaan lisäksi tarvitaan ajastettu ajo (cron job), joka tekee uusinnan lainasääntöjen mukaisesti.

Jos automaattinen uusinta on käytössä, pitää Ei uusintaa ennen -asetuksessa olla määritys. Muuten ajastettu ajo pyrkii uusimaan lainan joka päivä eräpäivän jälkeen. 

**Ei automaattista uusintaa tämän jälkeen**

Asetuksella voi määrittää päivien määrän, jonka jälkeen automaattista uusintaa ei tehdä. Esim. automaattisia uusintoja ei tehdä enää 80 päivää lainauspäivän jälkeen.

**Varauksia sallittu (yhteensä)**

Asetuksella määritetään, kuinka monta varausta voi tehdä yhteensä. Tässä on huomioitava, että jokainen lainasääntörivi sallii tässä määritetyn määrän varauksia. Jos jätetään tyhjäksi, asiakas voi tehdä rajoittamattoman määrän varauksia.

Kokemus on osoittanut, että Finnassa tulee suorituskykyongelmia, jos asiakkaalla on voimassa olevia varauksia yli 500-600 kpl. Asiakkaan varaukset eivät lataudu näkyville Finnassa, jos varauksia on todella paljon.

**Varauksia sallittu (päivittäin)**

Asetuksella määritetään, kuinka monta varausta asiakas voi tehdä päivittäin.

**Varauksia tietuetta kohti (määrä)**

Asetuksella määritetään, kuinka monta varausta asiakas voi tehdä tietuetta kohti. Lehtivarausten kohdalla on sallittava enemmän kuin yksi, koska numeroniteet ovat joko yhden tietueen tai vuositietueiden alla (riippuu kimpan koosta). Jos lehdillä varausmäärä rajataan esim. yksi/tietue, voi asiakas tehdä silloin vain yhteen lehtitietueen niteeseen varauksen.

Tämän käytössä on kimpoissa erilaisia käytäntöjä. Osa sallii tietueeseen saman verran varauksia kuin mitä on maksimimäärä, osa sallii vain yhden varauksen/tietue.

<img src="/assets/files/docs/Asetukset/lainasaannot4.png" title="Laina- ja maksusääntöjen loppuosa" alt="Laina- ja maksussääntöjen loppuosa" style="width:70.0%" />

**Hyllyvaraukset sallittu**

Tällä asetuksella säädetään, onko hyllyvarausten teko sallittua vai ei. Vaihtoehdot ovat Kyllä, Jos yhtään ei ole saatavilla ja Jos jokin ei ole saatavana.

Mikään ei suoraan ole vaihtoehtona "ei", mutta "Jos yhtään ei ole saatavilla" on teknisesti lähimpänä sitä.

**Verkkokirjaston nidevaraukset**

Asetuksella säädetään, voiko verkkokirjastossa (koskee myös Finnaa) tehdä nidevarauksia säännön piirissä oleviin niteisiin. Käytännössä kaikkiin muihin sääntöihin paitsi aikakauslehtiä koskeviin sääntöihin kannattaa laittaa _Älä salli_, jotta asiakkaat eivät tee turhaan yhteen tiettyyn niteeseen kohdistuvia varauksia. Lehtien osalta nidevaraukset taas ovat välttämättömiä, koska yksi nide on aina yksi lehden numero.

**Varausten noutoaika (päiviä)**

Asetuksella määritetään varausten noutoaika päivinä, jos se pitää olla sääntörivi- tai kirjastokohtainen. Noutoajan voi määrittää myös ReservesMaxPickUpDelay-järjestelmäasetukseen, jolloin se on oletusarvo, josta sitten poiketaan laina- ja maksusääntöjen säädöillä. Tyypillisesti tämä pitää lisätä esim. kirjastoautoille, joilla on tarve pidemmälle noutoajalle reittien vuoksi.

**Artikkelipyynnöt**

Asetuksella määritetään, onko asiakkaiden mahdollista tehdä Kohan verkkokirjastossa artikkelipyyntöjä. Ominaisuus ei ole käytössä yleisillä kirjastoilla.

**Lainausalennus (%)**

Asetuksellä määritetään lainausalennus prosentteina, mikäli käytössä on maksulliset lainaukset. Suomessa nämä ei taida olla edes laillisia, joten tähän ei tarvitse määrittää mitään.

**Toiminnot**

Sarakkeessa on Muokkaa- ja Poista-napit. Muokkaa-napista pääset muokkaamaan valitsemaasi riviä ja Poista-napilla rivin voi poistaa.

### 6.2 Oletussäännöt lainauksille, varauksille ja palautuksille

![](/assets/files/docs/Asetukset/lainasaannot5.png)

Voit asettaa lainojen sallitulle määrälle sekä varausten ja palautusten säännöille oletusarvot, joita käytetään, jos nidetyypille tai asiakastyypille ei ole määritelty tämän osion alla mitään arvoja. Näitä sääntöjä käytetään, jos mitään muuta sääntöä ei löydy.

**Sallittu lainamäärä**

Maksimimäärä lainoja. Tämä asetus ei ohita yläpuolella olevaa laina- ja maksusääntötaulukkoa.

**Yhteenlaskettu on-site-lainojen sallittu määrä**

On-site-lainojen maksimimäärä. Tämä asetus ei ohita yläpuolella olevaa laina- ja maksusääntötaulukkoa.

**Varauksia sallittu enintään (määrä)**

Varausten maksimimäärä. Tämä asetus ei ohita yläpuolella olevaa laina- ja maksusääntötaulukkoa.

**Varaussääntö**

Minkä kirjastojen niteitä/teoksia asiakas voi varata, perustuu asiakkaan kotikirjastoon. 

Vaihtoehdot: 
* Ei asetettu - oletus
* Mistä tahansa kirjastosta, eli minkä tahansa kirjaston asiakas voi tehdä kirjaston niteisiin varauksen.
* Paikallisesta varausryhmästä, eli vain ne asiakkaat, joiden kotikirjasto vastaa niteen kotikirjaston varausryhmää voi tehdä varauksen.
* Kotikirjastosta, eli vain asiakkaat, joiden kotikirjasto on sama kuin niteen kotikirjasto voi tehdä varauksen
* Ei varattavissa, eli kukaan asiakas ei voi varata.

Suositus: Mistä tahansa kirjastosta, kun käytössä on yhteinen varausjono. Muita vaihtoehtoja ei ole testattu ja ne perustuu asiakkaan kotikirjastoon, mikä ei käytännössä Suomen toimintaympäristössä tarkoita mitään.

**Varauksen noutokirjasto täsmää**

Asetuksella määritetään, mistä kirjastoista asiakas voi noutaa varauksensa.

Vaihtoehdot: 
* Ei asetettu, 
* mikä tahansa kirjasto, 
* niteen varausryhmä, 
* asiakkaan varausryhmä, 
* niteen kotikirjasto, 
* niteen sijaintikirjasto.

**Palautussääntö**

Asetuksella määritetään, mihin nide palaa, kun se palautetaan.

Vaihtoehdot:
* Ei asetettu
* Nide palaa kotikirjastoon
* Nide palaa lainaavaan kirjastoon
* Nide kelluu
* Nide kelluu kirjastoryhmän mukaan (KS-muutos). Tämä vaihtoehto pitää valita, jos haluaa käyttää kellutusryhmiä, jotka määritetään kirjastoryhmissä.

**Toiminnot**

Tallenna ja Pois päältä. Jälkimmäisellä voi tyhjentää asetetut asetukset.

### 6.3 Oletussääntö maksun hyvitykselle, kun palautetaan kadonnut nide

![](/assets/files/docs/Asetukset/lainasaannot6.png)

Asetuksessa voi määrittää oletussäännön maksun hyvityksille, kun kadonnut nide palautetaan. 

Vaihtoehdot:
* Hyvitä kadonneen aineiston korvausmaksu
* Hyvitä kadonneen aineiston korvausmaksu ja veloita uusi myöhästymismaksu
* Hyvitä kadonneen aineiston korvausmaksu ja palauta myöhästymismaksu
* Jätä kadonneen aineiston korvausmaksu

### 6.4 Oletusvaraussääntö nidetyypeittäin

![](/assets/files/docs/Asetukset/lainasaannot7.png)

Voit muokata tämän kirjaston sääntöjä nidetyypin mukaan, riippumatta asiakastyypistä. 

Varauksien määrityksillä on seuraavanlaisia vaikutuksia:

* Mistä tahansa kirjastosta: Asiakkaat mistä tahansa kirjastosta voivat varata tämän niteen. (käytetään oletusarvoa jos ei muutoin määritelty)
* Paikallisesta varausryhmästä: Niteen voivat varata vain asiakkaat, joiden kotikirjasto vastaa niteen kotikirjaston varausryhmää.
* Kotikirjastosta: Vain niteen kotikirjaston asiakkaat voivat varata niteen.
* Ei varattavissa: Asiakkaat eivät voi varata nidettä, eikä se jää varauksiin kiinni palautettaessa. Tällä säännöllä voi siis määrittää tietyn nidetyypin ei-varattavaksi.

Huom: Jos järjestelmäasetus 'AllowHoldPolicyOverride' on sallittu, lainauksen henkilökunta voi ohittaa nämä säännöt.
Tärkeä: Säännöt pohjautuvat ReservesControlBranch-järjestelmäasetukseen.

Voit määrittää, mistä asiakas voi noutaa varauksensa **Varauksen noutokirjasto täsmää** -sarakkeessa.

Vaihtoehdot:
* mikä tahansa kirjasto
* niteen varausryhmä
* asiakkaan varausryhmä
* niteen kotikirjasto
* niteen sijaintikirjasto

**Palautussääntö**-sarakkeessa voidaan määrittää, mitä tapahtuu, kun nide palautetaan.

Vaihtoehdot:
* Aineisto (Nide) palaa kotikirjastoon
  * jos käytössä on AutomaticItemReturn-järjestelmäasetus, käyttäjä ei saa ilmoitusta kuljetuksesta. 
* Aineisto (Nide) palaa lainaavaan kirjastoon
  * jos käytössä on AutomaticItemReturn-järjestelmäasetus, käyttäjä ei saa ilmoitusta kuljetuksesta.
* Aineisto (Nide) kelluu
* Aineisto (Nide) kelluu kellutusryhmän mukaan
  * Koha-Suomi-muutos

***

## 7. Asiakasmääreet

Asiakasmääreet ovat itse määritettäviä lisäkenttiä, jotka voi liittää asiakkaisiin. Jotta asiakasmääreitä voi lisätä, pitää järjestelmäasetus ExtendedPatronAttributes olla päällä.

![](/assets/files/docs/Asetukset/asiakasmaare.png)

Koha-Suomen kimpoilla on neljä kaikille yhteistä asiakasmäärettä: Automaattityyppi (AUTOTYPE), Sotu-avain (SSN), Automaatin toimittaja (TOIMITTAJA) ja Varaustunnus (HOLDID). Lisäksi voi olla kimppakohtaisia asiakasmääreitä, esim. OUTI-kirjastoissa on käytössä Y-tunnus-määre yhteisöasiakkaille ja Vaarassa Toveri-omatoimikoneille omatoimipalvelujen käyttöehtojen hyväksymiseen määre.

Asiakasmääreet näkyvät asiakastiedoissa **Muut määreet ja tunnukset** -kohdassa.

![](/assets/files/docs/Asetukset/asiakasmaare1.png)

### 7.1 Uuden asiakasmääreen tekeminen

Uuden asiakasmääreen voi lisätä Uusi asiakasmääre -napista.

![](/assets/files/docs/Asetukset/asiakasmaare2.png)

**Asiakasmääreen tunnus** -kohtaan kirjoitetaan sopiva tunnus. Se kannattaa olla vähintään kolmemerkkinen, eikä se kannata olla sama kuin jokin muu tunnus (hyllypaikka, asiakastyyppi, nidetyyppi jne). Tunnus voi olla korkeintaan kymmenenmerkkinen.

**Kuvaus** -kohtaan voi antaa tunnukselle selkokielisen nimen.

**Toistettava** -kohtaan laitetaan rasti, jos määreen voi laittaa samalle asiakkaalle useamman kerran.

**Yksilöivä tunnus** -kohtaan laitetaan rasti, jos tunnus on yksilöivä eli uniikki. Samaa arvoa ei saa silloin laitettua kahdelle eri asiakkaalle. Esim. Sotu-avain on yksilöivä tunnus.

**Näytä verkkokirjastossa** -kohta tarkoittaa tällä hetkellä Kohan omaa opacia, mutta tähän kannattaa laittaa rasti tulevaisuutta ajatellen, jos sen halutaan näkyvän myös Finnassa.

**Muokattavissa verkkokirjastossa** -kohta tarkoittaa myös tällä hetkellä Kohan omaa opacia, mutta tähän kannattaa laittaa rasti tulevaisuutta ajatellen, jos sen halutaan näkyvän myös Finnassa.

**Haettavissa** -kohdassa määritetään, voiko määreellä hakea asiakkaita. Tähän kannattaa laittaa rasti ainakin Sotu-avaimen osalta.

**Pakollinen** -kohdassa määritetään, onko määre pakollinen.

**Näytä asiakkaan suppeissa tiedoissa** -kohdassa määritetään, näytetäänkö määre asiakastiedoissa vasemmalla olevassa tietoruudussa. Koha-Suomen kimpoissa tietoruutu on piilotettu css-määrityksellä.

**Säilytä pseudonymisointia varten** -kohdassa voi määrittää määreen tallennettavaksi pseudonymisoituihin tietoihin.

**Auktorisoidun arvon luokka** - kohtaan voi määrittää auktorisoidun arvon, jonka arvoja ehdotetaan vaihtoehdoiksi teksikentän sijaan. Esim. Automaattityyppi-määreelle on tähän valittu AUTOMTYPE-auktorisoitu arvo, jolloin määreelle annetaan alasvetovalikkoon vaihtoehdoiksi auktorisoidun arvon tunnukset.

![](/assets/files/docs/Asetukset/asiakasmaare3.png)

![](/assets/assets/files/docs/Asetukset/docs/Asetukset/asiakasmaare4.png)

**Kirjastorajoitus** - kohdassa asiakasmääreen voi rajoittaa koskevaksi vain tiettyä kirjastoa. Pääsääntöisesti määreet koskevat kaikkia kirjastoja.

**Tyyppi**-kohdassa asiakasmääreen voi rajata yhdelle asiakastyypille. Esim. OUTIssa Y-tunnus-määre on rajattu yhteisöasiakkaille. Kohta jätetään tyhjäksi, jos määreen haluaa koskevan kaikkia asiakastyyppejä.

**Luokka** -kohtaan voi valita PA_CLASS-auktorisoidun arvon luokan, jos sellaisia on määritetty. Näillä määreitä voidaan ryhmittää otsikoiden alle.

## 8. Aineistokuljetusten rajoitukset

Aineistokuljetusten rajoitukset -osiossa voi määrittää, kuinka niteitä voi kuljettaa perustuen lähettävään kirjastoon, vastaanottavaan kirjastoon ja kokoelmakoodiin/nidetyyppiin. Rajoitukset toimivat vain, jos UseBranchTransferLimits-järjestelmäasetus on päällä.  BranchTransferLimitsType-järjestelmäasetuksessa valitaan, perustuuko rajoitukset kokoelmakoodiin vai nidetyyppiin. 

Rajoitukset tehdään kirjastokohtaisesti eli ensin valitaan haluttu kirjasto. Sen jälkeen valitaan nidetyyppi/kokoelmakoodi-kohtaisesti, mihin kirjastoihin kuljetus sallitaan. Laita rasti niiden kirjastojen kohdalle, joihin kuljetus sallitaan.

![](/assets/files/docs/Asetukset/kuljetus.png)

Rajoituksia voi säätää myös **Kehittyneellä editorilla**, joka on matriisityyppinen taulukko. Siellä valitaan ensin nidetyyppi/kokoelmakoodi ja sen jälkeen pääsee säätämään koko kirjastoverkon rajoituksia kerralla. Isossa kimpassa tämä näkymä on hankala, mutta pienemmissä siedettävämpi.

![](/assets/files/docs/Asetukset/kuljetus1.png)

## 9. Kuljetusten painomatriisi

Kuljetusten painomatriisilla voi määritellä aineistojen kuljetuksille "kustannuksen" eri kirjastopisteiden välillä. Painomatriisi vaikuttaa vain Varausjono-raportin luomiseen, ei normaaliin varausjonon purkautumiseen. Järjestelmäasetus UseTransportCostMatrix pitää olla määritetty käyttöön, jotta määritettyjä arvoja käytetään.

Kustannukset voi merkitä haluamillaan minimi- ja maksimiarvoilla, esim. 1-100. Arvoja muokataan klikkaamalla haluttua kenttää ja kirjoitetaan arvo kenttään.

## 10. Nidekierron huomautukset

Nidekierron huomautuksilla voi säätää oletussäännöt kirjastoittain ja asiakastyypeittään siitä, lähetetäänkö laina- ja palautuskuitit. Nämä säännöt ohitetaan asiakaskohtaisilla viestiasetuksilla. Oletuksena on, että viestit lähetetään.

![](/assets/files/docs/Asetukset/nidekierronhuomautukset.png)

Asetusta muutetaan klikkaamalla hiirellä halutun asiakastyyppi/nidetyyppi-yhdistelmän kohdalla.

## 11. Kaupungit ja kunnat

Kaupungit ja kunnat -osiossa pystyy lisäämään postinumerot ja postitoimipaikat ikään kuin auktorisoiduiksi arvoiksi, jotka näkyvät asiakkaan lisäysnäytöllä alasvetovalikossa. Käytännössä tänne on laitettu kimpan alueen postinumerot, jotta alasvetovalikosta ei tule turhan pitkä. Postinumeroiden lisäys parantaa tietojen oikeellisuutta asiakastiedoissa, kun tiedot tulee valinnan jälkeen automaattisesti oikeassa muodossa ja oikeaan kenttään.

![](/assets/files/docs/Asetukset/kaupungit.png)

* _Toiminnot_-sarakkeesta voit joko muokata tai poistaa jo olemassa olevan postinumeron.

Uusi tieto lisätään valitsemalla _Uusi kaupunki_, jonka jälkeen täytetään vähintäänkin pakolliset tiedot.

![](/assets/files/docs/Asetukset/kaupungit1.png)

* _Kunta_: Lisää tähän postitoimipaikka.
* _Osavaltio_: Ei tarpeellinen Suomessa, jätä tyhjäksi.
* _Postinumero_: Lisää tähän postinumero.
* _Maa_: Ei tarpeellinen Suomessa, jätä tyhjäksi.

Tallenna tiedot valitsemalla _OK_ ja peruuta tietojen tallennus valitsemalla _Peruuta_.

## 12. Noutopalvelu

Noutopalvelu-toiminnolla voidaan hallinnoida asiakaskäyntejä esim. sellaisissa tilanteissa, että kirjasto on muuten kiinni, mutta asiakkaat voivat tulla tiettyyn aikaan hakemaan varauksensa/lainansa kirjastolta.

Palvelun tiedot määritetään kirjastokohtaisesti ja vaatii, että järjestelmäasetus _CurbsidePickup_ on käytössä. Jotta asiakkaat voisivat itse varata noutoaikoja, pitäisi käytössä olla Kohan oma verkkokirjasto. Finna ei tue tätä toimintoa.

![](/assets/files/docs/Asetukset/noutopalvelu.png)

Mene halutun kirjaston välilehdelle.

* _Ota käyttöön_: Laita rasti tähän, jotta noutopalvelu aktivoituu kyseiselle kirjastolle.
* _Noutojen kesto_: Määrittele, kuinka monta minuuttia nouto kestää. Esim. 5 minuuttia.
* _Maksimimäärä asiakkaita yhdelle jaksolle_: Maksimimäärä yhtäaikaisia noutoja yhdelle jaksolle.
* _Asiakkaan ajastama nouto_: Sallii asiakkaiden ajastaa itse noutopalveluajan. Huom! Vaatii toimiakseen Kohan oman verkkokirjaston, jota meillä ei ole käytössä.
* _Ota käyttöön vain odottaville varauksille_: Otetaan käyttöön vain, jos asiakkaalla on noudettavia varauksia.

* _Noutopalvelun tunnit_: Merkitse viikonpäivät ja kellonajat, jolloin noutopalvelu on käytössä. Uuden jakson saa määritettyä _Lisää_-napilla.

_Tallenna asetukset_ -napilla saat tallennettua tekemäsi määritykset.

Noutopalvelu löytyy Kohan Lainaus ja palautus -osiosta.

## 13. Asiakkaan rajoitukset

Asiakkaille voi lisätä manuaalisesti rajoituksia, jotka voi määrittää Asiakkaan rajoitukset osiossa ylläpidossa. Jotta nämä tulisi näkyville asiakastiedoissa rajoitusta lisätessä, pitää olla päällä järjestelmäasetus PatronRestrictionTypes. Yhden rajoitetyypin voi kerrallaan asettaa oletukseksi.

![](/assets/files/docs/Asetukset/rajoitukset.png)

Uusi rajoitus lisätään klikkaamalla _Uusi rajoitus_.

![](/assets/files/docs/Asetukset/rajoitukset2.png)

* _Koodi_: Rajoituksen tunnus
* _Otsikko_: Rajoituksen kuvaus, joka näkyy rajoitusta lisätessä.
* _Poista maksun jälkeen_: Toiminnolla saa rajoitteen poistumaan, kun alla oleva maksuraja saavutetaan eli asiakas maksaa niin paljon maksuja, että niitä on vähemmän kuin maksurajaan on merkitty.
* _Maksuraja_: Tähän merkitään summa, jonka alle kun asiakkaan maksut menee, poistuu rajoitus automaattisesti.

Rajoitustyypit näkyvät asiakkaan tiedoissa rajoitusta lisätessä näin:

![](/assets/files/docs/Asetukset/rajoitukset3.png)

## 14. Maksutyypit

Maksutyypeissä on näkyvillä sekä manuaalisesti lisättävät maksutyypit että järjestelmän sisäiset maksutyypit.

![](/assets/files/docs/Asetukset/maksutyypit.png)

Järjestelmän sisäiset maksutyypit saa näkyville klikkaamalla _Näytä kaikki maksutyypit_. Manuaalisesti lisättyjä maksuja pystyy muokkaamaan ja arkistoimaan. Uuden maksutyypin voi luoda valitsemalla _Uusi maksutyyppi_.

![](/assets/files/docs/Asetukset/maksutyypit1.png)

* _Maksutyypin tunnus_: Maksutyypin tunnus, joka kirjautuu maksutauluun maksuja lisätessä.
* _Oletussumma_: Voit määrittää maksulle oletussummaan, joka tulee automaattisesti maksu-kenttään maksua lisätessä asiakkaan tiedoissa.
* _Kuvaus_: Maksun selkokielinen kuvaus, joka näkyy käyttäjälle maksua lisätessä asiakkaan tiedoissa.
* _Voidaan lisätä maksun käsin?_: Tämä pitää valita, jotta maksu tulee näkyviin asiakkaan tiedoissa maksun lisäykseen.
* _Voidaan myydä?_: Tämä liittyy Kohan kassa-toimintoon. Jos tähän lisää rastin, tulee maksutyyppi näkyviin kassa-toiminnossa myytävänä tuotteena.
* _Lasketaan mukaan noissuecharge-asetukseen?_: Tämä tarkoittaa, että maksutyyppi otetaan huomioon, kun lasketaan lainauskieltoon vaikuttavia maksuja. Huom! Vain julkisoikeudelliset maksut saavat aiheuttaa lainakiellon. Julkisoikeudellisia maksuja ovat kirjaston myöhästymismaksut ja noutamattoman varauksen maksut.
* _Kirjastorajoitus_: Voit rajata maksutyypin halutessasi tiettyjen kirjastojen käyttöön. Valitse _Kaikki kirjastot_, jos et halua rajoittaa.

### 14.1 Yleisimpiä maksutyyppejä

Tunnus|Kuvaus|Käyttökohde|Saako estää lainauksen?
---|---|---|---
NEW_CARD|Uusi kortti|Maksu uudesta kortista|Ei
ODUE|Palautuskehotus|Koha-Suomen oma lisäys, jolla palautuskehotuksesta lisätään asiakkaalle maksu|Kyllä
OVERDUE|Myöhästymismaksu|Päivittäinen myöhästymismaksu|Kyllä
Pay|Maksusuoritus|Asiakkaan tekemä maksusuoritus
RESERVE_EXPIRED|Noutamattoman varauksen maksu|Lisätään ajastetulla ajolla asiakkaalle, kun hän ei nouda varaustaan|Kyllä


## 15. Credit-tyypit

Credit-tyypeillä merkitään Kohassa maksusuoritukset, hyvitykset ja maksujen peruutukset. Maksutyypit kirjataan positiivisina arvoina, credit-tyypit negatiivisina arvoina, jolloin tilitapahtumat pysyvät balanssissa. Kun asiakkaalla ei ole maksamattomia maksuja, ovat creditit ja maksutyypit yhtä suuria.

![](/assets/files/docs/Asetukset/credittyypit.png)

Uuden credit-tyypin voi lisätä _Uusi credit-tyyppi_ -linkistä.

![](/assets/files/docs/Asetukset/credittyypit1.png)

* _Credit-tyypin koodi_: Credit-tyypin tunnus, joka kirjataan maksut-tauluun
* _Kuvaus_: Credit-tyypin selkokielinen kuvaus, joka näkyy asiakkaan maksuissa.
* _Voidaan lisätä käsin_: Jos tähän laittaa raksin, näkyy tyyppi credit-maksujen lisäysvälilehdellä (Koha-Suomen kimpoissa piilotettu).
* _Ota käyttöön credit-numero_: Jos on tarpeen saada jokaiselle credit-maksulle oma juokseva numeronsa, tällä valinnalla sellaisen saa käyttöön. Numeron muoto määritetään AutoCreditNumber-järjestelmäasetuksessa.
* _Kirjastorajoitus_: Valitse haluamasi kirjastot tai _Kaikki kirjastot_, jos et halua rajata tiettyihin kirjastoihin.

### 15.1 Yleisimpiä credit-tyyppejä

Tunnus|Kuvaus|Käyttökohde
---|---|---
PAYMENT|Maksusuoritus|Asiakas on maksanut maksun joko kokonaan tai osan siitä
WRITEOFF|Maksun poisto|Asiakkaan maksu on poistettu

### 15.2 Yhdessä sovitut credit-tyypit

[Vanhentuneiden maksujen poistoajoa](https://github.com/KohaSuomi/Koha/issues/804) suunniteltaessa sovittiin, että kaikki lisäävät credit-tyyppeihin EXPIRED-tyypin ja sille kuvaukseksi _Vanhentuneen maksun mitätöinti_.

## 16. Liitännäiset

Liitännäisissä näkyvät kaikki asennetut liitännäiset ja niiden tila. Liitännäisiä on eri tyyppisiä. Osa on ns. työkaluja, jotka saa käynnistettyä (esim. tarratulostustyökalu), osa toimii vain taustalla, eikä niillä ole käyttöliittymää (esim. tekstiviestiajurit). Osa on ns. raporttiliitännäisiä.

![](/assets/files/docs/Asetukset/liitannaiset.png)

* Uusia liitännäisiä saa asennettua _Lataa liitännäinen_ -napin kautta. Koha tukee vain KPZ-muotoisia tiedostoja.
* Näytettäviä liitännäisiä voi suodattaa _Näytä liitännäisiä luokan mukaan_ -valikosta.
* Toiminnot-sarakkeen napista voi liitännäisestä riippuen tehdä seuraavia toimintoja:
  * _Käynnistä työkalu_: Jos liitännäinen on työkalutyyppinen, voi sen avata tästä.
  * _Määrittely_: Jos liitännäiseen liittyy asetuksia ja määrittelyjä, voi ne tehdä tästä.
  * _Poista asennus_: Tästä saa liitännäisen asennuksen poistettua.
  * _Poista käytöstä_: Tästä saa liitännäisen pois käytöstä, mutta sen asennus säilyy. Jos liitännäinen on poistettu käytöstä, saa sen taas käyttöön valitsemalla _Ota käyttöön_.

## 17. Hallinnoi taustatöitä

Kohassa menee erilaiset tietokantaa kuormittavat toiminnot taustatyöjonoon, josta ne käsitellään sitä mukaa kuin ehditään. Jonoon menevät mm. tietueiden ja niteiden erämuokkaukset- ja poistot, tietueiden indeksoinnit, varausten eräpoistot ja tietueiden vienti välivarastoon. Pääsääntöisesti työt valmistuvat saman minuutin sisään, mutta ruuhka-aikoina käsittelyssä voi mennä kauemminkin.

![](/assets/files/docs/Asetukset/taustatyot.png)

* _Vain nykyiset taustatyöt_: Jos tämä on valittuna, näytetään vain taustatyöt, jotka ovat keskeneräisiä. Jos taulukossa ei ole mitään sisältöä, ota tästä pois raksi, niin näet vanhempia töitä.
* _Sisällytä vain taustatyöt, jotka on aloitettu viimeisen tunnin aikana_: Tämä rajaa näytettävat taustatyöt niihin, jotka on aloitettu viimeisen tunnin aikana.
* Sarakkeen otsikkojen perusteella voi suodattaa näkymää. _Tyyppi_-sarakkeessa voi suodattaa näkyville esimerkiksi niteiden poistot eräajona.
* _Näytä_-napista saa näkyville työstä tarkempia tietoja. Osasta töistä näkee, mitä tietueita tai niteitä muutos on koskenut, mutta osasta ei näy teostietoja.
![](/assets/files/docs/Asetukset/taustatyot1.png)


## 18. MARC-kuvailupohjat

MARC-kuvailupohjissa määritetään mitä MARC-kenttiä on näkyvillä tietuetta ja nidettä muokatessa. Oletuspohjassa on näkyvillä suurin osa MARC-kentistä, mutta voi olla tarpeen tehdä aineistotyyppikohtaisia pohjia, jolloin näkyville jätetään vain juuri sille aineistolle tarpeelliset MARC-kentät. Nidetietojen kenttien näkyvyyttä hallinnoidaan 952-kentällä.

Koha-Suomella on käytössä skripti, joka päivittää kuvailupohjiin uudet ja muuttuneet MARC-kentät Kansalliskirjaston ylläpitämän yhtenäisformaatin pohjalta.

TäTi-tietokannassa on täydellisimmät MARC-kuvailupohjat, koska primäärikuvailu on sovittu tehtävän siellä. Vain esineet kuvaillaan paikalliskantaan.


![](/assets/files/docs/Asetukset/kuvailupohjat.png)

Toiminnot-napista pääsee tutkailemaan MARC-rakennetta, muokkaamaan ja poistamaan kuvailupohjan sekä viemään ja tuomaan pohjan.

![](/assets/files/docs/Asetukset/kuvailupohjat1.png)

MARC-kuvailupohjia voi viedä tietokannasta toiseen, mutta kannattaa huomioida pari asiaa:
* jos lähtötietokannassa on kuvailupohjaan liitetty sellaisia auktorisoituja arvoja, joita ei kohdetietokannassa ole, eivät nämä kentät siirry kohdetietokantaan.
* jos lähtö- ja kohdetietokannassa on erilaiset määritykset Kohan MARC-määrityksissä, voi linkitys MARC-kentän ja tietokannan taulun välillä muuttua tai poistua kokonaan, jolloin voi tulla ongelmia tietojen näkymisessä Kohan eri näytöillä. Tai jopa niin, että tiedot eivät tallennu.

### 18.1 MARC-rakenne

MARC-rakenne-toiminnon takaa avautuu taulukkona kaikki kyseiseen pohjaan liittyvät MARC-kentät

![](/assets/files/docs/Asetukset/kuvailupohjat2.png)

Toiminnot-napin takaa pääseen muokkaamaan yksittäisen tagin (kentän) tietoja, katsomaan sen osakenttiä, muokkaamaan osakenttiä ja poistamaan tagin (kentän).

#### 18.1.1 Tagin muokkaus

![](/assets/files/docs/Asetukset/kuvailupohjat3.png)

Tagin muokkauksessa voi muokata:

* _Kuvaus virkailijaliittymässä_: Kentän otsikko näytetään kuvailua tehdessä tämän kentän mukaisesti. Jos kentän nimeen tulee muutos, pitää se muokata täällä.
* _Kuvaus verkkokirjastossa_: Sama kuin yllä, mutta koskee Kohan verkkokirjastoa, joka meillä ei ole käytössä.
* _Toistettava_: Jos kenttä on toistettavissa, tähän laitetaan rasti.
* _Pakollinen_: Jos kenttä halutaan määrittää pakolliseksi, tähän laitetaan rasti
* _Tärkeä_: Tämä on lievempi vaihtoehto pakollisuudelle. Se antaa tietuetta tallennettaessa ilmoituksen, että tärkeitä kenttiä on tyhjänä, mutta ei pakota täyttämään kenttää.
* _1. indikaattorin oletusarvo_: Tähän voi määrittää 1. indikaattorin oletusarvon tarvittaessa.
* _Toisen indikaattorin oletusarvo_: Tähän voi määrittää 2. indikaattorin oletusarvon tarvittaessa.
* _Auktorisoitu arvo_: Tähän voi määrittää kentälle käyttöön auktorisoidun arvon luokan.

#### 18.1.2 Näytä osakentät

MARC-kentän osakenttiä voi tutkailla Näytä osakentät -vaihtoehdolla.

Jos kenttä on kiinteämittainen, on osakentän arvon @-merkki.
![](/assets/files/docs/Asetukset/kuvailupohjat4.png)

Jos kentällä on varsinaisia osakenttiä, listataan ne taulukkona ensin numerot ja sitten kirjaimet.
![](/assets/files/docs/Asetukset/kuvailupohjat5.png)

Osakenttiä (myös @-merkillistä kiinteämittaista) voi muokata tai poistaa tämän näkymän kautta.

#### 18.1.3 Muokkaa osakenttiä

Muokkaa osakenttiä -vaihtoehdolla avautuu osakenttien muokkausnäkymä. Kentän osakentät ovat erillisillä välilehdillä. Viimeisenä välilehtenä on _Uusi_, josta saa lisättyä uuden osakentän. Osakenttien järjestystä voi muokata ottamalla hiirellä kiinni osakentän välilehdestä ja raahaamalla sen haluamaansa kohtaan. Järjestys vaikuttaa myös tietueen kuvailuun, missä osakentät järjestyvät tässä näkymässä tehdyn välilehtien järjestyksen mukaisesti.

Kentän perustiedot
![](/assets/files/docs/Asetukset/kuvailupohjat6.png)

* _Osakentän koodi_: Ei ole muokattavissa
* _Kuvaus virkailijaliittymässä_: Kentän otsikko näytetään kuvailua tehdessä tämän kentän mukaisesti. Jos kentän nimeen tulee muutos, pitää se muokata täällä.
* _Kuvaus verkkokirjastossa_: Sama kuin yllä, mutta koskee Kohan verkkokirjastoa, joka meillä ei ole käytössä.
* _Toistettava_: Jos kenttä on toistettavissa, tähän laitetaan rasti.
* _Pakollinen_: Jos kenttä halutaan määrittää pakolliseksi, tähän laitetaan rasti
* _Tärkeä_: Tämä on lievempi vaihtoehto pakollisuudelle. Se antaa tietuetta tallennettaessa ilmoituksen, että tärkeitä kenttiä on tyhjänä, mutta ei pakota täyttämään kenttää.
* _Näytetään välilehdellä_: Valikosta valitaan, millä välilehdellä osakenttä näytetään kuvailussa. Kaikki saman MARC-kentän osakentät pitää määrittää samalle välilehdelle tai valita _Älä huomioi_, jotta MARC-pohjien tarkistus ei valita niistä.

* _Oletusarvo_: Tähän voi tarvittaessa kirjoittaa kentälle jonkin oletusarvon, jos sellainen on mahdollista määrittää. Onnistunee helpommin kiinteämittaisilla kentillä.
* _Maksimipituus_: Kentän maksimipituudeksi kannattaa määrittää 9999 merkkiä, mikäli ei ole erityisesti tarpeen rajoittaa, miten pitkästi kenttään saa kirjoittaa/lisätä tietoja.
* _Näkyvyys_: Tässä kohdassa voi tehdä useammanlaisia määrittelyjä
  * _Verkkokirjasto_: Tällä valitaan, näkyykö kenttä Kohan verkkokirjastossa vai ei.
  * _Virkailijaliittymä_: Tällä valitaan, näkyykö kenttä virkailijaliittymässä vai ei.
  * _Editori_: Tällä valitaan, näkyykö kenttä tietueen kuvailussa peruseditorissa.
  * _Supistettu_: Tällä valitaan, onko kenttä peruseditorissa heti näkyvissä vai onko se "supistettu" piiloon, jolloin sen saa näkyviin klikkaamalla pääkenttää.
  * _Merkitty_: Tämä tarkoittaa, että kenttä piilotetaan kaikkialta eli käytännössä sama kuin ottaisi itse rastin pois kaikista muista tämän kohdan bokseista.

## 19. Kohan MARC-määritykset

_Kohan MARC-määrityksissä_ määritetään, mitkä MARC-kentät yhdistetään Kohan tietokannan biblio, biblioitems ja items-taulujen sarakkeisiin. Kun kytkös on tehty, viedään MARC-kentän sisältö tietokannan tauluun, josta tiedon hakeminen on nopeampaa kuin marcxml:n sisältä.

Jos mäppäyksiä muutetaan, pitää tehdä täydellinen uudelleenindeksointi, jotta muuttuneet tiedot päivittyvät tietueista tietokannan tauluun. Uusille ja muokatuille tietueille sovelletaan uusia sääntöjä samantien.

Uusi määritys lisätään klikkaamalla halutun Koha-kentän kohdalla _Lisää_-nappia ja kirjoittamalla avautuvan popupiin lisättävän MARC-kentän numero ja osakenttä pilkulla erotettuna. Jos haluaa tehdä kytköksen kontrollikenttään, se lisätään kirjoittamalla '@'-merkki ja kontrollikentän numero.

![](/assets/files/docs/Asetukset/koha2marc.png)

Määrityksen voi poistaa klikkaamalla halutun Koha-kentän kohdalla _Poista_-nappia.

### Koha-kirjastojen 29.3.2022 yhdessä sopimat Koha2MARC-mäppäykset

| Sarake | MARC-kentät |
| --- | --- |
| Biblio.abstrac | 520 ‡a |
| Biblio.author | 100 ‡a, 110 ‡a, 111 ‡a |
| biblio.biblionumber | 999 ‡c |
| biblio.copyrightdate | 260 ‡c, 264 ‡c |
| Biblio.datecreated | (automaattisesti aikaleima) |
| Biblio.frameworkcode | 999 ‡b |
| biblio.medium | 245 ‡h |
| biblio.notes | 500 ‡a |
| biblio.part_name | 245 ‡p |
| biblio.part_number | 245 ‡n |
| biblio.serial | 942 ‡s |
| biblio.seriestitle | 830 ‡a 
| biblio.subtititle | 245 ‡b |
| biblio.timestamp | (automaattisesti aikaleima) |
| biblio.title | 245 ‡a |
| biblio.unititle | 130 ‡a, 240 ‡a |
| biblioitems.agerestriction | 049 ‡c |
| biblioitems.biblioitemnumber | 999 ‡d |
| biblioitems.biblionumber | (automaattisesti tietueen biblionumber) |
| biblioitems.cn_class | 084 ‡a |
| biblioitems.cn_item | 942 ‡i |
| biblioitems.cn_sort | 942 ‡6 |
| biblioitems.cn_source | 942 ‡2 |
| biblioitems.cn_suffix | 942 ‡m |
| biblioitems.collectionissn | 490 ‡x |
| biblioitems.collectiontitle | 490 ‡a |
| biblioitems.collectionvolume | 490 ‡v |
| biblioitems.ean | 024 ‡a |
| biblioitems.editionresponsibility | 028 ‡b |
| biblioitems.editionstatement | 250 ‡a |
| biblioitems.illus | 300 ‡b |
| biblioitems.isbn | 020 ‡a |
| biblioitems.issn | 022 ‡a |
| biblioitems.itemtype | 942 ‡c |
| biblioitems.lccn | ei mäppäystä |
| biblioitems.notes | ei mäppäystä |
| biblioitems.number | 830 ‡v |
| biblioitems.pages | 300 ‡a |
| biblioitems.place | 260 ‡a, 264 ‡a |
| biblioitems.publicationyear | ei mäppäystä |
| biblioitems.publishercode | 028 ‡a |
| biblioitems.size | 300 ‡c |
| biblioitems.timestamp | (automaattisesti aikaleima) |
| biblioitems.totalissues | ei mäppäystä |
| biblioitems.url | 856 ‡u |
| biblioitems.volume | 362 ‡a |
| biblioitems.volumedate | ei mäppäystä |
| biblioitems.volumedesc | ei mäppäystä |
| items.barcode | 952 ‡p |
| items.biblioitemnumber | (automaattisesti tietueen biblioitemnumber) |
| items.biblionumber | (automaattisesti tietueen biblionumber) |
| items.booksellerid | 952 ‡e |
| items.ccode | 952 ‡8 |
| items.cn_sort | 952 ‡6 |
| items.cn_source | 952 ‡2 |
| items.coded_location_qualifier | 952 ‡f |
| items.copynumber | 952 ‡t |
| items.damaged | 952 ‡4 |
| items.damaged_on | (automaattisesti aikaleima) |
| items.dateaccessioned | 952 ‡d |
| items.datelastborrowed | 952 ‡s |
| items.datelastseen | 952 ‡r |
| items.deleted_on | (automaattisesti aikaleima) |
| items.enumchron | 952 ‡h |
| items.exclude_from_local_holds_priority | ei mäppäystä |
| items.holdingbranch | 952 ‡b |
| items.homebranch | 952 ‡a |
| items.issues | 952 ‡l |
| items.itemcallnumber | 952 ‡o |
| items.itemlost | 952 ‡1 |
| items.itemlost_on | (automaattisesti aikaleima) |
| items.itemnotes | 952 ‡z |
| items.itemnotes_nonpublic | 952 ‡x |
| items.itemnumber | 952 ‡9 |
| items.itype | 952 ‡y |
| items.location | 952 ‡c |
| items.materials | 952 ‡3 |
| items.more_subfields_xml | ei mäppäystä |
| items.new_status | ei mäppäystä |
| items.notforloan | 952 ‡7 |
| items.onloan | 952 ‡q |
| items.permanent_location | (automaattisesti location-kentän mukaisesti) |
| items.price | 952 ‡g |
| items.renewals | 952 ‡m |
| items.replacementprice | 952 ‡v |
| items.replacementpricedate | 952 ‡w |
| items.reserves | 952 ‡n |
| items.restricted | 952 ‡5 |
| items.stack | ei mäpppäystä |
| items.stocknumber | 952 ‡i |
| items.sub_location | 952 ‡j |
| items.timestamp | (automaattisesti aikaleima) |
| items.uri | 952 ‡u |
| items.withdrawn | 952 ‡0 |
| items.withdrawn_on | (automaattisesti aikaleima) |

## 20. MARC-kuvailupohjan testaus

MARC-kuvailupohjan testaus -toiminto testaa nimensä mukaisesti, että kuvailupohjissa on kaikki kunnossa. Sivulla kannattaa käydä aina sen jälkeen, kun muuttaa kuvailupohjia ja korjata mahdolliset virheet.
![](/assets/files/docs/Asetukset/kuvailupohjantestaus.png)

* itemtypeä ei ole liitetty -ilmoitukseen ei tarvitse reagoida, koska meillä on määritetty 942c-kenttään auktorisoiduksi arvoksi MTYPE eli aineistotyyppi.
* yhden MARC-kentän osakentät pitäisi pääsääntöisesti pitää samalla välilehdellä.

## 21. Auktoriteettityypit

Auktoriteettityypeissä määritetään Kohan sisäisten auktoriteetien kuvailupohjat. Näitä ovat esim. Yhteisön nimi ja henkilön nimi. Auktoriteeteille on oma määrittelynsä [MARC21-formaatissa](https://marc21.kansalliskirjasto.fi/aukt/index.htm).

Tällä hetkellä Kohan auktoriteettejä ei käytetä ja ylläpidetä varsinkaan paikalliskannoissa kovin aktiivisesti. TäTiin tuodaan [Auktoriteettitietokanta Asterista](https://www.kiwi.fi/display/melinda/Auktoriteettitietokanta+Asteri) auktoriteettitietueita.

## 22. Luokitusjärjestelmät

Luokitusjärjestelmillä määritetään, mitä luokitusjärjestelmiä käytetään ja miten items.itemcallnumber-kentän tiedot normalisoidaan items.cn_sort-kenttään. Jälkimmäisen mukaan tehdään mm. luokan mukaan järjestäminen tiedonhaussa.

![](/assets/files/docs/Asetukset/luokitusjarjestelmat.png)

### 22.1 Luokitusjärjestelmät

Koha-Suomessa on käytössä ykl-luokitusjärjestelmä. Mikäli sellaista ei ole, lisää sellainen _Uusi luokitusjärjestelmä_ -napin kautta.

![](/assets/files/docs/Asetukset/luokitusjarjestelmat2.png)

* _Luokituksen lähdekoodi_: Luokitusjärjestelmän tunniste, esim. ykl
* _Kuvaus_: Selkokielinen kuvaus luokitusjärjestelmälle
* _Lähde käytössä?_: Tähän pitää laittaa rasti, jotta luokitusjärjestelmää voisi käyttää.
* _Luokitusopas_: Tässä on Koha-Suomessa käytössä kahta eri versiota, outi ja lumme. Katso tarkemmin alempaa.
* _Katkaisusääntö_: Tällä voi määrittää katkaisusäännön. Tällä ei ole merkitystä Koha-Suomen ympäristöissä.

Tältä näyttää ykl-luokitusjärjestelmän tiedot:
![](/assets/files/docs/Asetukset/luokitusjarjestelmat1.png)

### 22.2 Luokitusoppaat

Luokitusoppailla määritetään, miten signum items.itemcallnumber-kentästä normalisoidaan items.cn_sort-kenttään. cn_sort-kenttää taas käytetään tiedonhaussa luokan mukaan järjestämiseen. Koha-Suomella on kaksi versioita outi ja lumme.

* outi on tarkoitettu signumeille, joissa luokka on toisena arvona signumissa. Esim. AIK 84.2 PAA tai ROAIK 84.2 PAA. Tieto siirtyy cn_sort-kenttään täten muodossa 84.2 PAA
* lumme on tarkoitettu signumeille, jotka alkavat luokalla. Esim. 84.2 PAA AIK. Tieto siirtyy samassa muodossa cn_sort-kenttään, koska luokkatieto on jo ensimmäisenä.

Valitse käyttöön outi tai lumme sen mukaan, minkä muotoisia kimpan signumit ovat.

## 23. Tietueiden täsmäytyssäännöt

## 24. Tietueiden yhdistämisssäännöt

Tietueiden yhdistämissäännöillä määritetään, mitä tehdään kuvailutietueen kentille, kun tietueita muokataan tai korvataan ulkopuolisesta lähteestä. MARC-kentän voi esim. suojata poistamiselta tai suojata niin, että sen sisältöä ei voi muuttaa.

![](/assets/files/docs/Asetukset/yhdistamissaannot.png)

### 24.1 Säännön lisääminen

Kun lisää säännön, valitaan ensin _Osio_. Vaihtoehtoja ovat:

* Lähde eli missä Kohan osiossa sääntö pätee. Esim. kuvailueditorissa.
* Käyttäjäkategoria eli mitä asiakastyyppiä sääntö koskee.
* Käyttäjätunnus eli mitä käyttäjiä sääntö koskee.

_Suodata_-sarakkeen vaihtoehdot riippuvat siitä, mitä on valittu _Osiossa_.

Kun on valittuna _Lähde_, on vaihtoehdot seuraavat:
* \*-merkki eli sääntö koskee kaikkia paikkoja, joissa tietueita voidaan muokata
* Tietueiden muokkaus eräajona
* Virkailijatyökalun MARC-muokkaus - eli kuvailueditori
* Välivarastoitujen MARC-tietueiden tuonti
* Z39.50 - eli Z39.50/SRU-haku. Tämä koskee myös Koha-Suomen valutustoimintoa.
* import_lexile.pl (ei tietoa, mikä tämä on)

Kun valittuna on  _Käyttäjäkategoria_, tulevat vaihtoehdot Asiakastyyppeihin määritetyistä tyypeistä.

Kun valittuna on _Käyttäjätunnus_, tulee esille kenttä, johon voi kirjoittaa käyttäjätunnuksen.

_Kenttä_-sarakkeeseen kirjoitetaan, mitä MARC-kenttää sääntö koskee. Tässä ei voi olla osakenttiä. Mahdollisia tapoja on:
* tarkka kenttä, esim. "650".
* säännöllinen lauseke (regex), esim. "6..", jolloin kaikki 6xx-kentät täsmää sääntöön.
* villikorttisääntö "\*", joka täsmää kaikkiin MARC-kenttiin.

Tarkin sääntö toteutetaan ensin, jos sääntöjä on useampi.

### 24.2 Valmiit säännöt

_Asetettu_-sarakkeesta voi valita valmiin säännön, jolloin seuraaviin sarakkeisiin tulee valmiiksi sitä koskevat valinnat. Vaihtoehtoja ovat:
* Mukauta, jolla voi tehdä oman säännön.
* Suojaa, joka estää kaikki kentän ylikirjoitukset/korvaukset
* Korvaa, joka sallii kaikki päivitykset vastaaviin kenttiin.
* Lisää uusi, joka sallii kentän lisäämisen, jos alkuperäisessä tietueessa ei ole kyseistä kenttää.
* Lisää ja liitä, joka sallii kentän liittämisen, mutta ei poistamista tai korvaamista.
* Suojaa poistamiselta, joka sallii kaikki päivitystoiminnot paitsi poiston

### 24.3 Mukautetut säännöt

_Lisätty_: Sääntö toteutetaan uusille tuotavan tietueen kentille, jos alkuperäisessä tietueessa ei ole kyseistä kenttää. Jos valittuna on _Lisää_, lisätään kenttä, jos _Ohita_, kentän sisältö heitetään menemään.

_Liitetty_: Jos kummassakin tietueessa on sama kenttä samalla sisällöllä, Liitetty-sääntö toteutetaan tulevalle tietueelle, mutta ei alkuperäiselle. Jos valittuna on _Lisätty_, lisätään ne alkuperäiseen tietueeseen, jos _Ohita_, kentän sisältö heitetään menemään.

_Poistettu_ (removed): Jos kummassakin tietueessa on sama kenttä, Poistettu (removed) -sääntö toteutetaan alkuperäiselle tietueelle. Jos valittuna on _Poistettu_, kentän sisältö poistetaan, jos _Ohita_, kentän sisältö pidetään.

_Poistettu_ (deleted): Jos alkuperäisessä tietueessa on kenttiä, joita tulevassa ei ole, Poistettu (deleted) -sääntö toteutetaan tulevalle tietueelle. Jos valittuna on _Poistettu_, kenttä poistetaan alkuperäisestä tietueesta, jos _Ohita_, kentän sisältö säilytetään.


## 25. OAI-joukkojen asetukset

## 26. Nidehakukentät

## 27. Haun rajaukset

Haun rajauksilla voi luoda tiedonhaussa linkkejä fasettien yläpuolelle tallennettuihin hakuihin. Tällä on toteutettu esim. Emokohde/osakohde-"fasetit". Vaatii, että SavedSearchFilters-järjestelmäasetus on päällä. Jotta käyttäjä voi lisätä hakurajauksia, pitää hänellä olla käyttäjäoikeus _manage_search_filters_.

![](/assets/files/docs/Asetukset/haunrajaukset.png)

Haun rajaukset voi tehdä tiedonhausta käsin ja niitä voi muokata sen jälkeen Haun rajaukset -sivulla.

![](/assets/files/docs/Asetukset/haunrajaukset1.png)

Haun rajauksen saa tehtyä tekemällä ensin haluamansa haun ja sitten valitsemalla hakutulosten yläpuolelta _Tallenna haku rajauksena_

![](/assets/files/docs/Asetukset/haunrajaukset2.png)

* _Näkyvyys_: Valitse, näytetään hakurajaus verkkokirjastossa ja/tai virkailijaliittymässä. Verkkokirjastolla tarkoitetaan Kohan omaa verkkokirjastoa, jota meillä ei ole käytössä. Ei vaikuta siis Finnaan.
* _Tallenna uutena haun rajauksena_: Anna tässä kohtaa hakurajaukselle kuvaava nimi ja valitse _Tallenna_
* _Korvaa olemassa oleva haun rajaus_: Jos haluat korvata jo olemassa olevan haun rajauksen, valitse tästä korvattava rajaus ja valitse _Korvaa_.

### 27.1 Ohje Emokohde- ja Osakohde -fasettien lisäämiseen

Ohje: 
* Laita päälle SavedSearchFilters-järjestelmäasetus. 
* Tee haku bib-level:("a") -> Klikkaa hakutuloslistan saatuasi _Tallenna haku rajauksena_ 
![kuva](https://user-images.githubusercontent.com/33121325/222130824-f0a74f08-b16f-4ddf-9d0d-50fa3598d88c.png)
  * Laita rasti kohtaan _Näytä virkailijaliittymässä?_
  * Anna haulle nimi **Osakohde** tai **Rajaa osakohteisiin** ja tallenna. 
  * Voit myös korvata jonkin aiemman rajauksen, jos olet harjoitellut tekemistä aiemmin.
* Tee uusi haku bib-level:("m") -> Klikkaa _Tallenna haku rajauksena_ 
![kuva](https://user-images.githubusercontent.com/33121325/222131310-15e9b6f7-ec88-4872-ac43-815ac7e6be92.png)
  * Laita rasti kohtaan _Näytä virkailijaliittymässä?_
  * Anna haulle nimi **Emokohde** tai **Rajaa emokohteisiin** ja tallenna.
  * Voit myös korvata jonkin aiemman rajauksen, jos olet harjoitellut tekemistä aiemmin.
* Rajauksia voi muokata jälkikäteen Ylläpito -> Haun rajaukset

**Huom!** Jos haluat rajauksiin laajemmin mukaan eri tyyppisiä tietueita, niin 
* emokohderajauksen voi tehdä myös tästä hausta: bib-level:m OR bib-level:c OR bib-level:i OR bib-level:s
* osakohderajauksen voi tehdä myös tästä hausta: bib-level:a OR bib-level:b OR bib-level:d


## 28. Hakukoneen asetukset (Elasticsearch)

## 29. Rahayksiköt ja vaihtokurssit

## 30. Budjetit

## 31. Tilit

## 32. EDI-tilit

## 33. Kirjasto-EANit

## 34. Tunnistustietojen tarjoajat

## 35. Z39.50/SRU-palvelimet

Z39.50/SRU-palvelimien ylläpidossa voi määrittää käyttöön Z39.50/SRU-palvelia. Osa palvelimista on vapaasti käytettävissä, osa vaatii esim. käyttäjätunnuksen ja salasanan.

### 35.1 Uusi Z39.50-palvelin

![](/assets/files/docs/Asetukset/z3950.png)

* _Palvelimen nimi_: Palvelimen selkokielinen nimi, josta käyttäjä tunnistaa sen helposti.
* _Palvelin_: Palvelimen osoite.
* _Portti_: Palvelimen portti.
* _Tietokanta_: Tietokannan nimi, tämän saa palvelimen ylläpitäjältä.
* _Käyttäjätunnus_: Käyttäjätunnus, jos palvelu vaatii sellaisen.
* _Salasana_: Salasanan, jos palvelu vaatii sellaisen.
* _Ennaltavalittu_: Jos tähän laittaa valinnan, tulee tietokanta Z39.50-hakua tehdessä automaattisesti valituksi haun kohteeksi.
* _Järjestys_: Tällä voi määrittää palvelimien keskinäisen järjestyksen haussa.
* _Määreet_: PQF-määreet, joita käytetään jokaisessa haussa.
* _Muoto_: Tietueiden formaatti, valitse MARC21
* _Merkistö_: Tietueiden merkistökoodaus, valitse utf8
* _Aikakatkaisu_: Tähän voi halutessaan lisätä aikakatkaisun, kuinka kauan tietoja haetaan palvelimelta. Jos tähän syöttää arvoksi 0, ei aikakatkaisu ole käytössä.
* _Tietuetyyppi_: Valitse, haetaanko bibliografisia tietueita vai auktoriteettitietueita.
* _XSLT Tiedosto(t) muunnettuihin tuloksiin_: Tietueiden tuontiin voidaan määrittää sääntöjä, joiden mukaan esimerkiksi tiputetaan tiettyjä kenttiä, kun tietue tuodaan omaan tietokantaan. Säännöt ovat erillisessä XSLT-tiedostossa, jonka osoite palvelimella laitetaan tähän kenttään. Tiedostoja voi olla useampi ja ne erotetaan toisistaan pilkulla.
  * Tällainen sääntötiedosto on meillä olemassa Libris-tietokannalle, jolloin kyseisen palvelimen tiedoissa tähän kenttään lisätään tiedosto-osoite /etc/koha/z3950/libris.xsl

### 35.2 Uusi SRU-palvelin

![](/assets/files/docs/Asetukset/sru.png)

* _Palvelimen nimi_: Palvelimen selkokielinen nimi, josta käyttäjä tunnistaa sen helposti.
* _Palvelin_: Palvelimen osoite.
* _Portti_: Palvelimen portti.
* _Tietokanta_: Tietokannan nimi, tämän saa palvelimen ylläpitäjältä.
* _Käyttäjätunnus_: Käyttäjätunnus, jos palvelu vaatii sellaisen.
* _Salasana_: Salasanan, jos palvelu vaatii sellaisen.
* _Ennaltavalittu_: Jos tähän laittaa valinnan, tulee tietokanta Z39.50-hakua tehdessä automaattisesti valituksi haun kohteeksi.
* _Järjestys_: Tällä voi määrittää palvelimien keskinäisen järjestyksen haussa.
* _Määreet_: PQF-määreet, joita käytetään jokaisessa haussa.
* _Muoto_: Tietueiden formaatti, valitse MARC21
* _Merkistö_: Tietueiden merkistökoodaus, valitse utf8
* _Aikakatkaisu_: Tähän voi halutessaan lisätä aikakatkaisun, kuinka kauan tietoja haetaan palvelimelta. Jos tähän syöttää arvoksi 0, ei aikakatkaisu ole käytössä.
* _Tietuetyyppi_: Valitse, haetaanko bibliografisia tietueita vai auktoriteettitietueita.
* _Muut SRU-valinnat_: Muita SRU-määrityksiä.
* _SRU-hakukenttien vastaavuus_: Tällä asetuksella määritetään Kohan hakuindeksin ja SRU-palvelimen indeksien vastaavuus toisiinsa eli esim. mistä palvelimen kentästä haetaan tekijätietoa.
* _XSLT Tiedosto(t) muunnettuihin tuloksiin_: Tietueiden tuontiin voidaan määrittää sääntöjä, joiden mukaan esimerkiksi tiputetaan tiettyjä kenttiä, kun tietue tuodaan omaan tietokantaan. Säännöt ovat erillisessä XSLT-tiedostossa, jonka osoite palvelimella laitetaan tähän kenttään. Tiedostoja voi olla useampi ja ne erotetaan toisistaan pilkulla.

## 36. SMTP-palvelimet

## 37. Tarkoititko?

## 38. Taulujen asetukset

## 39. Äänihälytykset

## 40. Jaa käyttötilastojasi

## 41. Muut kentät

## 42. Pikanäppäimet
