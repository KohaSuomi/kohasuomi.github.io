---
title: 'Kohan ohje suomeksi'
permalink: /dokumentaatio/hankinta/
redirect_from:
  - /theme-setup/
toc: true
---

# 5. Hankinta

**Huomioitavaa:** Hankinnan tilejä ei saa poistaa, jotta tilastointi
toimisi oikein. Tilit voi sulkea halutessaan, eikä se vaikuta
tilastoihin.

Kohan Hankinta mahdollistaa tilausten teon ja budjetin seuraamisen.
Kirjastolle pitää olla määritettynä budjetti ja vähintään yksi tili,
jotta tilauksia voi tehdä.

- Mene: _Muita toimintoja -&gt; Hankinnat_

![](/assets/files/docs/Hankinta/hankinta1.png)

## 5.1 Budjetin lisääminen

Budjetin voi lisätä joko _Hankinnan_ kautta tai ylläpidosta _Hankinnan
asetusten_ kautta.

![](/assets/files/docs/Hankinta/hankinta02.png) tai ![](/assets/files/docs/Hankinta/hankinta2.png)

Klikkaa _Uusi budjetti_.

**Täytä seuraavat tiedot:**

- Budjetin alku- ja loppumispäivämäärä
- _Kuvaus_-kenttään laitetaan budjetille selkeä nimi (vähintään
  kirjaston nimi ja vuosi. Voi myös laittaa mitä budjetti koskee).
- _Yhteensä_-kenttään laitetaan budjetin summa.
- _Aktivoi budjetti_, jotta budjettia voi käyttää. _Vinkki:_ Kun
  budjettia ei enää haluta käyttää, muokkaa sitä ja valitse _Lukitse
  budjetti_.

![](/assets/files/docs/Hankinta/hankinta3.png)

**Tallenna** muutokset.

### 5.1.1 Budjetin sulkeminen

Kun budjettia ei enää tarvita, voi sen sulkea. HUOMIO! **Älä poista
budjettia tai tilejä**, koska se vaikuttaa tilastoihin. Jos budjetti tai
tilit poistetaan, ei saada enää siltä vuodelta hankintatilastoja. Lisäksi hankintatieto ei näy enää teoksen perustiedot-näytöllä Hankinta-välilehdellä.

Valitse vasemmasta reunasta _Budjetit_ ja etsi suljettava budjetti.

![](/assets/files/docs/Hankinta/hankinta301.png)

Valitse oikealta _Toiminnot_-napista _Sulje_

![](/assets/files/docs/Hankinta/hankinta302.png)

## 5.2 Tilin lisääminen

