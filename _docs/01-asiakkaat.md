---
title: 'Kohan ohje suomeksi'
permalink: /dokumentaatio/asiakkaat/
redirect_from:
  - /theme-setup/
toc: true
---

# 1. Asiakkaat

Aina ennen asiakastiedon lisäämistä on hyvä tarkistaa löytyykö asiakkaan tiedot jo Kohasta. Voit 
hakea asiakkaan tietoja esim. nimihaulla sekä syntymäaikahaulla.

## 1.1. Asiakkaan hakeminen

Klikkaamalla yläpalkin linkkiä _Asiakkaat_ saat asikastietojen hakusivun, jossa voit selata tai
hakea asiakkaiden tietoja.

<img src="/assets/files/docs/Asiakkaat/Asiakkaat_hakusivu.png" alt="" style="width:90.0%" />

Klikkaamalla pientä valikko-kuvaketta hakulaatikon oikealla puolella
saat lisää hakuominaisuuksia käyttöösi. Alasvetovalikoista saat lisää hakuehtoja.

Huom. Samat hakuominaisuudet aukeavat automaattisesti Asiakkaat-sivun vasempaan laitaan. 

![](/assets/files/docs/Asiakkaat/hae_asiakasta1.png)

Alasvetovalikoissa tekemiesi valintojen perusteella voit hakea asiakasta eri tavoin.

\- Perushaku:  
Anna asiakkaan nimi tai nimen osa, käyttäjätunnus, kirjastokortin
viivakoodi, varaustunniste tai varaustunnisteen osa. Antaessasi nimen tai osan nimestä tai varaustunnisteesta valitse hakutyypiksi _sisältää_

\- Sukunimi:  
Anna asiakkaan sukunimi tai sukunimen osa. Valitse hakutyypiksi
_sisältää_

\- Kortin numero:
Anna asiakkaan kortin numero

\- Sähköposti:  
Anna asiakkaan sähköpostiosoite tai osa siitä ja valitse hakutyypiksi
_sisältää_

\- Asiakkaan ID:  
Anna Kohan Asiakkaan ID-numero (eri kuin kirjastokortti)

\- Käyttäjätunnus:  
Anna asiakkaan erillinen käyttäjätunnus, kirjastokortin numero tai osa siitä. Käyttäjätunnuksen tallennuksessa voi olla kimppakohtaisia eroja. Antaessasi osan kirjastokortin numerosta valitse hakutyypiksi _sisältää_

\- Lankapuhelin:  
Anna lankapuhelinnumero kokonaisuudessaan kuten se on syötetty järjestelmään
tai käytä tyhjää merkkiä numeroiden jaksotteluun. Esim. haettaessa
numeroa (013) 267 6200 voit kirjoittaa sen juuri samalla tavalla tai
muodossa 013 267 6200

\- Osoite:  
Anna asiakkaan osoite tai osoitteen osa ja valitse hakutyypiksi _sisältää_

\- Syntymäaika:  
Voit hakea muodoissa PP.KK.VVVV, PPKKVV tai PPKKVVVV

\- Etunimi:
Tee asiakashaku etunimellä tai kaikilla etunimillä. Valitse hakutyypiksi _sisältää_

\- Matkapuhelin:
Anna matkapuhelinnumero kokonaisuudessaan kuten se on syötetty järjestelmään
tai käytä tyhjää merkkiä numeroiden jaksotteluun. Esim. haettaessa
numeroa 0442676200 voit kirjoittaa sen juuri samalla tavalla tai
muodossa 044 267 6200


Voit valita jokaisessa haussa hakutyypin _alkaa_ tai _sisältää_.
Valinta _sisältää_ toimii vapaasanahaun kaltaisesti eli haettu merkkijono
voi olla missä tahansa kohdassa hakukentässä.

Saat tarkennettua hakua myös valitsemalla asiakkaan _kirjaston_ ja/tai rajaamalla hakua _asiakastyypin_ mukaan.

Voit myös selata asiakkaita sukunimen ensimmäisen kirjaimen mukaan
linkkinä olevien kirjainten mukaan.

![](/assets/files/docs/Asiakkaat/aastaoohon.png)

Huom. Laajan asiakashaun voit tehdä myös muillakin sivuilla kuin vain Asiakkaat-sivulla, jos vihreässä yläpalkissa näkyy vaihtoehto _"Hae asiakkaita"_.  Klikkaa tuolloin _"Hae asiakkaita"_ aktiviiseksi ja avaa valikko-kuvakkeesta hakukentät esille.
{: .notice--warning}

## 1.2. Lisää uusi asiakas

Asiakkaat lisätään menemällä Asiakkaat-välilehdelle.

<img src="/assets/files/docs/Asiakkaat/Lisaauusiasiakas1.png" alt="" style="width:90.0%" />

Sivulla on alasvetovalikkovaihtoehdot: **Uusi asiakas** ja **Asiakkaan pikalisäys**. 
Huom. Kaikissa kimpoissa ei ole _Asiakkaan pikalisäys_-vaihtoehtoa käytössä, joten valitse kimppasi ohjeistama asiakkaan lisäystapa.

![](/assets/files/docs/Asiakkaat/Lisaauusiasiakas2.png)

Klikkaa _Uusi asiakas_, saat alasvetovalikon, josta valitset _asiakastyypin_.

![](/assets/files/docs/Asiakkaat/Lisaauusiasiakas3.png)

### 1.2.1. Henkilötunnuksen lisääminen asiakastietoihin

Oheisissa ruutukaappauksissa käytetty sotu on tehty
henkilötunnusgeneraattorin avulla, se ei ole kenenkään henkilön oikea
tunnus, mutta täyttää tunnuksen ominaisuudet tarkistusmerkkiä myöten.
Sotu-avaimella muodossa “sotuxxxx” voi hakea asiakkaan tiedot esille,
mutta henkilötunnus ei näy.


