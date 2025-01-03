---
title: 'Kohan ohje suomeksi'
permalink: /dokumentaatio/raportit/
redirect_from:
  - /theme-setup/
toc: true
---

# 9. Raportit

Raporteilla voi hakea tietokannasta mm. tilastotietoja ja erilaisia
listoja asiakkaista, teoksista tai niteistä. Jos sinulla on oikeus
käyttää raportteja, pääset niihin joko etusivun kautta

![](/assets/files/docs/Raportit/raportit1.png)

tai yläreunan _Muita toimintoja_ -valikosta  
![](/assets/files/docs/Raportit/raportit2.png)

## 9.1 Kohan raportit

Raportit-osiossa on erilaisia raporttitoimintoja:

![](/assets/files/docs/Raportit/raportit3.png)

1.  Ohjatut raportit -osiossa voi tehdä itse SQL-kyselyitä ohjatusti tai
    käyttää tallennettuja raportteja. _Luo ohjattu raportti_ -toimintoa ei kannata käyttää, mikäli ei ole varma, mitä on tekemässä. Sillä saa helposti tehtyä todella raskaita raportteja, jotka voivat vaikuttaa Kohan suorituskykyyn hidastavasti.
2.  Tilastovelholla voi hakea tilastoja eri aihealueista käyttäen
    valmiita vaihtoehtoja. Velhossa rajausmahdollisuudet ovat rajatummat kuin jos itse tekee SQL-kyselyn.
3. Raporttiliitännäiset-osiossa on raportit, jotka on toteutettu Kohaan liitännäisenä.
4.  Oikeassa reunassa on valmiita raportteja

### 9.1.1 Ohjatut raportit

Ohjatuissa raporteissa voi luoda ohjatusti uusia raportteja. Tätä
käyttääksesi, sinulla pitää olla oikeus luoda raportteja. Vaikka
toiminto kuulostaa helpolta käyttää, ei se ikävä kyllä sitä ole.
Valittavissa olevat vaihtoehdot ja niiden yhdistelyvaihtoehdot ovat
rajalliset. Toiminnolla saa tehtyä helposti suhteettoman isoja hakuja.

Valitse raporttien etusivulla _Luo ohjattu raportti_  
![](/assets/files/docs/Raportit/raportit4.png)

Valitse sitten, mihin Kohan osa-alueeseen kohdistuvan raportin haluat
luoda.  
![](/assets/files/docs/Raportit/raportit5.png)

Valitse, mihin muotoon raportin haluat  
![](/assets/files/docs/Raportit/raportit6.png)

Valitse näytettävät/käytettävät tietokannan taulut ja sarakkeet  
![](/assets/files/docs/Raportit/raportit7.png)

Valitse rajoituskriteerit  
![](/assets/files/docs/Raportit/raportit8.png)

Valitse yhteenlaskettavat tiedot  
![](/assets/files/docs/Raportit/raportit9.png)

Valitse raportin järjestys  
![](/assets/files/docs/Raportit/raportit10.png)

Näe nyt, minkälaisella SQL-kyselyllä tietoja lähdetään hakemaan
tietokannasta. Joudut vielä tallentamaan raportin.  
![](/assets/files/docs/Raportit/raportit11.png)

Anna raportille nimi ja tallenna  
![](/assets/files/docs/Raportit/raportit12.png)

Voit nyt ajaa juuri tekemäsi raportin _Aja raportti_ -napista painamalla. Voit myös muokata SQL-kyselyä ja valita sen jälkeen _Päivitä ja aja SQL_.
![](/assets/files/docs/Raportit/raportit13.png)

#### 9.1.2.1 Käytä tallennettua raporttia

Tallennettuista raporteista löytyvät ohjatun raporttien luonnin kautta tehdyt ja SQL-kyselyillä tehdyt raportit.

![](/assets/files/docs/Raportit/raportit14.png)

