---
title: 'Kohan ohje suomeksi'
permalink: /dokumentaatio/kuvailu/
redirect_from:
  - /theme-setup/
toc: true
---

# 5. Kuvailu

Kuvailuun meno: _Muita toimintoja -&gt; Kuvailu_. Jos linkkiä ei
näy, käyttäjätunnuksellasi ei ole kuvailuoikeuksia.

![](/assets/files/docs/Luettelointi/kuvailu1.png)

## 5.1. Bibliografiset tietueet

Kohassa bibliografinen tietue (nimeketietue) sisältää kuvailutiedot
aineistosta. Näitä tietoja ovat mm. nimeke, tekijä, ISBN ym. Tieto on
tallennettu MARC 21 -formaatin mukaisesti. Kun nimeketiedot on
tallennettu, voidaan tietueelle lisätä niteitä.

### 5.1.1. Tietueen lisääminen

#### Tyhjästä tietueesta

Tietue voidaan lisätä kuvailemalla tai kopioimalla. Uusi nimeke
voidaan kuvailla tyhjälle pohjalle.

Klikkaa _Uusi tietue_ ja valitse sopiva kuvailupohja valikosta.

![](/assets/files/docs/Luettelointi/kuvailu2.png)

#### Z39.50/SRU-haulla

Jos haluat tuoda valmiin kuvailutietueen toisesta
kirjastosta/tietokannasta

Klikkaa _Uusi Z39.50/SRU-haku_ ja tee haku

![](/assets/files/docs/Luettelointi/kuvailu3.png)

**Vinkki** Jos hakutuloksia ei löydy, kokeile hakua vähemmillä
hakusanoilla, sillä kaikki Z39.50/SRU -kohteet eivät löydä tietoja
kaikista kentistä. Sanahakua kannattaa myös kokeilla.

Hakutuloksia voit tarkastella MARC-muodossa tai korttimuodossa tai tuoda
tietueen Kohaan

![](/assets/files/docs/Luettelointi/kohakuvat7221.png)

![](/assets/files/docs/Luettelointi/kohaversio2111k5.png)

![](/assets/files/docs/Luettelointi/kohaversio2111k6.png)

\*Jos et löydä hakemaasi, klikkaa _Tee uusi haku_ näytön vasemmassa
alareunassa.

Kun olet avannut tyhjän kuvailupohjan tai tuonut nimeketietueen
Z39.50/SRU -haun kautta, pääset jatkamaan kuvailua.

![](/assets/files/docs/Luettelointi/kuvailu5.png)

### 5.1.2. Tietueen valuminen TäTistä/Tietuesiirtäjä