Syötä _Lisää hetu_-kohtaan asiakkaan henkilötunnus. Klikkaa _Tallenna_.

![](/assets/files/docs/Asiakkaat/Lisaahetu.png)


\- Jos henkilötunnusta ei ole ennestään Sotuteekissä, siitä tulee ilmoitus
"Hetu tallennettu!". 

![](/assets/files/docs/Asiakkaat/Hetutallennettu1.png)

Sotu-avain siirtyy automaattisesti kirjoitussuojattuun kenttään nimeltä
Sosiaaliturvatunnus/Henkilötunnus/Sotu-avain/Hetu-avain
(kentän nimi voi vaihdella kimpan mukaan). 

![](/assets/files/docs/Asiakkaat/Sotuavain.png)

Voit jatkaa uuden asiakkaan tallentamista käyttäen Sotuteekin antamaa sotu-avainta.

\- Jos syötetty henkilötunnus on jo Sotuteekissa, järjestelmä tutkii automaattisesti kimppasi asiakasrekisteristä löytyykö 
henkilötunnuksen sotu-avaimella asiakastietoja.

Jos tietoja ei löydy kimpan asiakasrekisteristä, niin käyttäjälle tulee ilmoitus “Hetu asetettu!". Jatka tuolloin uuden asiakkaan
tallentamista käyttäen Sotuteekin antamaa sotu-avainta.

![](/assets/files/docs/Asiakkaat/Hetuasetettu.png)

Jos asiakastiedot löytyvät, niin käyttäjälle tulee ilmoitus "Asiakas on jo olemassa! Paina OK siirtyäksesi tietoihin." 
Klikkaamalla _OK_ käyttäjä siirtyy automaattisesti asiakkaan tietoihin, joita tarvittaessa muokataan.

![](/assets/files/docs/Asiakkaat/Sotu3.png)

\- Jos henkilötunnus on virheellinen, tulee siitä ilmoitus: “Tarkista hetu!”.

![](/assets/files/docs/Asiakkaat/Tarkistahetu.png)

#### 1.2.1.1. Sotuteekki

Kohaan on tehty Suomessa ominaisuus, **Sotuteekki**, jonne tallennetaan
tietoturvallisesti asiakkaiden henkilötunnukset. Sotuteekki on yhteinen kaikille Koha-kimpoille.