- Kaikki-välilehdeltä löytyy kaikki tallennetut raportit
- Muilta välilehdiltä löytyy niihin määritetyt raportit. Osion määritys
  tehdään raportin tallennuksen yhteydessä.
- Haku-kentällä voi rajata taulukossa näkyviä raportteja. Jos tiedät
  raportin nimen tai numeron, voit hakea sen niillä suoraan.

Raportin voi ajaa valitsemalla rivin oikeasta reunasta _Käynnistä_  
![](/assets/files/docs/Raportit/raportit15.png)

Käynnistä-napissa on pieni nuoli, jonka alta löytyy muita vaihtoehtoja  
![](/assets/files/docs/Raportit/raportit16.png)

- _Näytä_-vaihtoehdolla näet raportin SQL-koodin
- _Esikatsele SQL_ -vaihtoehdolla näet SQL-koodin erillisessä popupissa.
- _Muokkaa_-vaihtoehdolla voit muokata raportin SQL-koodia (vaatii erillisen oikeuden)
- _Kopioi_-vaihtoehdolla voit kopioida raportin SQL-koodin ja muokata sitä uutena raporttina (vaatii erillisen oikeuden)
- _Ajastus_-vaihtoehdolla voit ajastaa raportin käynnistymään tiettynä ajankohtana. **HUOM!** Ajastus ei toimi.
- _Poista_ -vaihtoehdolla voit poistaa kyselyn (vaatii erillisen oikeuden)

Ajettavan raportin ominaisuuksista/määrityksistä riippuu, mitä
käynnistyksen jälkeen tapahtuu. Osa raporteista voi pyytää käyttäjää
valitsemaan esimerkiksi kirjaston tai päivämäärän. Osa ei kysy mitään
lisämäärityksiä.  
![](/assets/files/docs/Raportit/raportit161.png)

Raportin määrityksistä riippuu myös, mitä sarakkeita ja tietoja tulee
näkyviin.

![](/assets/files/docs/Raportit/raportit18.png) ![](/assets/files/docs/Raportit/raportit17.png)

- Tulosten (rivien) kokonaismäärä näkyy otsikon ja selitteen alapuolella
- Rivejä sivulla -valikosta voit määrittää, kuinka monta riviä
  näytetään per sivu. Joissain raporteissa on voitu määrittää
  valmiiksi, että näytetään tietty määrä rivejä.
- Otsikon yläpuolella on työkalurivi, jossa pääsee tekemään samoja toimintoja kuin Käynnistä-napin valikosta.
- Raportin tiedot voi ladata eri muodoissa
  - Puolipisteellä eroteltua tekstiä (.csv)
  - Tabulaattorein eroteltu teksti
  - OpenDocument-taulukkolaskenta
  - FinnaJSON (jotta tämä toimii, pitää tulosten ensimmäinen sarake sisältää tietueen biblionumberin)
  - Kaavio (.svg), jos kaavion on ensin luonut.
  - Raportin tuloksista poistetaan HTML-koodit, kun ne ladataan tiedostoksi eli esimerkiksi linkit poistetaan.
- Tuloksista voi luoda kaavioita, jos ne ovat numeerisia. Esimerkiksi nimekelistauksista ei voi tehdä järkeviä kaavioita.

#### 9.1.2.2 Erämuokkaustoiminnot raporttien kautta

Jos raportin tulokset sisältävät sarakkeen, jossa on niteen itemnumber, tietueen biblionumber, asiakkaan borrowernumber tai cardnumber voi tulokset viedä eräkäsittelyyn. Jos tuloksia on paljon, voit valita Rivejä sivulla -valikosta, kuinka monta riviä viedään eräajoon. Valikon kautta voi saada näkyville maksimissaan 1000 riviä. Jotkin raportit on jo kyselyssä määritetty näyttämään tietty määrä rivejä, jolloin niitä voi olla esillä enemmän kuin 1000.

