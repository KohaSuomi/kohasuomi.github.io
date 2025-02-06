---
title: 'Kohan ohje suomeksi'
permalink: /dokumentaatio/tiedonhaku/
redirect_from:
  - /theme-setup/
toc: true
---

# 10. Tiedonhaku
## 10.1. Perushaku

Kun haluat hakea Kohasta, napauta _Hae tietokannasta_-linkkiä, kirjoita hakusanat ja paina Enter. Haun voi käynnistää myös valkeaa nuolta klikkaamalla.

![](/assets/files/docs/Tiedonhaku/Tiedonhaku1_haun_suorittaminen.png)

Haku yhdistää oletuksena hakusanat AND-operaattorilla, eli palauttaa tietueet, joiden tiedoissa esiintyvät kaikki annetut hakusanat. AND-operaattorin lisäksi haussa voi käyttää myös OR- ja NOT-operaattoreita. 

Hakusanojen automaattinen katkaisu on kimppakohtainen asetus (QueryAutoTruncate). Mikäli asetus on päällä hakusanat katkaistaan automaattisesti, eli haku _seitse_ kohdistuu kaikkiin merkkijonon _seitse_ sisältäviin sanoihin, kuten _seitsemän, seitsemäs tai kuusikymmentäseitsemän_.
Jos asetus ei ole päällä, tulee hakusanat katkaista *-merkillä.

Sanojen järjestys ei vaikuta hakutulokseen. Haku _tiedonhaku kirjastot_ antaa saman tuloksen kuin _kirjastot tiedonhaku_.  

Perushakuun voi lisätä rajauksen hakuindeksiin eli haluttuihin kenttiin tai haluttuun kirjastoon. Nämä ovat kimppakohtaisia asetuksia (_IntranetCatalogSearchPulldown_ ja _IntranetAddMastheadLibraryPulldown_). Rajaukset saa näkyviin hakulaatikon lopussa olevasta valikko-kuvakkeesta. Molemmat rajaukset ovat samanlaiset kuin tarkassa haussa.
Hakuindeksirajauksissa voi valita mihin kenttään haku kohdistuu. Kirjastorajaus rajaa hakutuloksen vain sellaisiin tietueisiin, joiden niteissä on joko koti- tai sijaintikirjastona valittu kirjasto.

![](/assets/files/docs/Tiedonhaku/Tiedonhaku1_haun_rajaus.png)

### 10.1.1. Hakusanojen etuliitteet

Voit kohdistaa haun tiettyihin kenttiin kirjoittamalla hakusanojen eteen etuliitteitä:

- ti: nimeke  
  esim. ti:kuparisydän

<!-- -->

- su: asiasana  
  esim. su:pilapiirrokset

<!-- -->

- pb: kustantaja  
  esim. pb:wsoy

<!-- -->

- au: tekijä  
  esim. au:lehtolainen

<!-- -->

- lcn: luokka  
  esim. lcn:78.61

<!-- -->

- ln: kieli  
  esim. ln:est

<!-- -->

- ccode: kokoelmakoodi  
  esim. ccode:lyla