Täydellisten kuvailutietueiden valutus paikalliskantaan on selostettu [erillisessä ohjeessa](https://github.com/KohaSuomi/koha-plugin-broadcast-biblios/wiki/K%C3%A4ytt%C3%B6ohjeet).
Tämä toiminto on käytössä Koha-Suomen yleisissä kirjastokimpoissa.

### 5.1.3. Osakohteiden lisääminen

Tietueelle voi lisätä osakohteita (julkaisuun sisältyviä novelleja, artikkeleita, sävellyksiä jne.)
Valitse nimeketiedoissa _Uusi -&gt; Uusi osakohde_.

![](/assets/files/docs/Luettelointi/kuvailu6.png)

Musiikin osakohteille on tehty oma tallennuspohja. Valitse se valikosta,
mikäli kuvailet musiikkiaineistoa.

![](/assets/files/docs/Luettelointi/kohakuvatkausi540.jpg)

Kuvaile osakohde. Pakollisia kenttiä ovat 245a (päänimeke), 300a
(laajuus tai kesto), 942c (aineistolaji, valitaan valikosta) sekä
tallennuksen jälkeen muodostuva 008-kenttä. Jos et halua tarkemmin
määritellä osakohteiden ominaisuuksia, riittää kun tallennat toiseen
kertaan tietueen. Emotietueesta täyttyy linkkikenttä 773
tarvittavilla emon tiedoilla automaattisesti, kuten kuvassa alla:

![](/assets/files/docs/Luettelointi/kuvailu7.png)

Osakohteella ei ole niteitä, joten niteidentallennusnäytölle ei tarvitse
tallentaa mitään, vaan voit palata vasemmalta _Perustiedot_-painikkeesta
teoksen tietoihin.

### 5.1.4. Tietueiden muokkaaminen peruseditorissa

Muokataksesi nimeketietuetta ollessasi Kuvailu-osiossa klikkaa _Toiminnot_-valikosta
_Muokkaa tietuetta_ hakutulosnäytöllä

![](/assets/files/docs/Luettelointi/luettelointi11.png)

tai klikkaa Tiedonhaun puolella _Muokkaa_-valikosta _Muokkaa tietuetta_.

![](/assets/files/docs/Luettelointi/kohakuvat580.png)

Tietue avautuu MARC-muokkaukseen.

![](/assets/files/docs/Luettelointi/kuvailu8.png)

Kun muokkaat tietuetta, kentän nimen perässä on kuvakkeet, joista
vasemmalla oleva kopioi kentän ja oikealla puolella oleva tyhjentää
kentän. Kopiointilinkki on näkyvissä vain, jos formaatin mukaan kenttä
on toistettavissa.

![](/assets/files/docs/Luettelointi/luettelointi002.png)

Kiinteämittaisten kenttien oikealla puolella on kuvake, jota
klikkaamalla avautuu valikko, jonka avulla kenttää muokataan.

![](/assets/files/docs/Luettelointi/luettelointi003.png)

![](/assets/files/docs/Luettelointi/kuvailu9.png)

Huomaa! Joidenkin kiinteämittaisten kenttien arvo muuttuu sen
perusteella, minkä tyyppistä aineistoa olet kuvailemassa ja mikä
tallennuspohja on valittuna.

![](/assets/files/docs/Luettelointi/kuvailu10.png)

#### Finto-liitännäiset

Täti-tietokannassa on käytössä Finto-liitännäiset (pluginit), joilla pystyy hakemaan termejä Fintosta. Toiminnon kuvaus löytyy Teknisestä
dokumentaatiosta [Finto-plugin](https://koha-suomi.fi/dokumentaatio/finto/)-sivulta.

#### Tietueen tallentaminen

Kun olet muokannut nimeketietueen, muista tallentaa se
_Tallenna_-painikkeesta, jossa on kolme eri vaihtoehtoa.

![](/assets/files/docs/Luettelointi/kuvailu11.png)

#### Kuvailutietueen korvaaminen uudella Z39.50/SRU-haun kautta

Vaihtoehtoisesti voit etsiä Z39.50/SRU-haun kautta toisesta kirjastosta
täydellisemmän kuvailutietueen, jolla korvaat nykyisen
tietueen.

![](/assets/files/docs/Luettelointi/kuvailu121.png)

Jos käytät tätä korvaamista, pääset Z39.50/SRU-hakusivulle valitsemaan
valikosta kirjaston, jonka tietueella nimeketietue korvataan.

![](/assets/files/docs/Luettelointi/kuvailu141.png)

Oletusarvona on tässä haku TäTistä ja Melindasta, mutta voit
valita mitä tahansa valikon kirjastoista hakukirjastoksesi.
_Haku_-painike alareunassa aloittaa haun.

Tässä hakutuloksena on kaksi tietuetta. Valitse haluamasi tietueen
kohdalla Toiminnot-sarakkeesta _Tuo_.

![](/assets/files/docs/Luettelointi/kohakuvat7221.png)

Teitpä muutokset tietueeseen kummalla tavalla tahansa, muista klikata
_Tallenna_ -painiketta. Valikosta voit valita sopivan tallennustavan.

![](/assets/files/docs/Luettelointi/kohakuvat72241.png)

### 5.1.5. Tietueiden muokkaaminen uudessa editorissa (kehittynyt editori)

Jos halutaan käyttää uutta editoria, se pitää laittaa päälle ylläpidon asetuksessa _EnableAdvancedCatalogingEditor_. Editori ei ole vielä täysin
luotettava, joten kannattaa suhtautua varauksella sen käyttöön.

![](/assets/files/docs/Luettelointi/kuvailu515k1.png)

Voit avata uuden, tyhjän tietueen tai tuoda toisesta järjestelmästä
haluamasi tietueen haun kautta.

![](/assets/files/docs/Luettelointi/kuvailu515k2.png)

Z39.50/SRU-haun kautta voit tuoda haluamasi tietueen omaan
kirjastojärjestelmään.

![](/assets/files/docs/Luettelointi/luettelointi103.png)

Oikeassa reunassa on sarake _Työkalut_, josta voit katsoa MARC-tietueen
sisällön ja tuoda sen omaan kirjastojärjestelmääsi.

Kun haluat lisätä kentän kuvailutietueeseen, syötät kentän numeron ja
indikaattorien paikat ja indikaattorit sekä osakentän tunnuksen ja sen
sisällön.

![](/assets/files/docs/Luettelointi/luettelointi104.png)

#### 5.1.5.1. Pikanäppäimet uudessa editorissa

_Pikanäppäimet_-valikon alta löytyy tarvittavat pikanäppäimet: 

![](/assets/files/docs/Luettelointi/kohakuvatkausi545.png)

#### 5.1.5.2. Virtuaalinäppäimistö 

Näppäinyhdistelmällä Shift-Ctrl-K saat esiin virtuaalinäppäimistön ja valikkorivillä olevasta painikkeesta
_Näppäimistöasettelu_ pääset valitsemaan, millä kielellä haluat virtuaalinäppäimistön näkyville.

![](/assets/files/docs/Luettelointi/kohakuvatkausi546.png)

#### 5.1.5.3. Makrot uudessa editorissa

Makro on kätevä tapa lisätä kenttiä tietueeseen uudessa editorissa. Makro otetaan käyttöön
valikkorivin _Makrot_-painikkeesta. Anna ensin uudelle makrolle kuvaava nimi ja sen jälkeen lisää
tarvittavat toiminnot. Voit lisätä useita toimintoja samaan makroon. Makro tallentuu automaattisesti.

![](/assets/files/docs/Luettelointi/kohakuvaedi2.png)

![](/assets/files/docs/Luettelointi/kohakuvaedi3.png)

![](/assets/files/docs/Luettelointi/kohakuvaedi1.png)

Valmiita makroja löydät yhteisön wikistä https://wiki.koha-community.org/wiki/Advanced_editor_macros (englanniksi)

### 5.1.6. Tietueen kopioiminen

Aina et löydä haluamaasi tietuetta Z39.50/SRU -haun kautta. Näissä
tapauksissa voit tehdä kopion samantyyppisestä tietueesta ja muokata
kopiota vastaamaan luetteloitavaa nimekettä. Tehdäksesi kopion klikkaa
_Muokkaa uutena kopiona_.

![](/assets/files/docs/Luettelointi/kohakuvatkausi5471.png)

Tämä avaa uuden MARC-tietueen, jossa kentät on täytetty kopioidun
tietueen tiedoilla ja voit muokata tietoja haluamiksesi.  
Muista tyhjentää kenttien 001, 003 ja 035 sisältö, kun aloitat tietueen muokkauksen.
Näin tietueelle tulee uusi tietueen kontrollinumero kenttään 001, kun
tallennat tietueen. Kenttään 003 lisätään kuvailupaikan koodi.

![](/assets/files/docs/Luettelointi/kuvailu16.png)

### 5.1.7. Tietueiden yhdistäminen

Useita tietueita (tuplia) voidaan yhdistää yhdeksi tietueeksi
Kuvailun tai tiedonhaun kautta.

#### 5.1.7.1 Tietueiden yhdistäminen kuvailun kautta

Hae yhdistettävät tietueet kuvailuhaun kautta, valitse niistä
haluamasi tietueet ja käytä _Yhdistä valitut_ -toimintoa.

![](/assets/files/docs/Luettelointi/kuvailu17.png)

Voit tehdä yhdistelyn myös _Listat_-työkalulla. Valitse yhdistettävät
tietueet tiedonhaun kautta ja lisää ne jollekin listallesi, josta voit
ottaa nimekkeet yhdistettäväksi. Yhdistämistoiminnon avulla saat kaikki
niteet ja nimekkeeseen liittyvät varaukset oikeassa järjestyksessä
jäljelle jäävään nimeketietueeseen.

![](/assets/files/docs/Luettelointi/kuvailu18.png)

Valitse listalta se tietue, mikä jää kohdetietueeksi (mihin muut
tietueet yhdistetään) ja voit valita myös kuvailupohjan.  
Vertaile tietueiden tietoja ja tarvittaessa siirrä muista tietueista
tarvittavia kenttiä kohdetietueeseen. Jos kentän toistaminen on estetty
kuvailuformaatissa, kentän toistaminen antaa virheilmoituksen.

![](/assets/files/docs/Luettelointi/luettelointi0141.png)

Kun kuvailu näyttää valmiilta, klikkaa ruudun alareunassa _Yhdistä_.
Asetuksissa voidaan määritellä, mitkä kentät näkyvät
yhdistämisraportissa. Tässä tapauksessa kentät ovat 001, 245ab, 650.

![](/assets/files/docs/Luettelointi/luettelointi0121.png)

Yhdistämisraportti näyttää tältä edellä mainittujen asetusten mukaan:

![](/assets/files/docs/Luettelointi/luettelointi0131.png)

#### 5.1.7.2 Tietueiden yhdistäminen tiedonhaun kautta

Hae tiedonhaussa teokset ja vie ne haluamaasi listaan.

<img src="/assets/files/docs/Luettelointi/tietueenyhdistaminen2.png" alt="" style="width:50.0%" />

Avaa lista, valitse kaikki ja sen jälkeen _“Yhdistä valitut”_

<img src="/assets/files/docs/Luettelointi/tietueenyhdistaminen3.png" alt="" style="width:50.0%" />

Voit valita yhdistettävät tietueet myös suoraan tiedohaun tuloksesta.

![](/assets/files/docs/Luettelointi/kohakuvat551.png)

Tämän jälkeen prosessi jatkuu kuten [kuvailun kautta aloitettaessa](https://koha-suomi.fi/dokumentaatio/kuvailu/#5171-tietueiden-yhdist%C3%A4minen-kuvailun-kautta)
kuvasta “Yhdistetään tietueita”.

### 5.1.8. Tietueiden poistaminen

Tietue voidaan poistaa valitsemalla _Muokkaa_-valikosta _Poista tietue_.

![](/assets/files/docs/Luettelointi/kuvailu19.png)

Tietuetta ei voi poistaa, mikäli tietueeseen liittyy niteitä. Tällöin
_Poista tietue_ -teksti näkyy harmaana.

![](/assets/files/docs/Luettelointi/kuvailu20.png)

### 5.1.9. Tietueen tiedot muutoslokilla ja tietojen palautus

Tietueeseen tehdyt muutokset tallentuvat muutoslokille, johon pääsääntöisesti on pääsy kimpan pääkäyttäjillä. Muutoslokille pääsee tietueen perustiedot-näytöltä kohdasta _Muutosloki_.

![](/assets/files/docs/Luettelointi/muutosloki.png)

* _Pvm_-sarakkeessa näytetään muutoksen tekopäivä.
* _Virkailija_-sarakkeessa näytetään muutoksen tehneen virkailijan borrowernumber.
* _Osio_-sarakkeessa näytetään, missä Kohan osiossa muutos on tehty.
* _Toiminto_-sarakkeessa näytetään, mikä toiminto on tehty.
* _ID-tunnus_-sarakkeessa näytetään, mitä tietuetta ja/tai nidettä on muokattu.
* _Tiedot_-sarakkeessa näytetään tietueen tiedot ennen muutosta.
  * _Palauta_-napilla pystyy palauttamaan kyseisen rivin kuvailutiedot takaisin tietueeseen. Tätä voi käyttää, jos esim. tietueen päälle on vahingossa valunut väärät tiedot tai tietoja on vahingossa muokattu vääränlaisiksi.
* _Käyttöliittymä_-sarakkeessa näytetään, minkä käyttöliittymän kautta muutos on tehty. Vaihtoehtoja ovat esim. Ajastettu ajo, REST, Virkailijaliittymä. 

## 5.2. Nidetietueet

Kohassa jokaisella nimeketietueella (bibliografinen tietue) voi olla
yksi tai useampi nide. Jokaisella niteellä on omistajakirjasto ja sijaintikirjasto
sekä hyllypaikka.

### 5.2.1. Niteiden lisääminen

Uuden nimeketietueen lisäämisen jälkeen pääset suoraan tyhjään
nidetietueeseen, johon voit liittää niteen tai useampia niteitä. Niteitä
pääset lisäämään myös klikkaamalla _Muokkaa niteitä_.

![](/assets/files/docs/Luettelointi/kuvailu21.png)

Tai voit lisätä uuden niteen milloin tahansa nimeketietuenäytöllä
klikkaamalla _Uusi_ ja valitsemalla _Uusi nide_.

![](/assets/files/docs/Luettelointi/kuvailu22.png)

Niteen tallennusnäyttö näyttää tältä:

![](/assets/files/docs/Luettelointi/kuvailu23.png)

Pakolliset kentät on merkitty punaisella, mutta vähintään seuraavat
tiedot olisi hyvä täyttää, jotta niteitä voisi lainata:

- 2 - Luokitus
- a - Omistajakirjasto
- b - Sijaintikirjasto
- o - Kohan koko signum
- p - Viivakoodi
- v - Korvaushinta  
  *Tämä summa peritään asiakkaalta, kun nide merkitään
  kadonneeksi asiakkaalta
- y - Kohan nidetyyppi

_Huom! Näkyvissä olevat kentät voivat vaihdella kirjastokimpan ja
käytetyn kuvailupohjan mukaan._

Jos kentän lopussa näkyy kolme pistettä, sitä klikkaamalla saa kyseisen
kentän päivitettyä (esimerkissä signumin muodostaminen ja viivakoodin
muodostaminen).

![](/assets/files/docs/Luettelointi/luettelointi015.png)

Nidetietojen alla on neljä nappia, joista valitset haluamasi toiminnon.

![](/assets/files/docs/Luettelointi/kuvailu24.png)

- _Lisää nide_ lisää vain yhden niteen
- _Lisää ja kopioi_ lisää niteen ja täyttää lomakkeen uudelleen
  samoilla arvoilla, joita voit muuttaa
- _Lisää useita kopioita niteestä_ kysyy, montako nidettä haluat
  lisätä ja lisää niin monta nidettä lisäten jokaiselle oman
  viivakoodin (lisäämällä +1 edelliseen)
- _Tallenna pohjana_ voit tallentaa uuden nidetallennuspohjan
  tai muokata jo olemassa olevaa tallennuspohjaa  

![](/assets/files/docs/Luettelointi/kuvailu25.png)

![](/assets/files/docs/Luettelointi/kuvailu26.png)

Lisäämäsi tietue tulee taulukkoon.

![](/assets/files/docs/Luettelointi/luettelointi26.png)

Voit suodattaa kokoelmatietoja, kun kirjoitat haku-laatikkoon.
 
![](/assets/files/docs/Luettelointi/kohakuvat5701.png)

Riittää, kun aloitat kirjoittamaan suodatinta, kaikki siihen sopivat
tulokset listataan.

### 5.2.1.1. Vanhan niteen lisääminen

Jos sinulla on tarve tallentaa vanha nide uutena Kohaan, on syytä vaihtaa
niteen hankintapäivä. Hankinnat tilastoidaan aina hankintapäivän mukaan.
Vanhoja niteitä ei haluta hankintatilastoon, joten vanhan niteen osakenttään 
_d - Hankintapvm_ tulee merkitä joku vanha päiväys ennen Kohan käyttöönottoa.
Päivämäärästä voi heti päätellä, että niteen saapumispäivä ei ole todellinen
(esim. 24.12.2010).

![](/assets/files/docs/Luettelointi/kuvailu27.png)

### 5.2.1.2 Nidetyypin automaattinen generointi

Koha-Suomessa on tehty liitännäinen, jolla pystyy generoimaan automaattisesti nidetyypin niteelle sille valittujen tietojen perusteella. Liitännäinen hakee tietokannasta samoilla ehdoilla olevia niteitä ja tutkii, mikä nidetyyppi on suosituin vastaavilla niteillä. Sitten se ehdottaa samaa suosituinta nidetyyppiä uudelle/muokattavalle niteelle. Valinta tehdään aineistotyypin, hyllypaikan, hyllytarkenteen ja kokoelmakoodin perusteella.

Generointi onnistuu painamalla Nidetyyppi-kentän vieressä olevaa kolmea pistettä, mikäli liitännäinen on käytössä.

![Kohan nidetyyppi -kentän vierestä ympyröity kolme pistettä](/assets/files/docs/Luettelointi/nidetyyppi-liitannainen.png)

Jos liitännäinen on käytössä, nidetyyppi-kenttään ei voi saada alasvetovalikkoa nidetyypeistä. Jos kolmen pisteen ehdottama nidetyyppi ei ole oikea tai sopiva, pitää nidetyypin tunnus kirjoittaa kenttään käsin.

Jos Nidetyyppi-kenttään kirjoittaa väärän/olemattoman tunnuksen, tulee nidettä tallennettaessa ponnahdusikkuna, jossa listataan kimpan olemassa olevat nidetyyppien tunnukset:

![Ponnahdusikkuna, jossa on listattuna kimpassa käytössä olevat nidetyyppien tunnukset](/assets/files/docs/Luettelointi/nidetyyppi-liitannainen2.png)

[Liitännäisen käyttöönotto-ohje](https://koha-suomi.fi/dokumentaatio/kayttoonotto-ohjeita/#nidetyypin-automaattinen-generointi).

### 5.2.2. Niteiden muokkaaminen

Niteitä voi muokata monella tavalla.

#### Klikkaamalla _Muokkaa -&gt; Hallinnoi niteitä_ nimeketietonäytöltä

![](/assets/files/docs/Luettelointi/kuvailu28.png)

Tämä avaa listauksen, missä voit klikata _Toiminnot_-linkkiä sen niteen
rivin alussa, mitä nidettä haluat muokata.

![](/assets/files/docs/Luettelointi/kuvailu29.png)

#### Klikkaamalla _Muokkaa nidettä_ Niteet-välilehdellä halutun niteen kohdalla

![](/assets/files/docs/Luettelointi/kuvailu30.png)

Tämä avaa listauksen, kuten edellä (valitsemasi nide näkyy korostetulla
pohjalla valmiiksi)  

![](/assets/files/docs/Luettelointi/kuvailu31.png)

#### Klikkaamalla _Muokkaa -&gt; Muokkaa niteitä eräajossa_

![](/assets/files/docs/Luettelointi/kuvailu32.png)

Tämä avaa erämuokkaustyökalun, jossa voit muokata useiden niteiden
tietoja yhtä aikaa.

Jos järjestelmäasetuksissa on määritelty, että niteiden valinta on
mahdollista, voit klikata nidetietojen näytöllä kunkin niteen vasemmalla
puolella valintalaatikosta ne niteet, joita haluat käsitellä. Voit
poistaa niteitä tai muokata niitä.

![](/assets/files/docs/Luettelointi/kuvailu33.png)

Voit käyttää myös erämuokkaustyökalua muokkaukseen.

### 5.2.2.1. Niteen tilatietojen pikamuokkaus

Toisinaan pitää vaihtaa kadonneiden tai vaurioituneiden niteiden tila.
Tällöin ei tarvitse muokata koko nidetietuetta, vaan voi klikata niteen
viivakoodia lainausnäytöllä tai lainahistoriassa ja päästä niteen
yhteenvetoon. Siellä pääsee merkitsemään niteen kadonneeksi tai
vaurioituneeksi.

![](/assets/files/docs/Luettelointi/kuvailu34.png)

Täällä voit alasvetovalikosta valita tilan, joka merkitsee niteen
_kadonneeksi_ tai _ilmoittaa palauttaneensa_ -tilaan. Huom! Noudata
kadonnut-tilaa käytettäessä kimpassasi sovittuja käytänteitä.
Kadonnut-tila voi lisätä kimpan asetuksista riippuen niteen
korvaushinnan asiakkaan velkasaldoon. Valikoiden sisältö voi vaihdella eri kimpoissa.

![](/assets/files/docs/Luettelointi/kuvailu35.png)

Jos valitset _Ilmoittaa palauttaneensa_ ja klikkaat _Aseta tila_
-nappia, nide poistuu asiakkaan lainoista ja näkyviin tulee päivämäärä,
milloin tila on merkitty.

![](/assets/files/docs/Luettelointi/kuvailu36.png)

Viimeisin lainaaja jää näkyviin _Historia_-tietoihin.

![](/assets/files/docs/Luettelointi/kuvailu37.png)

Voit merkitä niteen myös vahingoittuneeksi.

![](/assets/files/docs/Luettelointi/kuvailu38.png)

### 5.2.2.2. Niteiden erämuokkaus nimekkeessä

#### Tiedon lisääminen

Jos haluat muokata jonkun nimekkeen useamman niteen tietoja kerralla,
sen pääsee tekemään valitsemalla nimeketietonäytöllä _Muokkaa -&gt;
Muokkaa niteitä eräajossa_.

![](/assets/files/docs/Luettelointi/kuvailu32.png)

Siellä voit valita joko kaikki niteet tai valitsemalla vasemmalla
olevasta sarakkeesta vain ne niteet, joihin muutokset kohdistuvat.
Nidelistauksen alapuolella näkyy _Muokkaa niteitä_ -taulukko, johon
tarvittavat muutokset tehdään. Tässä esimerkissä muutetaan kaikille
niteille kokoelmakoodiksi _Lyhytlaina_.

![](/assets/files/docs/Luettelointi/luettelointi46.png)

Rivillä 8 _Kokoelmakoodi_ valitaan tässä tapauksessa Lyhytlaina.  
Sivun alareunassa on painike _Tallenna_ eli muista tallentaa muutokset.

![](/assets/files/docs/Luettelointi/luettelointi47.png)

Muutokset näkyvät tallennuksen jälkeen uutena sarakkeena
_Kokoelmakoodi_. Tämä sarake on näkyvissä vain, jos siellä on jotain
kokoelmatietoa, tyhjää saraketta ei näytetä.

![](/assets/files/docs/Luettelointi/luettelointi48.png)

#### Tiedon poistaminen

Esimerkissä olevan _Lyhytlaina_-kokoelmakoodin poistaminen tapahtuu
vastaavalla tavalla.  
Haetaan nimeke, jonka niteiltä kokoelmakoodi poistetaan, valitaan
_Muokkaa -&gt; Muokkaa niteitä eräajossa_.

![](/assets/files/docs/Luettelointi/luettelointi49.png)

Kokoelmakoodi-kentän valintaruutuun tehdään valinta (laitetaan täppä) ja
tallennetaan, niin _Lyhytlaina_-kokoelmakoodi poistuu valituilta
niteiltä.

### 5.2.3. Nidetiedot

Jokaisen nimeketietueen vasemmalla puolella on valikko, josta pääset
tarkastelemaan niteitä.

![](/assets/files/docs/Luettelointi/luettelointi501.png)

Jos nide on hankittu Kohan hankintamoduulin kautta, näkyy _Historiassa_
myös hankintatiedot. Jos tilaus- tai saapumispäivä näkyy linkkinä, siitä
pääsee niteen hankintatietoihin.

### 5.2.4. Niteen siirtäminen

Nide voidaan siirtää nimeketietueelta toiselle käyttämällä _Liitä nide_
-toimintoa.

![](/assets/files/docs/Luettelointi/kohakuvat5741.png)

Liittämiseen tarvitaan siirrettävän niteen viivakoodi, joka luetaan sen
nimekkeen tietoihin, mihin nide halutaan siirtää.
Jos nide on hankittu hankintaosion kautta, siirtyy siirron yhteydessä 
myös niteen hankintatieto.

![](/assets/files/docs/Luettelointi/luettelointi521.png)

Yksinkertaisesti lisäät siirrettävän niteen viivakoodin ja klikkaat OK.

Jos haluat siirtää useita niteitä yhteen tietueeseen, voit käyttää
_yhdistä tietueet_ -toimintoa.

### 5.2.5. Niteiden poisto

Niteiden poisto voidaan tehdä eri tavoilla. Jos haluat poistaa vain
yhden niteen, on yksinkertaisinta avata nimeketietueen tarkat tiedot ja
sieltä _Muokkaa -&gt; Muokkaa niteitä_.

![](/assets/files/docs/Luettelointi/luettelointi531.png)

Jokaisen niteen vasemmalla puolella on _Toiminnot_-valikko, jossa on 
yhtenä vaihtoehtona _Poista_.

![](/assets/files/docs/Luettelointi/kuvailu391.png)

Kun klikkaat _Poista_, saat vielä varmistuskysymyksen:

![](/assets/files/docs/Luettelointi/kuvailu40.png)

Nidettä ei voi poistaa, jos se on lainassa. Jos haluat poistaa kaikki
niteet nimekkeeltä, voit käyttää _Muokkaa -&gt; Poista kaikki niteet_.

![](/assets/files/docs/Luettelointi/luettelointi561.png)

Jos järjestelmäasetuksissa on määritelty mahdollistamaan niteiden
valinta, voit klikata nidetietojen näytöllä kunkin niteen vasemmalla
puolella valintalaatikosta ne niteet, joita haluat käsitellä. Voit
poistaa niteitä tai muokata niitä.

![](/assets/files/docs/Luettelointi/kuvailu411.png)

Voit käyttää myös _Muokkaa -&gt; Poista niteitä eräajossa_, jos poistat
enemmän niteitä kerralla.

![](/assets/files/docs/Luettelointi/luettelointi581.png)

Täällä voit valita niteet, jotka poistetaan.

![](/assets/files/docs/Luettelointi/luettelointi591.png)

### 5.2.6. Niteen lainahistoria

Jokaisella nimekkeellä säilytetään lainahistoria (asiakastietojen kanssa
tai ilman niitä, riippuu järjestelmän asetuksista), mutta jokaisella
niteellä on myös oma havaintohistoriansa. Tämä löytyy
_Niteet_-välilehdeltä.

![](/assets/files/docs/Luettelointi/kuvailu5265.png)

Historia-otsikon alla näkyy linkki _Raportti_, jota
klikkaamalla näkyy tämän niteen havaintohistoria. (huom. raportin numero on kimppakohtainen).

![](/assets/files/docs/Luettelointi/kuvailu5266.png)

Perustiedot-näkymästä on kaksi erilaista lainaushistorialinkkiä. Vasemmalla valikossa
on _Lainahistoria_.

![](/assets/files/docs/Luettelointi/kuvailu5261.png)

Sen näkymästä selviää mm. kunkin niteen lainauspäivä, eräpäivä ja palautuspäivä.

![](/assets/files/docs/Luettelointi/kuvailu5262.png)

Nimekkeen tietojen alimmaisena rivinä on linkki _Lainatilasto_-raporttiin (huom. raportin numero
on kimppakohtainen).

![](/assets/files/docs/Luettelointi/kuvailu5263.png)

Avautuvan raportin kautta näet mm. nimekkeen niteiden yhteisen lainamäärän.

![](/assets/files/docs/Luettelointi/kuvailu5264.png)

## 5.3. Erämuokkaukset

### 5.3.1. Niteiden muokkaus eräajona

Niteiden muokkaus nimeketietueessa on ohjeistettu kohdassa [5.2.2.2](https://koha-suomi.fi/dokumentaatio/kuvailu/#5222-niteiden-er%C3%A4muokkaus-nimekkeess%C3%A4)

Kuvailun työkaluista lähdetään liikkeelle valitsemalla niteet, mitä muokataan.

![](/assets/files/docs/Luettelointi/kuvailu50.png)

Niteet voi tuoda
- _Viivakooditiedostosta_, joka on tehty esim. keräämällä viivakoodeja muistioon tai tallentamalla nidehaku viivakooditiedostoksi
- _Nidenumerotiedostosta_ (itemnumber), joka on tehty esim. raportit-osiossa sql-kyselyllä tietokannasta
- _Lukemalla niteet yksi kerrallaan_ tekstilaatikkoon (jokainen omalle rivilleen)

Niteille voi halutessaan lisätä oletuspohjan arvot laittamalla rastin kohtaan _Täytä kentät oletusarvoilla, oletuspohjasta_. Huomioi, että tämä ei välttämättä tuo mitään arvoja niteille, jos oletusluettelointipohjaan ei ole määritetty oletusarvoja 952-kenttään.

Valitse _Jatka_ muokataksesi niteitä.

Erämuokkauksessa voit
![](/assets/files/docs/Luettelointi/kuvailu51.png)

- valita, mitä niteitä muokataan
- poistaa niteiltä lainassa-tilan (käytä harkiten)
- säätää, mitä tietoja niteistä näytetään muokkauksessa

![](/assets/files/docs/Luettelointi/kuvailu52.png)

- Pakolliseksi merkittyjä tietoja ei pysty poistamaan niteiltä, mutta ne voi vaihtaa toiseksi tiedoksi.
- Tiedon pystyy poistamaan laittamalla rastin halutun kentän viereen. Esim. kokoelmakoodin saa poistettua laittamalla rastin _Kokoelma_-kentän viereen.
- Tiedon pystyy lisäämään joko valitsemalla alasvetovalikosta vaihtoehdon tai kirjoittamalla kenttään haluttu tieto. Riippuu kentästä, kumpi vaihtoehto on mahdollista. Esim. kirjasto- ja hyllypaikkatieto valitaan alasvetovalikosta, mutta huomautus-kenttiin kirjoitetaan haluttu tieto.

Muutokset tehdään valitsemalla _Tallenna_. Jos et haluakaan tehdä muutoksia, valitse _Peruuta_ tai sulje ikkuna/välilehti, jolloin muutoksia ei tehdä.

### 5.3.2. Niteiden poisto eräajona

Niteiden poistossa eräajona pystyy poistamaan ison joukon niteitä kerralla.

Valitse ensin poistettavat niteet.
![](/assets/files/docs/Luettelointi/kuvailu53.png)

- _Viivakooditiedostosta_, joka on tehty esim. keräämällä viivakoodeja muistioon tai tallentamalla nidehaku viivakooditiedostoksi
- _Nidenumerotiedostosta_ (itemnumber), joka on tehty esim. raportit-osiossa sql-kyselyllä tietokannasta
- _Lukemalla niteet yksi kerrallaan_ tekstilaatikkoon (jokainen omalle rivilleen)

Valitse sitten _Jatka_.

Poistettavat niteet listautuvat avautuvalle sivulle.
![](/assets/files/docs/Luettelointi/kuvailu54.png)

- Voit valita, mitä sarakkeita niteistä näytetään.
- Voit vielä tässä vaiheessa ottaa pois rastin sellaisen niteen kohdalta, jota ei tarvikaan poistaa.
- Suositus: Kannattaa laittaa rasti kohtaan _Poista tietueet, jos kaikki niteet poistettu_, jotta tietokantaan ei jää “roikkumaan” niteettömiä nimekkeitä. Huomioi kuitenkin kimppakohtaiset käytännöt.

Valitse lopuksi _Poista valitut_ -painike.

Työ menee taustatyöjonoon.
![](/assets/files/docs/Luettelointi/kuvailu55.png)

Voit tarkastella työn etenemistä _Tarkastele jonossa olevan työn tietoja_

![](/assets/files/docs/Luettelointi/kuvailu56.png)

Voit päivittää näytön esim. näppäinyhdistelmällä Crtl+R tai selaimen painikkeesta

![](/assets/files/docs/Luettelointi/kuvailu57.png)

Pääset palaamaan työlistaan _Palaa työslistaan_-linkistä.

Huomaa, että päädyt niteiden eräpoistoon myös silloin, jos valitset tietueesta useamman niteen ja sitten valitset taulukon yläpuolelta _Poista valitut_

![](/assets/files/docs/Luettelointi/kuvailu58.png)


### 5.3.3. Tietueiden muokkaus eräajona

Tietueiden muokkauksessa eräajona voi lisätä/muokata tai poistaa MARC-kenttiä. Valituille tietueille voi esimerkiksi lisätä kielikoodin tai huomautuksen.

Erämuokkauksessa on rajoituksia

- jos tietueessa on jo olemassa muokattavaksi valittu MARC-kenttä, päivittää työkalu sen. Se ei lisää uuttaa toistumaa kentästä.
- kiinteämittaista kenttää 000 (leader) ei pysty muokkaamaan/poistamaan eräajona

Ennen kuin tietueita voi muokata, pitää määrittää käytettävä MARC-muokkauksen pohja.

Tietueiden erämuokkaukseen pääse kahta kautta.

#### Korista

![](/assets/files/docs/Luettelointi/kuvailu59.png)

Vie muokattavat tietueet koriin ja valitse kaikki (tai halutut) ja valitse sitten _Erämuokkaus_.

#### Kuvailu-välilehdeltä

Mene _Kuvailu_-välilehdelle ja valitse _Tietueiden muokkaus eräajona_

![](/assets/files/docs/Luettelointi/kuvailu60.png)

- Valitse ensin, muokataanko bibliografisia tietueita (nimekkeitä) vai auktoriteettitietueita (esim. kirjailija, asiasana).
- Seuraavaksi valitaan muokattavat tietueet joko
  - tuomalla ne tiedostosta, jossa on lista tietuenumeroista (biblionumber). Tällaisen voi luoda esim. sql-kyselyllä _Raportointi_-osiossa tai keräämällä tietuenumeroita Muistioon. Tiedostomuoto on oltava txt, jokainen tietuenumero omalle rivilleen.
  - valitsemalla valmiin listan Kohasta, tätä varten tee lista poistettavista tietueista.
  - listaamalla tietuenumerot tekstikenttään yksi per rivi
- Viimeiseksi valitaan, mitä muokkauspohjaa käytetään eli mitä muutoksia tietueille tehdään.

Valitse sitten _Jatka_.

![](/assets/files/docs/Luettelointi/kuvailu61.png)

- Voit vielä vaihtaa muokkauspohjan tai tullessasi korista käsin, valitse se nyt.
- Voit tarkistaa muokkauksen tuloksen valitsemalla _Näytä MARC_, jolloin avautuu MARC-tietueen esikatselu ja mukana on myös haluttu muutos:

![](/assets/files/docs/Luettelointi/kuvailu62.png)

Kun kaikki on kuten pitääkin, valitse _Muokkaa valittuja tietueita_.

Muokkauksen jälkeen työn ilmoitetaan olevan jonossa. Voit tarkistaa tilanteen painamalla _Tarkastele jonossa olevan työn tietoja_ kuten edellä osiossa 5.3.2. on opastettu.

### 5.3.4. Tietueiden poisto eräajona

Tietueiden eräpoistoon pääse kahta kautta.

#### Korista

![](/assets/files/docs/Luettelointi/kuvailu64.png)

Vie muokattavat tietueet koriin ja valitse kaikki (tai halutut) ja valitse sitten _Eräpoisto_.

#### Kuvailu-välilehdeltä

Mene _Kuvailu_-välilehdelle ja valitse _Tietueiden poisto eräajona_

![](/assets/files/docs/Luettelointi/kuvailu63.png)

- Valitse ensin, poistatko bibliografisia tietueita (nimekkeitä) vai auktoritettitietueita (esim. kirjailijoita, asiasanoja).
- Voit tuoda poistettavat tietueet joko
  - tiedostona, joka sisältää poistettavien tietueiden tietuenumerot (biblionumber). Tällaisen listan voi luoda esimerkiksi sql-kyselyllä _Raportointi_-osiossa tai keräämällä tietuenumeroita Muistioon.
  - valitsemalla valmiin listan Kohasta, tätä varten tee lista poistettavista tietueista.
  - lisäämällä tietuenumerot tekstikenttään yksi per rivi.

Valitse sitten _Jatka_.

Tietueiden poistossa listataan poistoon valitut tietueet.

![](/assets/files/docs/Luettelointi/kuvailu65.png)

- jos tietueeseen liittyy lainassa olevia niteitä, ei sitä pysty poistamaan.
- voit vielä tässä vaiheessa ottaa rastin pois niiltä tietueilta, joita et halua poistaa.
- Huomioi: tietueiden eräpoisto poistaa myös tietueeseen liittyvät lehtitilaukset, niteet ja varaukset 
  - tämä voi olla kätevää esim. kun teos ei ilmesty ja siihen on paljon varauksia, jolloin sitä ei pysty poistamaan tietueesta käsin poistamatta ensin varauksia.
 
Valitse lopuksi _Poista valitut tietueet_. Jos et haluakaan poistaa, valitse _Peruuta_ tai sulje ikkuna/välilehti, jolloin poistoa ei tehdä.

Poiston jälkeen työn ilmoitetaan olevan jonossa. Voit tarkistaa tilanteen painamalla _Tarkastele jonossa olevan työn tietoja_ kuten edellä osiossa 5.3.2. on opastettu.

### 5.3.5. Niteen muokkaus iän mukaan

Kuvailu-osion Niteen muokkaus iän mukaan -toiminnolla teet säännön tai sääntöjä, joiden perusteella niteen tiedot muuttuvat automaattisesti. Automatiikan toimintaan tarvitaan säännön lisäksi järjestelmänkehittäjän ajastama yöllinen ajo (_misc/cronjobs/automatic_item_modification_by_age.pl_).

Tee uusi sääntö tai muokkaa jo olemassa olevaa sääntöä valitsemalla toiminnon etusivulta _Muokkaa sääntöjä_ 

<img src="/assets/files/docs/Tyokalut/ianmukaan01.png" alt="" style="width:90.0%" />

Muokkaa olemassa olevaa sääntöä tai tee uusi sääntö valitsemalla _Lisää sääntö_  

<img src="/assets/files/docs/Tyokalut/ianmukaan02.png" alt="" style="width:90.0%" />

Määritä uudelle säännölle nämä:
<img src="/assets/files/docs/Tyokalut/ianmukaan03.png" alt="" style="width:90.0%" />

- **Ikä päivinä**. kirjoita päivien määrä.
- **Ikä**, valitse se niteen päiväyskenttä, jonka mukaan ikä lasketaan.
- **Ehdot**, valitse arvo, joka muuttuu automaattisesti. Voit lisätä useamman ehdon valitsemalla kentän vierestä _Lisää ehto_
- **Korvaajat**, valitse arvo, joka korvaa automaattisesti Ehdot-kohdan arvon. Voit  lisätä useamman korvaajan valitsemalla _Lisää korvaaja_ kentän vierestä.

Tallenna sääntö näytön yläreunan _Tallenna_-painikkeella.

Poista tarpeeton sääntö valitsemalla _Poista tämä sääntö_.

---

### 5.3.6. MARC-muokkauksen pohjat

Tietueiden erämuokkaukseen tarvitaan sääntö, jonka perusteella tietuemuutos tehdään. Tee sääntö _Kuvailu_-osion _MARC-muokkauksen pohjat_ -toiminnossa.

Kiinteämittaisen kentän erämuokkaus onnistuu, kun kentän kaikki merkkipaikat on määritelty ehtoon. Poikkeuksena kiinteämittainen kenttä 000 (leader) , jota ei pysty muokkaamaan eikä poistamaan eräajona.

![](/assets/files/docs/Luettelointi/kuvailu66.png)

#### Uuden muokkauspohjan tekeminen

Tee uusi pohja valitsemalla _Uusi pohja_

![](/assets/files/docs/Luettelointi/kuvailu67.png)

Anna pohjalle kuvaava nimi. Voit myös kopioida malliksi jo olemassa olevan pohjan.

![](/assets/files/docs/Luettelointi/kuvailu68.png)

Lisää pohjaan toiminnot niistä muutoksista, jotka tietueille tehdään. Valitse _Uusi toiminto_

![](/assets/files/docs/Luettelointi/kuvailu69.png)

Valitse alasvetovalikosta tarvittava toiminto.

![](/assets/files/docs/Luettelointi/kuvailu70.png)

Valitse alasvetovalikosta koskeeko muutos kaikkia muutettavan kentän toistumia vai vain ensimmäistä kenttätoistumaa. 

![](/assets/files/docs/Luettelointi/kuvailu71.png)

Kirjoita muutettava kenttä.

![](/assets/files/docs/Luettelointi/kuvailu72.png)

Valitse tarvittaessa muut ehdot.

![](/assets/files/docs/Luettelointi/kuvailu73.png)

Kirjoita ehtoon liittyvä kenttä ja valitse alasvetovalikosta, milloin kenttä huomioidaan.
Lisää tarvittaessa ehtoon _RegEx_-sääntö. (Säännöllinen lauseke (engl. regular expression, regexp) on yksinkertainen merkkijonokieli, joka voi joko vastata tai olla vastaamatta jotain toista merkkijonoa. Tekstin lähde: [Säännöllinen lauseke](https://www.linux.fi/wiki/S%C3%A4%C3%A4nn%C3%B6llinen_lauseke))

![](/assets/files/docs/Luettelointi/kuvailu75.png)

_Kuvaus_-kenttään voit lisätä tiedon, mitä muokkaustominto tekee tietueelle. Tallenna toiminto valitsemalla _Lisää toiminto_.

![](/assets/files/docs/Luettelointi/kuvailu76.png)

Voit lisätä samaan pohjaan useamman toiminnon ja muuttaa toimintojen suoritusjärjestyksen nuolipainikkeilla.

## 5.4 Työkalut

Kuvailuun liittyy myös työkaluja. Ne löytyvät Kuvailu-osiosta Työkalut-otsikon alapuolelta.

### 5.4.1 Poistettujen tietueiden palautus

Poistettuja tietueiden palautusta varten on työkalu nimeltään _Poistettujen kuvailutietueiden palautustyökalu_. Tämä on Koha-Suomen oma työkalu, joka tulee poistumaan, kun yhteisössä tehty vastaava työkalu tulee meillä aikanaan versionvaihdossa 25.11.

#### 5.4.1.1 Poistettujen kuvailutietueiden hakeminen

Poistettuja kuvailutietueita voi hakea aikavälin perusteella

![](/assets/files/docs/Luettelointi/kuvailu77.png)

### 5.4.2 Poistettujen niteiden palautus

## 5.5. Auktoriteetit

ohje tehdään myöhemmin

## 5.6. Kuvailuohjeet

<a href="https://koha-community.org/manual/latest/en/html/cataloging.html" target="_blank">Yhteisön kuvailuohjeet</a>

### 5.6.1. Niteiden tarrat ja niiden tulostaminen

Koha-Suomen ohje [tarratulostukseen](https://koha-suomi.fi/dokumentaatio/tyokalut/#1294-tarratulostusty%C3%B6kalu)

### 5.5.2. Niteiden tallennusohjeet

<table>
<thead>
<tr class="header">
<th>Kenttä</th>
<th>Otsikko</th>
<th>Kuvaus</th>
<th>Huomautus</th>
</tr>
</thead>
<tbody>
<tr>
<td>952$0</td>
<td>Pois kierrosta -tila</td>
<td>Oletusarvot:<br />
0 = (tyhjä)<br />
1 = Pois kierrosta</td>
<td>Koodattu arvo, taulukko <em>Auktorisoidut arvot -&gt; WITHDRAWN</em>.<br /> <em>Pois kierrosta </em>-tilaista nidettä ei voi lainata, 
  ellei <em>BlockReturnOfWithdrawnItems</em> -järjestelmäasetus salli sitä.</td>
</tr>
<tr>
<td>952$1</td>
<td>Kadonnut-tila</td>
<td>Oletusarvot:<br />
0 = (tyhjä)<br />
1 = Kadonnut<br />
2 = Myöhässä (kadonnut)<br />
3 = Kadonnut ja korvattu<br />
4 = Puuttuu</td>
<td>Koodattu arvo, taulukko <em>Auktorisoidut arvot -&gt; LOST</em><br />
Asetuksissa voi muokata <em>hidelostitems</em>-määrityksellä, näkyykö kadonnut aineisto verkkokirjastossa.
Järjestelmäasetuksilla <em>IssueLostItem</em> (lainaus) ja <em>BlockReturnOfLostItems</em> (palautus) voidaan määritellä, 
miten nide käyttäytyy lainauksessa/palautuksessa.</td>
</tr>
<tr>
<td>952$2</td>
<td>Luokitus</td>
<td>Luokitusjärjestelmä, jonka mukaan luokkanumerot järjestyvät</td>
<td>Asetuksissa luokituslähteet, jonne on tallennettu <em>ykl = Yleisten kirjastojen luokitus</em> oletusarvoksi <em>(Luokitus - &gt; DefaultClassificationSource)</em></td>
</tr>
<tr>
<td>952$3</td>
<td>Liitteiden määrä</td>
<td>Moniviestimien tms. osien määrä tai liitteiden määrä ja kuvaus</td>
<td>Näkyy lainaus- ja palautusnäytöllä, ilmoittaa niteeseen kuuluvan aineiston määrän (esim. montako liitettä). </td>
</tr>
<tr>
<td>952$4</td>
<td>Vaurioitunut-tila</td>
<td>Oletusarvot:<br />
0 = (tyhjä)<br />
1 = Vaurioitunut</td>
<td>Koodattu arvo, taulukko <em>Auktorisoidut arvot - &gt; DAMAGED</em>.<br /> Järjestelmäasetuksella <em>AllowHoldsOnDamagedItems</em> määritetään,
voiko <em>Vaurioitunut</em>-tilan nidettä varata.</td>
</tr>
<tr>
<td>952$5</td>
<td>Käyttörajoitukset</td>
<td>Oletusarvot:<br />
0 = (tyhjä)<br />
1 = Rajoitettu pääsy</td>
<td>Koodattu arvo, taulukko <em>Auktorisoidut arvot - &gt; RESTRICTED.</em><br />
Rajoitetun pääsyn nidettä ei voi lainata. Niteen tila hakutuloksessa on <em>Saatavana (Rajoitettu pääsy)</em> </td>
</tr>
<tr>
<td>952$7</td>
<td>Ei lainattavissa</td>
<td>Oletusarvot:<br />
0 = (tyhjä)<br />
–1 = Tilattu<br />
1 = Ei lainata<br />
2 = Henkilökunnan käsikirjasto</td>
<td>Koodattu arvo, taulukko <em>Auktorisoidut arvot -&gt; NOT_LOAN</em><br />
Negatiiviset arvot sallivat varaamisen. Niteiden varattavuuteen vaikuttaa
usea järjestelmäasetus: <em>TrapHoldsOnOrder</em>, <em>SkipHoldTrapOnNotForLoanValue</em>, <em>UpdateNotForLoanStatusOnCheckin</em>.
Lainattavuuteen vaikuttaa järjestelmäasetus <em>AllowNotForLoanOverride</em>. </td>
</tr>
<tr>
<td>952$8</td>
<td>Kokoelmakoodi</td>
<td>Esim. Pikalaina, Celia-kokoelma</td>
<td>Koodattu arvo, taulukko <em>Auktorisoidut arvot -&gt; CCODE</em></td>
</tr>
<tr>
<td>952$a</td>
<td>Omistajakirjasto</td>
<td>Kirjaston nimi</td>
<td>Vaaditaan. Nimi on määriteltävä perusasetuksissa <em>Kirjastot ja ryhmät</em>.</td>
</tr>
<tr>
<td>952$b</td>
<td>Sijaintikirjasto</td>
<td>Kirjaston nimi</td>
<td>Vaaditaan. Nimi on määriteltävä perusasetuksissa <em>Kirjastot ja ryhmät</em>.</td>
</tr>
<tr>
<td>952$c</td>
<td>Hyllypaikka</td>
<td>Esim. Aikuiset, Lapset, Kotiseutukokoelma</td>
<td>Koodattu arvo, taulukko <em>Auktorisoidut arvot -&gt; LOC</em>.<br /> Hyllypaikka voi muuttua niteen palautuksessa, jos
järjestelmäasetuksessa <em>UpdateItemLocationOnCheckin</em> on määritykset sitä varten. Uudelle niteelle voidaan antaa oletusarvo
<em>NewItemsDefaultLocation</em> -järjestelmäasetuksessa. </td>
</tr>
<tr>
<td>952$d</td>
<td>Hankintapvm</td>
<td>VVVV-KK-PP</td>
<td>Päiväyksen tulee olla järjestelmän ymmärtämässä muodossa: VVVV-KK-PP. Päiväys täyttyy automaattisesti, 
  jos kentässä on <em>dateaccessioned</em>-liitännäinen käytössä. Tieto tarvitaan hankintatilastoa varten.</td>
</tr>
<tr>
<td>952$e</td>
<td>Hankintapaikka</td>
<td>Koodattu arvo tai toimittajan nimi</td>
<td>Täytetään automaattisesti hankintamoduulissa Kohaan tallennetun toimittajan tunnuksella, kun nide on saapunut.</td>
</tr>
<tr>
<td>952$g</td>
<td>Hankintahinta</td>
<td>Desimaalinumero, ei valuuttamerkkejä (esim. 10.00)</td>
<td>Täytetään automaattisesti hankinnan tiedoilla, kun nide on saapunut.</td>
</tr>
<tr>
<td>952$h</td>
<td>Sarjanumero</td>
<td>Esim. 2016 : 3</td>
<td>Täytetään automaattisesti kausijulkaisuissa, jos niteet on merkitty saapuneeksi saapumisvalvonnan kautta</td>
</tr>
<tr>
<td>952$o</td>
<td>Kohan koko signum</td>
<td>Esim. AIK 84.2 JAA</td>
<td>Voidaan täyttää automaattisesti, perustuu järjestelmäasetukseen <em>itemcallnumber</em></td>
</tr>
<tr>
<td>952$p</td>
<td>Viivakoodi</td>
<td>Max. 20 merkkiä</td>
<td>Pakollinen tieto lainauksen kannalta, mutta ei muuten.</td>
</tr>
<tr>
<td>952$u</td>
<td>URI</td>
<td>Niteen oma URL</td>
<td>Koko URL, joka alkaa http: Täytetään vain, jos niteellä on oma URL, mutta ei ole tarpeellinen, jos nimekkeellä on 856$u-kenttään osoite tallennettuna.</td>
</tr>
<tr>
<td>952$v</td>
<td>Korvaushinta</td>
<td>Desimaalinumero, ei valuuttamerkkejä (esim. 10.00)</td>
<td>Täytetään automaattisesti hankintamoduulista, kun nide on saapunut.</td>
</tr>
<tr>
<td>952$w</td>
<td>Hinta voimassa alkaen</td>
<td>VVVV-KK-PP</td>
<td>Päiväyksen tulee olla järjestelmän ymmärtämässä muodossa: VVVV-KK-PP. Täytetään automaattisesti hankintamoduulista, kun nide on saapunut.</td>
</tr>
<tr>
<td>952$x</td>
<td>Huomautus virkailijoille</td>
<td></td>
<td>Tämä huomautus ei näy verkkokirjastossa. Tällä hetkellä tämä huomautus näkyy vain niteiden muokkausnäytöllä ja Niteet-välilehdellä virkailijatyökalussa.</td>
</tr>
<tr>
<td>952$y</td>
<td>Kohan nidetyyppi</td>
<td>Esim. AIK28, EILAINATA ym. </td>
<td>Pakollinen tieto. Koodattu arvo, määritellään perusasetuksisssa <em>Nidetyypit</em>.</td>
</tr>
<tr>
<td>952$z</td>
<td>Yleinen huomautus</td>
<td>Esim. Liitteenä 3 CD-levyä</td>
<td>Näkyy verkkokirjastossa ja virkailijaliittymässä</td>
</tr>
</tbody>
</table>