Budjettiin pitää lisätä _tilejä_, jotta sitä voi käyttää. Voit jakaa
määrärahoja esim. kirjastoittain, aineistoittain tai miten on tarve.
[Huomioi EditX-hankinnan
vaatimukset](https://tiketti.koha-suomi.fi/projects/koha-suomen-dokumentaatio/wiki/EditX-hankinta).
**Tilien luonti EDItX-ohjeistuksen mukaan on kriittisen tärkeää.**

Tilin voi lisätä kahdella tavalla

- Valitse juuri lisäämäsi budjetti klikkaamalla budjetin nimeä,
  jolloin avautuu uusi sivu. Valitse siellä _Uusi_ ja avautuvasta
  valikosta _Uusi tili kohteelle xxx_  
  ![](/assets/files/docs/Hankinta/hankinta4.png)

<!-- -->

- Valitse budjetin nimen kohdalla oikeanpuolimmaisesta sarakkeesta
  _Toiminnot_ ja sieltä _Lisää tili_  
  ![](/assets/files/docs/Hankinta/hankinta04.png)

Täytä tilin tiedot

![](/assets/files/docs/Hankinta/hankinta5.png)

Kolme ensimmäistä riviä ovat pakollisia täytettäviä.

- _Tilikoodi_ on uniikki koodi tilille. Huomioi EditX-hankinnan
  vaatimukset.
- _Tilin nimi_ kannattaa olla selkeä ja helposti ymmärrettävä.
  Kimpoissa kannattaa käyttää kirjaston nimeä ensimmäisenä sanana
  budjetin nimessä.
- _Summassa_ voi olla vain numeroita ja desimaalierotin, ei muita
  merkkejä. Summa ei voi ylittää budjetille määritettyä
  kokonaissummaa.
- _Varoituskohta_ (%) tai (summa) voidaan merkitä halutessa, näin Koha
  varoittaa ennen kuin ylität tietyn määrän käytetyistä määrärahoista.
- _Omistaja_ on se henkilö, joka voi tehdä muutoksia tiliin.
  Käyttäjäksi voi lisätä käyttäjätunnuksia, joilla on hankinnan
  oikeudet (toiminnossa virhe: pääkäyttäjiä ei voi ohjeista huolimatta
  lisätä käyttäjiksi). Hae käyttäjätunnuksella tai nimellä ja klikkaa
  _Lisää_. Saat ilmoituksen “Asiakas ‘xxx’ lisätty.”, jonka jälkeen
  klikkaa _Sulje_.  
  ![](/assets/files/docs/Hankinta/hankinta05.png)
- _Käyttäjä_ voi omistajan lisäksi käyttää tiliä, mutta ei voi tehdä
  muutoksia sen tietoihin. Lisääminen samalla tavalla kuin
  Omistaja-kohdassa, myös sama virhe esiintyy tässä.
- _Kirjasto_, jonka tilistä on kysymys, valitaan alasvetovalikosta.
- _Rajoita käyttö:_ valitse valikosta, ketkä saavat käyttää tiliä.
  Kimpoissa kannattaa rajauksia tehdä, jotta kaikille ei näy kaikkien
  kirjastojen tilit (nopeuttaa manuaalisten tilausten tekemistä).  
  ![](/assets/files/docs/Hankinta/hankinta6.png)
- _Muuta:_ tähän voit kirjoittaa tarvittavan huomautuksen, joka tulee
  näkyviin tiliä käytettäessä.
- _Tilasto 1:n muoto_ ja _Tilasto 2:n muoto_: näihin voi halutessaan
  valita auktorisoidun arvon. Ei suositeltavaa.

Tallenna lopuksi _OK_-painikkeesta.

Hankinnan etusivulla näkyy kaikki tilit.  
![](/assets/files/docs/Hankinta/hankinta7.png)

Voit piilottaa näkyviltä käytöstä poistetut budjetit klikkaamalla
_Piilota käytöstä poistetut budjetit_. Takaisin näkyviin ne saa
klikkaamalla _Näytä käytöstä poistetut budjetit_.

Jos haluat nähdä, mitä teoksia on tilattu tiettyä tiliä käyttäen,
klikkaa tilin kohdalla Tilattu-sarakkeessa linkkinä olevaa summaa.  
![](/assets/files/docs/Hankinta/hankinta8.png)

Lue lisää budjetin/tilin käytöstä luvussa _5.9. Budjetointi ja tilien
seuranta._

## 5.2 Toimittaja

Ennen ensimmäisen tilauksen tekemistä pitää olla vähintään yksi
toimittaja tallennettuna.

### 5.2.1 Lisää toimittaja

Lisätäksesi toimittajan klikkaa _Uusi toimittaja_ -nappia
_Hankinnat_-sivulla.  
![](/assets/files/docs/Hankinta/hankinta9.png)

Toimittajan lisäyslomake koostuu kolmesta osasta.

- Ensimmäinen osio sisältää toimittajan yhteystiedot.  
  ![](/assets/files/docs/Hankinta/hankinta10.png)
  - Näistä kentistä vain _Nimi_-kenttä on pakollinen (punaisella,
    \*), muu tieto helpottaa laskutuksen ja reklamoinnin
    tekemisessä.

<!-- -->

- Toinen osio koostuu yhteyshenkilön tiedoista.  
  ![](/assets/files/docs/Hankinta/hankinta11.png)
  - Mikään näistä tiedoista ei ole pakollinen.

<!-- -->

- Viimeinen osio sisältää aineiston hintoihin liittyviä tietoja.  
  ![](/assets/files/docs/Hankinta/hankinta12.png)
  - Toimittajan tulee olla _Aktiivinen_, jotta tilauksen voi tehdä
  - _Lista- ja laskuhinnat_ näkyvät tietyssä valuutassa, joka
    tallennetaan järjestelmäasetuksissa
  - _Veronumero_ (ei tietoa onko Suomessa käytössä)
  - Valitse, ovatko _lista- ja laskuhinnat verollisia vai
    verottomia_.
  - Tallenna veroprosentti, jos kirjastolta veloitetaan verot
    tilauksesta
  - Jos toimittaja antaa yleisen alennuksen aineistosta, laita
    alennusprosentti _Alennus_-kenttään
    - Voit antaa niteeseen kohdistuvan oikean alennusprosentin
      tilausta tehtäessä
  - Jos tiedät normaalin toimitusajan aineistolle, voit antaa
    _toimitusajan_ päivinä. Tästä Koha pystyy arvioimaan, milloin
    tilaus joutuu myöhässä olevien tilausten raporttiin.
  - _Muuta_-kenttä on sisäiseen käyttöön tuleva huomautus.

### 5.2.2. Näytä/muokkaa toimittajaa

Nähdäksesi toimittajan tiedot, tulee ensin tehdä haku
_Hankinnat_-etusivulla. Voit hakea myös toimittajan nimen osalla.

![](/assets/files/docs/Hankinta/hankinta13.png)  
![](/assets/files/docs/Hankinta/hankinta14.png)

Kun klikkaat linkkinä olevaa toimittajan nimeä, näet toimittajan tiedot.

![](/assets/files/docs/Hankinta/hankinta15.png)

Jos haluat tehdä muutoksia toimittajan tietoihin, klikkaa _Muokkaa
toimittajaa_ -nappia. Jos toimittajalla ei ole yhtään tilausta, silloin
on näkyvillä myös _Poista toimittaja_ -nappi. Muuten on näkyvillä
_Vastaanota tilauksia_ -nappi.

![](/assets/files/docs/Hankinta/hankinta16.png)

### 5.2.3 Toimittajan sopimukset

Voit määritellä sopimuksia (joilla alku- ja loppupäivämäärä) ja liittää
ne toimittajaan. Sopimusten avulla voit vuoden lopussa nähdä kuinka
paljon kullekin toimittajalle on maksettu.

#### 5.2.3.1 Lisää sopimus

Toimittajan tietojen sivun yläreunassa on _Uusi -&gt; Sopimus_.

![](/assets/files/docs/Hankinta/hankinta17.png)

Saat lomakkeen, johon pitää tallentaa perustiedot sopimuksesta.

![](/assets/files/docs/Hankinta/hankinta18.png)

**Tärkeää:** Et voi tallentaa sopimusta jälkikäteen. Loppupäivämäärä ei
saa olla ennen kuluvaa päivää.

Kun sopimus on tallennettu, se näkyy toimittajan tiedoissa alhaalla.

![](/assets/files/docs/Hankinta/hankinta19.png)

Sopimuksen voi valita alasvetovalikosta, kun luot tilauskoria.  
![](/assets/files/docs/Hankinta/hankinta20.png)

## 5.3 Hankintaehdotukset

Kohassa on toiminto, jolla pystyy tekemään ja käsittelemään
hankintaehdotuksia. Tehdyt hankintaehdotukset näkyvät
_Hankinnat_-sivulla toimittajahaun oikealla puolella.  
![](/assets/files/docs/Hankinta/hankinta21.png)

Hankintaehdotus näkyy myös virkailijatyökalun etusivulla (niille, joilla
on oikeus käsitellä ehdotuksia)  
![](/assets/files/docs/Hankinta/hankinta22.png)

Klikkaamalla _Ehdotukset_ pääset näkemään ja muokkaamaan
hankintaehdotuksia. Jos odottavia ehdotuksia ei ole, pääset
hankintaehdotusten muokkaukseen klikkaamalla
_Hankintaehdotukset_-linkkiä _Hankinnat_-sivun vasemmassa reunassa.

![](/assets/files/docs/Hankinta/hankinta23.png)

### Hankintaehdotuksen tekeminen

Hankintaehdotuksia voi tehdä virkailijatyökalussa kirjaston puolesta tai
asiakkaan puolesta. Asiakkaat voivat tehdä hankintaehdotuksia Kohan
verkkokirjastossa (ei Finnassa tällä hetkellä).

#### Kirjaston puolesta

Hankintaehdotusten hallinnassa on nappula _Uusi hankintaehdotus_

![](/assets/files/docs/Hankinta/hankinta233.png)

#### Asiakkaan puolesta

Hae asiakkaan tiedot esille ja mene Hankintaehdotukset välilehdelle  
![](/assets/files/docs/Hankinta/hankinta231.png)

Täällä näkyvät asiakkaan tekemät hankintaehdotukset sekä nappula _Uusi
hankintaehdotus_, josta voi tehdä uuden ehdotuksen asiakkaan puolesta.

![](/assets/files/docs/Hankinta/hankinta232.png)

Täytä vähintään pakolliseksi merkityt tiedot (punaisella).

![](/assets/files/docs/Hankinta/hankinta234.png)

- _Ehdotuksen syy_ -valikosta voi valita valmiista vaihtoehdoista.

Lomakkeen alemmissa osioissa on ehdotuksen hallintaan ja ja
hankintatietoihin liittyviä tietoja:

![](/assets/files/docs/Hankinta/hankinta235.png)

- _Ehdotus luotu_ -kenttään tulee luontipäivä ja tekijän nimi. Jos
  ehdotus tehdään asiakkaan puolesta, tulee siihen asiakkaan nimi. Jos
  taas kirjaston puolesta, tulee siihen ehdotuksen tehneen virkailijan
  nimi.
- Jos ehdotuksen haluaa kohdistaa tiettyyn kirjastoon, voi sen valita
  Hankintatiedot-osiosta Kirjasto-kohdasta

### Hankintaehdotusten ylläpitäminen

![](/assets/files/docs/Hankinta/hankinta24.png)  
Hankintaehdotukset lajitellaan eri välilehtiin niiden tilan mukaan:
_Hyväksytty, Odottaa, Tarkistettu, Tilattu ja Hylätty_. Jokaisessa
hyväksytyssä tai hylätyssä ehdotuksessa näkyy sen käsitelleen henkilön
nimi ja syy, joka on tallennettu ehdotuksen hyväksymiselle tai
hylkäämiselle (löytyy _Tila_-sarakkeesta).

- _Hyväksytty_-tila on ehdotuksella, jolle on valittu _Hyväksytty_
  alasvetovalikosta.
- _Odottaa_-tila on niillä ehdotuksilla, joita ei ole vielä käsitelty.
- _Tarkistettu_-tila on ehdotuksella, jolle on valittu _Tarkistettu_
  alasvetovalikosta.
- _Tilattu_-tila on niillä ehdotuksilla, jotka on tilattu käyttämällä
  _Lisää tilaus tilauskoriin Hankintaehdotuksesta_-linkkiä.
- _Hylätty_-tila on ehdotuksella, jolle on valittu _Hylätty_
  alasvetovalikosta.

Jos kirjastoon tulee paljon hankintaehdotuksia, niitä voi suodattaa
käyttämällä vasemman reunan valikoita.  
![](/assets/files/docs/Hankinta/hankinta25.png)  
Klikkaamalla sinistä otsikkoa (linkki) saat avattua valikon tarkempaan
suodatukseen ja klikkaamalla _<span lang="tyhjennä"></span>_ kaikki
suodattimet tyhjennetään ja näet kaikki hankintaehdotukset.

**Vinkki:** Hankintaehdotukset rajoitetaan automaattisesti kirjastoosi
tehtyihin ehdotuksiin. Jos haluat nähdä kaikkien (tai jonkun muun
kirjaston) hankintaehdotukset, klikkaa _Hankintatiedot_-linkkiä
suodattaaksesi haluamasi kirjaston.

![](/assets/files/docs/Hankinta/hankinta26.png)

Kun katsot _Odottaa_-tilassa olevia ehdotuksia, voit tehdä valinnan
kunkin nimekkeen vasemmalla puolella olevaan laatikkoon ja valita näille
nimekkeille tilan alla olevasta valikosta ja syyn valinnalle. Voit myös
kokonaan poistaa ehdotuksen _Poista valitut_ -valinnalla.

![](/assets/files/docs/Hankinta/hankinta27.png)

Voit myös muokata hankintaehdotuksen tietoja ennen hyväksymistä.  
![](/assets/files/docs/Hankinta/hankinta28.png)

Klikkaamalla _Muokkaa_ ruudun yläreunassa voit päästä muokkaamaan
hankintaehdotusta.  
![](/assets/files/docs/Hankinta/hankinta29.png)

Tällä näytöllä voit antaa ehdotukselle lisäinformaatiota tai korjata
asiakkaan antamia tietoja. Voit myös muuttaa ehdotuksen tilan eli
hyväksyä tai hylätä ehdotuksen.

- Jos valitset tilaksi Odottaa, ehdotus menee takaisin
  Odottaa-välilehdelle.

Voit valita Hyväksymisen tai hylkäämisen syyn alasvetovalikosta. Jos
valikosta puuttuu jokin paljon käyttämäsi syy, ota yhteyttä kimppasi
pääkäyttäjään. Hän pystyy lisäämään valikkoon uusia vaihtoehtoja.  
![](/assets/files/docs/Hankinta/hankinta30.png)

Jos valitset syyksi _Muut…_ , saat kehotuksen syöttää syyn
tekstilaatikkoon. Klikkaamalla _Peruuta_ laatikon oikealla puolella saat
takaisin syyvalikon.

![](/assets/files/docs/Hankinta/hankinta31.png)

Kun olet klikannut _OK_, ehdotus menee sopivalle välilehdelle. Tila
vaihtuu myös asiakkaan tiedoissa verkkokirjastossa ja asiakkaalle lähtee
sähköpostiviesti ehdotuksen hyväksymisestä/hylkäämisestä.

![](/assets/files/docs/Hankinta/hankinta32.png)

## 5.4 Tilausten teko

Kun teet tilauksen, aloita hakemalla toimittajan tiedot.  
![](/assets/files/docs/Hankinta/hankinta33.png)

### 5.4.1 Tilauksen luominen

Hae ensin toimittajan tiedot.

![](/assets/files/docs/Hankinta/hankinta40.png)

Klikkaa _Uusi tilauskori_ -nappia toimittajan nimen oikealla puolella.

**Vinkki:** Voit lisätä nimekkeitä myös olemassa olevaan tilaukseen
klikkaamalla _Lisää tilauskoriin_ kunkin tilauksen rivin oikeassa
laidassa. Jos tilaus on jo suljettu, silloin siihen ei voi lisätä
tilauksia.

Uutta tilauskoria varten täytyy täyttää muutamia tietoja:

![](/assets/files/docs/Hankinta/hankinta41.png)

- Tilauskorille on annettava nimi, jonka avulla se on helpompi
  tunnistaa myöhemmin.
- Laskutuspaikan ja toimituspaikan oletusarvona on se kirjasto, mihin
  olet kirjautuneena, mutta voit vaihtaa nämä arvot alasvetovalikosta
- Toimittajaksi tulee juuri hakemasi toimittaja, mutta voit myös
  vaihtaa sen alasvetovalikosta
- Huomautuskentät ovat valinnaisia ja niihin voi lisätä mitä tahansa
  tietoa.

Jos toimittajallesi on tallennettu sopimuksia, voit valita sopimuksen
alasvetovalikosta.

Klikkaa lopuksi _Tallenna_.

![](/assets/files/docs/Hankinta/hankinta42.png)

Kun tilaus on luotu, voit lisätä siihen nimekkeitä, joita tilataan.
Aloita klikkaamalla _Lisää tilauskoriin_ -nappia.

Valitse sitten, miten haluat lisätä nimekkeen:

![](/assets/files/docs/Hankinta/hankinta421.png)

Ensin esitellään kaikki eri tavat lisätä tilaus, lopussa kerrotaan Nide-
ja tilitystietojen lisääminen.

#### 5.4.1.1. Olemassa olevasta tietueesta

- Jos tilaat lisäkappaleita olemassa olevaan nimekkeeseen, voit
  yksinkertaisesti hakea kyseisen tietueen haulla.  
  ![](/assets/files/docs/Hankinta/hankinta43.png)

Hakutuloksessa klikkaa _Tilaus_-linkkiä.  
![](/assets/files/docs/Hankinta/hankinta44.png)

\* Kaikki tilauksessa tarvittavat luettelointitiedot on jo
tilaustiedoissa mukana.

#### 5.4.1.2. Hankintaehdotuksesta

**Huomioi:** Jos kimpalla/kirjastolla on Finna käytössä
verkkokirjastona, ei asiakkaat pysty tällä hetkellä tekemään suoraan
Kohaan tulevia hankintaehdotuksia.

- Asiakkaiden tekemistä hankintaehdotuksista voi tehdä tilauksen.
  Jotta hankintaehdotukset ja tilaukset pysyisivät järjestyksessä,
  kannattaa tilaus tehdä hankintaehdotuksen linkin kautta.  
  ![](/assets/files/docs/Hankinta/hankinta45.png)
  - Tuloksista klikkaa _Tilaus_-linkkiä sen nimekkeen kohdalla,
    minkä haluat tilata ja saat lomakkeen, jossa on valmiina
    tilaukseen liittyviä tietoja sekä linkki hankintaehdotukseen.

![](/assets/files/docs/Hankinta/hankinta46.png)

\* Voit tehdä muutoksia tietoihin tarvittaessa.

\* Tilaukorissa näkyy nimekkeen kohdalla linkki hankintaehdotukseen ja
ehdotuksen tekijän nimi.  
![](/assets/files/docs/Hankinta/hankinta47.png)

Hankintaehdotusten perusteella tehdyistä tilauksista lähtee asiakkaalle
sähköpostiviesti, jossa kerrotaan tehdystä tilauksesta. Myös
verkkokirjastossa asiakas näkee hankintaehdotuksensa tilan.

#### 5.4.1.3. Lehtitilauksesta

Kun käytät _Kausijulkaisut_-osiota, voit linkittää lehtitilauksen tiedot
hankintaan valitsemalla _Lehtitilauksesta_.

- Klikkaamalla tilauslinkkiä pääset hakusivulle, josta voit hakea
  lehtitilauksen tiedot.  
  ![](/assets/files/docs/Hankinta/hankinta48.png)

Hakemasi lehden tilaustiedot tulevat näytölle ja oikeassa reunassa
olevassa sarakkeessa on _Tilaus_-linkki.  
![](/assets/files/docs/Hankinta/hankinta49.png)

Klikkaamalla Tilaus saat lehtitilauksen tiedot tilauslomakkeelle ilman
Lisää nide -osiota, koska lehtitilauksessa sitä ei tarvita.  
![](/assets/files/docs/Hankinta/hankinta50.png)

#### 5.4.1.4. Uudesta (tyhjästä) tietueesta

Jos tilaat sellaisen teoksen, jonka tietoja ei löydy valmiina mistään,
valitse _Uudesta (tyhjästä) tietueesta_.  
![](/assets/files/docs/Hankinta/hankinta51.png)

- Anna tyhjään lomakkeeseen kaikki tarvittavat tiedot tilauksesta.
  Huom! Näin tehdyn tietueen tietoja pitää käydä jälkikäteen
  täydentämässä, jotta teos löytyy tiedonhaun kautta:
  - kenttä 000, ja siinä heti ensimmäinen rivi kenttä nro 00. Rivin
    päässä on nk. tag –merkki, klikkaa se auki, jolloin saat auki
    nk. Nimiövalikon, ja sieltä kohdan 7 = Tietueen bibliografinen
    taso. Itse tehdyssä tietueessa se tarjoaa “Osakohde
    monografiassa”, joka pitää muuttaa “Monografiaksi” eli M:ksi.
    Teetpä tilauksen mistä tahansa aineistosta tuo pitää käydä
    korjaamassa.
  - Välilehdellä 9 pitää käydä valitsemassa lisäksi aineistolaji.

#### 5.4.1.5. Ulkoisesta lähteestä (toinen tietokanta)

Jos haluat tehdä tilauksen toisen kirjaston luetteloimien tietojen
perusteella, voit valita _Ulkoisesta lähteestä_. Kyseessä on
Z39.50-haku. Voit myös valita _Valitse MARC-luettelointipohja_
-kohdasta, mitä luettelointipohjaa käytetään tietueen tuomiseen.

![](/assets/files/docs/Hankinta/hankinta52.png)

Hakutuloksesta pääset valitsemaan oikealla olevasta linkistä _Tilaus_
sen nimekkeen, minkä haluat tilata.  
![](/assets/files/docs/Hankinta/hankinta53.png)

Jos tilaamasi nimeke näyttää olevan Kohan mielestä tuplatietue, saat
varoituksen ja valintavaihtoehtoja, mistä valitset sopivan toiminnon.
Voit tarkistaa linkistä, mikä tietokannan tietue Kohan mielestä on
sama.  
![](/assets/files/docs/Hankinta/hankinta531.png)

- Jos tietue on sama, valitse _Käytä olemassa olevaa tietuetta_
- Jos tietue ei ole sama, valitse _Luo uusi tietue_
- Jos haluat peruuttaa luettelointiedon tuonnin, valitse _Peruuta ja
  palaa tilaukseen_

Tähän tilauslomakkeeseen ei voi muuttaa luettelointitietoja. Jos haluat
tässä vaiheessa muokata tietueen tietoja, valitse _Muokkaa tietuetta_.  
![](/assets/files/docs/Hankinta/hankinta54.png)

#### 5.4.1.6. Tilaus väliaikaistiedostosta

Tilauksen voi tehdä myös aineistontoimittajan lähettämän tiedoston
kautta.

![](/assets/files/docs/Hankinta/hankinta55.png)

- Valitse haluamasi tiedosto ja klikkaa _Lisää tilauksia_. Voit
  järjestää listoja klikkaamalla sarakeotsikon perässä olevaa nuolta.

Avattu tilaustiedosto näyttää tältä. Jos nimeke on jo tallennettu
Kohaan, siinä näkyy linkkinä oleva numeropari nimekkeen edessä ja koko
nimeke on hennon vaaleanpunaisella pohjalla. Esim. punaisella korostettu
nimeke löytyy jo Kohasta, mutta numero 0 tarkoittaa, että käsittelijän
kirjastossa nimekettä ei vielä ole, mutta muissa kirjastoissa on
yhteensä 2. Kun kursorin vie numeron päälle, näkyy niiden kirjastojen
nidemäärät ko. nimekkeessä.  
![](/assets/files/docs/Hankinta/hankinta56.png)

Pitkässä listassa voit käyttää hakutoimintoa _Ctrl+f_, niin saat ruudun
vasempaa alareunaan hakulaatikon, jonka avulla voit etsiä haluamaasi
nimekettä.  
![](/assets/files/docs/Hankinta/hankinta57.png)

Tiedostosta klikkaat valintaruutua sen nimekkeen vasemalla puolella,
minkä haluat tilata. Niteiden määrän oletusarvo on 1, joten jos tilaat
useamman, vaihda tähän oikea numero tilattavien niteiden mukaan.  
![](/assets/files/docs/Hankinta/hankinta58.png)

Nidetiedot-välilehdellä voit käydä tekemässä sellaisia valintoja, jotka
koskevat kaikkia ko. tilauksen niteitä (esim. hyllypaikka).  
![](/assets/files/docs/Hankinta/hankinta59.png)

Kun olet merkinnyt kaikki tilattavat nimekkeet ja niiden nidemäärät,
siirry ikkunan yläreunassa _Tilitystietojen oletusarvot_ -välilehdelle.
Siellä valitaan alasvetovalikosta oikea tili tilaukselle.  
![](/assets/files/docs/Hankinta/hankinta60.png)

Klikkaa _Tallenna_, kun tilauksesi sisältää kaikki haluamasi nimekkeet.

#### 5.4.1.7. Varatuimpien nimekkeiden listalta

Listalle tulee teokset, joilla on eniten varauksia per nide.

![](/assets/files/docs/Hankinta/hankinta64.png)

- Varauksia per nide -suhdetta voi säätää vasemmasta reunasta
- Jos haluat, että tilattu-tilaiset niteet otetaan mukaan, laita rasti
  kohtaan _Sisällytä tilatut_ (tämä kannattaa laittaa)
- Oikeasta reunasta Tarvitaan lisäniteitä -sarakkeesta klikkaamalla
  pääsee lisäämään teoksen tilauskoriin

#### 5.4.1.8. Tilattavien niteiden tiedot

Kun olet tuonut nimeketiedot tavalla tai toisella, täytyy täyttää
tilattavien niteiden tiedot (vähintään 1 nide). Pakolliset tiedot on
merkitty punaisella.  
![](/assets/files/docs/Hankinta/hankinta62.png)

- Jos luot vain yhden niteen, klikkaa _Lisää nide_
- Jos haluat luoda useamman niteen, klikkaa _Lisää useita niteitä_,
  jolloin painikkeen viereen tulee kenttä. Kirjoita kenttään haluttu
  nidemäärä ja klikkaa _Lisää_

Niteet listautuu Nide-osion yläpuolelle.  
![](/assets/files/docs/Hankinta/hankinta621.png)

Kun olet lisännyt tarvittavan määrän niteitä, täytä tilitystiedot.  
Huom. Desimaalierotin vaihtelee. Tilausta tehdessä numeroiden
desimaalierottimena tulee käyttää pistettä (tilanne 15.8.2019)

![](/assets/files/docs/Hankinta/hankinta63.png)

- **Määrä**-kohtaan tulee tilaamiesi niteiden määrä yllä olevasta
  taulukosta.
  - **Tärkeää**: Et voi lisätä käsin määrää, vaan se täytyy tehdä
    edellisen kohdan Lisää nide -toiminnon kautta.

<!-- -->

- **Tili**-valikosta valitaan käytettävä tili

<!-- -->

- **Rahayksikkö**-valikosta valitaan rahayksikkö

<!-- -->

- **Toimittajan hinta** annetaan ilman alennuksia.

<!-- -->

- Jos hinta on **vahvistamaton**, laita valinta ruutuun.
  - HUOM! Jos tilauksessa on yksikin vahvistamaton hinta, tilausta
    ei voi sulkea.

<!-- -->

- Anna **veroprosentti** aineiston mukaan (kuvassa väärä prosentti).
  - Kun olet antanut alennusprosentin, klikkaa tab-näppäintä, niin
    Koha täyttää loput hintatiedot.

Kun olet täyttänyt kaikki tarvittavat kentät, klikkaa _Tallenna_
lisätäksesi niteet tilaukseen. Jos hinta menee yli budjetin, saat siitä
huomautuksen.

Kun tilaus on tallennettu, saat yhteenvedon tilauksesta.

![](/assets/files/docs/Hankinta/hankinta641.png)

Jos haluat nähdä kaikki tiedot, laita valintamerkki ruutuun _Näytä
kaikki_.

![](/assets/files/docs/Hankinta/hankinta65.png)

Ennen tilauksen sulkemista voit vielä muokata tilauskoria ja siitä
tilauksia.

- Klikkaamalla _Peruuta teoksen tilaus_ poistat tilausrivin ja siihen
  liittyvät **kaikki** niteet, mutta tietue jää tietokantaan.

<!-- -->

- Klikkaamalla _Peruuta tilaus ja poista nimeketietue_ poistat sekä
  tilausrivin, niteet että nimeketietueen tietokannasta.
  - Nimeketietuetta ei voi poistaa, jos siihen kuuluu ennestään
    niteitä, tilauksia tai varauksia.

![](/assets/files/docs/Hankinta/hankinta66.png)

- Voit muokata tilauskorin nimeä ja muita tietoja klikkaamalla
  _Muokkaa tilauskoria_ -painiketta.
- Tilauskorin voi poistaa kokonaan _Poista tämä tilauskori_
  -painikkeesta.
- _Vie tämä tilaus CSV-muodossa_ -painikkeen kautta voit viedä
  tilauskorin tiedot CSV-muotoiseksi tiedostoksi.
- Sähköpostitilaus?

### 5.4.2. Tilauksen sulkeminen

Tilauskori pitää sulkea, jotta tilaukset voidaan vastaanottaa.
Sulkemisen yhteydessä tilauskorin voi halutessaan lisätä samannimiseen
tilausryhmään laittamalla rastin kohtaan “Lisää tämä tilauskori uuteen,
samannimiseen tilausryhmään”.

![](/assets/files/docs/Hankinta/hankinta67.png)

- **Huom!** Jos yhdenkään tilauksen hinta on vahvistamaton, tilausta
  ei voi sulkea.

### 5.4.3. Tilausryhmän tekeminen

Tilausryhmä on yksinkertaisesti ryhmä tilauksia. Joissakin kirjastoissa
eri henkilöt voivat luoda tilauksia, jotka sitten kootaan tietyn ajan
kuluttua yhteen ja tehdään niistä toimittajalle tilaus. Tilausryhmässä
voi olla siis yksi tai useampia tilauksia.

Kun klikkaat _Sulje tämä tilauskori_, saat varmistuskysymyksen. Voit
myös valita, lisäätkö tilauksen uuteen, samannimiseen listaryhmään vai
et.  
![](/assets/files/docs/Hankinta/hankinta67.png)

Uuden tilausryhmän luominen vie tilausryhmien sivulle, jossa voit
tulostaa tilauksen tai ladata sen CSV-muodossa tai EDIFACT-tilauksena.
Tilauskorin sulun yhteydessä tehdyt tilausryhmät menevät
“Suljettu”-välilehdelle.  
![](/assets/files/docs/Hankinta/hankinta68.png)

Tilausryhmiin pääsee myös kun hakee Hankinnan etusivulla ensin
toimittajan nimellä, ja valitsee sitten vasemmasta reunausta
_Tilausryhmät_.

![](/assets/files/docs/Hankinta/hankinta69.png)

### 5.4.4 EDItX-tilaaminen

Koha-Suomessa on käytössä EDItX-tilaussanomia käsittelevä rajapinta,
jolla toimittajan verkkokaupassa tehdyt tilaukset saadaan vietyä Kohan
tilauskoreiksi oikean toimittajan alle EDItX-tilaussanoman pohjalta.
Tilatuista teoksista lisätään minitietueet ja niteitä tilattu määrä.
Myös kirjaston budjettia/tilejä veloitetaan tilauksen mukaisesti.

![](/assets/files/docs/Hankinta/hankinta70.png)

Verkkokauppatilauksista syntyy Kohaan tilauskorit  
![](/assets/files/docs/Hankinta/hankinta701.png)

Tilaukset otetaan vastaan Kohan normaalin tilauksen vastaanoton
prosessin mukaan.

[Powerpoint](https://tiketti.koha-suomi.fi:83/documents/10)
EDItX-toiminnallisuuden käyttöönotosta

## 5.5. Tilausten vastaanottaminen

Tilauksia lähdetään vastaanottamaan toimittajan kautta. Hae ensin
toimittajan tiedot.

![](/assets/files/docs/Hankinta/hankinta71.png)

Klikkaa _Vastaanota tilauksia_.

![](/assets/files/docs/Hankinta/hankinta72.png)

Aineistoa vastaanotettaessa kysytään toimittajan laskun numeroa (tähän
voi laittaa esimerkiksi lähetyslistan tunnuksen). Jokaiselle
toimitukselle kannattaa tehdä oma laskunumeronsa. Jos käyttää aina
samaa, hidastuu vastaanotto.  
![](/assets/files/docs/Hankinta/hankinta73.png)

- Lähetyspäivämääräksi tulee automaattisesti kuluva päivä, sen voi
  muuttaa tarvittaessa.
- Postituskulut-kenttään voi halutessaan lisätä postikulut.
- Postikulut voi myös halutessaan ohjata tietylle tilille
  Postikulut:-valikosta. Huom! Älä valitse tähän mitään, jos et lisää
  postikuluja.

Huom. Desimaalierotin vaihtelee. Tilausta vastaanotettaessa numeroiden
desimaalierottimena tulee käyttää pilkkua (tilanne 15.8.2019)

Kun klikkaat _Seuraava_, saat sivun, josta ensisilmäyksellä saa kuvan,
ettei vastaanotettavia ole. Näin ei kuitenkaan ole. Voit nyt etsiä
vastaanotettavan teoksen kirjoittamalla/syöttämällä vasemman reunan
Suodata-laatikkoon esim. teoksen nimen alun, ISBN-numeron tai tekijän
nimestä alun. Valitse sitten “Suodata”

![](/assets/files/docs/Hankinta/hankinta96.png)

Klikkaa vastaanotettavan teoksen rivin oikeassa reunassa olevaa
_Vastaanota_-linkkiä.

![](/assets/files/docs/Hankinta/hankinta75.png)

Valitse vastaanotettava nide klikkaamalla ruutua
_Vastaanotettu?_-sarakkeessa tai kirjoittamalla vastaanotettava määrä
oikealla Vastaanotettu-kenttään. Jos kirjoitat oikealle numeron,
vasemmalle tulee vastaava määrä rasteja. Voit valita myös vain osan
niteistä, mikäli on saapunut osatoimitus.

![](/assets/files/docs/Hankinta/hankinta76.png)

- Voit myös vaihtaa käytettävän tilin halutessasi.
- _Muokkaa_-linkistä pääset muokkaamaan yksittäisen niteen tietoja.
  Muokkausnäyttö avautuu toiseen välilehteen.

Valitse lopuksi vasemmalta alhaalta _Tallenna_.

Tietueen tallennuksen jälkeen palaat takaisin tilauskoriin. Huomaa, että
jos käytit hakua, niin taulukko on edelleen rajattu näyttämään
hakuehtoa. Voit peruuttaa vastaanoton, mikäli valitsit vahingossa väärän
tietueen, klikkaamalla _Peruuta kuitti_, jolloin teos siirtyy takaisin
vastaanotettaviin.

![](/assets/files/docs/Hankinta/hankinta77.png)

Kun olet vastaanottanut koko lähetyksen, valitse alareunasta _Lopeta
vastaanotto_, jolloin ohjaudut kuittisivulle.  
![](/assets/files/docs/Hankinta/hankinta771.png)

- Laita rasti kohtaan _Suljettu_, jolloin lasku suljetaan, eikä jää
  turhaan avoimeksi.
- Valitse sitten _Tallenna_.

Pääset pois sivulta valitsemalla vasemmalta valikosta esim. Hankinnat.

## 5.6. Tilauksen peruminen

**Huom!** Tilausrivin poistaminen poistaa kaikki siihen liittyvät niteet

- myös jo lainassa olevat. Jos jotain teosta ei saadakaan kaikkia osia,
  ei saa poistaa koko riviä, koska silloin poistuu myös vastaanotetut
  niteet. Kohassa ei ole varsinaisesti olemassa osatoimitus-toimintoa.
  Poista saapumattomat niteet tiedonhaun kautta.

Hae toimittajan tiedoilla kuten tilausta vastaanotettaessa. Tilauksen
peruminen lähtee vastaanottonäkymästä.

![](/assets/files/docs/Hankinta/hankinta78.png)

Tee uusi lasku tai valitse mikä tahansa avoinna olevan laskun numero,
johon voit vastaanottaa tilauksen.

![](/assets/files/docs/Hankinta/hankinta79.png)

Hae peruttava tilaus teoksen hakutoiminnolla.

![](/assets/files/docs/Hankinta/hankinta80.png)

- Klikkaa _Peruuta teoksen tilaus_ -linkkiä, jolloin poistuu
  tilausriviin liittyvät niteet, mutta luettelointitiedot ja muiden
  niteet ja asiakkaiden varaukset säilyvät.
- Jos tilausriviin teokseen ei liity muita tilauksia, niteitä ja
  varauksia, voi poistaa myös nimekkeen _Peruuta teoksen tilaus ja
  nimeketietue_ -linkistä.

Saat varmistuskysymyksen tilauksen poistosta.

Jos poistat myös nimekkeen ilmoitetaan se varmistusviestissä  
![](/assets/files/docs/Hankinta/hankinta81.png)  
Jos taas et poista nimekettä, sekin kerrotaan varmistusviestissä  
![](/assets/files/docs/Hankinta/hankinta82.png)

- Voit valita halutessasi valikosta myös syyn peruutukselle.

## 5.7. Myöhässä olevien tilausten reklamointi

Jos olet tallentanut toimittajan sähköpostiosoitteen
toimittajatietoihin, voit lähettää reklamoinnin tilauksesta, jonka
toimitus on myöhässä. Sivu voi avautua hitaasti, jos myöhässä olevia on
paljon.

Valitse _Hankinnat_-sivulla vasemmasta reunasta _Myöhässä olevat_
-linkkiä

![](/assets/files/docs/Hankinta/hankinta831.png)

Pääset listauksen, jota voit suodattaa sivun vasemmassa reunassa
olevasta valikosta esimerkiksi tilauspäivän tai toimittajan mukaan.
Suodatus koskee vain suljettuja tilauksia.  
![](/assets/files/docs/Hankinta/hankinta83.png)

Kun tilauksia on suodatettu toimittajan mukaan, hakutulos näyttää tältä:

![](/assets/files/docs/Hankinta/hankinta84.png)

- Nimeketietojen vasemmassa reunassa on sarake, josta voi valita ne
  nimekkeet, joita halutaan reklamoida.
- Sivun alareunasta klikkaa _Reklamoi tilaus_, kun haluat reklamaation
  lähtevän toimittajalle.
- Voit myös tallentaa tiedot CSV-muodossa.

Kun sähköpostin lähetys onnistuu, tulee seuraava ilmoitus:  
![](/assets/files/docs/Hankinta/hankinta85.png)

HUOM! Arvioitu saapumispäivä perustuu toimittajan tiedoissa
tallennettuun _Toimitusaika_-arvoon.

## 5.8 Laskut

Laskuja pääsee hallinnoimaan hankinnnan etusivulta _Laskut_-linkistä.

![](/assets/files/docs/Hankinta/hankinta851.png)

Voit rajata hakua esim. laskunumeron, toimittajan, lähetyspäivän tai
teoksen nimen mukaan.

![](/assets/files/docs/Hankinta/hankinta852.png)

Saat listan hakuehtoja vastaavista laskuista. Tässä on haettu laskuja
toimittajan mukaan:  
![](/assets/files/docs/Hankinta/hankinta853.png)

- Voit yhdistää laskuja valitsemalla ne ja painamalla _Yhdistä
  valitut_ -nappia.

_Toiminnot_-napin alta löytyy lisää vaihtoehtoja

![](/assets/files/docs/Hankinta/hankinta854.png)

- Voit avata laskun tiedot tarkemaan katseluun
- Voit avata laskun uudelleen, jos se on suljettu
- Voit poistaa laskun

## 5.9. Hankinnan hakutoiminnot

Jokaisen hankintaosion sivun yläreunassa on pikahakulaatikko toimittajan
tai tilauksen hakua varten.

### Toimittajahaku

![](/assets/files/docs/Hankinta/hankinta86.png)

Toimittajahaussa voit hakea millä tahansa sanan osalla.

![](/assets/files/docs/Hankinta/hankinta87.png)

- Huom! Selain ehdottaa aikaisemmin kirjoittamiasi sanoja, jos olet
  sallinut sen selaimen asetuksissa. Koha ei ehdottele
  toimittajatietoja.

![](/assets/files/docs/Hankinta/hankinta88.png)

### Hankintahaku

Hankintahaussa voit hakea tilaamiasi nimekkeitä joko toimittajatietojen
kanssa tai ilman toimittajan nimeä. Nimekkeestä riittää myös osa, ei
tarvitse olla kokonaan.

![](/assets/files/docs/Hankinta/hankinta89.png)

![](/assets/files/docs/Hankinta/hankinta90.png)

Klikkaamalla plus-merkkiä hankintahaun oikealla puolella voit laajentaa
hakuehtoja.

![](/assets/files/docs/Hankinta/hankinta91.png)

Saat laajemman hakulomakkeen, kun valitset haun oikeassa reunassa olevaa
_Tarkka haku_ -linkkiä.

![](/assets/files/docs/Hankinta/hankinta92.png)

Tarkassa haussa pystyt hakemaan mm. ISBN-numerolla  
![](/assets/files/docs/Hankinta/hankinta921.png)

## 5.9. Budjetointi ja tilien seuranta

Hankinnan etusivulla on näkyvillä kaikki aktiiviset tilit.

![](/assets/files/docs/Hankinta/hankinta93.png)

- Voit suodattaa näkymää _Haku_-kentällä

Klikkaamalla jotain _Tilatttu_- tai _Käytetty_-sarakkeen summaa saat
näkyviin siihen tiliin tehdyt tilaukset.

![](/assets/files/docs/Hankinta/hankinta94.png)

![](/assets/files/docs/Hankinta/hankinta95.png)

- Myöst tällä sivulla toimii _Haku_-kenttä.
- Voit myös järjestää tuloksia otsikkorivin nuolilla.