![Kuvailutietueet](/assets/files/docs/Raportit/raportit181.png)
- Tietueiden muokkaus eräajona
- Tietueiden poisto eräajona
- Lisää listalle

![Niteet](/assets/files/docs/Raportit/raportit182.png)
- Niteiden muokkaus eräajona
- Niteiden poisto eräajona

![Asiakkaat](/assets/files/docs/Raportit/raportit1821.png)
- Asiakkaiden muokkaus eräajona (jos cardnumber-sarake)
- Kirjastokorttien luonti (jos borrowernumber-sarake)

#### 9.1.2.3 Linkit nide-, kuvailu- ja asiakastietueisiin

Jos tallennetussa raportissa on sarake, jossa on nidetunnus (itemnumber), kuvailutietueen tunnus (biblionumber) tai asiakkaan id (borrowernumber), tulee tunnuksen kohdalle automaattisesti valikko, josta pääsee muokkaamaan tai katsomaan tietuetta. Jos kyseessä on asiakkaan id, pääsee myös suoraan lainaamaan asiakkaalle.

Nidetietue

![](/assets/files/docs/Raportit/raportit183.png)

Asiakastietue

![](/assets/files/docs/Raportit/raportit184.png)

### 9.1.2 Tilastovelho

Tilastovelholla pystyy hakemaan tietoja tietokannasta seitsemästä eri
aihealueesta.

![](/assets/files/docs/Raportit/raportit19.png)

#### Hankintatilastot

![](/assets/files/docs/Raportit/raportit20.png)

- Tilastoja voi hakea kahden kriteerin perusteella. Valitse haluamasi
  vaihtoehdot _Rivi_- ja _Sarake_-kohtiin.
- Valitse myös _Solun arvo_ -kohdasta, mitä haettaville luvuille
  tehdään. Lasketaanko esim. kuinka monta nidettä.
- Valitse _Tulostus_-kohdasta, haluatko tulokset näytölle vai
  tiedostoon.

![](/assets/files/docs/Raportit/raportit21.png)

#### Asiakastilastot

![](/assets/files/docs/Raportit/raportit22.png)

- Tilastoja voi hakea kahden kriteerin perusteella. Valitse haluamasi
  vaihtoehdot _Rivi_- ja _Sarake_-kohtiin.
- Valitse _Tulostus_-kohdasta, haluatko tulokset näytölle vai
  tiedostoon.

Valinnoistasi riippuen tuloksista muodostuu taulukko.

![](/assets/files/docs/Raportit/raportit23.png)

#### Kokoelmatilastot

![](/assets/files/docs/Raportit/raportit24.png)

- Tilastoja voi hakea kahden kriteerin perusteella. Valitse haluamasi
  vaihtoehdot _Rivi_- ja _Sarake_-kohtiin.
- Valitse _Solun arvo_ -kohdasta, mitä valituille kriteereille
  tehdään.
- Valitse _Tulostus_-kohdasta, haluatko tulokset näytölle vai
  tiedostoon.

Valinnoistasi riippuen tuloksista muodostuu taulukko.

![](/assets/files/docs/Raportit/raportit25.png)

#### Lainaustilastot

![](/assets/files/docs/Raportit/raportit26.png)

- Tilastoja voi hakea kahden kriteerin perusteella. Valitse haluamasi
  vaihtoehdot _Rivi_- ja _Sarake_-kohtiin.
- Valitse _Solun arvo_ -kohdasta, mitä valituille kriteereille
  tehdään.
- Valitse _Tulostus_-kohdasta, haluatko tulokset näytölle vai
  tiedostoon.

Valinnoistasi riippuen tuloksista muodostuu taulukko.

![](/assets/files/docs/Raportit/raportit27.png)

#### Kausijulkaisutilaukset

![](/assets/files/docs/Raportit/raportit28.png)

- Valitse toimittaja ja kirjasto sekä otetaanko mukaan myös loppuneet
  tilaukset.