[Lista etuliitteistä ja tarkemmat ohjeet etuliitteiden
käyttämiseen](https://koha-community.org/manual/22.11/en/html/searching.html#indexes) (englanniksi). 

[Tiedonhaun cheat sheet](https://github.com/KohaSuomi/kohasuomi.github.io/files/13215370/Kohan.indeksit.pdf)
eli lista yleisimmin käytetyistä Kohan indekseistä ja niiden lyhenteistä.

## 10.2. Tarkka haku

Tarkassa haussa voit määrittää haun perushakua täsmällisemmin. 

Tarkka haku aukeaa napauttamalla _Haku_-painikkeen viereistä nuolta ja valitsemalla _Tarkka haku_ ylälaidan valikossa.

![](/assets/files/docs/Tiedonhaku/Tiedonhaku4_tarkka_haku.png)

Voit hakea kirjoittamalla hakusanat hakukenttiin ja valitsemalla alasvetovalikoista hakusanojen kohteet. Voit määrittää hakusanojen rajaavuuden valitsemalla niille alasvetovalikosta operaattorin _ja, tai, ei_. Lisää hakuehtoja voit lisätä _\[+\]-painikkeella_.

![](/assets/files/docs/Tiedonhaku/Tiedonhaku5_tarkan_haun_hakulauseet.png)

Luokkarajaus on valikossa _Standardinumero_-kohdan alla:

![](/assets/files/docs/Tiedonhaku/Tiedonhaku7_luokkarajaus.png)

Rajoitukset-osiossa voi hakea julkaisuvuosien mukaan seuraavasti:
* 2005		julkaisuvuosi on 2005
* 2005-2010	julkaisuvuosi on välillä 2005-2010 (sisältäen 2005 ja 2010)
* -2010		julkaisuvuosi on 2010 tai vanhempi
* \<2010 	julkaisuvuosi on pienempi kuin 2010
* 2005- 	julkaisuvuosi on 2005 tai uudempi
* \>2005 	julkaisuvuosi on suurempi kuin 2005

![](/assets/files/docs/Tiedonhaku/Tiedonhaku6_vuosirajaus.png)

Voit valita hakutulosten järjestyksen _Järjestys_-valikosta. Tulosten oletusjärjestys on parametroitavissa asetuksella (_defaultSortField_), eli se on kimppakohtaisesti päätettävissä. Tulokset voi järjestää esimerkiksi osuvuuden, julkaisuvuoden, tekijän, nimekkeen ja suosion (lainamäärä) mukaan. Järjestäminen nimekkeen mukaan tapahtuu kentän 245 perusteella.

![](/assets/files/docs/Tiedonhaku/Tiedonhaku6_jarjestys.png)

## 10.3. Hakutuloksen rajaaminen 

### 10.3.1 Hakutuloksen rajaaminen faseteilla

Hakutulosta voi rajata hakutuloslistan vasemman reunan faseteilla. Fasettien sisältö riippuu hakutuloksesta.

Jos olet hakenut esimerkiksi hakusanalla _valokuvaus_, hakutulos voi näyttää tältä:

![](/assets/files/docs/Tiedonhaku/Tiedonhaku14_fasetit_lahtotilanne_2024.png)

Voit rajata hakutulosta luonnonvalokuvausta käsitteleviin teoksiin valitsemalla _Asiasanat_-fasetista termin _luonnonvalokuvaus_.

![](/assets/files/docs/Tiedonhaku/Tiedonhaku15_fasetit_rajaus.png)

Tämän jälkeen tuloslista näyttää vain luonnonvalokuvausta käsittelevät teokset.

![](/assets/files/docs/Tiedonhaku/Tiedonhaku16_fasetit_lopputilanne_2024.png)

### 10.3.2 Haku hakutuloksesta

Jo tehdyn haun hakutuloksiin voi tehdä uuden haun, jolla tarkennetaan ja rajataan hakua. _Hae tuloksista_ -haun voi tehdä hakusanahakuna tai sen voi kohdistaa alasvetovalikosta esim. tekijään tai asiasanaan. 

![](/assets/files/docs/Tiedonhaku/haku_hakutuloksesta_2024.png)

Huom. Hakusanat tulee tarvittaessa katkaista \*-merkillä. Kimppakohtainen asetus automaattikatkaisusta ei päde tässä haussa.
{: .notice--warning}

## 10.4. Hakuhistoria

Tehtyjä hakuja voi tarkastella ja suorittaa uudelleen _Hakuhistoria_-toiminnolla. _Hakuhistoria_ on oikean yläkulman alasvetovalikossa.

![](/assets/files/docs/Tiedonhaku/Tiedonhaku18_hakuhistoria_valikko.png)

Hakuhistoriassa haut on jaettu kuluvan istunnon aikana ja aiemmissa istunnoissa tehtyihin hakuihin.

![](/assets/files/docs/Tiedonhaku/Tiedonhaku19_hakuhistorianakyma.png)

Historian voi poistaa valitsemalla poistettavat haut ja klikkaamalla _Poista_.

Huom. Jos hakuhistoriaa ei itse poista, se säilyy Kohassa 1 kk ajan. Koha-Suomen [säilytysajat](https://koha-suomi.fi/dokumentaatio/tietojensailytysajat/#hakuhistoria).
{: .notice--warning}

## 10.5. Nidehaku

Nidehaulla voit esimerkiksi:

- Tutkia luokan niteiden määrää karsintaa varten.
- Hakea nollalainoja.
- Hakea joukon niteitä ja muokata, tai poistaa niiden tietoja eräajona.
- Tarkastaa, ovatko kaikki lehtiniteet siirretty pois lehtiemon alta.
- Tarkastaa, onko lehtien vanhoja numeroita jäänyt tietokantaan.

_Nidehaku_ on _Haku_-valikossa.

![](/assets/files/docs/Tiedonhaku/Tiedonhaku18_1_nidehaku.png)

_Nidehaku_ palauttaa tuloksena listan hakuehdot täyttävistä niteistä. Haun muotoilu vastaa pääosin _tarkkaa hakua_.

Haun voi kohdistaa esimerkiksi niteiden viivakoodeihin, luokkiin, nimekkeisiin ja tekijöihin. Nimeketietojen yhteydestä löytyy myös teoksen mahdollinen alanimeke, osan nimi, osan numero ja aineiston yleismääre. Käytä hauissa aina valintalistan alaosan _räätälöityjä hakukenttiä_. Muista kentistä ainoastaan _ISBN_ ja _ISSN_ toimivat luotettavasti.

![](/assets/files/docs/Tiedonhaku/Tiedonhaku19_1_hakukentat.png)

Hakusanoja voi yhdistää operaattoreilla _JA_ ja _TAI_. _Uusi kenttä_ lisää uuden hakukentän. 

Alla olevassa esimerkissä on lisätty uusi hakukenttä, asetettu molemmat hakusanat vaadituiksi _JA_-operaattorilla ja kohdistettu hakusanat _Nimeke_- ja _Henkilötekijä_-kenttiin. Lisäksi hakusanat on katkaistu %-merkeillä. 

![](/assets/files/docs/Tiedonhaku/Tiedonhaku20_nidehaun_tekstihaku.png)

Nidehaussa hakusanoja ei katkaista automaattisesti, joten ne kannattaa aina katkaista %-merkeillä. Esimerkiksi tekijä-haku _jansson, tove_ ei palauta  osumia, koska MARC-kentästä haettu tekijätieto päättyy pisteeseen tai pilkkuun. Haku _jansson, tove%_ toimii oikein. Katkaisun lisäksi hakusanat on kirjoitettava aina tarkasti oikein. Esimerkiksi haku *%tove jansson*% ei palauta mitään, koska tekijätieto on muodossa _Jansson, Tove_. Yksittäisen merkin voi korvata merkillä \_ (alaviiva).

Hakua voi rajata myös sivun yläosan valintalistoilta. Nidehaun kahden ensimmäisen osion valikot toimivat niin, että voit hakea valikon sisällöstä. Valikosta voi valita useamman vaihtoehdon, jolloin valitut vaihtoehdot näkyvät rivillä listattuna. Jos haluat rajata hakutuloksesta pois ehtoja, valitse valintalistalta _ei ole_, joka vastaa NOT-operaattoria.

![](/assets/files/docs/Tiedonhaku/nidehaku_parannettu_useamman_vaihtoehdon_valinta_25.png)

Sivun alalaidassa on vielä rajaus luokkavälillä, niteen tilalla ja lainatiedoilla. Luokkavälillä rajaaminen toimii epäloogisesti. Haku palauttaa vain luokkarajauksen ylärajaa pienemmät tulokset. Esimerkiksi alla oleva haku palauttaa luokkien 84.2-84.5 teokset. Haku luokasta 91 luokkaan 92 palauttaisi puolestaan vain 91-alkuisten luokkien niteet. Luokalla rajaaminen onnistuu helpommin käyttämällä räätälöityä kenttää _Luokka (084$a)_.

![](/assets/files/docs/Tiedonhaku/Tiedonhaku22_nidehaku_luokkahaku.png) 

_Lainauksien määrä_ -valinnalla voit hakea niteitä lainamäärän perusteella. Lainauspäivämäärästä rajataan tuloksia niteen lainojen ajankohdan perusteella. Alla on haettu kaikki yli 10 kertaa lainatut niteet, jotka on lainattu 25.05.2023.

![](/assets/files/docs/Tiedonhaku/Tiedonhaku27_nidehaun_lainarajat.png)

Kun olet valinnut haluamasi ehdot, voit hakea napauttamalla _Haku_-painiketta.

![](/assets/files/docs/Tiedonhaku/Tiedonhaku26_nidehaku_hakupainike.png)

Voit tarkentaa hakua sarakkeiden ylälaidassa olevilla rajauskentillä:

![](/assets/files/docs/Tiedonhaku/Tiedonhaku24_nidehaku_tulosten_lisafiltterit.png)

Versiossa 24.05 nidehaun tuloksiin tuli uutena sarakkeena Lainauspvm, jossa näytetään niteen viimeisin lainauspäivä.

![](/assets/files/docs/Tiedonhaku/nidehaun_sarake_lainauspvm_25.png)

### 10.5.1. Tulosten vienti CSV- tai -viivakooditiedostoksi

Tulokset voi halutessaan viedä ohjelmasta CSV- tai -viivakooditiedostona jatkokäyttöä varten ylälaidan painikkeilla.

Versiossa 24.05 tuli mukaan uutena ominaisuutena nidenumeron eli itemnumberin vieminen mukaan CSV-tiedostoon.

![](/assets/files/docs/Tiedonhaku/Tiedonhaku25_nidehaku_tulosten_painikkeet.png)

Hakua pääsee muokkaamaan painamalla _Muokkaa hakua_-painiketta.

## 10.6. Teostiedot

Yksittäisen teoksen tietoihin pääsee monta reittiä, esimerkiksi asiakkaan lainojen kautta tai tiedonhaun tuloksista. Järjestelmäasetuksella _RedirectToSoleResult_ pystyy määrittämään siirrytäänkö tiedonhaussa suoraan tietueeseen, jos haku tuottaa vain yhden tuloksen, vai näytetäänkö hakutuloslista. Teoksen Perustiedot-näytöllä näkee yleisimmin tarvittavat tiedot. Eri otsikot tulevat näkyville vain, jos teokselle on tallennettu kyseinen tieto.

Vasemmassa reunassa on näkyvissä järjestelmäastuksista ja käyttäjän oikeuksista riippuen seuraavat välilehdet:

- Perustiedot
- MARC
- Otsikoitu MARC
- Niteet
- Varaukset, sulkeissa varausten määrä
- Lainahistoria
- Muutosloki (vaatii erillisen käyttäjäoikeuden)

### 10.6.1. Kuvailutiedot

![](/assets/files/docs/Tiedonhaku/tietue1_2024.png)

- nimeke
- tekijät ja heidän funktiot
- osakohteissa linkki emotietueeseen
- teoksen kieli
- julkaisutiedot
- fyysinen kuvaus
- alkuteoksen nimi
- musiikkiaineistossa mm. soitinkokoonpano
- sisällön kuvailu eli asiasanat ja kohdehenkilöt ja -yhteisöt yms.
- luokitus (ykl ja fiktiivinen lisäluokka)
- linkit kansikuvaan ja kuvaukseen
- yhteenveto (kenttään 520 lisätty huomautus sisällöstä, tiivistelmästä yms.)
- linkki MARC-esikatseluun, josta näkee kaikki teokselle tallennetut tiedot MARC-kentittäin
- MARC-kuvailupohjat, kertoo mitä kuvailupohjaa tietue käyttää
- kansikuva, jos sellaiseen on linkki
- linkki varauksiin
- musiikkiaineistolla ja erilaisilla artikkelikokoelmilla useimmiten linkit osakohteisiin ja tieto osakohteiden määrästä
- elasticsearch tietue (Elasticsearchiin lisätty ominaisuus, että käyttäjä voi katsoa perustiedot-näytöllä tietueen indeksiin tallennetut tiedot)
- lainatilasto raportti

### 10.6.2. MARC-, Otsikoitu MARC ja ISBD-välilehdet

MARC

![](/assets/files/docs/Tiedonhaku/tietue5.png)

Otsikoitu MARC

![](/assets/files/docs/Tiedonhaku/tietue6.png)

ISBD

![](/assets/files/docs/Tiedonhaku/tietue10.png)

## 10.7. Nidetiedot ja niiden suodattaminen

Teoksen kuvailutietojen alla on tiedot siihen liittyvistä niteistä ja niiden saatavuudesta. Näkyvillä olevista niteistä voi hakea kirjoittamalla _Haku_-laatikkoon haluttu hakutermi. Vielä tarkemmin näkyvillä olevia niteitä voi myös suodattaa valitsemalla nidetaulukon yläpuolelta _Suodata_. Järjestelmäasetuksesta riippuen niteet ovat joko yhdellä välilehdellä tai jaettuna kirjautumiskirjaston kokoelmaan ja muihin kokoelmiin. Kokoelman nimen perässä näkyy välilehdellä olevien niteiden määrä.

![](/assets/files/docs/Tiedonhaku/tietue2.png)

Niteistä kerrotaan

- _Nidetyyppi_
- _Nykyinen kirjasto_ (=sijaintikirjasto)
- _Kotikirjasto_, jonka yhteydessä myöa hyllypaikka ja hyllytarkenne
- _Kokoelma_
- _Luokka_ (eli käytännössä “Kohan koko signum”)
- _Tila_: _Saatavana_, _Lainattu asiakkalle_, _Kuljetettavana_, _Kadonnut_, _Ei lainata_ jne.
  - jos teos on lainassa, kerrotaan asiakkaan kirjastokortin numero, mikä toimii myös linkkinä asiakastietoihin
  - jos teoksella on useampi näytettävä tila, näytetään ne allekkain
- _Viimeisin havainto_ (päivittyy mm. lainatessa ja palautettaessa. Myös silloin, kun palautetaan hyllyssä olevana)
- _Viimeksi lainattu_
- _Viivakoodi_, jota klikkaamalla pääsee niteen tietoihin vasemman reunan _Niteet_-välilehdelle.
- _Kausijulkaisun numerointi_, eli lehden numero, esim. 2019 : 1
- _Yleiset huomautukset_

Näkyvillä olevissa tiedoissa voi olla kimppakohtaista vaihtelua.

Suodatus on kätevä toiminto.

![](/assets/files/docs/Tiedonhaku/tietue4.png)

Voit suodattaa näkyville esim.

- tietyn kirjaston niteet (sijainti- tai kotikirjasto)
- tietyn kokoelman niteet
- saatavana olevat niteet: kirjoita Tila-kenttään “Saatavana”
- tietyn viivakoodin
- tietyn lehden numeron: kirjoita Kausijulkaisun numerointi -kenttään
  esim. 2019 : 1
  - _vinkki_, jos haluat näkyville vain esim. numeron 1 eikä muita
    ykkösellä alkavia numeroita, niin laita loppuun vielä yksi
    välilyönti, jolloin muut ykkösellä alkavat numerot eivät enää
    täsmää hakuun.
- tietyllä huomautuksella olevan niteen

Nidetietojen nouto tietueen perustiedot-näytölle uudistui versiossa 24.05 niin, että se tapahtuu nykyään REST-apin kautta. Nidetaulun suodatus, järjestely ja sivutus tehdään APIn avulla.

![](/assets/files/docs/Tiedonhaku/nidetietojen_sivutus_25.png)

- Jos niteitä on paljon, ne sivutetaan. Tässä voi olla kimppakohtaisia eroja ja osassa kimpoista on voitu asettaa oletuksena näkymään kaikki niteet kerralla.
- Voit säätää näytettävien niteiden määrää sivulla nidetaulukon yläpuolelta.
- _Tila_-sarakkeen mukaan ei pysty hakemaan/suodattamaan niteitä.
- Jos yhdelläkään teoksen niteellä ei ole jonkin sarakkeen tietoa, piilottuu kyseinen sarake automaattisesti. Tällainen sarake voi olla esimerkiksi _Kokoelma_-sarake.

### 10.7.1. Niteet-välilehti

Vasemman reunan _Niteet_-välilehdellä näkee tarkempia historiatietoja niteistä. Sinne pääsee myös klikkaamalla yksittäisen niteen viivakoodia _Kokoelmat_-taulukosta (saatavuustiedoista).

![](/assets/files/docs/Tiedonhaku/tietue7_2024.png)  

Niteestä näkee mm.

- koti- ja nykyisen kirjaston, nidetyypin, hyllypaikan, kokoelman ja luokan
- kenellä nide on tällä hetkellä lainassa
- kuinka monta kertaa nide on uusittu
- voi asettaa niteen
  - Kadonneeksi (Huomioi, että järjestelmäasetuksista riippuen tästä kadonneeksi asettaminen voi viedä niteen korvaushinnan asiakkaan maksuihin.)
  - Vahingoittuneeksi (sama kuin Varattavuus niteen muokkauksessa)
  - Pois kierrosta -tilaiseksi (jos sallittu)

![](/assets/files/docs/Tiedonhaku/tietue8_2024.png)  

Historia-tiedoista näkee:

- tilauspäivän
- toimittajan
- vastaanottopäivän
- laskun numeron
- niteen lainakerrat
- viimeisin havainto ja lainauspäivä
- viimeksi palauttaneen asiakkaan kirjastokortin numeron
- kolmen viimeksi lainanneen asiakkaan kirjastokortin numerot
- näkee ja voi asettaa yleisen huomautuksen tai viesti virkailijalle -huomautuksen

### 10.7.2. Hankintatiedot

_Hankintatiedot_-välilehdeltä näkee mm. miltä toimittajilta teosta on tilattu, milloin, mihin hintaan ja kuinka monta kappaletta. Jos on tarvittavat käyttäjäoikeudet, niin välilehden linkeistä pääsee toimittajatietoihin ja tilauskoreihin.

![](/assets/files/docs/Tiedonhaku/tietue3.png)

### 10.7.3. Teoksen ja niteen lainahistoria

Teoksen kaikkien niteiden lainahistoriaan pääsee vasemman reunan _Lainahistoria_-linkistä. Yksittäisen niteen lainahistoriaa pystyy tarkastelemaan _Niteet_-välilehdeltä _Näytä niteen lainahistoria_ -linkistä.

Lainahistoria-sivulla näkee
- teoksen kaikkien niteiden lainakerrat yhteensä
- viivakoodin, lainanneen kirjaston, onko uusittu, koska lainattu, mikä oli eräpäivä ja koska palautettu

![](/assets/files/docs/Tiedonhaku/tietue9.png)

Yksittäisen niteen lainahistorianäytöllä on listattuna kaikki kirjastot ja kuinka monta kertaa kyseinen nide on kirjastosta lainattu sekä viimeisin havaintopäivä.

![](/assets/files/docs/Tiedonhaku/tietue11.png)  

**Huomioi**: Jos nide palautetaan eri kirjastoon kuin mistä se on lainattu, tieto ei kirjaudu tälle näytölle. Eli tällä näytöllä näkyy vain lainaava kirjasto ja viimeisin havaintopäivä kirjautuu lainanneelle kirjastolle, vaikka palautus on tapahtunut toisessa kirjastossa.
{: .notice--warning}

## 10.8 Hakukone Elasticsearch ja sen indeksit

Yleiset ja tieteelliset Koha-kirjastot kokosivat yhdessä keväällä 2021 indeksoinnin (tiedonhaun) tarpeet ja siitä syntyi seuraavanlainen määrittely.

Osasta MARC-kentistä puuttuu kuvaus, koska ne eivät ole osa formaattia.

### 10.8.1 Indeksi, luokka, luokan selite

|Indeksin nimi|Luokka|Luokan selite|
|---|---|---|
|abtract|520|Huomatus sisällöstä, tiivistelmä, tms.|
|accessibility-content|341abcde|Saavutettavuussisältö|
|acqsource|952e|Hankintapaikka - nidetieto|
|agelevel|049c|Tarkastus tai inventointi - suomalainen kenttä - elokuvan tai pelin ikäraja|
|agelevel|521a|Huomautus kohderyhmästä|
|alt-performance-medium|382p|Vaihtoehtoinen esityskokoonpano|
|arl|526c|Lukutaidon aste|
|arp|526d|Nimekkeen pistearvo|
|audience-term|385a|Kohderyhmä|
|auth-code|042a|autentikointikoodi|
|author|100a|Pääkirjaus - henkilönnimi|
|author|110a|Pääkirjaus - yhteisönnimi|
|author|111a|Pääkirjaus - kokouksen nimi|
|author|505r|Huomautus sisällön rakenteesta - tekijä|
|author|700a|Lisäkirjaus - henkilönnimi|
|author|710a|Lisäkirjaus - yhteisönimi|
|author|711a|Lisäkirjaus - kokouksen nimi|
|author|800a|Sarjalisäkirjaus - henkilönnimi|
|author|810a|Sarjalisäkirjaus - yhteisönnimi|
|author|811a|Sarjalisäkirjaus - kokouksen nimi|
|author|900a|Viittaus - henkilönnimi - suomalainen kenttä|
|author|910a|Viittaus - yhteisönnimi - suomalainen kenttä|
|author|911a|Viittaus - kokouksen nimi - suomalainen kenttä|
|author-in-order|245c|Vastuullisuusmerkinnöt jne.|
|author-in-order|505r|Huomautus sisällön rakenteesta - tekijä|
|author-name-corporate|110|Yhteisönnimi|
|author-name-corporate|111|Kokouksen nimi|
|author-name-corporate|710|Lisäkirjaus - Yhteisönnimi|
|author-name-corporate|711|Lisäkirjaus - Kokouksen nimi|
|author-name-corporate|810|Sarjalisäkirjaus - Yhteisönnimi|
|author-name-corporate|811|Sarjalisäkirjaus - Kokouksen nimi|
|author-name-personal|100|Pääkirjaus - henkilönnimi|
|author-name-personal|400|Katso-viittaus henkilönnimestä?|
|author-name-personal|700|Lisäkirjaus- henkilönnimi|
|author-name-personal|800|Sarjalisäkirjaus - henkilönnimi|
|author-personal-bibliography|100a|Pääkirjaus - henkilönnimi|
|author-title|100|Pääkirjaus - henkilönnimi|
|author-title|110|Pääkirjaus - yhteisönnimi|
|author-title|111|Pääkirjaus - kokouksen nimi|
|author-title|400t|-|
|author-title|410t|-|
|author-title|411t|-|
|author-title|700t|Lisäkirjaus - henkilönnimi, teoksen nimeke|
|author-title|710t|Lisäkirjaus - yhteisönnimi, teoksen nimeke|
|author-title|711t|Lisäkirjaus - kokouksen nimi, teoksen nimeke|
|author-title|800t|Sarjalisäkirjaus - henkilönnimi, teoksen nimeke|
|author-title|810t|Sarjalisäkirjaus - yhteisönnimi, teoksen nimeke|
|author-title|811t|Sarjalisäkirjaus - kokouksen nimi, teoksen nimeke|
|awards-note|586a|Huomautus palkinnosta|
|barcode|952p|Niteen viivakoodi|
|bfg-number|015|NBN-tunnus|
|bib-level|leader_/7|Tietueen taso (nimiö)|
|biblioitemnumber|999d|Tietueen biblionumber|
|bio|008_/34|Elämäkerta|
|bnb-card-number|015|NBN-tunnus|
|canceled-isbn|020z|Peruttu tai virheellinen ISBN-tunnus|
|canceled-issn|022z|Peruttu ISSN-tunnus|
|canceled-issn|490z|Peruttu ISSN-tunnus|
|carrier-type-term|338a|Tallennetyyppi|
|ccode (collection-code)|9528|Kokoelmakoodi|
|classification-source|9522|Niteen luokituksen lähde|
|cn-bib-sort|9426|Järjestämistä varten normalisoitu tietueen luokka|
|cn-bib-source|9422|Tietueen luokituksen lähde|
|cn-class|942h|Luokka|
|cn-item|942i|Item part|
|cn-prefix|942k|Signumin prefiksi|
|cn-sort|9526|Järjestämistä varten normalisoitu niteen luokka|
|cn-suffix|942m|Signumin suffiksi|
|cni|003|Tietueen kontrollinumeron tunniste|
|code-geographic|043|Maantieteellisen alueen koodi|
|code-institution|040|Luetteloiva organisaatio|
|coded-location-qualifier|952f|Niteen koodattu paikkamääre|
|coden|030|CODEN-tunnus|
|collection-960|960|-|
|conference-name|111|Pääkirjaus - Kokouksen nimi|
|conference-name|411|Katso-viittaus konferenssin nimestä?|
|conference-name|611|Kokouksen nimi asiasanana|
|conference-name|711|Lisäkirjaus - Kokouksen nimi|
|conference-name|811|Sarjalisäkirjaus - Kokouksen nimi|
|content-type-term|336a|Sisältötyyppi|
|control-number|001|Tietueen kontrollinumero|
|control-number-identifier|003|Tietueen kontrollinumeron tunniste|
|copydate|260c|Julkaisu-, jakelu- jne. aika|
|copydate|264c|Tuotanto-, julkaisu-/kustannus-, jakelu- tai valmistusaika tai tekijänoikeusvuosi|
|copydate|008_/7-10|Julkaisuaika|
|copynumber|952t|Nidenumero|
|corporate-name|110|Pääkirjaus - Yhteisönnimi|
|corporate-name|410|Katso-viittaus yhteisönnimestä?|
|corporate-name|610|Yhteisönnimi asiasanana|
|corporate-name|710|Lisäkirjaus - Yhteisönnimi|
|corporate-name|810|Sarjalisäkirjaus - Yhteisönnimi|
|creator-term|386a|Tekijän ominaisuudet - tekijä|
|cross-reference|1009|Linkitys tekijä-auktoritettiin|
|cross-reference|2459|Linkitys nimeke-auktoriteettiin|
|cross-reference|7009|Linkitys tekijä-auktoriteettiin|
|ctype|008_/24-27|Sisältö|
|curriculum|658abc|Opinto-ohjelman tai kurssin tavoitteet hakuterminä|
|damaged|9524|Niteen Vaurioitunut-arvo|
|date-entered-on-file|008_/0-5|Luontipäivä|
|date-of-acquisition|952d|Hankintapäivä niteessä|
|date-of-publication|008_/7-10|Julkaisuaika|
|date-of-publication|260c|Julkaisu-, jakelu- jne. aika|
|date-of-publication|264c|Tuotanto-, julkaisu-/kustannus-, jakelu- tai valmistusaika tai tekijänoikeusvuosi|
|date-time-last-modified|005|Viimeisimmän päivityksen ajankohta|
|datelastborrowed|952s|Viimeksi lainattu (nide)|
|datelastseen|952r|Viimeksi nähty (nide)|
|description-source-note|588a|Huomautus kuvailun perustasta|
|dewey-classification|082|Deweyn luokitus, DDC|
|dissertation-information|502|Huomautus väitöskirjasta|
|doubling-instrument|382d|Sivusoitin|
|editor|100a|Pääkirjaus - henkilönnimi|
|editor|700a|Lisäkirjaus - henkilönnimi|
|encoding-format|347b|Tiedostomuoto|
|extent|300|Ulkoasutiedot|
|ff7-00|007_/0|Aineistoluokka|
|ff7-01|007_/1|Aineiston erityismääre|
|ff7-01-02|007_/0-1|Aineistoluokka ja Aineiston erityismääre|
|ff7-02|007_/2|Määrittelemätön??|
|ff8-23|008_/23|Ilmiasu|
|ff8-29|008_/29|Kokousjulkaisu|
|geographic-class|052|Maantieteellinen luokitus|
|holdinglibrary|952b|Sijaintikirjasto|
|homelibrary|952a|Kotikirjasto|
|host-item|773at|Linkkikenttä - emokohde|
|host-item-number|7739|Linkkikenttä - emokohde|
|identifier-other|024aa|Muut standarditunnukset|
|identifier-publisher-for-music|028|Julkaisijan ja jakajan tunnus|
|identifier-standard|010|Library of Congress kontrollinumero|
|identifier-standard|011|?|
|identifier-standard|015|NBN-tunnus|
|identifier-standard|017|Tekijänoikeus- tai vapaakappaletunnus|
|identifier-standard|018|Artikkelin tekijänoikeusmaksun koodi|
|identifier-standard|020a|ISBN-tunnus|
|identifier-standard|022a|ISSN-tunnus| 
|identifier-standard|024a|Muut standarditunnukset|
|incorrect-issn|022y|ISSN-tunnus (virheellinen)|
|incorrect-issn|490y|ISSN-tunnus (virheellinen)|
|index-term-genre|655a|Aineiston lajityyppi/muoto hakuterminä|
|index-term-genre|655x|Aineiston lajityyppi/muoto hakuterminä|
|index-term-uncontrolled|653a|Kontrolloimaton hakutermi|
|indexed-by|510|Huomautus tietolähteestä|
|interest-age-level|049c|Tarkastus tai inventointi - suomalainen kenttä - elokuvan tai pelin ikäraja|
|interest-age-level|521a|Huomautus kohderyhmästä|
|interest-grade-level|521a|Huomautus kohderyhmästä|
|isbn|020a|ISBN-tunnus|
|isbn-all|020a|ISBN-tunnus|
|isbn-all|020z|Peruttu tai virheellinen ISBN-tunnus|
|issn|022a|ISSN-tunnus|
|issn|490x|ISSN-tunnus, International Standard Serial Number|
|issn|830x|Sarjalisäkirjauksen ISSN|
|issn-all|022a|ISSN-tunnus|
|issn-all|022y|ISSN-tunnus (virheellinen)|
|issn-all|022z|Peruttu ISSN-tunnus|
|issn-all|490x|ISSN-tunnus, International Standard Serial Number|
|issn-all|490y|ISSN-tunnus (virheellinen)|
|issn-all|490z|Peruttu ISSN-tunnus|
|issn-all|830x|Sarjalisäkirjauksen ISSN|
|issues|952l|Lainauksia|
|itemnumber|9529|Niteen numero|
|itemtype|942c|Aineistotyyppi|
|itemtype|952y|Nidetyyppi|
|itype|942c|Aineistotyyppi|
|koha-auth-number|1000|Pääkirjaus - henkilönnimi - auktoriteettitietueen kontollinumero|
|koha-auth-number|1100|Pääkirjaus - yhteisönnimi - auktoriteettitietueen kontollinumero|
|koha-auth-number|1110|Pääkirjaus - kokouksen nimi - auktoriteettitietueen kontollinumero|
|koha-auth-number|1300|Pääkirjaus - yhtenäistetty nimeke - auktoriteettitietueen kontollinumero|
|koha-auth-number|2450|?|
|koha-auth-number|4000|?|
|koha-auth-number|4100|?|
|koha-auth-number|4400|?|
|koha-auth-number|4900|?|
|koha-auth-number|6000|Henkilönnimi asiasanana - auktoriteettitietueen kontollinumero|
|koha-auth-number|6100|Yhteisönnimi asiasanana - auktoriteettitietueen kontollinumero|
|koha-auth-number|6110|Kokouksen nimi asiasanana - auktoriteettitietueen kontollinumero|
|koha-auth-number|6300|Yhtenäistetty nimeke asiasanana - auktoriteettitietueen kontollinumero|
|koha-auth-number|6480|Aikaa ilmaiseva termi asiasanana - auktoriteettitietueen kontollinumero|
|koha-auth-number|6510|Maantieteellinen nimi asiasanana - auktoriteettitietueen kontollinumero|
|koha-auth-number|6520|?|
|koha-auth-number|6530|?|
|koha-auth-number|6540|Fasettianalysoitu asiasana - auktoriteettitietueen kontollinumero|
|koha-auth-number|6500|Kontrolloidun asiasanaston asiasana - auktoriteettitietueen kontollinumero|
|koha-auth-number|6550|Aineiston lajityyppi/muoto hakuterminä - auktoriteettitietueen kontollinumero|
|koha-auth-number|6560|Ammatti hakuterminä - auktoriteettitietueen kontollinumero|
|koha-auth-number|6570|Tapahtuma tai toiminto hakuterminä - auktoriteettitietueen kontollinumero|
|koha-auth-number|6620|Hierarkkinen maantieteellinen nimi asiasanana - auktoriteettitietueen kontollinumero|
|koha-auth-number|6900|?|
|koha-auth-number|6910|?|
|koha-auth-number|6960|?|
|koha-auth-number|6970|?|
|koha-auth-number|6980|?|
|koha-auth-number|6990|?|
|koha-auth-number|7000|Lisäkirjaus - henkilönnimi - auktoriteettitietueen kontollinumero|
|koha-auth-number|7100|Lisäkirjaus - yhteisönnimi - auktoriteettitietueen kontollinumero|
|koha-auth-number|7110|Lisäkirjaus - kokouksen nimi - auktoriteettitietueen kontollinumero|
|koha-auth-number|7300|Lisäkirjaus - yhtenäistetty nimeke - auktoriteettitietueen kontollinumero|
|koha-auth-number|7510|Lisäkirjaus - maantieteellinen nimi - auktoriteettitietueen kontollinumero|
|koha-auth-number|7960|?|
|koha-auth-number|7970|?|
|koha-auth-number|7980|?|
|koha-auth-number|7990|?|
|koha-auth-number|8000|Sarjalisäkirjaus - henkilönnimi - auktoriteettitietueen kontollinumero|
|koha-auth-number|8100|Sarjalisäkirjaus - yhteisönnimi - auktoriteettitietueen kontollinumero|
|koha-auth-number|8110|Sarjalisäkirjaus - kokouksen nimi - auktoriteettitietueen kontollinumero|
|koha-auth-number|8300|Sarjalisäkirjaus - yhtenäistetty nimeke - auktoriteettitietueen kontollinumero|
|koha-auth-number|8960|?|
|koha-auth-number|8970|?|
|koha-auth-number|8980|?|
|koha-auth-number|8990|?|
|language-intermediate-translation|041k|Kielikoodi - välikäännösten kieli|
|language-original|041h|Kielikoodi - alkuperäinen kieli|
|lc-call-number|050b|Library of Congress -luokitus - kappalenumero|
|lc-card-number|010|Library of Congress kontrollinumero|
|lc-card-number|011|?|
|lexile-number|521a|Huomautus kohderyhmästä|
|lf|008_/33|Kirjallisuuslaji|
|library-specific-notes|598a|Paikallinen huomautus|
|library-specific-notes|599a|Paikallinen huomautus|
|llength|leader_/0-4|Tietueen pituus|
|ln|008_/35-37|Kieli|
|ln|041a|Kielikoodi - tekstin tai ääniraidan kieli|
|ln|041d|Kielikoodi - lauletun tai puhutun aineiston kieli |
|ln|041j|Kielikoodi - tekstityksen kieli|
|ln-acaudio|041q|Kielikoodi - äänivastineen kieli|
|ln-audio|041a|Kielikoodi - tekstin tai ääniraidan kieli|
|ln-audio|041d|Kielikoodi - lauletun tai puhutun aineiston kieli|
|ln-captions|041p|Kielikoodi - Kuulovammaisille tarkoitetun tekstityksen kieli|
|ln-subtitle|041j|Kielikoodi - tekstityksen kieli|
|ln-visual|041r|Kielikoodi - Visuaalinen kieli (ei-teksti)|
|local-classification|952o|Kohan koko signum|
|local-number|999c|Kohan biblionumber|
|location|952c|Hyllypaikka|
|location-item-part|852i|Sijainti|
|lost|9521|Kadonnut-tila|
|map-scale|034|Kartta-aineiston matemaattiset tiedot koodeina|
|material-type|007|Ulkoasutiedot|
|materials-specified|9523|Liitteiden määrä|
|media-type-term|337a|Mediatyyppi|
|methodology-controlled-term|567b|Huomautus metodologiasta|
|microform-generation|007_/11|Mikrotallenteen sukupolvi|
|mtype|942c|Aineistotyyppi|
|music-key|130r|Pääkirjaus - yhtenäistetty nimeke - sävellaji|
|music-key|240r|Yhtenäistetty nimeke - sävellaji|
|music-key|243r|Kokoava yhtenäistetty nimeke - sävellaji|
|music-key|630r|Yhtenäistetty nimeke asiasanana - sävellaji|
|music-key|700r|Lisäkirjaus - henkilönnimi - sävellaji|
|music-key|730r|Lisäkirjaus - yhtenäistetty nimeke - sävellaji|
|musical-opus-number|383b|Musiikkiteoksen numerointimerkintö|
|musical-publisher-with-opus|383e|Musiikkiteoksen numerointimerkintö|
|musical-serial-number|383a|Musiikkiteoksen numerointimerkintö|
|musical-thematic-index-number|383c|Musiikkiteoksen numerointimerkintö|
|nal-call-number|070|National Agricultural Library -luokitus|
|name|100|Pääkirjaus - henkilönnimi|
|name|110|Pääkirjaus - yhteisönnimi|
|name|111|Pääkirjaus - kokouksen nimi|
|name|400||
|name|600a|Henkilönnimi asiasanana|
|name|610|Yhteisönnimi asiasanana|
|name|611|Kokouksen nimi asiasanana|
|name|700|Lisäkirjaus - henkilönnimi|
|name|710|Lisäkirjaus - yhteisönnimi |
|name|711|Lisäkirjaus - kokouksennimi|
|name|800|Sarjalisäkirjaus - henkilönnimi|
|name|810|Sarjalisäkirjaus - yhteisönnimi|
|name|811|Sarjalisäkirjaus - kokouksen nimi|
|name-and-title|100|Pääkirjaus - henkilönnnimi|
|name-and-title|110|Pääkirjaus - yhteisönnimi|
|name-and-title|111|Pääkirjaus - kokouksen nimi|
|name-and-title|400at||
|name-and-title|410at||
|name-and-title|411at||
|name-and-title|600at|Henkilönnimi asiasanana + teoksen nimeke|
|name-and-title|610at|Yhteisönniminimi asiasanana + teoksen nimeke|
|name-and-title|611at|Kokouksen nimi asiasanana + teoksen nimeke|
|name-and-title|700at|Lisäkirjaus - henkilönnimi + teoksen nimeke|
|name-and-title|710at|Lisäkirjaus - yhteisönnimi + teoksen nimeke|
|name-and-title|711at|Lisäkirjaus - kokouksen nimi + teoksen nimeke|
|name-and-title|800at|Sarjalisäkirjaus - henkilönnimi + teoksen nimeke|
|name-and-title|810at|Sarjalisäkirjaus - yhteisönnimi + teoksen nimeke|
|name-and-title|811at|Sarjalisäkirjaus - kokouksen nimi + teoksen nimeke|
|name-geographic|651|Maantieteellinen nimi asiasanana|
|name-geographic|751a|Lisäkirjaus - maantieteellinen nimi|
|nlm-call-number|060|National Library of Medicine -luokitus|
|not-onloan-count|999x|Koha-kenttä|
|notated-music-format-term|348a|Nuottiaineiston muoto|
|note|500|Yleinen huomautus|
|note|505|Huomautus sisällön rakenteesta|
|note|509ac|Huomautus muusta opinnäytteestä|
|note|546a|Huomautus kielistä|
|note|590|Paikallinen huomautus|
|note|594a|Paikallinen huomautus|
|note|598a|Paikallinen huomautus|
|note|599a|Paikallinen huomautus|
|note|952z|Yleinen huomautus|
|notforloan|9527|Ei lainattavissa|
|number-db|015|NBN-tunnus, National Bibliography Number|
|number-govt-pub|086|Virallisjulkaisujen luokitus|
|number-legal-deposit|017|Tekijänoikeus- tai vapaakappaletunnus|
|number-local-acquisition|952i|Inventaarionumero|
|number-natl-biblio|015|NBN-tunnus|
|onloan|952q|Lainassa|
|other-classification|084a|Luokka|
|other-control-number|035|Järjestelmän tuottama kontrollinumero|
|ownership-history|561a|Huomautus omistushistoriasta|
|performance-medium|382a|Esityskokoonpano|
|performance-note|382v|Esityskokoonpanon huomautus|
|personal-name|100|Henkilönnimi|
|personal-name|400||
|personal-name|600a|Henkilönnimi asiasanana|
|personal-name|700|Lisäkirjaus - henkilönnimi|
|personal-name|800|Sarjalisäkirjaus - henkilönnimi|
|pl|008_/15-17|Julkaisu-, tuotanto- tai toteuttamismaa|
|place-of-origin|	257a|Tuottajan maa|
|place-of-origin|	370g|Teoksen tai ekspression luontipaikka|
|place-of-origin|	655z|Maantieteellinen lisämääre|
|place-of-publication|	260a|Julkaisu-/kustannus-, jakelu- jne. paikka|
|place-of-publication	|264a|Tuotanto-, julkaisu-/kustannus-, jakelu- tai valmistuspaikka|
|placement|	852h|Paikkamerkin hyllyluokka|
|price|952g|Hankintahinta|
|provider|260|Julkaisutiedot|
|provider|264|Huomautus tuotanto-, julkaisu-/kustannus-, jakelu-, valmistus- tai tekijänoikeustiedoista|
|publisher|264b|Tuottajan, julkaisijan/kustantajan, jakajan tai valmistajan nimi|
|publisher|260b|Julkaisijan/kustantajan, jakajan jne. nimi|
|reading-grade-level|521a|Huomautus kohderyhmästä|
|record-control-number|770w|Tietueen kontrollinumero - linkkikenttä suplementti/erikoisnumero|
|record-control-number|772w|Tietueen kontrollinumero - linkkikenttä suplementin pääjulkaisu|
|record-control-number|773w|Tietueen kontrollinumero - linkkikenttä emokohde|
|record-control-number|774w|Tietueen kontrollinumero - linkkikenttä osakohde|
|record-control-number|775w|Tietueen kontrollinumero - linkkikenttä muu painos|
|record-control-number|776w|Tietueen kontrollinumero - linkkikenttä toinen ilmiasu|
|record-control-number|777w|Tietueen kontrollinumero - linkkikenttä kanssajulkaisu|
|record-control-number|780w|Tietueen kontrollinumero - linkkikenttä edeltäjä|
|record-control-number|785w|Tietueen kontrollinumero - linkkikenttä seuraaja|
|record-control-number|787w|Tietueen kontrollinumero - linkkikenttä muu suhde|
|record-control-number|800w|Bibliografisen tietueen kontrollinumero - sarjalisäkirjaus henkilönnimi|
|record-control-number|810w|Bibliografisen tietueen kontrollinumero - sarjalisäkirjaus yhteisönnimi|
|record-control-number|811w|Bibliografisen tietueen kontrollinumero - sarjalisäkirjaus kokouksen nimi|
|record-control-number|830w|Bibliografisen tietueen kontrollinumero - sarjalisäkirjaus yhtenäistetty nimeke|
|record-control-number-773w|773w|Tietueen kontrollinumero - linkkikenttä emokohde|
|record-source|008_/39|Luetteloiva organisaatio|
|related-periodical|247|Aikaisempi nimeke (kausijulkaisu)|
|related-periodical|780|Linkkikenttä edeltäjä|
|related-periodical|785|Linkkikenttä seuraaja|
|renewals|952m|Uusintojen määrä|
|replacementprice|952v|Korvaushinta|
|replacementpricedate|952w|Hinta voimassa alkaen|
|report-number|027|ISRN-tunnus tai muu standardoitu raporttinumero|
|reserves|952n|Varauksien määrä|
|restricted|9525|Käyttörajoitukset|
|rtype|leader_/6|Tietueen tyyppi|
|soloist|382b|Solisti|
|standardized-terms-of-access|506f|Pääsyrajoitus standarditerminologialla|
|stock-number|037|Hankintapaikka|
|su-geo|650z|Maantieteellinen lisämääre|
|su-geo|651a|Maantieteellinen nimi|

|subject|348a|Termi nuottiaineiston muodolle|
|subject|600a|Henkilönnimi|
|subject|600b|Numerointi (henkilönnimessä)|
|subject|600t|Teoksen nimeke|
|subject|610a|Yhteisönnimi |
|subject|610b|Alayksikkö (yhteisönnimessä)|
|subject|610t|Teoksen nimeke|
|subject|611ancdet|Kokouksen nimi asiasanana|
|subject|630a|Yhtenäistetty nimeke|
|subject|630n|Numerointitieto (yhtenäistetty nimeke)|
|subject|630p|Teoksen osan nimeke|
|subject|630r|Sävellaji|
|subject|648a|Aikaa ilmaiseva termi|
|subject|650a|Aihetta ilmaiseva termi tai maantieteellinen nimi|
|subject|650b|Maantieteellistä nimeä seuraava aihetta ilmaiseva termi|
|subject|650c|Tapahtumapaikka|
|subject|650d|Tapahtuman aika|
|subject|650v|Muotoa ilmaiseva lisämääre|
|subject|650x|Yleinen lisämääre|
|subject|650y|Aikaa ilmaiseva lisämääre|
|subject|650z|Maantieteellinen lisämääre|
|subject|651a|Maantieteellinen nimi asiasanana|
|subject|653a|Kontrolloimaton hakutermi|
|subject|655a|Lajityyppiä/muotoa kuvaava termi tai fokustermi|
|subject|655x|Yleinen lisämääre (lajityypille)|
|subject-name-personal|600a|Henkilönnimi|
|subloc|952j|Hyllytarkenne|
|suppress|942n|?|
|system-control-number|035a|Järjestelmän tuottama kontrollinumero|
|system-control-number-cancelled|035z|Peruttu tai virheellinen kontrollinumero|
|system-details-note|538a|Huomautus järjestelmävaatimuksista|
|ta|008_/22|Kohderyhmä?|
|terms-governing-use-and-reproduction|540abc|Käytön ja kopioinnin ehdot, käyttöluvan antaja, käyttöehtojen peruste|
|terms-of-access|506a|Pääsyrajoituksen ehdot|
|terms-of-use|540a|Käytön ja kopioinnin ehdot|
|terms-of-use-authorization|540c|Käyttöehtojen peruste|
|terms-of-use-jurisdiction|540b|Käyttöluvan antaja|
|thematic-number|630n|Numerointitieto (yhtenäistetty nimeke)|
|thematic-number|130n|Numerointitieto (yhtenäistetty nimeke)|
|thematic-number|240n|Numerointitieto (yhtenäistetty nimeke)|
|thematic-number|243n|Numerointitieto (yhtenäistetty nimeke)|
|thematic-number|700n|Numerointitieto (lisäkirjaus henkilönnimi)|
|thematic-number|730n|Numerointitieto (yhtenäistetty nimeke)|
|time-period|388a|Luomisaika|
|time-period|655y|Aikaa ilmaiseva lisämääre|
|title|130|Yhtenäistetty nimeke|
|title|210|Lyhennetty nimeke|
|title|211|?|
|title|212|?|
|title|214|?|
|title|222|Avainnimeke|
|title|240|Yhtenäistetty nimeke|
|title|245abnp|Päänimeke, muut nimeketiedot|
|title|246|Muut nimekkeet|
|title|247|Aikaisempi nimeke|
|title|490a|Sarjamerkintö|
|title|505t|Nimeke (huomautus sisällön rakenteesta)|
|title|700t|Teoksen nimeke|
|title|710t|Teoksen nimeke|
|title|711t|Teoksen nimeke|
|title|730|Yhtenäistetty nimeke (lisäkirjaus)|
|title|740|Nimeke, kontrolloimaton ja kohteeseen liittyvä tai analyyttinen (lisäkirjaus)|
|title|775t| Muun painoksen nimeke|
|title|780|Edeltäjä - linkkikenttä|
|title|785|Seuraaja - linkkikenttä|
|title-abbreviated|210|Lyhennetty nimeke|
|title-abbreviated|211|?|
|title-abbreviated|246|Muut nimekkeet|
|title-collective|243|Kokoava yhtenäistetty nimeke|
|title-cover|245a|Päänimeke|
|title-expanded|214|?|
|title-expanded|246|Muut nimekkeet|
|title-former|246|Muut nimekkeet|
|title-former|247|Aikaisempi nimeke|
|title-former|780|Edeltäjä - linkkikenttä|
|title-key|222|Avainnimeke|
|title-later|785|Seuraaja - linkkikenttä|
|title-other-variant|212|?|
|title-other-variant|247|Aikaisempi nimeke|
|title-other-variant|740|Nimeke, kontrolloimaton ja kohteeseen liittyvä tai analyyttinen (lisäkirjaus)|
|title-other-variant|775t| Muun painoksen nimeke|
|title-series|440a|Sarjamerkintö lisäkirjausmuodossa|
|title-series|490a|Sarjamerkintö (ei lisäkirjausmuodossa)|
|title-series|800t|Teoksen nimeke (sarjalisäkirjaus henkilönnimi)|
|title-series|830a|Yhtenäistetty nimeke (sarjalisäkirjaus)|
|title-series|830n|Numerointitieto (sarjalisäkirjaus)|
|title-series|830p|Teoksen osan nimeke (sarjalisäkirjaus)|
|title-series|830v|Sarjan sisäinen numerointi|
|title-uniform|130|Yhtenäistetty nimeke|
|title-uniform|240|Yhtenäistetty nimeke|
|title-uniform|700t|Teoksen nimeke|
|title-uniform|710t|Teoksen nimeke|
|title-uniform|711t|Teoksen nimeke|
|title-uniform|730|Yhtenäistetty nimeke|
|title-uniform|830a|Yhtenäistetty nimeke (sarjalisäkirjaus)|
|title-uniform|830n|Numerointitieto (sarjalisäkirjaus)|
|title-uniform|830p|Teoksen osan nimeke (sarjalisäkirjaus)|
|title-uniform|830v|Sarjan sisäinen numerointi|
|totalissues|9420|?|
|udc-aux-subdivision|080x|UDK lisäluku|
|udc-classification|080|Yleinen kymmenluokitus (UDK)|
|uri|952u|URI|
|withdrawn|9520|Pois kierrosta -tila|

### 10.8.2 Luokka, luokan selite, indeksi

|Luokka|Luokan selite|Indeksi|
|---|---|---|
|001|Tietueen kontrollinumero|control-number|
|003|Tietueen kontrollinumeron tunniste|cni|
|003|Tietueen kontrollinumeron tunniste|control-number-identifier|
|005|Viimeisimmän päivityksen ajankohta|date-time-last-modified|
|007|Ulkoasutiedot|material-type|
|007_/0|Aineistoluokka|ff7-00|
|007_/0-1|Aineistoluokka ja Aineiston erityismääre|ff7-01-02|
|007_/1|Aineiston erityismääre|ff7-01|
|007_/11|Mikrotallenteen sukupolvi|microform-generation|
|007_/2|Määrittelemätön??|ff7-02|
|008_/0-5|Luontipäivä|date-entered-on-file|
|008_/15-17|Julkaisu-, tuotanto- tai toteuttamismaa|pl|
|008_/22|Kohderyhmä?|ta|
|008_/23|Ilmiasu|ff8-23|
|008_/24-27|Ilmiasu|ctype|
|008_/29|Kokousjulkaisu|ff8-29|
|008_/33|Kirjallisuuslaji|lf|
|008_/34|Elämäkerta|bio|
|008_/35-37|Kieli|ln|
|008_/39|Luetteloiva organisaatio|record-source|
|008_/7-10|Julkaisuaika|date-of-publication|
|008_/7-10|Julkaisuaika|copydate|
|010|Library of Congress kontrollinumero|identifier-standard|
|010|Library of Congress kontrollinumero|lc-card-number|
|011|?|identifier-standard|
|011|?|lc-card-number|
|015|NBN-tunnus|identifier-standard|
|015|NBN-tunnus|number-natl-biblio|
|015|NBN-tunnus|number-db|
|017|Tekijänoikeus- tai vapaakappaletunnus|identifier-standard|
|017|Tekijänoikeus- tai vapaakappaletunnus|number-legal-deposit|
|018|Artikkelin tekijänoikeusmaksun koodi|identifier-standard|
|020a|ISBN-tunnus|identifier-standard|
|020a|ISBN-tunnus|isbn|
|020a|ISBN-tunnus|isbn-all|
|020z|Peruttu tai virheellinen ISBN-tunnus|canceled-isbn|
|020z|Peruttu tai virheellinen ISBN-tunnus|isbn-all|
|022a|ISSN-tunnus|identifier-standard|
|022a|ISSN-tunnus|issn|
|022a|ISSN-tunnus|issn-all|
|022y|ISSN-tunnus (virheellinen)|incorrect-issn|
|022y|ISSN-tunnus (virheellinen)|issn-all|
|022z|Peruttu ISSN-tunnus|canceled-issn|
|022z|Peruttu ISSN-tunnus|issn-all|
|024a|Muut standarditunnukset|identifier-standard|
|024aa|Muut standarditunnukset|identifier-other|
|027|ISRN-tunnus tai muu standardoitu raporttinumero|report-number|
|028|Julkaisijan ja jakajan tunnus|identifier-publisher-for-music|
|030|CODEN-tunnus|coden|
|034|Kartta-aineiston matemaattiset tiedot koodeina|map-scale|
|035|Järjestelmän tuottama kontrollinumero|other-control-number|
|035a|Järjestelmän tuottama kontrollinumero|system-control-number|
|035z|Peruttu tai virheellinen kontrollinumero|system-control-number-cancelled|
|037|Hankintapaikka|stock-number|
|040|Luetteloiva organisaatio|code-institution|
|041a|Kielikoodi - tekstin tai ääniraidan kieli|ln|
|041a|Kielikoodi - tekstin tai ääniraidan kieli|ln-audio|
|041d|Kielikoodi - lauletun tai puhutun aineiston kieli|ln-audio|
|041d|Kielikoodi - lauletun tai puhutun aineiston kieli|ln|
|041h|Kielikoodi - alkuperäinen kieli|language-original|
|041j|Kielikoodi - tekstityksen kieli|ln-subtitle|
|041j|Kielikoodi - tekstityksen kieli|ln|
|041k|Kielikoodi - välikäännösten kieli|language-intermediate-translation|
|041p|Kielikoodi - Kuulovammaisille tarkoitetun tekstityksen kieli|ln-captions|
|041q|Kielikoodi - äänivastineen kieli|ln-acaudio|
|041r|Kielikoodi - Visuaalinen kieli (ei-teksti)|ln-visual|
|042a|autentikointikoodi|auth-code|
|043|Maantieteellisen alueen koodi|code-geographic|
|049c|Tarkastus tai inventointi - suomalainen kenttä - elokuvan tai pelin ikäraja|agelevel|
|049c|Tarkastus tai inventointi - suomalainen kenttä - elokuvan tai pelin ikäraja|interest-age-level|
|050b|Library of Congress -luokitus - kappalenumero|lc-call-number|
|052|Maantieteellinen luokitus|geographic-class|
|060|National Library of Medicine -luokitus|nlm-call-number|
|070|National Agricultural Library -luokitus|nal-call-number|
|080|National Agricultural Library -luokitus|udc-classification|
|080x|UDK lisäluku|udc-aux-subdivision|
|082|Deweyn luokitus, DDC|dewey-classification|
|084a|Luokka|other-classification|
|086|Virallisjulkaisujen luokitus|number-govt-pub|
|100|Pääkirjaus - henkilönnimi|author-name-personal|
|100|Pääkirjaus - henkilönnimi|name|
|100|Pääkirjaus - henkilönnimi|author-title|
|100|Pääkirjaus - henkilönnimi|personal-name|
|100|Pääkirjaus - henkilönnimi|name-and-title|
|1000|Pääkirjaus - henkilönnimi - auktoriteettitietueen kontollinumero|koha-auth-number|
|1009|Linkitys tekijä-auktoritettiin|cross-reference|
|100a|Pääkirjaus - henkilönnimi|author|
|100a|Pääkirjaus - henkilönnimi|editor|
|100a|Pääkirjaus - henkilönnimi|author-personal-bibliography|
|110|Yhteisönnimi|author-name-corporate|
|110|Pääkirjaus - yhteisönnimi|name|
|110|Pääkirjaus - yhteisönnimi|author-title|
|110|Pääkirjaus - yhteisönnimi|corporate-name|
|110|Pääkirjaus - yhteisönnimi|name-and-title|
|1100|Pääkirjaus - henkilönnimi - auktoriteettitietueen kontollinumero|koha-auth-number|
|110a|Pääkirjaus - yhteisönönnimi|author|
|111|Pääkirjaus - kokouksen nimi|name-and-title|
|111|Kokouksen nimi|author-name-corporate|
|111|Kokouksen nimi|conference-name|
|111|Kokouksen nimi|name|
|111|Pääkirjaus - kokouksen nimi|author-title|
|1110|Pääkirjaus - kokouksen nimi - auktoriteettitietueen kontollinumero|koha-auth-number|
|111a|Pääkirjaus - kokouksen nimi|author|
|130|Yhtenäistetty nimeke|title|
|130|Yhtenäistetty nimeke|title-uniform|
|1300|Pääkirjaus - yhtenäistetty nimeke - auktoriteettitietueen kontollinumero|koha-auth-number|
|130n|Numerointitieto (yhtenäistetty nimeke)|thematic-number|
|130r|Pääkirjaus - yhtenäistetty nimeke - sävellaji|music-key|
|210|Lyhennetty nimeke|title|
|210|Lyhennetty nimeke|title-abbreviated|
|211|?|title|
|211|?|title-abbreviated|
|212|?|title-other-variant|
|212|?|title|
|214|?|title|
|214|?|title-expanded|
|222|Avainnimeke|title-key|
|222|Avainnimeke|title|
|240|Yhtenäistetty nimeke|title-uniform|
|240|Yhtenäistetty nimeke|title|
|240n|Numerointitieto (yhtenäistetty nimeke)|thematic-number|
|240r|Yhtenäistetty nimeke - sävellaji|music-key|
|243|Kokoava yhtenäistetty nimeke|title-collective|
|243n|Numerointitieto (yhtenäistetty nimeke)|thematic-number|
|243r|Kokoava yhtenäistetty nimeke - sävellaji|music-key|
|245(ab)|Päänimeke, muut nimeketiedot|title|
|2450|?|koha-auth-number|
|2459|Linkitys nimeke-auktoriteettiin|cross-reference|
|245a|Päänimeke|title-cover|
|245c|Vastuullisuusmerkinnöt jne.|author-in-order|
|246|Muut nimekkeet|title|
|246|Muut nimekkeet|title-abbreviated|
|246|Muut nimekkeet|title-expanded|
|246|Muut nimekkeet|title-former|
|247|Aikaisempi nimeke|title-other-variant|
|247|Aikaisempi nimeke|title|
|247|Aikaisempi nimeke|related-periodical|
|247|Aikaisempi nimeke|title-former|
|257a|Tuottajan maa|place-of-origin|
|260|Julkaisutiedot|provider|
|260a|Julkaisu-/kustannus-, jakelu- jne. paikka|place-of-publication|
|260b|Julkaisijan/kustantajan, jakajan jne. nimi|publisher|
|260c|Julkaisu-, jakelu- jne. aika|date-of-publication|
|260c|Julkaisu-, jakelu- jne. aika|copydate|
|264|Huomautus tuotanto-, julkaisu-/kustannus-, jakelu-, valmistus- tai tekijänoikeustiedoista|provider|
|264a|Tuotanto-, julkaisu-/kustannus-, jakelu- tai valmistuspaikka|place-of-publication|
|264b|Tuottajan, julkaisijan/kustantajan, jakajan tai valmistajan nimi|publisher|
|264c|Tuotanto-, julkaisu-/kustannus-, jakelu- tai valmistusaika tai tekijänoikeusvuosi|date-of-publication|
|264c|Tuotanto-, julkaisu-/kustannus-, jakelu- tai valmistusaika tai tekijänoikeusvuosi|copydate|
|300|Ulkoasutiedot|extent|
|336a|Sisältötyyppi|content-type-term|
|337a|Mediatyyppi|media-type-term|
|338a|Tallennetyyppi|carrier-type-term|
|341abcde|Saavutettavuussisältö|accessibility-content|
|347b|Tiedostomuoto|encoding-format|
|348a|Termi nuottiaineiston muodolle|subject|
|348a|Termi nuottiaineiston muodolle|notated-music-format-term|
|370g|Teoksen tai ekspression luontipaikka|place-of-origin|
|382a|Esityskokoonpano|performance-medium|
|382b|Solisti|soloist|
|382d|Sivusoitin|doubling-instrument|
|382p|Vaihtoehtoinen esityskokoonpano|alt-performance-medium|
|382v|Esityskokoonpanon huomautus|performance-note|
|383a|Musiikkiteoksen numerointimerkintö|musical-serial-number|
|383b|Musiikkiteoksen numerointimerkintö|musical-opus-number|
|383c|Musiikkiteoksen numerointimerkintö|musical-thematic-index-number|
|383e|Musiikkiteoksen numerointimerkintö|musical-publisher-with-opus|
|385a|Kohderyhmä|audience-term|
|386a|Tekijän ominaisuudet - tekijä|creator-term|
|388a|Luomisaika|time-period|
|400|Katso-viittaus henkilönnimestä?|author-name-personal|
|400||name|
|400||personal-name|
|4000||koha-auth-number|
|400at||name-and-title|
|400t||author-title|
|410|Katso-viittaus yhteisönnimestä?|corporate-name|
|4100||koha-auth-number|
|410at||name-and-title|
|410t||author-title|
|411|Katso-viittaus konferenssin nimestä?|conference-name|
|411at||name-and-title|
|411t||author-title|
|4400||koha-auth-number|
|440a|Sarjamerkintö lisäkirjausmuodossa|title-series|
|4900||koha-auth-number|
|490a|Sarjamerkintö (ei lisäkirjausmuodossa)|title-series|
|490a|Sarjamerkintö|title|
|490x|ISSN-tunnus, International Standard Serial Number|issn|
|490x|ISSN-tunnus, International Standard Serial Number|issn-all|
|490y|ISSN-tunnus (virheellinen)|incorrect-issn|
|490y|ISSN-tunnus (virheellinen)|issn-all|
|490z|Peruttu ISSN-tunnus|canceled-issn|
|490z|Peruttu ISSN-tunnus|issn-all|
|500|Yleinen huomautus|note|
|502|Huomautus väitöskirjasta|dissertation-information|
|505|Huomautus sisällön rakenteesta|note|
|505r|Huomautus sisällön rakenteesta - tekijä|author|
|505r|Huomautus sisällön rakenteesta - tekijä|author-in-order|
|505t|Nimeke (huomautus sisällön rakenteesta)|title|
|506a|Pääsyrajoituksen ehdot|terms-of-access|
|506f|Pääsyrajoitus standarditerminologialla|standardized-terms-of-access|
|509ac|Huomautus muusta opinnäytteestä|note|
|510|Huomautus tietolähteestä|indexed-by|
|520|Huomatus sisällöstä, tiivistelmä, tms.|abstract|
|521a|Huomautus kohderyhmästä|agelevel|
|521a|Huomautus kohderyhmästä|interest-age-level|
|521a|Huomautus kohderyhmästä|interest-grade-level|
|521a|Huomautus kohderyhmästä|reading-grade-level|
|521a|Huomautus kohderyhmästä|lexile-number|
|526c|Lukutaidon aste|arl|
|526d|Nimekkeen pistearvo|arp|
|538a|Huomautus järjestelmävaatimuksista|system-details-note|
|540a|Käytön ja kopioinnin ehdot|terms-of-use|
|540abc|Käytön ja kopioinnin ehdot, käyttöluvan antaja, käyttöehtojen peruste|terms-governing-use-and-reproduction|
|540b|Käyttöluvan antaja|terms-of-use-jurisdiction|
|540c|Käyttöehtojen peruste|terms-of-use-authorization|
|546c|Huomautus kielistä|note|
|561a|Huomautus omistushistoriasta|ownership-history|
|567b|Huomautus metodologiasta|methodology-controlled-term|
|586a|Huomautus palkinnosta|awards-note|
|588a|Huomautus kuvailun perustasta|description-source-note|
|590|Paikallinen huomautus|note|
|594a|Paikallinen huomautus|note|
|598a|Paikallinen huomautus|note|
|598a|Paikallinen huomautus|library-specific-notes|
|599a|Paikallinen huomautus|note|
|599a|Paikallinen huomautus|library-specific-notes|
|6000|Henkilönnimi asiasanana - auktoriteettitietueen kontollinumero|koha-auth-number|
|600a|Henkilönnimi|subject|
|600a|Henkilönnimi|subject-name-personal|
|600a|Henkilönnimi|name|
|600a|Henkilönnimi|personal-name|
|600at|Henkilönnimi asiasanana + teoksen nimeke|name-and-title|
|600b|Numerointi (henkilönnimessä)|subject|
|600t|Teoksen nimeke|subject|
|610|Yhteisönnimi asiasanana|corporate-name|
|610|Yhteisönnimi|name|
|6100|Yhteisönnimi asiasanana - auktoriteettitietueen kontollinumero|koha-auth-number|
|610a|Yhteisönnimi |subject|
|610at|Yhteisönniminimi asiasanana + teoksen nimeke|name-and-title|
|610b|Alayksikkö (yhteisönnimessä)|subject|
|610t|Teoksen nimeke|subject|
|611|Kokouksen nimi asiasanana|subject|
|611|Kokouksen nimi asiasanana|conference-name|
|611|Kokouksen nimi asiasanana|name|
|6110|Kokouksen nimi asiasanana - auktoriteettitietueen kontollinumero|koha-auth-number|
|611at|Kokouksen nimi asiasanana + teoksen nimeke|name-and-title|
|6300|Yhtenäistetty nimeke asiasanana - auktoriteettitietueen kontollinumero|koha-auth-number|
|630a|Yhtenäistetty nimeke|subject|
|630n|Numerointitieto (yhtenäistetty nimeke)|subject|
|630n|Numerointitieto (yhtenäistetty nimeke)|thematic-number|
|630p|Teoksen osan nimeke|subject|
|630r|Sävellaji|subject|
|630r|Yhtenäistetty nimeke asiasanana - sävellaji|music-key|
|6480|Aikaa ilmaiseva termi asiasanana - auktoriteettitietueen kontollinumero|koha-auth-number|
|648a|Aikaa ilmaiseva termi|subject|
|6500|Kontrolloidun asiasanaston asiasana - auktoriteettitietueen kontollinumero|koha-auth-number|
|650a|Aihetta ilmaiseva termi tai maantieteellinen nimi|subject|
|650b|Maantieteellistä nimeä seuraava aihetta ilmaiseva termi|subject|
|650c|Tapahtumapaikka|subject|
|650d|Tapahtuman aika|subject|
|650v|Muotoa ilmaiseva lisämääre|subject|
|650x|Yleinen lisämääre|subject|
|650y|Aikaa ilmaiseva lisämääre|subject|
|650z|Maantieteellinen lisämääre|su-geo|
|650z|Maantieteellinen lisämääre|subject|
|651ancdet|Maantieteellinen nimi asiasanana|subject|
|6510|Maantieteellinen nimi asiasanana - auktoriteettitietueen kontollinumero|koha-auth-number|
|651a|Maantieteellinen nimi|su-geo|
|6520|?|koha-auth-number|
|6530|?|koha-auth-number|
|653a|Kontrolloimaton hakutermi|subject|
|653a|Kontrolloimaton hakutermi|index-term-uncontrolled|
|6540|Maantieteellinen nimi asiasanana - auktoriteettitietueen kontollinumero|koha-auth-number|
|6550|Aineiston lajityyppi/muoto hakuterminä - auktoriteettitietueen kontollinumero|koha-auth-number|
|655a|Lajityyppiä/muotoa kuvaava termi tai fokustermi|index-term-genre|
|655a|Lajityyppiä/muotoa kuvaava termi tai fokustermi|subject|
|655x|Yleinen lisämääre (lajityypille)|index-term-genre|
|655x|Yleinen lisämääre (lajityypille)|subject|
|655y|Aikaa ilmaiseva lisämääre|time-period|
|655z|Maantieteellinen lisämääre|place-of-origin|
|6560|Ammatti hakuterminä - auktoriteettitietueen kontollinumero|koha-auth-number|
|6570|Tapahtuma tai toiminto hakuterminä - auktoriteettitietueen kontollinumero|koha-auth-number|
|658abc|Opinto-ohjelman tai kurssin tavoitteet hakuterminä|curriculum|
|6620|Hierarkkinen maantieteellinen nimi asiasanana - auktoriteettitietueen kontollinumero|koha-auth-number|
|6900|?|koha-auth-number|
|6910|?|koha-auth-number|
|6960|?|koha-auth-number|
|6970|?|koha-auth-number|
|6980|?|koha-auth-number|
|6990|?|koha-auth-number|
|700|Lisäkirjaus - henkilönnimi|editor|
|700|Lisäkirjaus - henkilönnimi|author-name-personal|
|700|Lisäkirjaus - henkilönnimi|name|
|700|Lisäkirjaus - henkilönnimi|personal-name|
|7000|Lisäkirjaus - henkilönnimi - auktoriteettitietueen kontollinumero|koha-auth-number|
|7009|Linkitys tekijä-auktoriteettiin|cross-reference|
|700a|Lisäkirjaus - henkilönnimi|author|
|700at|Lisäkirjaus - henkilönnimi + teoksen nimeke|name-and-title|
|700n|Numerointitieto (lisäkirjaus henkilönnimi)|thematic-number|
|700r|Lisäkirjaus - henkilönnimi - sävellaji|music-key|
|700t|Teoksen nimeke|title|
|700t|Teoksen nimeke|title-uniform|
|700t|Teoksen nimeke|author-title|
|710|Lisäkirjaus yhteisönnimi|author-name-corporate|
|710|Lisäkirjaus yhteisönnimi|name|
|710|Lisäkirjaus yhteisönnimi|corporate-name|
|7100|Lisäkirjaus - yhteisönnimi - auktoriteettitietueen kontollinumero|koha-auth-number|
|710a|Lisäkirjaus yhteisönnimi|author|
|710at|Lisäkirjaus - yhteisönnimi + teoksen nimeke|name-and-title|
|710t|Teoksen nimeke|title|
|710t|Teoksen nimeke|title-uniform|
|710t|Teoksen nimeke|author-title|
|711|Lisäkirjaus - Kokouksen nimi|author-name-corporate|
|711|Lisäkirjaus - Kokouksen nimi|conference-name|
|711|Lisäkirjaus - Kokouksen nimi|name|
|7110|Lisäkirjaus - kokouksen nimi - auktoriteettitietueen kontollinumero|koha-auth-number|
|711a|Lisäkirjaus - kokouksen nimi|author|
|711at|Lisäkirjaus - kokouksen nimi + teoksen nimeke|name-and-title|
|711t|Teoksen nimeke|title|
|711t|Teoksen nimeke|title-uniform|
|711t|Teoksen nimeke|author-title|
|730|Yhtenäistetty nimeke (lisäkirjaus)|title-uniform|
|730|Yhtenäistetty nimeke (lisäkirjaus)|title|
|7300|Lisäkirjaus - yhtenäistetty nimeke - auktoriteettitietueen kontollinumero|koha-auth-number|
|730n|Numerointitieto (yhtenäistetty nimeke)|thematic-number|
|730r|Lisäkirjaus - yhtenäistetty nimeke - sävellaji|music-key|
|740|Nimeke, kontrolloimaton ja kohteeseen liittyvä tai analyyttinen (lisäkirjaus)|title-other-variant|
|740|Nimeke, kontrolloimaton ja kohteeseen liittyvä tai analyyttinen (lisäkirjaus)|title|
|7510|Lisäkirjaus - maantieteellinen nimi - auktoriteettitietueen kontollinumero|koha-auth-number|
|751a|Lisäkirjaus - maantieteellinen nimi|name-geographic|
|770w|Tietueen kontrollinumero - linkkikenttä suplementti/erikoisnumero|record-control-number|
|772w|Tietueen kontrollinumero - linkkikenttä suplementin pääjulkaisu|record-control-number|
|7739|Linkkikenttä - emokohde|host-item-number|
|773at|Linkkikenttä - emokohde|host-item|
|773w|Tietueen kontrollinumero - linkkikenttä emokohde|record-control-number|
|773w|Tietueen kontrollinumero - linkkikenttä emokohde|record-control-number-773w|
|774w|Tietueen kontrollinumero - linkkikenttä osakohde|record-control-number|
|775t| Muun painoksen nimeke|title|
|775t| Muun painoksen nimeke|title-other-variant|
|775w|Tietueen kontrollinumero - linkkikenttä muu painos|record-control-number|
|776w|Tietueen kontrollinumero - linkkikenttä toinen ilmiasu|record-control-number|
|777w|Tietueen kontrollinumero - linkkikenttä kanssajulkaisu|record-control-number|
|780|Edeltäjä - linkkikenttä|title|
|780|Edeltäjä - linkkikenttä|related-periodical|
|780|Edeltäjä - linkkikenttä|title-former|
|780w|Tietueen kontrollinumero - linkkikenttä edeltäjä|record-control-number|
|785|Seuraaja - linkkikenttä|title-later|
|785|Seuraaja - linkkikenttä|title|
|785|Seuraaja - linkkikenttä|related-periodical|
|785w|Tietueen kontrollinumero - linkkikenttä seuraaja|record-control-number|
|787w|Tietueen kontrollinumero - linkkikenttä muu suhde|record-control-number|
|7960|?|koha-auth-number|
|7970|?|koha-auth-number|
|7980|?|koha-auth-number|
|7990|?|koha-auth-number|
|800|Sarjalisäkirjaus - henkilönnimi|personal-name|
|800|Sarjalisäkirjaus - henkilönnimi|author-name-personal|
|800|Sarjalisäkirjaus - henkilönnimi|name|
|8000|Sarjalisäkirjaus - henkilönnimi - auktoriteettitietueen kontollinumero|koha-auth-number|
|800a|Sarjalisäkirjaus - henkilönnimi|author|
|800at|Sarjalisäkirjaus - henkilönnimi + teoksen nimeke|name-and-title|
|800t|Sarjalisäkirjaus - henkilönnimi, teoksen nimeke|title-series|
|800t|Sarjalisäkirjaus - henkilönnimi, teoksen nimeke|author-title|
|800w|Bibliografisen tietueen kontrollinumero - sarjalisäkirjaus henkilönnimi|record-control-number|
|810|Sarjalisäkirjaus - Yhteisönnimi|author-name-corporate|
|810|Sarjalisäkirjaus - Yhteisönnimi|name|
|810|Sarjalisäkirjaus - Yhteisönnimi|corporate-name|
|8100|Sarjalisäkirjaus - yhteisönnimi - auktoriteettitietueen kontollinumero|koha-auth-number|
|810a|Sarjalisäkirjaus - Yhteisönnimi|author|
|810at|Sarjalisäkirjaus - yhteisönnimi + teoksen nimeke|name-and-title|
|810t|Sarjalisäkirjaus - Yhteisönnimi|author-title|
|810w|Bibliografisen tietueen kontrollinumero - sarjalisäkirjaus yhteisönnimi|record-control-number|
|811|Sarjalisäkirjaus - Yhteisönnimi|author-name-corporate|
|811|Sarjalisäkirjaus - Kokouksen nimi|conference-name|
|811|Sarjalisäkirjaus - kokouksen nimi|name|
|8110|Sarjalisäkirjaus - kokouksen nimi - auktoriteettitietueen kontollinumero|koha-auth-number|
|811a|Sarjalisäkirjaus - Yhteisönnimi|author|
|811at|Sarjalisäkirjaus - kokouksen nimi + teoksen nimeke|name-and-title|
|811t|Sarjalisäkirjaus - kokouksen nimi, teoksen nimeke|author-title|
|811w|Bibliografisen tietueen kontrollinumero - sarjalisäkirjaus kokouksen nimi|record-control-number|
|8300|Sarjalisäkirjaus - yhtenäistetty nimeke - auktoriteettitietueen kontollinumero|koha-auth-number|
|830a|Yhtenäistetty nimeke (sarjalisäkirjaus)|title-series|
|830a|Yhtenäistetty nimeke (sarjalisäkirjaus)|title-uniform|
|830n|Numerointitieto (sarjalisäkirjaus)|title-series|
|830n|Numerointitieto (sarjalisäkirjaus)|title-uniform|
|830p|Teoksen osan nimeke (sarjalisäkirjaus)|title-series|
|830p|Teoksen osan nimeke (sarjalisäkirjaus)|title-uniform|
|830v|Teoksen osan nimeke (sarjalisäkirjaus)|title-series|
|830v|Teoksen osan nimeke (sarjalisäkirjaus)|title-uniform|
|830w|Bibliografisen tietueen kontrollinumero - sarjalisäkirjaus yhtenäistetty nimeke|record-control-number|
|830x|Sarjalisäkirjauksen ISSN|issn|
|830x|Sarjalisäkirjauksen ISSN|issn-all|
|852h|Paikkamerkin hyllyluokka|placement|
|852i|Sijainti|location-item-part|
|8960|?|koha-auth-number|
|8970|?|koha-auth-number|
|8980|?|koha-auth-number|
|8990|?|koha-auth-number|
|900a|Viittaus - henkilönnimi - suomalainen kenttä|author|
|910a|Viittaus - yhteisönnimi - suomalainen kenttä|author|
|911a|Viittaus - kokouksen nimi - suomalainen kenttä|author|
|9420||totalissues|
|9422|Tietueen luokituksen lähde|cn-bib-source|
|9426|Järjestämistä varten normalisoitu tietueen luokka|cn-bib-sort|
|942c|Aineistotyyppi|mtype|
|942c|Aineistotyyppi|itemtype|
|942h|Luokka|cn-class|
|942i|Item part|cn-item|
|942k|Signumin prefiksi|cn-prefix|
|942m|Signumin prefiksi|cn-suffix|
|942n|?|suppress|
|9520|Pois kierrosta -tila|withdrawn|
|9521|Kadonnut -tila|lost|
|9522|Niteen luokituksen lähde|classification-source|
|9523|Liitteiden määrä|materials-specified|
|9524|Vaurioitunut -tila|damaged|
|9525|Käyttörajoitukset|restricted|
|9526|Järjestämistä varten normalisoitu niteen luokka|cn-sort|
|9527|Ei lainattavissa|notforloan|
|9528|Kokoelmakoodi|ccode|
|9529|Niteen numero|itemnumber|
|952a|Omistajakirjasto|homebranch|
|952b|Sijaintikirjasto|holdingbranch|
|952c|Hyllypaikka|location|
|952d|Hankintapvm|date-of-acquisition|
|952e|Hankintapaikka|acqsource|
|952f|Koodattu paikkamääre|coded-location-qualifier|
|952g|Hankintahinta|price|
|952i|Inventaarionumero|number-local-acquisition|
|952j|Hyllytarkenne|subloc|
|952l|Lainauksia yhteensä|issues|
|952m|Uusintoja yhteensä|renewals|
|952n|Varauksia yhteensä|reserves|
|952o|Kohan koko signum|local-classification|
|952p|Viivakoodi|barcode|
|952q|Lainassa|onloan|
|952r|Viimeksi nähty pvm|datelastseen|
|952s|Viimeksi lainattu pvm|datelastborrowed|
|952t|Nidenumero|copynumber|
|952u|URI|uri|
|952v|Korvaushinta|replacementprice|
|952w|Korvaushinta|replacementpricedate|
|952y|Nidetyyppi|itemtype|
|952y|Nidetyyppi|itype|
|952z|Yleinen huomautus|note|
|960|?|collection-960|
|999c|Koha biblionumber|local-number|
|999d|Koha biblioitemnumber|biblioitemnumber|
|999x|?|not-onloan-count|
|leader_/0-4|Tietueen pituus|llength|
|leader_/6|Tietueen tyyppi|rtype|
|leader_/7|Tietueen taso (nimiö)|bib-level|

## 10.9 Finna-Koha-kirjanmerkin lisääminen

Selaimen kirjanmerkkeihin voi lisätä kirjanmerkin, joka sisältää pienen JavaScript-rimpsun, jonka avulla pääsee siirtymään Finnasta tietuesivulta Kohaan saman tietueen perustiedot-näytölle tai varaussivulle.

Alla on rimpsut kumpaakin tapaa varten. Rimpsut ovat OUTI-kirjastojen osoitteiden mukaiset, joten muokkaa tarvittaessa ne omaan kimppaan sopivaksi.

Finnan tietuesivulta Kohan varaussivulle:
<pre>
javascript:(function(){var path = window.location.href;if(path.includes("finna.fi/Record/")){ var tietueid = path.split("Record/outi.").pop().split(/[^0-9]/).reverse().pop();window.open('https://outi.koha-suomi.fi/cgi-bin/koha/reserve/request.pl?biblionumber=' + tietueid);}})()
</pre>

Finnan tietuesivulta Kohan perustiedot-näytölle:
<pre>
javascript:(function(){var path = window.location.href;if(path.includes("finna.fi/Record/")){ var tietueid = path.split("Record/outi.").pop().split(/[^0-9]/).reverse().pop();window.open('https://outi.koha-suomi.fi/cgi-bin/koha/catalogue/detail.pl?biblionumber=' + tietueid);}})()
</pre>