Sotuteekissa esimerkiksi laskuttajat voivat tarkistaa asiakkaan henkilötunnuksen
sotu-avaimella. Heillä on erilliset tunnukset tarkistusta varten.
Sotuteekistä tarkemmin Kohan ohje suomeksi -ohjeen
kohdassa [12.16.3 Sotuteekki](https://koha-suomi.fi/dokumentaatio/tyokalut/#12163-sotuteekki)

### 1.2.2. Nimi, syntymäaika ja varaustunnus

Syötä asiakkaan koko nimi ja syntymäaika. Varaustunniste täyttyy automaattisesti. Huomaathan,
että kimppasi Kohassa ei välttämättä näy kaikki kuvissa näkyvät kentät tai vaihtoehdot.

![](/assets/files/docs/Asiakkaat/Varaustunnus1.png)

Asiakastyyppeille on määritetty ikärajoituksia. Ohjelma tarkistaa
syntymäajan mukaan, voiko asiakas kuulua asiakastyyppiin, joka hänelle 
ollaan tallentamassa. Voit saada tällaisen virheilmoituksen:  
![](/assets/files/docs/Asiakkaat/ikaraja.png)

Virheilmoituksen saatuasi kaikista helpointa on aloittaa asiakkaan tietojen tallennus uudelleen alusta, sillä asiakastyypeillä on erilaiset lomakepohjat.
{: .notice--warning}

### 1.2.3. Takaaja-tiedon tallentaminen ja poistaminen

Jos kyseessä on lapsiasiakas, hänelle pitää tallentaa takaaja. Klikkaa
_Lisää takaaja_ -nappia, niin pääset hakemaan rekisteristä lapselle
takaajan.

Huom. kaikissa kimpoissa ei ole kuvassa näkyvää _Näytä takaajille lainat_-vaihtoehtoa valittavissa.

![](/assets/files/docs/Asiakkaat/Lisaatakaaja.png)

Takaajaa voi hakea joko nimellä tai kirjastokortin numerolla. Valitse
alasvetovalikoista sopivat vaihtoehdot.

Saat listan hakuun sopivista asiakkaista. Klikkaa oikealta _Valitse_ tai _Select_-painiketta
oikean henkilön kohdalla. 

<img src="/assets/files/docs/Asiakkaat/Valitsetakaaja.png" alt="" style="width:90.0%" />

Valitse alasvetovalikosta takaajan suhde asiakkaaseen. Alasvetovalikon 
vaihtoehdot voivat vaihdella kimpoissa.

![](/assets/files/docs/Asiakkaat/Asiakastakaaja.png)

Valinnan jälkeen lapsen tiedoissa näkyy takaajan nimi sekä kirjastokorttinumero. 

Voit tallentaa lapsiasiakkaalle useamman kuin yhden huoltajan tiedot. 

Huom. Ensimmäisenä lisätylle takaajalle järjestelmä lähettää huollettavan mahdolliset laskut ja huomautukset.
{: .notice--warning}

![](/assets/files/docs/Asiakkaat/Takaajat.png)

Jos takaajaa ei löydy asiakasrekisteristä, avaa selaimessa uusi välilehti ja
tallenna takaajan tiedot rekisteriin. Palaa tallennuksen jälkeen lapsiasiakkaan
tietoihin toiselle välilehdelle ja tee takaajahaku uudelleen.

Roskakorin kuvaketta klikkaamalla saat takaajatiedon poistettua. **Huom. alaikäisellä asiakkaalla tulee aina olla vähintään yksi takaaja**, joten lapsiasiakkaan tietojen tallennus ei onnistu, jos häneltä puuttuu takaajatieto.

#### 1.2.3.1. Ei-asiakas takaaja-tiedon lisääminen

Kimppakohtainen.

![](/assets/files/docs/Asiakkaat/Eiasiakastakaaja.png)

### 1.2.4. Osoite

Osoite-osiossa _Kunta_ tarkoittaa käytännössä postitoimipaikkaa, ei
pelkästään kotikuntaa. Englanninkielistä sanaa City ei voi kääntää
postitoimipaikaksi tässä kohdassa, sillä City-sanaa käytetään kunta-merkityksessä
muussa yhteydessä. Voit valita postinumeron ja postitoimipaikan alasvetovalikosta tai kirjoittaa ne itse.

![](/assets/files/docs/Asiakkaat/Osoitetiedot.png)

### 1.2.5. Yhteystiedot

Syötä _Yhteystiedot_-osiossa asiakkaan puhelinnumero (lankapuhelinnumero _Lankapuhelin_-kenttään ja matkapuhelinnumero _Matkapuhelin_-kenttään) ja sähköpostiosoite. Matkapuhelin-kenttään lisätty numero kopioituu automaattisesti asiakkaan viestiasetuksiin. 

Huom! Puhelin-kenttiin ei saa kirjoittaa muuta kuin puhelinnumeron. Numeroon ei tallenneta muita välimerkkejä kuin kansainvälisen suunnan plusmerkki (esim. +358) eikä kirjaimia (esim. äiti).

Sähköpostiosoite on se osoite, johon asiakasviestit lähtevät.

![](/assets/files/docs/Asiakkaat/Yhteystiedot1.png)

Asiakas voi halutessaan valita ensisijaisen yhteydenottotavan kirjaston henkilökunnan yhteydenottoja varten, jos toiminto on otettu kimpassa käyttöön.


### 1.2.6. Vaihtoehtoinen osoite

Asiakkaalle voidaan tallentaa myös vaihtoehtoinen osoite, jos vaihtoehto on otettu kimpassa käyttöön.

![](/assets/files/docs/Asiakkaat/Vaihtoehtoinenosoite.png)


### 1.2.7. Kirjastotiedot

#### 1.2.7.1. Kirjastonhallinta

_Kirjastonhallinta_-osio sisältää kirjaston käyttöön liittyviä tietoja.

![](/assets/files/docs/Asiakkaat/kirjastohallinta.png)

\- Lue asiakkaan kirjastokortin numero ylimmäisenä olevaan
_Kirjastokortin numero_ -kenttään.

\- _Kirjasto_-kenttään valitaan asiakkaan kotikirjasto, jota Koha
ehdottaa esim. varausta tehtäessä noutokirjastoksi.

\- _Tyyppi_-kohdassa voi vaihtaa asiakastyypin. 
Huom! Jos tässä kohtaa vaihtaa asiakastyypin, muutos ei tuo esille mm. takaajatieto-kenttää tai
poista sitä näkyvistä. **Jos valitsit alussa väärän asiakastyypin, niin aloita asiakastietojen tallentaminen alusta.**

\- Valitse asiakasviestien kieli kohdassa _Ilmoitusten kieli_.

#### 1.2.7.2 Kirjaston asetukset

<img src="/assets/files/docs/Asiakkaat/Huomautuslaatikko1.png" alt="" style="width:90.0%" />

\- _Tullut asiakkaaksi_ -päivämäärä tulee automaattisesti kuluvan päivän
mukaiseksi.

\- _Vanhenee_ -kohtaan ei tarvitse merkitä mitään. Tieto tulee
automaattisesti asiakaslajille tehtyjen määritysten mukaan.

\- _Huomautus (näkyy verkkokirjastossa)_ -kohtaan voi merkitä
huomautuksen, jonka asiakas näkee verkkokirjastosta. Huomautus
näkyy OPACissa ja Finnassa.

Finnassa huomautus näkyy Omat tiedot-välilehdellä kohdassa _Huomautukset_.

<img src="/assets/files/docs/Asiakkaat/Huomautuslaatikko2.png" alt="" style="width:80.0%" />

\- _Huomautus (näkyy virkailijatyökalussa)_ -laatikkoon tallennettu huomautus
näkyy virkailijoille Kohassa tiedot- ja lainausnäytöillä.

<img src="/assets/files/docs/Asiakkaat/Huomautuslaatikko.png" alt="" style="width:90.0%" />

#### 1.2.7.3. Kirjautumistunnus

_Kirjautumistunnus_-osioon voi lukea esim. kirjastokortin numeron tai
erillisen käyttäjätunnuksen, jolla asiakas voi kirjautua
verkkokirjastoon. Huom! Kimppakohtaisia eroja.

![](/assets/files/docs/Asiakkaat/kirjautumistunnus.png)

Tallennettu käyttäjätunnus näkyy asiakkaan _Tiedot_-välilehdellä.

#### 1.2.7.4. Muut määritteet ja tunnukset

Tässä valitaan mm. automaattien automaattityyppi, automaatin toimittaja sekä yhteisöasiakkaan Y-tunnuskenttä.

![](/assets/files/docs/Asiakkaat/Muutmaareetjatunnukset1.png)

![](/assets/files/docs/Asiakkaat/Muutmaareetjatunnukset2.png)

Myös muita kimppakohtaisia määritteitä voi olla käytössä.

### 1.2.8. Asiakkaan viestiasetukset

Lopuksi vielä tallennetaan asiakkaan viestiasetukset. Käytettävissä
olevat viestivaihtoehdot vaihtelevat kimpoittain.

![](/assets/files/docs/Asiakkaat/Asiakkaanviestiasetukset.png)

\- _Ilmoitus eräpäivänä_: Ilmoitus lainojen erääntymisestä eräpäivänä. 

\- _Ennakkoilmoitus_: Etukäteisilmoitus lähestyvästä eräpäivästä. Asiakas
voi valita, montako päivää etukäteen ilmoitus tulee. 
**Huom! Jos tähän valitsee 0, ei viestiä lähetetä, vaikka rasti olisi paikallaan.**

\- _Saapumisilmoitus_: Ilmoitus asiakkaalle noudettavissa olevasta
varauksesta.

\- _Palautuskuitti_: Lista asiakkaan juuri palauttamasta aineistosta. Tämä on
  sähköinen versio palautuskuitista.

\- _Lainauskuitti_: Lista asiakkaan juuri lainaamista niteistä. Tämä on
  sähköinen versio lainauskuitista.
  
\- _Vain koosteilmoitus_-ruksit tallentuvat ennakkoilmoitukseen ja eräpäiväilmoitukseen 
automaattisesti. Viestit lähetetään asiakkaille koosteina, jotta he saavat 
yhdessä viestissä kaikkien erääntyvien niteiden tiedot.

\- _“Tekstiviesti numeroon”_ -kenttään kopioituu automaattisesti Matkapuhelin-kenttään
lisätty numero. Tekstiviesti numeroon -kenttä on kirjoitussuojattu. Tekstiviesti-vaihtoehtoon ei 
laiteta rastia, jos tässä kentässä ei ole puhelinnumeroa.


\- Nämä viestiasetukset kumoavat asiakaslajeille tehdyt oletusvalinnat.
\- Asiakas voi itse muuttaa kaikkia viestiasetuksia verkkokirjastossa, paitsi _Koosteilmoitus_-asetuksia.
{: .notice--warning}

## 1.3. Tallennus

Lopuksi tallenna tiedot.

Järjestelmä ilmoittaa, jos jotain tarvittavaa tietoa puuttuu. Täydennä tiedot ja tallenna uudelleen.

![](/assets/files/docs/Asiakkaat/Pakollinenkentta.png)


## 1.4. Ei-tilastoitavat-lainat

Tämä asiakastyyppi on luotu sellaisille lainoille, joita henkilökunta
tekee työtarkoitusta varten. Huom! Voi olla kimppakohtaisia eroja
asiakastyypin nimessä sekä käytännöissä. Tämän asiakastyypin lainoja ei
Lasketa mukaan tilastoihin.

![](/assets/files/docs/Asiakkaat/eitilastoituvat.png)

## 1.5. Asiakkaan tietojen muokkaaminen

<img src="/assets/files/docs/Asiakkaat/Muokkaanappi1.png" alt="" style="width:90.0%" />

Asiakastietojen yläreunassa olevilla painikkeilla pääset 
- muokkaamaan asiakastietoja
- lisäämään asiakkaalle huollettavan
- vaihtamaan salasanan
- kopioimaan asiakkaan tiedot
- tulostamaan asiakkaan haluamia kuitteja asiakaspalvelutilanteessa mm. Tänään lainatut-kuitin
- tekemään asiakkaalle tiedonhaussa varauksen siten, että asiakastieto säilyy muistissa
- lisäämään asiakastietoihin viestin



Harvemmin tarvittavia muokkaustoimintoja löytyy Muita toimintoja-alasvetovalikosta, joista tarkemmin 
kohdassa [1.5.7 Muita toimintoja -alasvetovalikko](https://koha-suomi.fi/dokumentaatio/asiakkaat/#157-muita-toimintoja--alasvetovalikko)

### 1.5.1. Lisää huollettava

Tämän napin kautta pääset tallentamaan asiakkaalle huollettavan. _Lisää huollettava_-painike avaa alasvetovalikon kimpan asiakastyypeistä, joilla tulee olla takaaja. Valittuasi sopivan asiakastyypin pääset lisäämään asiakastiedot huollettavalle. Takaaja-tieto täydentyy automaattisesti. Valitse Suhde-alasvetovalikosta oikea vaihtoehto.

![](/assets/files/docs/Asiakkaat/Lisaahuollettava.png)

### 1.5.2. Salasanan vaihtaminen

Asiakkaan salasanan pääsee muokkaamaan _Vaihda salasana_-painikkeen kautta. 

Asiakkaan salasanaa ei voi nähdä. Jos asiakas unohtaa salasanansa, hänelle tallennetaan uusi salasana.

<img src="/assets/files/docs/Asiakkaat/salasana.png" alt="" style="width:90.0%" />

\- Koha ei voi näyttää entistä salasanaa. Jätä salasanakenttä tyhjäksi tai valitse _Peruuta_,
jos et halua vaihtaa salasanaa.

\- Jos haluat automaattisesti luodun salasanan, klikkaa _Valitse tästä
luodaksesi satunnaisesti luodun salasanaehdotuksen. Salasanat näytetään
tekstinä._

Muista tallentaa.

### 1.5.3. Asiakkaan tietojen kopioiminen

Joissakin tilanteissa on tarpeen käyttää asiakastietojen kopioimista, jos
esim. samaan perheeseen tehdään useita kortteja. Kohassa on
toiminto, jolla voidaan kopioida henkilötiedot, jotka toistuvat eri
tietueissa.

Avaa sen asiakkaan tiedot, jonka haluat kopioida ja klikkaa
_Kopioi_-nappia tietueen yläreunassa.

Tarkista, että kaikki tiedot ovat oikein ja täydennä puuttuvat tiedot.

Tallennuksen jälkeen siirryt automaattisesti uuden asiakkaan tietoihin.

### 1.5.4. Tulosta

Tästä alasvetovalikosta voit valita ja tulostaa asiakkaan haluaman kuitin. Huom. kuiteissa voi olla kimppakohtaisia eroja.

![](/assets/files/docs/Asiakkaat/Tulosta.png)

Kuittien tulostamisesta tarkemmin Kohan ohje suomeksi -ohjeen
kohdassa [2.1.1. Kuittien tulostaminen](https://koha-suomi.fi/dokumentaatio/lainaus/#211-kuittien-tulostaminen)

### 1.5.5. Hae ja varaa

_Hae ja varaa_-näppäin siirtää suoraan Tarkkaan hakuun tekemään tiedonhaun. Pääset tekemään varauksen asiakkaalle suoraan hakutuloslistalla tai tietueen tiedoissa. 

![](/assets/files/docs/Asiakkaat/Haejavaraa1.png)

Hakutuloslistalla voit tarvittaessa myös poistaa muistista asiakkaan tiedot valitsemalla _Unohda [asiakkaan tiedot]_. 
Tietuetiedoissa poistotoimintoa ei ole.

![](/assets/files/docs/Asiakkaat/Haejavaraa2.png)

Varaamisesta tarkemmin Kohan ohje suomeksi -ohjeen
kohdassa [4.1.2 Varauksen teko asiakastietojen kautta](https://koha-suomi.fi/dokumentaatio/varaukset/#412-varauksen-teko-asiakastietojen-kautta)

### 1.5.6. Lisää viesti

Tällä toiminnolla lisätään asiakastietoihin viestejä. Voit valita esimääritellyistä viesteistä tarvitsemasi pohjan ja muokata sitä tarvittaessa tai kirjoittaa tyhjään kenttään tarvittavan tekstin.
Voit lisätä ns. Sisäisen viestin tai Asiakasliittymäviestin.

Sisäinen viesti näkyy vain virkailijaliittymässä.
![](/assets/files/docs/Asiakkaat/Jataviesti1.png)

Asiakasliittymäviesti näkyy asiakkaalle verkkokirjastossa.
![](/assets/files/docs/Asiakkaat/Jataviesti2.png)

Sekä sisäiset viestit että asiakasliittymäviestit näkyvät asiakkaan Lainaus- ja Tiedot-sivuilla. Ne voi poistaa klikkaamalla roskakorikuvaketta.

<img src="/assets/files/docs/Asiakkaat/Jataviesti3.png" alt="" style="width:90.0%" />

**Viestiin tallentuu automaattisesti päivämäärä, kirjasto sekä viestin tallentaja, joten niitä ei tarvitse manuaalisesti lisätä viestiin.**

### 1.5.7. Muita toimintoja -alasvetovalikko

![](/assets/files/docs/Asiakkaat/Muitatoimintoja1.png)

Muita toimintoja -napin takaa löytyy toiminnot, joilla pääsee uusimaan tilin, lähettämään asiakkaalle tervetuloa-sähköpostin, poistamaan asiakkaan tunnuksen sekä päivittämään lapsiasiakkaan aikuiseksi.

#### 1.5.7.1. Asiakaan käyttöoikeuden jatkaminen

Asiakastilin vanhennuttua asiakas ei pääse käyttämään korttiaan. Tilin uusimiselle on useita linkkejä ja paikkoja. 

Yläpalkin _Muokkaa_ ja _Muita toimintoja_ valikoista pääsee joka asiakastieto-sivulla päivittämään asiakkaan käyttöoikeuden.


Lainausnäytöllä vanhentumispäivämäärän perässä olevista linkeistä _Uusinta_ ja _Muokkaa tietoja_ voi jatkaa asiakkaan käyttöoikeutta. 

![](/assets/files/docs/Asiakkaat/Tilinuusiminen2.png)


Asiakkaan tiedot -sivulla tilin voi uusia Huomio- ja Kirjastotiedot -kohdissa _Uusinta- tai Muokkaa tietoja_-linkkien kautta.

![](/assets/files/docs/Asiakkaat/Tilinuusiminen1.png)

![](/assets/files/docs/Asiakkaat/Tilinuusiminen3.png)


Asiakkaalle tallentuu tilin vanhentumispäivämäärä asiakastyypille määritellyn voimassaoloajan mukaan.

Järjestelmä ilmoittaa myös lähestyvästä vanhentumispäivästä. 
![](/assets/files/docs/Asiakkaat/Tilinuusiminen4.png)


Huom. Käyttöoikeuden voi päivittää tarvittaessa aiemminkin kuin vasta sen mennessä umpeen.

### 1.5.7.2. Poista

Tällä toiminnolla poistetaan asiakas rekisteristä.

Koha varmistaa, että haluatko varmasti poistaa asiakkaan. Kun klikkaat _Kyllä, poista_, niin asiakastili lähtee heti pois asiakasrekisteristä. _Ei, älä poista_ -napin klikkaus peruu toimenpiteen.

![](/assets/files/docs/Asiakkaat/Poista1.png)

Koha ilmoittaa selkeästi miksi asiakasta ei voi poistaa rekisteristä.

![](/assets/files/docs/Asiakkaat/Poista2.png)

![](/assets/files/docs/Asiakkaat/Poista3.png)

![](/assets/files/docs/Asiakkaat/Poista4.png)

### 1.5.7.3. Päivitä lapsi aikuiseksi

Tätä toimintoa ei käytetä sillä asiakastyypit päivittyvät järjestelmässä automaattisesti.

### 1.5.8. Lapsiasiakkaan takaajan vaihtaminen

Takaajatiedot pääsee muokkaamaan _Muokkaa_-painikkeen takaa. Kohdassa _Asiakastakaaja_ voit sekä poistaa että lisätä takaajan. 

Poistaminen tapahtuu ruksaamalla poistettava takaaja ja sen jälkeen klikkaa _Tallenna_. 

![](/assets/files/docs/Asiakkaat/Poistatakaaja.png)

Lisääminen tapahtuu _Lisää takaaja_ -painikkeella. Hae lisättävän huoltajan tiedot avautuvassa ikkunassa.

![](/assets/files/docs/Asiakkaat/Valitsetakaaja.png)

Valitse hakutuloksesta huoltaja ja klikkaa _Valitse_ (_Select_).

Valitse takaajan suhde ja tallenna.

### 1.5.9. Asiakkaan kuva

Asiakkaan kuva voidaan lisätä asiakastietoihin, jos järjestelmäasetuksissa se on sallittu. Kaikissa kirjastoissa tätä ominaisuutta ei ole otettu käyttöön.

Kuvan voi lisätä sillä sivulla, jossa näkyy kuvalaatikko kysymysmerkillä. Klikkaa kuvan kohdalla _Lisää_-painiketta.

![](/assets/files/docs/Asiakkaat/Asiakaskuva1.png)

Jos tarkoituksena on ottaa asiakkaasta kuva, niin valitse _Salli_, mutta jos tarkoituksena on ladata valmis kuva, niin valitse _Estä_.

![](/assets/files/docs/Asiakkaat/Asiakaskuva2.png)

Tässä Asiakaskuva-laatikossa ei ole sallittu Kohankäyttää kameraa.
![](/assets/files/docs/Asiakkaat/Asiakaskuva3.png)


### 1.5.10. Rajoitukset

Joissakin tilanteissa Koha estää lainaamasta aineistoa asiakkaalle, jos estot ovat 
laitettu päälle järjestelmäasetuksissa. Näissä tilanteissa näytölle tulee huomautus lainaamisen eston syystä.

#### 1.5.10.1. Käyttäjätilin huomautukset

![](/assets/files/docs/Asiakkaat/Kayttajatilinhuomautukset.png)

Nämä molemmat vaihtoehdot ovat eräänlaisia rajoituksia eli ne estävät asiakasta käyttämästä asiakastunnustaan.

##### 1.5.10.1.1 Väärä osoite

Jos haluat henkilökunnan tarkistavan asiakkaan osoitteen esim. ennen
lainaamista, valitse _Kyllä_ Tarkista osoite -kohdassa. Lainaus- ja tiedot-näytöillä 
näkyy ilmoitus _Osoite: Tarkista osoite_.

![](/assets/files/docs/Asiakkaat/vaaraosoite.png)

Ilmoituksen voit poistaa, kun olet korjannut asiakkaan osoitetiedot. Huomautus poistuu, kun 
asiakastietojen muokkausnäytöllä kohdassa _Käyttäjätilin huomautukset_ vaihdat Tarkista osoite -kohtaan vaihtoehdon “Ei” ja tallennat asiakastiedot.

##### 1.5.10.1.2 Kortti kadonnut

Jos asiakas ilmoittaa kadottaneensa kirjastokorttinsa, voit merkitä sen
kadonneeksi klikkaamalla _Kyllä_ Kortti kadonnut -kohdassa. Lainaus- ja tiedot-näytöillä näkyy 
ilmoitus _Kadonnut: Asiakkaan kortti on merkitty kadonneeksi_.

![](/assets/files/docs/Asiakkaat/Kadonnutkortti.png)

Ilmoitus poistuu, kun asiakastietojen muokkausnäytöllä kohdassa _Käyttäjätilin huomautukset_ vaihdat Kortti kadonnut -kohtaan vaihtoehdon “Ei” ja tallennat asiakastiedot.

##### 1.5.10.1.3 Tili lukittu

Asiakkaan tili lukitaan, jos hän yrittää kirjautua liian monta kertaa väärällä PIN-koodilla. 
Yritysten määrä asetetaan järjestelmäasetuksissa ja se voi vaihdella kimpoittain. 
Kun tili on lukittu, tulee asiakkaan tietoihin vasemman reunan "tietoboksiin" ilmoitus _Tili on lukittu_.

Lukitus poistuu automaattisesti, kun kirjautumisyritysten määrä nollautuu. Sen saa nollattua 
vaihtamalla PIN-koodin _Vaihda salasana_ -toiminnolla tai käyttämällä verkkokirjastossa salasanan palautustoimintoa.

![](/assets/files/docs/Asiakkaat/tililukittu.png)

##### 1.5.10.1.4 Rajoite liiallisista kirjautumisyrityksistä

Koha-Suomessa tehtiin toiminto, jossa asiakkaalle lisätään automaattisesti rajoite, jos hänen tilillään on yli 50 epäonnistunutta kirjautumisyritystä. Tässä tilanteessa oletettavaa on, että asiakkaan kortti on tai korttinumero on mahdollisesti väärissä käsissä ja asiakkaan henkilöllisyys kannattaa tarkistaa sekä vaihtaa asiakkaan kirjastokortti uuteen.

Rajoite poistuu automaattisesti, kun kirjautumisyritysten määrä nollautuu. Sen saa nollattua vaihtamalla PIN-koodin _Vaihda salasana_ -toiminnolla tai käyttämällä verkkokirjastossa salasanan palautustoimintoa. 

![](/assets/files/docs/Asiakkaat/liikaayrityksia.png)

Rajoitteen voi poistaa myös manuaalisesti kortinvaihtotilanteessa.

<img src="/assets/files/docs/Asiakkaat/liikaayrityksia2.png" alt="" style="width:90.0%" />

#### 1.5.10.2. Asiakkaan rajoitukset

Voit tallentaa asiakkaalle rajoituksen, joka aiheuttaa lainauskiellon, esim. kun lasku on lähetetty. 
Rajoite voidaan lisätä asiakkaalle myös automaattisesti, kun lasku luodaan. Rajoitus voi olla voimassa toistaiseksi tai määräajan.

Asiakkaalle lisätään vapaamuotoinen rajoite joko asiakkaan tiedoissa _Muokkaa_-painikkeen takaa tai Lainaus- ja tiedot-näytöillä välilehdellä _Rajoitukset_.

![](/assets/files/docs/Asiakkaat/Lisaarajoitus1.png)

![](/assets/files/docs/Asiakkaat/Lisaarajoitus2.png)

Klikkaa kohdasta _Lisää rajoitus_, kirjoita selityskenttään rajoituksen syy. Tallenna _Lisää rajoitus_-painikkeella. 

![](/assets/files/docs/Asiakkaat/Lisaarajoitus3.png)

Muokkaa-painikkeen kautta lisätty rajoite tallennetaan _Tallenna_ -painikkeella. 

![](/assets/files/docs/Asiakkaat/Lisaarajoitus4.png)

Rajoitteelle voi tarvittaessa määrittää automaattisen päättymisajan Vanhenee-kenttään. Vain myöhäisin päättymispäivämäärä näkyy 
lainausnäytöllä, kun rajoitteita on enemmän kuin yksi ja niille on asetettu päättymispäivämäärä.  

![](/assets/files/docs/Asiakkaat/Lisaarajoitus6.png)

![](/assets/files/docs/Asiakkaat/Lisaarajoitus5.png)

Jos et määritä päättymisaikaa, on rajoite voimassa toistaiseksi eikä rajoitteille näy lainausnäytöllä päättymispäivää.
![](/assets/files/docs/Asiakkaat/Lisaarajoitus7.png)

Rajoitteet voi ohittaa klikkaamalla _Ohita rajoitus tilapäisesti_. Tässä toimitaan kirjaston/kimpan ohjeiden mukaan.

![](/assets/files/docs/Asiakkaat/Rajoitukset6.png)

Kimppakohtaisia määritteitä/rajoitteita voi olla käytössä myös _Muut määreet ja tunnukset_-kohdassa.
![](/assets/files/docs/Asiakkaat/Lisaarajoitus8.png)

##### 1.5.10.2.1 Asiakkaan rajoitusten poistaminen

Rajoitteen voit poistaa asiakkaalta Poista-toiminnolla.

## 1.6. Asiakkaiden kommenttien ja muutospyyntöjen käsittely

Jos järjestelmäasetuksissa annetaan asiakkaille oikeus muuttaa tietojaan
verkkokirjaston kautta, hyväksytään muutokset virkailijaliittymässä ennen muutosten voimaantuloa. 
Jos järjestelmässä on hyväksymistä odottavia muutoksia, niistä näkyy Kohan etusivulla
linkki _Tietojensa muokkaamista haluavat asiakkaat_. 

<img src="/assets/files/docs/Asiakkaat/Etusivunlinkki.png" alt="" style="width:90.0%" />

Kun klikkaat linkkiä, saat listan kaikista odottavista muutospyynnöistä ja klikkaamalla asiakkaan
nimen kohdalta saat hänen tekemänsä muutokset näkyviin. Voit hyväksyä muutokset _Hyväksy_, kieltää _Kiellä_ ne tai jättää
ne kokonaan huomioimatta _Älä huomioi_.

![](/assets/files/docs/Asiakkaat/tietojenmuutos.png)

_Asiakkaan tiedot_ -linkistä pääset asiakkaan tietoihin katsomaan onko asiakkaalla
esim. rajoitteita, jotka päivityksen yhteydessä on syytä ottaa pois.

Asiakkaan tiedoissa käsittelemätön muutospyyntö näkyy lainaussivulla kohdassa Huomio: _Odottavat muutokset: Tarkista odottavat muutospyynnöt_

![](/assets/files/docs/Asiakkaat/Odottavatmuutokset.png)

## 1.7. Asiakkaan tiedot

Kun katsot asiakkaan tietuetta, on vasemmassa reunassa valittavissa
useita eri välilehtiä, joilla on erilaisia tietoja.

![](/assets/files/docs/Asiakkaat/vasen.png)

### 1.7.1. Lainaus
Lainaus-välilehden toiminnot on kuvattu tarkemmin Kohan ohje suomeksi -ohjeen 
kohdassa [2. Lainaaminen](https://koha-suomi.fi/dokumentaatio/lainaus/)

### 1.7.2. Tiedot

Kaikki asiakkaan (henkilö)tiedot näkyvät Tiedot-välilehdellä mm. yhteystiedot, viestiasetukset, sotu-avain, kirjastotiedot sekä mahdolliset huomautukset ja tiedot rajoituksista.
Huom. Näkymässä voi olla kimppakohtaisia eroja.

Jos asiakas on lapsi, hänen takaajansa nimet ovat linkkinä kohdassa Takaajat.

![](/assets/files/docs/Asiakkaat/Huoltajat.png)

Takaajan tietueessa näkyy kaikkien huollettavien tiedot kohdassa Huollettavat.

![](/assets/files/docs/Asiakkaat/Taattavat.png)

### 1.7.3. Maksut

Maksut -välilehden toiminnot on kuvattu tarkemmin Kohan ohje suomeksi -ohjeen 
kohdassa [3. Maksut](https://koha-suomi.fi/dokumentaatio/maksut/) 

### 1.7.4. Kiertolistat

Kiertolistat tarkoittaa lehtikiertolistaa eli jos kirjaston työntekijä
on jonkun lehden sisäisellä kiertolistalla.

![](/assets/files/docs/Asiakkaat/lehtikierto2.png)

Toiminnon käytössä voi olla kimppakohtaisia eroja.

### 1.7.5. Muutosloki

_Huom. Tämä välilehti ei näy kaikille käyttäjille._

Muutoslokille kertyy tietoa, kun asiakkaan tietoja on katsottu tai
muokattu ja jos asiakastieto on tullut asiakashaussa hakutuloslistalle.
Täällä näkyvät myös lainaus- ja palautustapahtumat, jos niin on
asetuksissa määritetty.

<img src="/assets/files/docs/Asiakkaat/lokitiedot.png" alt="" style="width:90.0%" />

\- _Pvm-sarake_ kertoo tarkan ajan (päivämäärä ja kellonaika), jolloin
asiakkaan tiedoissa on tapahtunut jotain

\- _Virkailija-sarake_ näyttää sen työntekijän tunnuksen, joka tietoja
on katsellut tai tehnyt muutokset/haun (virkailijan nimi ja
borrowernumber)

\- _Osio-sarake_ näyttää missä Kohan osiossa katselu/muutos on
tapahtunut

\- _Toiminto-sarakkeesta_ näkee mitä asiakkaan tiedoissa on tehty

\- _ID-tunnus-sarakkeessa_ näkyy, kenen asiakkaan tietoja on muutettu
(asiakkaan nimi ja borrowernumber)

\- _Tiedot-sarake_ kertoo tarkemmin mitä tapahtuma koskee esim. mikä
nide on lainattu tai asiakkaan kirjautuminen automaatille

\- _Käyttöliittymä-sarakkeesta_ näkee onko loki kertynyt esim.
  virkailijaliittymästä, Kohan verkkokirjastosta tai Finnasta
  tai palautus-/lainausautomaatilta. 
  
  Huom. Muutoslokiin pääsee myös Työkalujen kautta. 
  Se on ohjeistettu Kohan ohje suomeksi -ohjeen 
  kohdassa [12.14 Lokien katselu](https://koha-suomi.fi/dokumentaatio/tyokalut/#1214-lokien-katselu)

### 1.7.6. Ilmoitukset

Tällä näytöllä näkyy asiakkaalle lähteneet tai lähtemässä olevat
ilmoitukset. Ilmoittamistapa valitaan asiakastiedoissa asiakkaan
viestiasetuksissa.

<img src="/assets/files/docs/Asiakkaat/Lahetetytilmoitukset.png" alt="" style="width:90.0%" />

\- _Ilmoitus_-sarakkeessa näkyy viestin otsikko. Klikkaamalla viestin
nimeä pääset näkemään koko viestin.

\- _Tyyppi_-sarakkeessa näkyy, missä muodossa viesti on lähetetty.
Koha-Suomessa käytössä: printti, sms (tekstiviesti), sposti, suomi.fi, finvoice

\- _Tila_-sarakkeesta näkee viestin lähetyksen tilan

_lähetetty_: viesti on lähetetty eteenpäin järjestelmästä varsinaiseen
lähettävään järjestelmään

_odottaa_: viestiä ei ole vielä lähetetty eteenpäin lähettävään
järjestelmään

_epäonnistunut_: viestin lähetys on epäonnistunut. Osa
lähettävistä järjestelmistä (esim. tekstiviestioperaattorit) palauttaa
Kohaan epäonnistumisen syyn, jolloin se näkyy
Toimitushuomautus-sarakkeessa.

\- _Aika_-sarakkeessa näkyy viestin lähetysaika. Tieto päivittyy aina,
kun viestiä yritetään lähettää uudelleen eli kyse ei ole viestin
luontiajankohdasta.

\- _Toimitushuomautus_-sarakkeeseen tulee näkyviin viestin lähetyksen
  epäonnistumisen syy, jos Koha saa siitä tiedon. Lähinnä
  tekstiviestioperaattorit palauttavat virheen syyn.
  
  _Message is duplicate_ tarkoittaa, että Koha on hylännyt viestin, koska
  se on täsmälleen samanlainen kuin hiljattain lähetetty toinen viesti.
  Näitä näkyy erityisesti tekstiviestien yhteydessä.
  
  _Message validity period has expired_ tarkoittaa, että viestiä on
  yritetty lähettää maksimimäärä kertoja.
  
  _Unknown error_ tarkoittaa, että viestin epäonnistumisen syytä ei
  tiedetä tai pystytä tarkentamaan. Syy voi olla esim. asiakkaan
  puhelinnumero voi olla väärä tai hänen puhelimensa ei ota vastaan
  tekstiviestejä, tai operaattorin päässä on häiriö.
  
  _Recipient is temporarily unreachable_ tarkoittaa, että vastaanottajaan
  ei ole saatu yhteyttä.
  
  _Unallowed recipient phone number_
  tarkoittaa, että asiakkaan puhelinnumerossa on jotain vikaa tai se on
  väärässä muodossa (esim. lankapuhelin).

### 1.7.7. Tilastot

Tilastot-osiossa näkyy asiakkaan lainatilasto edelliseltä ja kuluvalta
päivältä. Lainat on jaoteltuna aineistolajeittain ja hyllypaikoittain.
Taulukossa näkyvät myös kuluvan päivän palautukset ja lainat.

<img src="/assets/files/docs/Asiakkaat/Asiakkaantilastot.png" alt="" style="width:90.0%" />

### 1.7.8. Hankintaehdotukset

_Toiminto ei ole käytössä_

### 1.7.9. Lainat

Asiakkaan tietojen alapuolella on taulukkonäkymässä asiakkaan lainat,
maksut, varaukset ja rajoitukset. Lainoihin pääsee klikkaamalla
_Lainassa_-painiketta. Maksut välilehteä ei näy, jos asiakkaalla ei ole maksuja.

![](/assets/files/docs/Asiakkaat/lainat.png)

Lainoista on tarkemmin Kohan ohje suomeksi -ohjeen
kohdassa [2.4. Asiakkaan lainat](https://koha-suomi.fi/dokumentaatio/lainaus/#24-asiakkaan-lainat)

### 7.7.9.1 Perheen lainat

_Huom. Perheen lainat-välilehden näkymisessä on kimppakohtaisia eroja_

![](/assets/files/docs/Asiakkaat/perheenlainat.png)

 _Perheen lainat_-välilehdellä takaajalle näkyvät huollettavien lainat ja huollettaville
 siellä näkyvät niiden henkilöiden lainat, joilla on sama takaaja.