- Valitse _Tulostus_-kohdasta, haluatko tulokset näytölle vai
  tiedostoon.

Valinnoistasi riippuen tuloksista muodostuu taulukko.

![](/assets/files/docs/Raportit/raportit29.png)

#### Maksutilastot eli Kassajärjestelmä

![](/assets/files/docs/Raportit/raportit30.png)

- Valitse aikaväli, maksun tyyppi ja kirjasto
- Valitse _Tulostus_-kohdasta, haluatko tulokset näytölle vai
  tiedostoon.

Valinnoistasi riippuen tuloksista muodostuu taulukko.

![](/assets/files/docs/Raportit/raportit31.png)

#### Varaustilastot

![](/assets/files/docs/Raportit/raportit32.png)

- Tilastoja voi hakea kahden kriteerin perusteella. Valitse haluamasi
  vaihtoehdot Rivi- ja Sarake-kohtiin.
- Valitse _Solun arvo_ -kohdasta, mitä valituille kriteereille
  tehdään.
- Valitse _Tulostus_-kohdasta, haluatko tulokset näytölle vai
  tiedostoon.

Valinnoistasi riippuen tuloksista muodostuu taulukko.

![](/assets/files/docs/Raportit/raportit33.png)

### 9.1.3 Eniten…

#### Asiakkaat, joilla on eniten lainoja

![](/assets/files/docs/Raportit/raportit34.png)

- Valitse haluamasi päivämäärävälit
- Valitse halutessasi kirjasto
- Valitse halutessasi aineistolaji
- Valitse halutessasi asiakastyyppi
- Voit rajoittaa tulosten määrää kirjoittamalla _Rajoita:_-kenttään
  numeron
- Alemmalla otsikottomalla (englanniksi By:) valikolla voit ryhmitellä
  tietoja esim. nidetyypin mukaan
- Valitse _Tulostus_ -kohdasta haluatko tulokset näytölle vai
  tiedostoon

Valinnoistasi riippuen tuloksista muodostuu taulukko.

![](/assets/files/docs/Raportit/raportit35.png)

#### Eniten lainattu aineisto

![](/assets/files/docs/Raportit/raportit36.png)

- Valitse haluamasi kriteerit. HUOM! Luokka tarkoittaa tässä
  yhteydessä signumia eli ei pysty hakemaan pelkällä ykl-luokalla.
- Voit rajoittaa tulosten määrää _Rajoitukset_-kohdassa. Alemmasta
  nimettömästä (englanniksi By:) valikosta voit valita, ryhmitelläänkö
  tulokset jonkin kriteerin mukaan.
- Valitse Tulostus -kohdasta haluatko tulokset näytölle vai
  tiedostoon.

Valinnoistasi riippuen tuloksista muodostuu taulukko.

![](/assets/files/docs/Raportit/raportit37.png)

### 7.1.4 Ei käytössä

Otsikko on hieman harhaanjohtava, mutta tarkoittaa, että aineistoa ei ole käytetty tai asiakkaita, jotka eivät ole lainanneet.

#### Asiakkaat, jotka eivät ole lainanneet

![](/assets/files/docs/Raportit/raportit38.png)

- Valitse asiakastyyppi. Voit myös valita, milloin asiakkaan on
  pitänyt viimeksi lainata.
- Voit rajoittaa tulosten määrää _Rajoitukset_-kohdassa. Alemmasta
  nimettömästä (englanniksi By:) valikosta voit valita, ryhmitelläänkö
  tulokset jonkin kriteerin mukaan.
- Valitse Tulostus -kohdasta haluatko tulokset näytölle vai
  tiedostoon.

Valinnoistasi riippuen tuloksista muodostuu taulukko

![](/assets/files/docs/Raportit/raportit39.png)

#### Niteitä, joita ei ole lainattu

![](/assets/files/docs/Raportit/raportit40.png)

- Valitse kirjasto ja nidetyyppi.
- Voit rajoittaa tulosten määrää _Rajoitukset_-kohdassa. Alemmasta
  nimettömästä (englanniksi By:) valikosta voit valita, ryhmitelläänkö
  tulokset jonkin kriteerin mukaan.
- Tulokset tulevat vain näytölle.

Valinnoistasi riippuen tuloksista muodostuu taulukko

![](/assets/files/docs/Raportit/raportit41.png)

### 9.1.5 Muu

#### Kadonnut aineisto

![](/assets/files/docs/Raportit/raportit42.png)

- Voit rajata raporttia viivakoodin, kirjaston, nidetyypin, kadonnut-tilan ja Ei lainattavissa -tilan mukaan.

Valinnoistasi riippuen tuloksista muodostuu taulukko

![](/assets/files/docs/Raportit/raportit43.png)

- Voit säätää näkyvillä olevia sarakkeita ja viedä tiedot Excel- tai CSV-muodossa, kopioida tai tulostaa ne.

#### Tilauksia tilin mukaan

![](/assets/files/docs/Raportit/raportit44.png)

- Valitse tili
- Valitse, haluatko tulokset näytölle vai tiedostoon

Valinnoistasi riippuen tuloksista muodostuu taulukko

![](/assets/files/docs/Raportit/raportit45.png)

#### Luettelo aineistoittain

Raportti laskee niteitä.

![](/assets/files/docs/Raportit/raportit46.png)

- Valitse haluamasi kirjasto tai jätä tyhjäksi, jos haluat nähdä kaikkien kirjastojen tilanteen

Valinnastasi riippuen tuloksista muodostuu taulukko.

![](/assets/files/docs/Raportit/raportit47.png)

#### Keskimääräinen laina-aika

![](/assets/files/docs/Raportit/raportit48.png)

- Tilastoja voi hakea kahden kriteerin perusteella. Valitse haluamasi
  vaihtoehdot _Rivi_- ja _Sarake_-kohtiin.
- Valitse _Tulostus_ -kohdasta haluatko tulokset näytölle vai
  tiedostoon.
- Raportti on hidas.  

Valinnoistasi riippuen tuloksista muodostuu taulukko

![](/assets/files/docs/Raportit/raportit49.png)

---

## 9.2 Lainaus ja palautus -osion raportit

Lainaus ja palautus -osiossa on myös muutamia hyödyllisiä raportteja. Niiden kuvaukset löytyvät wikin [Lainaus-osiosta](https://koha-suomi.fi/dokumentaatio/lainaus/#213-lainauksen-valmiit-raportit)


## 9.3 OKM-tilastot

Raportointiyökalu-liitännäisellä otetaan OKM:n määrittämien ehtojen mukaiset
tilastot. Se ajetaan kahdella eri syklillä: kuukausittain
kirjastoyksiköittäin ja vuosittain kunnittain.

Liitännäinen löytyy seuraavasti: Raportit -> Raporttiliitännäiset -> Raportointityökalu -> Toiminnot -> Aja raportti -> OKM

![](/assets/files/docs/Raportit/raportit512.png)

### 9.3.1 Liitännäisen määritykset

Raporttiliitännäisen ylläpidossa on asetus, johon tehdään tietyt
määritykset. Loput määritykset tulee suoraan työkalun koodista ja niitä
määrityksiä on avattu alla.

Asetuksessa määritetään, miten aineistotyypit, asiakaslajit ja
hyllypaikat jaotellaan OKM-tilastoihin sekä, mitä niteen tiloja ei oteta
mukaan tilastoihin.  
<img src="/assets/files/docs/Raportit/raportit52.png" title="OKM-järjestelmäasetus" alt="OKM-järjestelmäasetus" style="width:80.0%" />

- _itemTypeToStatisticalCategory_-otsikon alle, mitkä aineistotyypit
  ovat
  - Kirja-aineistoa: _Books_
  - Äänitteitä: _Recordings_
  - Nuotteja: _SheetMusicAndScores_
    - Jaotellaan automaattisesti MARC-kuvailutietojen mukaan
      Musiikkiäänitteisiin ja Muihin äänitteisiin.
  - Videoita: Videos
  - Muita: _Other_
  - Aikakauslehtiä: _Serials_
  - Celia-aineistoa: _Celia_
  - Elektronisia aineistoja: _Electronic_
  - Verkkoaineistoja: _Online_

- _patronCategories_-otsikon alle merkitään tilastoihin mukaan
  otettavat asiakaslajit. Eli esim. jos käytössä on
  “EITILASTO”-asiakastyyppi, jonka lainoja ei lasketa mukaan, niin
  sitä ei merkitä tähän mukaan.

- _excludedItemtypes_ -kohtaan merkitään aineistotyypit, joita ei lasketa mukaan kokoelmiin. Tähän lisätään esim. lehtiaineistojen aineistotyypit, koska niitä OKM:n ohjeistuksen mukaan ei lasketa nidetasolla mukaan kokoelmiin vaan ne ilmoitetaan vuosikertoina. Sitä tietoa taas ei tällä liitännäisellä lasketa.

- _notForLoanStatuses_-kohtaan merkitään ne ei-lainattavana-tilat eli notforloan-tilat, joita ei
  oteta mukaan kokoelmatilastoihin. Esim. tilattu-tilassa olevat niteet.

- _adultShelvingLocations_-kohtaan merkitään hyllypaikat, jotka sisältävät aikuisten aineistoa.

- _juvenileShelvingLocations_-kohtaan merkitään hyllypaikat, jotka sisältävät lasten aineistoa.

Esimerkkikonfiguraatio:

```
---
blockStatisticsGeneration: 0
itemTypeToStatisticalCategory:
 ALEHTI: Serials 
 ARTIKKELI: Other
 ATLAS: Books
 BLURAY: Videos
 BRAILLE: Books
 CD: Recordings
 PUHECD: Recordings
 CDROM: Other
 DATKAS: Other
 DIA: Other 
 DVD: Videos
 EKIRJA: Electronic
 ELEKTRON: Electronic 
 ELOKUVA: Videos
 ESINE: Other 
 EVIDEO: Electronic 
 KAAVIO: Other 
 KALVO: Other 
 KARTTA: Other
 PUHEKAS: Recordings 
 KAUKOKART: Other
 KAUSIJULK: Serials
 KIRJA: Books 
 KOKOELMA: Other
 KOLLAASI: Other
 KASIKIRJ: Books
 LAUTAPELI: Other
 LEVYKE: Other
 MAALAUS: Other
 MAGNEETTI: Other
 MIKROF: Other
 MONIVIES: Other 
 MUSATAL: Recordings 
 MUU: Other
 MUUPAINATE: Other
 NAUHAKAS: Other
 NUOTTI: SheetMusicAndScores 
 OPTINEN: Other
 PIIRIKOT: Other
 PIIRROS: Other
 PAIVITTYVA: Other
 RAINA: Videos 
 KORTTI: Other 
 SLEHTI: Serials
 SARJANOSA: Other
 TYOPIIR: Other
 VALOKUVA: Other 
 NEGATIIVI: Other 
 VIDEO: Videos
 VIDEOKAS: Videos
 VIDEOKELA: Videos 
 VIDEOLEVY: Videos
 VIDEOPELI: Other
 VIDEOSILM: Videos
 AANIKAS: Recordings
 AANILEVY: Recordings
 PUHELEVY: Recordings
 AANITALL: Recordings
 PUHETAL: Recordings
excludedItemtypes:
  - ALEHTI
  - KAUSIJULK
  - SLEHTI 
patronCategories:
  - HENKILO
  - KOTIPALVEL
  - LAPSI
  - LAOMATOIMI
  - MUUHUOL
  - YHTEISO
notForLoanStatuses:
  - -1
adultShelvingLocations:
  - AIK
  - VAR
  - MUS
  - LEH
  - KOT
  - OU
  - OUV
  - K
  - PALVELUT
  - VAREILAI
juvenileShelvingLocations:
  - LN
  - KOULU
  - VARLN
  - LUKIO
```
### 9.3.2 Kovakoodatut määritykset

Osa säännöistä on ns. kovakoodattuna liitännäiseen, eikä niitä pysty käyttäjä määrittelemään.

#### 9.3.2.1 Kirjastot ja kirjastoryhmät

OKM-tilastoryhmät määritetään ‘Kirjastot ja ryhmät’ -sivulla
ylläpidossa. Tilastoihin otetaan mukaan ne ryhmät, joiden tunnus päättyy
‘\_OKM’. Esim. JOE_OKM, OU_OKM. Vain näihin ryhmiin kuuluvat kirjastot
otetaan mukaan OKM-tilastoihin.

Tilastot ilmoitetaan OKM:lle kotikirjaston mukaan.

#### 9.3.2.2 Jako kielen mukaan

Nide lasketaan suomenkieliseksi, jos tietueen ensimmäinen 084$a-kenttä
on ‘fin’, tai kieltä ei ole määritetty.

Nide lasketaan ruotsinkieliseksi, jos tietueen ensimmäinen 084$a-kenttä
on ‘swe’.

Nide lasketaan muun kielisiin, jos tietueen ensimmäinen 084$a-kenttä ei
ole ‘fin’ tai ‘swe’, mutta se on määritetty.

#### 9.3.2.3 Jako lasten- ja aikuisten aineistoihin

Nide lasketaan lasten materiaaliksi ‘OKM’-järjestelmäasetuksessa
tehtyjen hyllypaikkamääritysten mukaan.

#### 9.3.2.4 Jako kauno- ja tietokirjoihin

Nide on kaunokirja, jos sen YKL-luokka **niteessä** on 80-85. Muut ovat tietokirjoja. Tieto otetaan niteen cn_sort-kentästä, jossa se pitää olla kentän ensimmäisenä tietona. cn_sort-kentän tieto muodostetaan niteen signum-kentästä (itemcallnumber) ja sitä varten on kaksi eri liitännäistä riippuen siitä, onko signum-kentässä ensimmäisenä luokka-arvo vai jotain muuta.

#### 9.3.2.5 Musiikkiäänitteet

Nide lasketaan musiikkitallenteeksi, jos sen YKL-luokka on 78.

#### 9.3.2.6 Hankinnat

Nide lasketaan mukaan hankintoihin, jos se on vastaanotettu määritetyllä
aikavälillä. Jos Hankinnat-osiota ei käytetä, nide kuitenkin lasketetaan
hankintoihin, jos se on lisätty kokoelmiin raportin ajossa määritettynä
ajanjaksona.

Aikaväli tarkistetaan niteen dateaccessioned-tiedon mukaan.

#### 9.3.2.7 Lainat

Lainat sisältävät ensilainat ja uusinnat.

Lainoiksi lasketaan määritettynä aikavälinä tehdyt lainat, joiden
lainaajat kuuluvat OKM-järjestelmäasetuksessa ‘patronCategories’-kohtaan
määritettyihin asiakastyyppeihin.

Lainat lasketaan lainanneelle kirjastolle. Verkkokirjastouusinnan
kirjastoksi lasketaan niteen nykyinen sijainti uusintahetkellä.

Poistettujen niteiden lainat lasketaan mukaan lainatilastoihin.

#### 9.3.2.8 Kausijulkaisut

Aikakauslehtiä ei lasketa mukaan kokoelmiin, poistoihin ja hankintoihin.
Ne ovat mukana kokonaislainoissa.

#### 9.3.2.9 Poistot

Kaikki määritetyllä aikavälillä poistetut niteet, pois lukien
aikakauslehdet, lasketaan poistoiksi.

Poistettuja niteitä ei lasketa määritetyn aikavälin kokoelmiin ja
hankintoihin, koska hankintatietoja ei säilytetä.

Poistettujen niteiden lainat lasketaan mukaan lainatilastoihin.

Tätä lukua ei enää ilmoiteta OKM:lle, vaan he laskevat poistot omalla laskukaavalla.

#### 9.3.2.10 Lainanneet asiakkaat

Lainaajat lasketaan aina uniikkeina arvoina. Tällöin, jos asiakas on lainannut vuoden aikana useammasta kirjastosta, tämä lasketaan näiden kirjastojen lainatilastoihin. Mutta koska vuosittaisissa OKM-tilastoissa kirjastot lasketaan ryhmittäin, lainaaja ei esiinny OKM-tilastoissa kuin kerran, jos kirjastot kuuluvat samaan OKM-ryhmään. Tästä voi syntyä tilanne, jossa kuukausittaiset kirjastokohtaiset tilastot antavat isomman luvun lainanneista asiakkaista kuin vuosittainen tilasto, jossa kirjastot on käsitelty yhdessä.

### 9.3.3 Raportin käyttöohje

OKM-tilastot -raporttiliitännäinen löytyy seuraavasti: Raportit -> Raporttiliitännäiset -> Raportointityökalu -> Toiminnot -> Aja raportti -> OKM-välilehti

OKM-tilastoraportin tiedot jaotellaan OKM:n laatimien ehtojen
mukaisesti. Sarakkeiden otsikoissa noudatetaan
[tilastot.kirjastot.fi](https://tilastot.kirjastot.fi/) -sivun
termistöä.

Klikkaa ensin Näytä/Piilota raporttilistaus -nappia ja valitse sieltä, minkä aikavälin tilastoja haluat tarkastella.

<img src="/assets/files/docs/Raportit/okm.png" title="Lista tarjolla olevista raporteista" alt="Lista tarjolla olevista raporteista" style="width:90.0%" />

- Voit myös käyttää Suodata-kenttää rajaamaan listalla näkyviä raportteja.

- Mitä isompi **Raportin ID-tunnus** on, sitä tuoreempi se on
- **Alkupvm ja Loppumispvm** -sarakkeista näkee, miltä aikaväliltä
  tilastot ovat
- **Tilastoryhmät** -sarakkeesta näkee, onko tilasto jaoteltu
  - OKM-tilastoryhmän mukaan eli käytännössä kaikki kunnan
    kirjastojen tilastot yhteenlaskettuna. Tämä otetaan
    tyypillisesti kerran vuodessa, kun raportoidaan tilastot
    OKM:lle.
  - kirjastoittain, jolloin listautuu kaikki kirjastot tunnuksen
    mukaan aakkosjärjestykseen. Tällä voi seurata kuukausitilastoja.
  - yhden kirjaston tilastot, jolloin otsikkona on kirjaston tunnus.
    Tätä vaihtoehtoa ei tyypillisesti ole ehdolla, mutta se on
    teknisesti mahdollista ajaa.
- Tilasto avataan **klikkaamalla** haluttua riviä.


Kun raportin on avannut, pystyy sen myös sen jälkeen lataamaan XSL-tiedostoksi tai tiedot kopioimaan leikepöydälle ja liittämään haluamaansa ohjelmaan.

<img src="/assets/files/docs/Raportit/okm2.png" title="Tilasto avattuna" alt="Tilasto avattuna" style="width:90.0%" />

- Rivejä voi suodattaa halutessaan. Tyhjennä suodatin -nappulalla saa tyhjennettyä Suodata-kentän.
- Tilastoja voi järjestellä otsikkorivien mukaan valitsemalla nuolen ylös tai alas.
