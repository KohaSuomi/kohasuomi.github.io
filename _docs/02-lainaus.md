---
title: 'Kohan ohje suomeksi'
permalink: /dokumentaatio/lainaus/
redirect_from:
  - /theme-setup/
toc: true
---

# 2. Lainaus

Käytä lainaustoiminnoissa Firefox-selainta, jolla voit määrittää asiakaskuitit 
tulostumaan automaattisesti (ohje kohdassa 9. Kuittitulostuksen
asetukset). Koha-Suomi suosittelee Firefox ESR-version käyttöä.

Lainauksen toimintoihin pääset useilla eri tavoilla. Virkailijaliittymän
etusivulla on pikakuvakkeita, joista pääset ohjelman eri toimintoihin,
mm. lainaus- ja palautustoimintoihin. Kaikista lainauksenvalvonnan
toiminnoista on listaus **Lainaus ja palautus** -sivulla, jonne pääset
jokaisen sivun vasemmasta yläreunasta olevasta linkistä.

![](/assets/files/docs/Lainaus/lainaus.png)

Ohjelman pikanäppäimet:

- tiedonhaku Alt+Q
- lainaus Alt+U
- palautus Alt+R
- lainakuitti Alt+P

## 2.1. Lainaaminen

Aloita lainaaminen lukemalla asiakkaan kirjastokortin viivakoodi
**Lainaus**-kenttään tai hakemalla asiakkaan tiedot hänen nimelläään.
Toimi kirjastosi käytäntöjen mukaan.

![](/assets/files/docs/Lainaus/lainaus_asiakastunnus.png)

Lue lainattavan niteen viivakoodi nidekenttään.

![](/assets/files/docs/Lainaus/lainaaminen.PNG)

- Viimeksi lainatun niteen tiedot näkyvät **Lainattu**-kentässä.
- Jos klikkaat täpän kohtaan **Näytä aina lainat reaaliaikaisesti**, lainaustilanteessa kaikki asiakkaan lainat näkyvät näytöllä. Tämä valinta voi olla piilotettuna kimpassasi.

**Tärkeää:**

- Monet viivakoodinlukijat lähettävät automaattisesti rivinvaihdon,
  joten **Lainaus**-painiketta ei tarvitse välttämättä klikata.
- Jos niteen viivakoodia ei löydy, saat ehdotuksen pikaluettelointiin
  niteen lisäämiseksi. Toiminto ei ole välttämättä kaikilla kimpoilla
  käytössä.

**Lainausasetukset**

![](/assets/files/docs/Lainaus/lainausasetukset.PNG)

- Asetuksissa on mahdollista määritellä lainattavalle aineistolle muu
  eräpäivä kuin oletuseräpäivä. Tämä vaihtoehto tulee näkyviin vain,
  jos järjestelmäasetuksissa on määritelty, että virkailijalla on
  oikeus muuttaa eräpäivää lainatessa.
- Jos kimpalla on käytössä **automaattinen uusinta**, ohjelma uusii
  lainatut teokset automaattisesti lainasääntöjen mukaisesti.
- Toiminnolla **Älä lyhennä laina-aikaa varausten määrän pohjalta**
  voi ohittaa järjestelmäasetuksen, jolla lyhennetään laina-aikaa, jos
  teoksen varausmäärä menee asetuksissa määritellyn rajan yli. Valinta tulee näkyviin vain kimpoissa, jossa tämä järjestelmäasetus on päällä.

### 2.1.1 Kuittien tulostaminen

Kun olet lainannut kaikki asiakkaan lainat, voit tulostaa lainauskuitin
eri tavoilla. Toimi kimppasi käytäntöjen mukaan.

Kuitin voit tulostaa:
- painamalla näppäimistöltä **Enter**. (Huom.
  järjestelmäasetuksista riippuen, Enter voi myös tyhjentää
  asiakastiedot)
- painamalla pikanäppäimiä **Alt+P**
- asiakastietojen yläpuolelta olevasta **Tulosta**-valikosta valitsemalla **Tänään lainatut**
  
**Huom!** Lainauskentän oikeassa yläkulmassa näkyvästä tulostimen kuvasta tulostuvat kaikki asiakkaan lainat kuitille.
![](/assets/files/docs/Lainaus/tulostin.PNG)

**Tulosta** -valikosta voit tulostaa myös:

![](/assets/files/docs/Lainaus/tulostakuitti.PNG)

- **Asiakastietojen yhteenveto:** A4-tuloste asiakastiedoista,
  lainoista, varauksista ja maksujen tilitystiedoista. Tätä ei
  suositella tulostettavan.
- **Tulosta kuitti:** tulostaa kaikki asiakkaan lainat kuitille.
  Tulosteessa erotellaan myöhässä olevat lainat oman otsikon alle.
- **Tänään lainatut:** tulostaa tänään lainattujen ja uusittujen
  lainojen tiedot kuitille.
- **Tulosta erääntyneet**: tulostaa erääntyneet lainat, jos asiakkaalla on myöhässä olevia lainoja.
- **Tulosta tänään palautetut:** antaa asiakkaan palautuksista kuitin.

Kimpan pääkäyttäjät voivat muokata kuiteille tulostuvia tietoja.

### 2.1.2 Asiakastietojen tyhjennys näytöltä

Kun lopetat lainaamisen, näytöltä pitää tyhjeentää asiakkaan tiedot.
Näytön voit tyhjentää kahdella tavalla:

- painamalla **Enter**. (Huom! asetuksista riippuen, Enter voi myös
  tulostaa asiakkaan lainakuitin).
- klikkaamalla **X** lainauskentän oikeasta yläkulmasta.

![](/assets/files/docs/Lainaus/tyhjennys.PNG)

---

## 2.2 Lainaamisen estot

Joissakin tilanteissa Koha estää lainaamasta aineistoa asiakkaalle, jos
estot ovat laitettu päälle järjestelmäasetuksissa. Näissä tilanteissa
näytölle tulee huomautus lainaamisen eston syystä.

### 2.2.1 Asiakkaalla on liikaa maksuja

![](/assets/files/docs/Lainaus/liikaamaksuja.png)  
Hox! Uusintatilanteessa ohjelma ei ilmoita, jos sallittujen maksujen
raja on ylittynyt.

### 2.2.2 Asiakkaalla on rajoitus (lainauskielto)

Asiakkaille voidaan tallentaa rajoitus, joka aiheuttaa lainaukiellon, esim. kun lasku on lähetetty.
Rajoitus voi olla voimassa toistaiseksi tai määräajan. 

Rajoituksen voit tallentaa asiakastietojen muokkausnäytöllä kohdassa **Asiakkaan
rajoitukset** tai välilehdellä **Rajoitukset**. Laita **Selitys**-kenttään rajoituksen syy ja jos rajoitus halutaan
olemaan voimassa vain tietyn ajan, laita **Vanhenee**-kohtaan viimeinen
voimassaolopäivä.

  ![](/assets/files/docs/Lainaus/rajoitteenlisäys.PNG)
  
  Tallenna rajoitus lopuksi **Lisää rajoitus** -painikkeesta.  
  
  Asiakkaan Tiedot ja Lainaus -näytöillä rajoitus näkyy näin:
  
  ![](/assets/files/docs/Lainaus/rajoite1.PNG)

### 2.2.3 Asiakkaan osoitetiedot ovat väärät

Jos asiakkan tiedoissa on päällä asetus, että osoite on tarkistettava,
lainaus estyy.  
![](/assets/files/docs/Lainaus/vaaraosoite1.png)

Lainaustilanteessa tulee huomautus:  
![](/assets/files/docs/Lainaus/tarkistaosoite.PNG)

Huomautuksen voit poistaa, kun olet korjannut asiakkaan osoitetiedot. Vaihda asiakastietojen muokkausnäytöllä täppä 
**Käyttäjätilin huomautukset** -osiossa  **Tarkista osoite** -kohtaan
“Ei” ja tallenna asiakastietojen muokkausnäyttö.

### 2.2.4 Asiakkaan kirjastokortti on kadonnut

Kun asiakas ilmoittaa kirjastokorttinsa kadonneen, tallenna **Kortti kadonnut** -tieto asiakastietojen muokkausnäytöllä osiossa **Käyttäjätilin huomautukset**.

![](/assets/files/docs/Lainaus/korttikadonnut1.PNG)

Lainaustilanteessa tulee huomautus:  
![](/assets/files/docs/Lainaus/korttikadonnut.PNG)

Kun asiakkaan kirjastokortti on kadonnut, toimi kimpassa sovittujen
käytäntöjen mukaan.  
Huomautuksen voit poistaa asiakastietojen muokkausnäytöllä vaihtamalla täppä
**Käyttäjätilin huomautukset** -osiossa **Kortti kadonnut** -kohtaan
“Ei”.

---

## 2.3 Lainauksen viestit ja huomautukset

### 2.3.1 Huomautus liitteistä

Jos lainaat niteen, joka sisältää useita osia ja tieto osista on
tallennettu niteen tietoihin kenttään 3 (Liitteiden määrä), saat
ponnahdusikkunan, jossa kerrotaan montako osaa nide sisältää.

![](/assets/files/docs/Lainaus/huomsisallosta.PNG)

Joskus lainaustilanteessa näytölle voi tulla keltaisessa laatikossa
oleva huomautus. Nämä huomautukset on käsiteltävä/huomioitava ennen
lainaamisen jatkamista.

### 2.3.2 Aineisto on varattu jollekin toiselle asiakkaalle. Varausta ei ole vielä otettu kiinni.

![](/assets/files/docs/Lainaus/lainhuom1.PNG)

### 2.3.3 Nide on varaushyllyssä varattuna toiselle asiakkaalle.

![](/assets/files/docs/Lainaus/lainhuom2.PNG)

- Jos esimerkiksi toinen perheenjäsen haluaa lainata varatun
  aineiston, valitse **Poista varaus** ja klikkaa **Kyllä, lainaa
  (Y)**. Varaus poistuu alkuperäiseltä varaajalta.
- Jos valitset vaihtoehdon **Peruuta odottava-tila** ja klikkaat **Kyllä, lainaa
  (Y)**, alkuperäisen varaajan noutoa odottanut varaus muuttuu takaisin voimassaolevaksi. 

### 2.3.4 Nide on jo lainassa tällä asiakkaalla.

![](/assets/files/docs/Lainaus/lainhuom3.PNG)

### 2.3.5 Aineisto on lainassa toisella asiakkaalla.

![](/assets/files/docs/Lainaus/lainhuom4.PNG)

### 2.3.6 Aineistoa ei lainata (niteen tila on “Ei lainattavissa”).

![](/assets/files/docs/Lainaus/lainhuom5.PNG)

- Lainauseston ohituksen salliminen määritellään järjestelmäasetuksissa.

### 2.3.7 Asiakkaalla on liian monta lainaa.

![](/assets/files/docs/Lainaus/lainhuom6.png)

- Lainauseston ohituksen salliminen määritellään järjestelmäasetuksissa.

### 2.3.8 Viivakoodia ei löytynyt.

![](/assets/files/docs/Lainaus/lainhuom7.png)

- Pikaluettelointi on mahdollista, jos se on sallittu
  järjestelmäasetuksissa.

### 2.3.9 Lainattava nide on merkitty kadonneeksi.

![](/assets/files/docs/Lainaus/lainhuom8.png)

- Järjestelmäasetuksissa voidaan määritellä, tuleeko kadonneeksi merkitystä niteestä huomautusta.

### 2.3.10 Lainattavalla niteellä on ikärajoitus, ja asiakas on liian nuori.

![](/assets/files/docs/Lainaus/lainhuom9.PNG)

- Ikärajoituksen ohituksen salliminen määritellään järjestelmäasetuksissa.

### 2.3.11 Lainattavalla niteellä on paljon varauksia, jonka takia lyhennetään laina-aikaa.

![](/assets/files/docs/Lainaus/lainhuom10.PNG)

- Laina-ajan lyhennys määritellään järjestelmäasetuksissa. Välttämättä se ei ole päällä kimppasi kirjastossa.

---

## 2.4 Asiakkaan lainat

**Lainassa**-painikkeesta saat näkyville asiakkaan kaikki lainat.  
![](/assets/files/docs/Lainaus/lainassa.PNG)

**Sarakkeen näkyvyys** -valikosta voit valita, mitä sarakkeita
Lainassa-välilehdellä näytetään.

![](/assets/files/docs/Lainaus/sarakkeen_nakyvyys.PNG)

**Vie**-valikosta voit tulostaa, kopioida tai viedä asiakkaan lainat Excel- tai CSV-tiedostoiksi.

![](/assets/files/docs/Lainaus/vie.PNG)

Valikosta **Lainojen määrä nidetyypeittäin** näet asiakkaan kaikki lainat yhteenlaskettuna nidetyypeittäin.

Ensimmäisenä näkyvät tänään lainatut lainat.
Myöhässä olevien lainojen eräpäivät näkyvät punaisella.

![](/assets/files/docs/Lainaus/lainat_naytto.PNG)

### 2.4.1 Lainojen uusinta

Lainassa olevien niteiden laina-ajan voit uusia sen mukaan, mitä järjestelmän
ylläpidon laina- ja käyttömaksusäännöissä on määritelty.

Lainat voi uusia asiakkaan tiedoissa Lainassa-välilehdellä tai Lainaus ja palautus -sivulla.

Huom! Jos asiakkaan sallittujen maksujen raja on ylittynyt, ohjelma ei huomauta siitä uusintatilanteessa.

#### 2.4.1.1 Lainojen uusinta asiakkaan tiedoissa olevalla Lainassa-välilehdellä.

![](/assets/files/docs/Lainaus/uusinta.png)

- Uusinta-sarakkeesta näet, kuinka monta kertaa kukin nide on uusittu. 
  Valitse uusittavat niteet ruksaamalla uusinnan valintaruutu uusittavan niteen kohdalla ja klikkaa näytön alareunasta painiketta **Uusi tai palauta
  valitut niteet** tai jos uusit kaikki lainat, klikkaa **Uusi
  kaikki** -painiketta.
  
- Uusinta-sarakkeen yläreunassa olevalla toiminnolla “valitse kaikki”
  voit valita uusittavaksi kaikki lainat, jotka on mahdollista uusia.
  Toiminto “ei valintaa” poistaa valinnat.
  
- Jos kimpassa on käytössä asetus, joka estää uusimisen samana päivänä
  uudestaan, tulee huomautus “Ei uusintaa ennen…”. Lainan voi uusia
  uudelleen kyseisen päivämäärän ja kellonajan jälkeen. Huomautus
  tulee, kun päivittää Lainassa-välilehden tai käy välillä toisella
  sivulla.  
  ![](/assets/files/docs/Lainaus/uusinta6.png)
  
  - Jos kimpassa on sallittu lainojen palauttaminen lainatnäytöllä ja Sarakkeen näkyvyys -valikosta on valittu Palautus-toiminto
  aktiiviseksi, voit palauttaa lainat valitsemalla palautettavat
  niteet **Palautus**-sarakkeesta ja klikkaamalla näytön alareunasta
  painiketta **Uusi tai palauta valitut niteet**.
  
- Jos kimpassa on käytössä **Ilmoittaa palauttaneensa** -toiminto, toiminto painikkeen **Palautusilmoitukset** saat näkyville myös Sarakkeen näkyvyys -valikosta.       Toimintoa voi käyttää tilanteissa, kun asiakas ilmoittaa, että hän on palauttanut lainan, joka näkyy vielä hänen lainoissaan. Ko. niteen kohdalle tallentuu      merkintä, että asiakas on palauttanut lainan. Tieto lainasta tallentuu myös Palautusilmoitukset-välilehdelle.  

![](/assets/files/docs/Lainaus/ilmoittaa_palauttaneensa.PNG)

Järjestelmäasetuksiin voidaan määritellä, kuinka monen "ilmoittaa palauttaneensa" -lainan jälkeen ohjelma huomauttaa määrästä virkailijalle.

#### 2.4.1.2 Uusinta Lainaus ja palautus -sivun Uusinta-linkistä.

- Huomio kirjastosi käyttösäännöt. Joissain kirjastoissa käyttösäännöt edellyttävät kirjastokorttia
  uusintatilanteessa eli tätä toimintoa ei saa silloin
  käyttää.

![](/assets/files/docs/Lainaus/uusinta1.PNG)

Uusi lainat lukemalla niteen viivakoodi uusintakentään.
Voit antaa uusittaville lainoille halutessasi eri eräpäivän, kuin nidetyypin oletuslaina-aika on.

![](/assets/files/docs/Lainaus/uusinta2.PNG)

Jos niteen uusiminen onnistuu, saat ilmoituksen.

![](/assets/files/docs/Lainaus/uusinta3.png)

Jos nide ei ole lainassa, saat ilmoituksen.

![](/assets/files/docs/Lainaus/uusinta5.PNG)

Jos viivakoodia ei löydy, saat ilmoituksen.

![](/assets/files/docs/Lainaus/uusinta4.PNG)

---

## 2.5 Asiakkaan varaukset

**Varaukset**-välilehdellä näet asiakkaan varaukset ja missä tilassa varaukset ovat. Välilehdellä
voit vaihtaa varauksen noutopaikan, poistaa varauksen, keskeyttää varauksen ja jatkaa keskeytetyn varauksen
käyttämällä varausten alapuolella olevia toimintopainikkeita, mikäli toiminnnot
ovat sallittu järjestelmäasetuksissa. 

![](/assets/files/docs/Lainaus/varaukset.PNG)

---

## 2.6 Asiakkaan rajoitukset, huomautukset ja viestit

### 2.6.1 Asiakkaan rajoitukset

Voit asettaa asiakkaalle rajoituksen, joka estää lainaamisen ja uusimisen. 

Rajoituksen voit lisätä asiakastietojen muokkausnäytöllä:

![](/assets/files/docs/Lainaus/rajoitus1.PNG)

tai Rajoitukset-välilehdellä:

![](/assets/files/docs/Lainaus/rajoitus2.PNG)

Rajoitus näkyy asiakkaan Lainaus- ja Tiedot-näytöillä sekä Rajoitukset-välilehdellä.
Rajoituksen voi ohittaa tilapäisesti, jos käyttäjän oikeudet sen sallivat.

![](/assets/files/docs/Lainaus/rajoitus3.PNG)

### 2.6.2 Huomautukset asiakastiedoissa

Voit tallentaa asiakastietojen muokkausnäytöllä asiakkaalle huomautuksia, jotka näkyvät asiakkaan Lainaus- ja Tiedot-näytöillä. 

![](/assets/files/docs/Lainaus/huomautukset1.PNG)

### 2.6.3 Viestit asiakastiedoissa

Voit lisätä asiakkaalle lyhyitä viestejä, jotka näkyvät asiakkaan Lainaus- ja Tiedot-näytöillä.
Viestin voit lisätä joko toimintapainikkeesta **Lisää viesti** tai linkistä **+Lisää uusi viesti**.

[![](/assets/files/docs/Lainaus/viesti1.PNG)

Kun valitset **Lisää uusi viesti**, pääset valitsemaan, näytetäänkö
viesti vain virkailijoille vai myös asiakkaalle verkkokirjastossa
(valikossa asiakkaan nimi).

[![](/assets/files/docs/Lainaus/lainausviesti2.PNG)

Voit valita viestin esimääritellyistä viesteistä tai kirjoittaa oman
viestin tyhjään kenttään. Kimpan pääkäyttäjät voivat lisätä esimääriteltyjä viestejä.

![](/assets/files/docs/Lainaus/lainausviesti3.PNG)

- HUOMIO! Viesti asiakkaalle näkyy myös virkailijoille.

### 2.6.2 Viestin näkyminen

Viesti näkyy asiakkaalle ja/tai virkailijalle lainausnäytön oikeassa
reunassa. Lihavoidut, punaiset viestit näkyvät vain virkailijoille,
kursiivilla näkyvät viestit sekä asiakkaalle että virkailijoille.

![](/assets/files/docs/Lainaus/lainausviesti4.png)

Asiakkaan huomautuksissa näkyvät myös maksut mikäli niitä on ja asiakkaan noutoa
odottavat varaukset.

### 2.6.3 Vanhentunut asiakastieto

Jos asiakastiedot vaativat määräaikaistarkistuksen (parametreissä
määritelty), näyttöön tulee ilmoitus:

![](/assets/files/docs/Lainaus/vanhentunut.png)

Tarkista asiakkaan yhteystiedot (osoite, puhelin numero,
sähköpostiosoite, viestiasetukset). Jos tiedot ovat ajantasalla, klikkaa
**Uusinta**. Jos tiedot täytyy päivittää, muokkaa ja päivitä tiedot ensin linkistä **Muokkaa tietoja**.

Käyttöoikeuden voi jatkaa myös valikosta **Muita toimintoja**,
valitsemalla **Asiakkaan käyttöoikeuden jatkaminen**.

![](/assets/files/docs/Lainaus/vanhentunut2.png)

---

## 2.7 Palauttaminen

Aineiston palauttamiseen pääset eri näyttöjen kautta.

![](/assets/files/docs/Lainaus/palautus.png)

Kaikista lainaustenvalvonnan toiminnoista on listaus **Lainaus ja
palautus** -sivulla, jonne pääset jokaisen sivun vasemmasta yläreunasta
olevasta linkistä.

### 2.7.1 Aineiston palauttaminen

Kun palautat aineistoa, lue niteen viivakoodi palautuskenttään.
Palautetun niteen tiedot tulevat näytölle.

![](/assets/files/docs/Lainaus/palautus1.png)

### 2.7.2 Palautuksen viestit

### 2.7.2.1 Toisen kirjaston aineiston palautus

Jos olet palauttamassa jonkun muun kirjaston aineistoa, saat viestin,
jossa ilmoitetaan mihin kirjastoon nide pitää kuljettaa.

![](/assets/files/docs/Lainaus/palautusviesti1.png)

- Tämän jälkeen niteen tilaksi muuttuu _Kuljetettavana_.  
  ![](/assets/files/docs/Lainaus/palautusviesti2.png)

<!-- -->

- Nide pitää palauttaa kotikirjastossaan, jotta sen tilaksi muuttuu
  Saatavana.

### 2.7.2.2 Useita osia sisältävän niteen palautus

Jos palautat niteen, joka sisältää useita osia ja tieto osista on
tallennettu niteen tietoihin kenttään 3 (Liitteiden määrä), saat
ponnahdusikkunan, jossa kerrotaan montako osaa nide sisältää.  
![](/assets/files/docs/Lainaus/huomsisallosta.png)

### 2.7.2.3 Varatun niteen palautus

Jos palautat niteen, josta on varaus, saat siitä ilmoituksen.  
![](/assets/files/docs/Lainaus/palautusviesti3.png)

- Valitsemalla toiminnon **Vahvista varaus**, nide menee
  Odottaa-tilaan.
- Toiminnolla **Tulosta kuitti ja vahvista**, ohjelma tulostaa
  varauksen Infokuitin ja muuttaa niteen Odottaa-tilaan.
- Toiminnolla **Älä huomioi**, niteen tilaksi jää saatavana ja varaus
  säilyy asiakkaalla voimassa olevana.

![](/assets/files/docs/Lainaus/palautusviesti4.png)

### 2.7.4.4 Varaus toisessa kirjastossa

Jos palautat niteen, josta on varaus jossain toisessa kirjastossa, saat
ilmoituksen ja tiedon, mihin kirjastoon nide pitää kuljettaa.

![](/assets/files/docs/Lainaus/palautusviesti5.png)

- Valitsemalla **Vahvista varaus ja kuljetus**, merkitset niteen
  kuljetettavaksi siihen kirjastoon, missä on varatun aineiston
  noutopaikka.
- Toiminnolla **Tulosta kuitti, kuljeta ja vahvista**, tulostaa
  ohjelma varauksen kuljetuskuitin ja merkitsee niteen kuljetettavaksi
  siihen kirjastoon, missä on varatun aineiston noutopaikka.
- Toiminnolla **Älä huomioi**, niteen tilaksi jää saatavana ja varaus
  säilyy asiakkaalla voimassa olevana.

![](/assets/files/docs/Lainaus/palautusviesti6.png)

### 2.7.2.5 Asiakkaan maksut palautusnäytöllä

Jos järjestelmä on asetettu näyttämään maksut palautuksen yhteydessä,
saat keltapohjaisen viestin asiakkaan maksuista.  
![](/assets/files/docs/Lainaus/palautusviesti7.png)

### 2.7.2.6 Kadonneeksi merkityn niteen palauttaminen

Jos palautat kadonneeksi merkityn niteen, saat seuraavan ilmoituksen:  
![](/assets/files/docs/Lainaus/palautusviesti8.png)

---

## 2.8 Varaukset

Asiakas voi varata aineistoa Kohassa. Lainaus- ja käyttömaksusäännöissä
ja asiakastyyppien ylläpidossa on määritelty säännöt, minkä mukaan
varauksia voi tehdä.

### 2.8.1 Varauksen teko tiedonhaun kautta

Varauksen voi tehdä usealla tavalla. Yksinkertaisin tapa on tehdä varaus
nimeketietojen näytön yläreunasta _Varaa_-napista.

![](/assets/files/docs/Lainaus/Varaus_1.PNG)

Varauksen voi tehdä myös hakutuloslistauksessa:

- näytön yläreunassa _Varaa_-napista, kun on valinnut näytöltä
  varattavat nimekkeet
- nimeketietojen jäljessä olevasta _Varauksia_-linkistä.

![](/assets/files/docs/Lainaus/Varaus_2.PNG)

Kun teet varauksen, täytyy asiakkaan tiedot hakea näytölle joko kortin
viivakoodilla tai asiakkaan nimellä hakemalla. Huom! Noudata kirjastosi
sovittuja käytäntöjä.

![](/assets/files/docs/Lainaus/varaus3.PNG)

### 2.8.2 Varauksen teko asiakastietojen kautta

Voit tehdä varauksen myös asiakastiedoista päin. Klikkaa _Hae ja varaa_
-nappia…

![](/assets/files/docs/Lainaus/Varaus_4_asiakastiedoista.PNG)

…hae tarvittava nimeke ja tee varaus.

![](/assets/files/docs/Lainaus/Varaus_5_Varaa_asiakkaalle.PNG)

Kun olet valinnut asiakkaan, jolle varaus tehdään, voi varauksen tietoja
tarkentaa:

- _Muuta_-laatikkkoon voit kirjoittaa varaukseen liittyviä lisätietoja
  tarvittaessa.
- Valitse _Noutopaikkaan_ kirjasto, mistä asiakas noutaa aineiston.
- Jos varaus halutaan alkamaan tulevaisuudessa, anna _Varauksen
  alkamispvm_ -laatikkoon aloituspäivämäärä. Muuten siihen tallentuu
  kuluva päivä.
- Jos varaus halutaan olemaan voimassa vain tiettyyn päivämäärään
  saakka, merkitse päiväys _Varaus vanhenee_ -laatikkoon.
- Oletuksena on _Varaa seuraava vapaa nide_. Jos haluat tietyn niteen
  varaukseen, valitse nide listalta _Varaus_-sarakkeesta.
- Varausten määrän voit valita _Tee varauksia (määrä)_ -sarakkeesta.
- _Kiireetön varaus_ antaa asiakkaan uusia varatun teoksen, Tätä valintaa voi käyttää jos teos tarvitsee esimerkiksi uuden tarran

![](/assets/files/docs/Lainaus/Varaus_6_Varaajan_tiedot.PNG)

### 2.8.3 Monta varausta kerralla

Jos haluat tehdä varauksen useammasta nimekkeestä kerralla, valitse
nimekkeiden vasemmalta puolelta valintaruudusta halutut nimekkeet ja
klikkaa _Varaa_-nappia.

![](/assets/files/docs/Lainaus/Varaus_7_useampi_kerralla.PNG)

Varaussivulle listautuu valitut teokset. Valitse noutopaikka ja klikkaa
_Varaa_.

![](/assets/files/docs/Lainaus/Varaus_8_Tee_varauksia.PNG)

---

## 2.8.4 Varausten käsittely

Varauksia voi muuttaa ja peruuttaa _Varaukset_-välilehdellä, jonne
pääsee nimeketietueen vasemmalla olevasta valikosta. Myös asiakkaan
varauksista käsin pääsee varauksiin klikkaamalla
_Varaukset_-välilehdellä teoksen nimeä.

![](/assets/files/docs/Lainaus/Varaus_9_varausten_käsittely.PNG)

Varauslistalla voit muuttaa varausten järjestystä, noutopaikkaa tai
keskeyttää tai peruuttaa varauksen.

![](/assets/files/docs/Lainaus/Varaus_10_varauslista.PNG)

### 2.8.4.1 Varausten järjestyksen muuttaminen

Jos jostain syystä täytyy varausjonon järjestystä muuttaa (ei saa tehdä
ilman erityistä syytä), se tapahtuu muuttamalla Järjestys jonossa
-sarakkeessa olevia numeroarvoja. Tai klikkailemalla vihreitä nuolia.
Huom! Tätä oikeutta ei välttämäti ole kaikilla työntekijöillä.

![](/assets/files/docs/Lainaus/Varaus_11_järjestys.PNG)

- Jos muutat järjestystä jonossa tai poistat varauksen, muista klikata
  _Päivitä varaukset_ -nappia tallentaaksesi toiminnot.

### 2.8.4.2 Varauksen kiinnittäminen viimeiseksi jonossa

Jos klikkaat varauksen oikealla puolella olevaa vihreää nuolta, varaus
menee viimeiseksi listalle ja pysyy viimeisenä, vaikka uusia varauksia
tulisi sen jälkeen. Tämä toiminto voi olla tarpeellinen esim.
kotipalveluasiakkaiden kohdalla, joilla niteiden laina-aika voi venyä
pidemmäksi kuin muilla asiakkailla.

![](/assets/files/docs/Lainaus/Varaus_12_kiinnitys_viimeiseksi.PNG)

Kun varauksen kohdalla näkyy vihreä nuoli, jonka alla on viiva, se
tarkoittaa, että varaus pysyy alimmaisena jonossa.

![](/assets/files/docs/Lainaus/Varaus_13_kiinnitys_viimeiseksi.PNG)

### 2.8.4.3 Yksittäisen varauksen keskeyttäminen

Jos asiakas haluaa keskeyttää yksittäisen varauksensa tietyksi ajaksi,
sen voi tehdä valitsemalla kalenterikuvakkeesta päivämäärän, mihin asti
varaus on keskeytettynä ja klikkaamalla Keskeytä-nappia.

![](/assets/files/docs/Lainaus/Varaus_14_keskeytä.PNG)

Kun varaus on keskeytetty, varauksen kohdalle tulee _Jatka_-nappi ja
näkyy päivämäärä, mihin saakka keskeytys on voimassa. Voit palauttaa
varauksen voimaan myös (tyhjentämällä päivämäärän ja) klikkaamalla
Jatka.

![](/assets/files/docs/Lainaus/Varaus_15_keskeytetty_varaus.PNG)

### 2.8.4.4 Asiakkaan kaikkien varauksien keskeyttäminen

Jos asiakas haluaa keskeyttää kaikki varauksensa, voi sen tehdä
asiakkaan tiedoissa _Varaukset_-välilehdellä klikkaamalla _Keskeytä
kaikki varaukset_ -nappia. Vastaavasti varaukset saa taas voimaan
klikkaamalla _Jatka kaikkia keskeytettyjä varauksia_ -nappia.

![](/assets/files/docs/Lainaus/Varaus_16_keskeytä_monta.PNG)

### 2.8.4.5 Varauksen poistaminen

Niteen tiedoissa varauksen poistaminen onnistuu yksitellen klikkaamalla varauksen
kohdalla Poista-nappia.

![](/assets/files/docs/Lainaus/Varaus_17_peruuta.PNG)

Useita varauksia kerralla voit poistaa merkitsemällä kunkin varauksen
alasvetovalikosta poistettavaksi ja klikkaamalla lopuksi _Päivitä
varaukset_.

![](/assets/files/docs/Lainaus/Varaus_19_peru_monta_varausta.PNG)

Varauksen voi myös poistaa asiakkaan tiedoissa _Varaukset_-välilehdellä
valitsemalla Poista?-sarakkeeseen “Kyllä” ja klikkaamalla _Peruuta
valitut varaukset_ -nappia.

![](/assets/files/docs/Lainaus/Varaus_17a_peru_asiakastiedoista_monta.PNG)

### 2.8.4.6 Peruuta odottava-tila ja kuljetustila

Kun varaus on jäänyt kiinni tai odottaa noutamista, voi varauksen tilan muuttaa takaisin aktiiviseksi varaukseksi Peruuta odottava-tila tai Peruuta kuljetustila -napeista. Teos palautuu varausjonoon. Käy samalla muuttamassa varauksen voimassaoloaika, muuten voimassaoloajaksi jää alkuperäinen kiinni jääneen teoksen aika. Tätä toimintoa tarvitaan esimerkiksi rikkinäisen teoksen kohdalla.

![](/assets/files/docs/Lainaus/Varaus_18_peruuta_odottava_ja_kuljetustila.PNG)

---

## 2.9 Varausten kiinnijääminen

Varaus voi jäädä kiinni joko virkailijaliittymässä palautettaessa tai
palautusautomaatilla palautettaessa.

### 2.9.1 Varaus palautetaan virkailijaliittymässä

Kun palautetaan varattuja niteitä, tulee varauksesta ilmoitus.

Kun varauksen noutokirjasto on **sama** kuin mihin nide on palautettu:  
![](/assets/files/docs/Lainaus/Varaus_20_varauskuitti.PNG)  
Kun varaus hyväksytään, asiakkaalle **lähtee noutoilmoitus**.

Kun varauksen noutokirjasto on **eri** kuin mihin nide on palautettu:  
![](/assets/files/docs/Lainaus/Varaus_21_kuljetuskuitti.PNG)  
Tässä tapauksessa nide menee kuljetustilaan, eikä asiakkaalle lähde
vielä noutoilmoitusta. Kuljetuskuitti tulostuu seuraavaksi. Asiakkaalle ilmoitus lähtee vasta, kun nide palautetaan
noutokirjastossa.

**Huomaa:** Molemmissa tapauksissa varaus vahvistetaan tai tulostetaan
kuitti ja hyväksytään varauksen kiinnijääminen. _Älä huomioi_ jättää
varauksen voimaan asiakkaalle, mutta sallii lainaamisen toiselle
asiakkaalle (ohjelma huomauttaa varauksesta).

### 2.9.2 Varaus palautetaan automaattiin

Jos kimpassa on käytössä varatun aineiston noutoilmoitusten
viivästäminen automaattipalautuksille, menevät kaikki automaatilla
palautetut varatut niteet kuljetustilaan. Myös noutopisteeseen
palautuneet jäävät odottamaan “kuljetusta” uudelleenkäsittelyyn.
Käytännössä kaikki automaattiin palautetut varaukset pitää siis
palauttaa noutopisteessä uudelleen virkailijaliittymässä, vasta siinä
vaiheessa noutoilmoitus lähtee asiakkaalle.

Jos viivästys ei ole käytössä, lähtee noutoilmoitus asiakkaalle heti,
kun aineisto palautetaan automaattiin.

### 2.9.3 Varausten näkyminen asiakkaan tiedoissa

Asiakkaan tiedoissa näkyy _Varaukset_-välilehdellä, minne varattu nide
on palautettu ja milloin.

**Virkailijaliittymässä palautettu varaus:**  
![](/assets/files/docs/Lainaus/Varaus_22_varausnäkymä_asiakkaalla.PNG)

Ensimmäinen nide odottaa noutopisteessä ja toinen on kuljetettavana noutokirjastoon

**Automaattiin palautettu:**

Jos noutoilmoitusten viivästäminen automaattipalautuksissa ei ole
käytössä, näkyy varaus samalla tavalla kuin yllä olevassa tapauksessa.

Jos käytössä on noutoilmoitusten viivästäminen, näkyy varaus näin:

![](/assets/files/docs/Lainaus/Varaus_23_Automaattiin_palautus.PNG)

### 2.9.4 Kiinni jääneiden varausten näkyminen kokoelmatiedoissa ja varausjonossa

**Kokoelmat**-välilehdellä nidetiedoissa näkyy varatun ja kuljetuksessa
olevan niteen tilanne.

Automaatilla palautettu, noutoilmoitusta ei vielä lähetetty. Varaus näkyy nidevarauksena.

![](/assets/files/docs/Lainaus/Varaus_24_palautettu_automaatilla.PNG)

1. Noudettavissa oleva, noutoilmoitus lähetetty
2. Teos on kuljetettavana

![](/assets/files/docs/Lainaus/Varaus_25_kokoelmat_varattu_ja_kuljetuksessa.PNG)


**Varausjono**-sivulla kiinni jäänyt varaus voi olla kolmessa eri
tilassa:
Automaatilla palautettu, kiinni jäänyt varaus, noutoilmoitusta ei vielä lähetetty. Priority-sarakkeessa varaus on In transit/Kuljetettavana-tilassa.

![](/assets/files/docs/Lainaus/Varausjono_1_InProcessing.PNG)

Noudettavissa oleva, noutoilmoitus lähetetty. Priority-sarakkeessa tietona Waiting/Odottaa 

![](/assets/files/docs/Lainaus/Varausjono_2_Waiting.PNG)

Kuljetettavana oleva varaus.

![](/assets/files/docs/Lainaus/Varausjono_3_InTransit.PNG)

---

## 2.9.5 Varauksen noutaa muu kuin varaaja itse

Jos varauksen noutaa joku muu kuin varaaja itse (perheenjäsen tai muu
valtuutettu), saat huomautuksen, josta pitää ensin valita Peruuta varaus
(poistaa varauksen varaajan tiedoista) ja sitten Kyllä, lainaa (Y).

![](/assets/files/docs/Lainaus/Varaus_27_VarauksenNoutoToinen_2.PNG)

---

## 2.10 Siirto-toiminto

Kirjastokimpassa voit siirtää niteitä toiseen kirjastoon käyttämällä
**Siirto**-työkalua.

- Valitse: Lainaus ja palautus -&gt; **Siirto**

![](/assets/files/docs/Lainaus/siirto1.png)  
Valitse alasvetovalikosta kirjasto, johon olet siirtämässä aineistoa ja
lue siirrettävän niteen viivakoodi _Syötä viivakoodi_ -kohtaan. Paina
lopuksi **OK**.

![](/assets/files/docs/Lainaus/siirto2.png)  
Nyt niteeseen tulee palautuksessa tieto määränpäästä..

![](/assets/files/docs/Lainaus/siirto3.png)  
ja niteen tilaksi kuljetuksessa.

![](/assets/files/docs/Lainaus/siirto4.png)

Kun nide saapuu kohteeseen, se on siellä palautettava, jotta nide ei ole
enää kuljetuksessa.

Nidettä ei ole pysyvästi siirretty kohdekirjastoon. Niteen kotikirjasto
ei muutu, mutta nykyinen paikka on toinen kirjasto.

![](/assets/files/docs/Lainaus/siirto5.png)

---

## 2.11 Kirjaston valinta

Oletuksena on, että kirjaudut virkailijatyökaluun kotikirjastossasi.
Kirjaston nimi näkyy virkailijatyökaluikkunan oikeassa yläreunassa.
**Tärkeää:** Lainat ja palautukset rekisteröityvät tunnukselle valitun
kirjaston mukaan.

![](/assets/files/docs/Lainaus/valinta1.png)

Jos työskentelet useammassa kirjastossa, pääset valitsemaan kirjaston
_Aseta kirjasto_ -napista. Valitse kirjasto alasvetovalikosta ja klikkaa
OK.

![](/assets/files/docs/Lainaus/valinta3.png)  
Valitsemasi kirjasto tulee näkyviin oikeaan yläkulmaan ja toiminnot
tapahtuvat valitsemassasi kirjastossa (lainat, palautukset jne.)

## 2.12 Pikaluettelointi (ei käytössä)

[Koha Manual - Fast Add
Cataloging](http://manual.koha-community.org/3.16/en/fastaddcat.html)

---

## 2.13 Lainauksen raportit

Useimmat raportit saadaan Raportit-moduulin kautta, mutta joitakin
raportteja löytyy myös Lainauksen toiminnoista.

Mene: _Lainaus ja palautus_ -&gt; _Lainausraportit_.

![](/assets/files/docs/Lainaus/raportti1.png)

### Varausjono

Tämä raportti näyttää kaikki varaukset kirjastossasi.

![](/assets/files/docs/Lainaus/raportti2.png)

### Hyllyvaraukset

**Huomioi:** Koha-Suomi on tehnyt oman versionsa hyllyvarauslistasta. Se
on kuvattu [wikin
Raportit-osiossa](https://tiketti.koha-suomi.fi/projects/koha-suomen-dokumentaatio/wiki/7_Raportit#722-Hyllyvaraukset)

Tämä listaus näyttää kaikki nimekkeet, joista on varauksia ja joilla on
niteitä saatavana. Ensin kannattaa tarkistaa ne varaukset, joissa
noutokirjastona on oma kirjasto/oman kunnan toinen kirjasto.
Noutokirjaston näkee viimeisestä sarakkeesta “Varauspvm ja noutopaikka”.

![](/assets/files/docs/Lainaus/raportti4.png)

Voit rajata hakua _Tarkenna tuloksia_ -valikosta vasemmalla.
Oletusarvona alkupäivämääränä on 365 vrk ennen kuluvaa päivää, mutta
päivämäärän voi muuttaa ennen hakua.

![](/assets/files/docs/Lainaus/raportti5.png)

Voit suodattaa hakutuloksesta _Kirjastot_-sarakkeen alla olevasta
valikosta oman kirjastosi aineistot esille. Jos valintaa ei ole tehty,
näkyvillä on _Ei mitään_.

![](/assets/files/docs/Lainaus/raportti6.png)

Näytön alareunassa näkyy, minkä verran aineistoa on suodatettu.

![](/assets/files/docs/Lainaus/lainrap6.png)

Voit muokata sarakkeiden näkyvyyttä..

![](/assets/files/docs/Lainaus/raportti7.png)

..ja lajitella hakutuloksia nuolimerkinnöistä.

![](/assets/files/docs/Lainaus/raportti8.png)

Hyllyvarauslistan voi tulostaa **ctrl+p** -näppäinyhdistelmällä.

### Noudettavissa olevat varaukset

Tämä raportti näyttää kaikki kirjastossasi noutoa odottavat niteet.

![](/assets/files/docs/Lainaus/nouto1.png)

Niteet, joiden noutoaika on mennyt umpeen, näkyvät _Vanhentuneet
varaukset_ -välilehdellä.

### Varauksia per nide

Tällä raportilla näet mm. varausten määrän yhtä nidettä kohti.

![](/assets/files/docs/Lainaus/pernide.png)

### Vastaanotettavat kuljetukset

Tässä raportissa näkyvät ne niteet, jotka Kohan mukaan on kuljetuksessa
kirjastoosi.

![](/assets/files/docs/Lainaus/kuljetus.png)

### Myöhässä

Koska tämä raportti vie paljon resursseja, sen määritykset annetaan
ennen raportin ajamista.

![](/assets/files/docs/Lainaus/raportti9.png)

### Myöhässä ja maksuja

![](/assets/files/docs/Lainaus/lainrap12.png)

---

## 2.14 Kirjaston sisäisen käytön seuranta

Ei vielä sisältöä.

---

## 2.15 Offline eli yhteydettömän tilan lainaus

Vaikka nettiyhteys ei toimisi, voit jatkaa lainaamista. Vaihtoehtoina on

1.  **Offline lainausohjelma Windowsille** (KOC). Erillinen ohjelma
    yksittäisille lainauskoneille. Tätä voi käyttää, kun ei ole yhteyttä
    internetiin. **Tämä on suositeltava vaihtoehto**
2.  **Koha Offline Circulation Tool** (KOCT), joka on selaimen lisäosa.
    Tätä voi käyttää esimerksi yllättävien verkkoyhteyskatkoksien
    aikana.
3.  **Yhteydettömän tilan lainaus**, jota voi käyttää, kun tietää
    ennakkoon, ettei yhteyttä ole. Esimerkiksi kirjastoautossa. **Ei
    suositella käytettäväksi**

### 2.15.1. Offline lainausohjelma Windowsille (KOC)

https://koha-community.org/manual/16.11/html/ch05s13.html  
tai  
http://manual.koha-community.org/3.8/en/offlinecirc.html  
Englanninkielinen asennettava ohjelma, jota ei ole käännetty suomeksi.

Ohjelman asennus- ja käyttöohjeohje PDF-muodossa: document\#36

![](/assets/files/docs/Lainaus/Offline_11.png)

Ennen kuin lainaus aloitetaan, voi tuoda .koc-tiedoston.
Asiakastiedoston tekevät kehittäjät, jotka toimittavat sen
tietoturvallisesti paikkaan, mistä käyttäjät saavat sen kopioitua omalle
koneelle. Tiedoston hyöty on siinä, että lainaustilanteessa näkyy
asiakkaan nimi, lainat sekä maksut. Tiedoston luomiseen menee tunteja,
joten äkillisissä tapauksissa tätä toimintoa ei voida käyttää.

**Huomaa:** Tietoturvan vuoksi ei ole kuitenkaan hyvä, että tehdään ns.
paikallisia kopioita asiakasrekisteristä. Ohjelmaa voi käyttää ilman
borrowers.db –tiedostoa.

Offline-ohjelmassa valitaan Database -&gt; Select Borrowers DB File.
Omalta koneelta valitaan tuotu .koc-tiedosto (useimmiten ladatut
tiedostot -kansiossa) ja klikataan Avaa.

![](/assets/files/docs/Lainaus/Offline_11_1.png)

Lainaaminen tehdään Issues-välilehdellä. Asiakkaan kirjastokortin numero
luetaan _Borrower Cardnumber_ -kenttään (tai tehdään haku
asiakastietoihin Search-laatikon kautta). Kun olet syöttänyt
kirjastokortin numeron, klikkaa \_Accept. Lainattavat teokset luetaan
_Item Barcode_ -kenttään ja Asiakkaan lainat näkyvät _Previously Scanned
Barcodes_ -ikkunassa. Eräpäivää ei voi tässä määritellä, mutta se
määrittyy automaattisesti aineistolle, kun lainaukset siirretään
pääjärjestelmään. Asiakkaalle voi antaa aineistolajin mukaisen
eräpäivälapun (kuittia ei pysty tulostamaan).

![](/assets/files/docs/Lainaus/Offline_12.png)

Kun asiakkaalle on lainattu kaikki aineisto, klikkaa _OK_ sivun
alareunassa. Päivän ensimmäisen lainaajan jälkeen saat ikkunan, jossa
valitset, millä nimellä ja mihin kansioon haluat tallentaa
offline-tiedostot. Kaikki loput asiakkaat ja lainat tallentuvat samaan
tiedostoon tai tiedostopaikkaan automaattisesti. Kannattaa käyttää aina
samaa kaavaa, sillä tiedosto pitää osata myös hakea kansiosta, kun
tiedot siirretään pääjärjestelmään. Esimerkissä on käytetty työpöytää
tallennuspaikkana ja oletustiedostonnimeä (koostuu päivämäärästä ja
kellonajasta: vvvv-kk-pp tunti-minuutti-sekunti-sekunninsadasosa).

![](/assets/files/docs/Lainaus/Offline_13.png)

_Returns_-välilehdellä voi tehdä palautuksia, mutta se ei ole
suositeltavaa varausten takia.

![](/assets/files/docs/Lainaus/Offline_14.png)

_History_~~välilehdellä näkyy kuluvan päivän lainaus~~ ja
palautustapahtumat.  
Type-sarakkeessa _issue_ tarkoittaa lainausta.

![](/assets/files/docs/Lainaus/Offlinehistory.png)

Kun nettiyhteys on jälleen käytettävissä, voit siirtää
offline-lainaukset pääjärjestelmään.  
Mene _Lainaus ja palautus_ -näyttöön ja valitse sieltä _Lähetä
yhteydettömän tilan lainaustiedosto (\*.koc)_.

![](/assets/files/docs/Lainaus/Offline_16.png)

Seuraavalla näytöllä etsi _Selaa_-napista tallennettu tiedosto.

![](/assets/files/docs/Lainaus/Offline_17.png)

Esimerkissä tiedosto tallennettiin työpöydälle. Kun olet valinnut
tiedoston, klikkaa _Avaa_-nappia ikkunan oikeassa alareunassa.

![](/assets/files/docs/Lainaus/Offline_18.png)

Tiedosto näkyy nyt valittuna. Klikkaa _Lähetä tiedosto_.

![](/assets/files/docs/Lainaus/Offline_19.png)

Kun lähetyksen tila on 100%, klikkaa _Lisää yhteydettömän tilan jonoon_.

![](/assets/files/docs/Lainaus/Offline_20.png)

Jos tiedostoja on useampia, tee kaikille sama toiminto klikkaamalla
Lähetä toinen KOC-tiedosto.  
Kun kaikki tiedostot on lähetetty, klikkaa _Näytä käsittelyä odottavat
yhteydettömän tilan tapahtumat_.

![](/assets/files/docs/Lainaus/Offline_21.png)

Seuraavalla näytöllä valitset kaikki rivit (jos siellä ei ole mitään
virheilmoituksia, ne rivit voit jättää vaikka valitsematta jos sellaisia
on) ja klikkaa _Käsittele_.

![](/assets/files/docs/Lainaus/Offline_22.png)

Kun saat alla olevan näytön, lähetys on onnistunut.

![](/assets/files/docs/Lainaus/Offline_23.png)

**Lopuksi**

Lopuksi **poista koneeltasi tiedostot täydellisesti**.

Etsi koneeltasi tiedosto, johon lainat tallennettiin.
Esimerkkitapauksessa Resurssin hallinta, Työpöytä. Klikkaa tiedosto(t)
aktiiviseksi ja paina sen jälkeen yhtä aikaa Shift + Del. Ohjelma kysyy
haluatko poistaa pysyvästi (lopullisesti). Vastaa kyllä.

Huom! Nämä tiedostot on poistettava kokonaan, koska Koha Offline
Circulation tallentaa kaikki lainat samaan paikkaan. Koha menee
sekaisin, jos useiden päivien lainat siirtyvät pääjärjestelmään yhä
uudelleen.

![](/assets/files/docs/Lainaus/Offline_24.png)

![](/assets/files/docs/Lainaus/Offline_25.png)

### 2.15.2 Koha Offline Circulation Tool (KOCT)

http://manual.koha-community.org/3.16/en/offlinecirc.html  
englanninkielinen lisäosa, jota ei ole käännetty suomeksi.

Ohje asennukseen ja käyttöön:

attachment:KOCTOffline-asennusjakäyttö.pdf

Lainausnäkymä:  
![](/assets/files/docs/Lainaus/KOCTLainausnäkymä.png)

### 2.15.3 Yhteydettömän tilan lainaus

**Tämä ei ole suositeltava tapa**

#### Etukäteen tehtävät toimet

Ennen yhteydettömän tilan lainausta täytyy työasemalle ladata
tiedostoja.

Mene: Lainaus ja palautus -&gt; Yhteydettömän tilan lainaus.

![](/assets/files/docs/Lainaus/Offline_1.png)

Synkronoi tiedostot jokaisella työasemalla klikkaamalla
Synkronoidaan-linkkiä.

![](/assets/files/docs/Lainaus/Offline_2.png)

Tämä antaa sinun ladata paikallisen kopion asiakkaista ja
lainaustiedoista. Klikkaa _Lataa tietueet_ sivun vasemmassa yläreunassa.
Kun tiedot on ladattu, näet niiden viimeisimmän päivitysajankohdan.

![](/assets/files/docs/Lainaus/Offline_3.png)

**Päivitys pitäisi tehdä säännöllisesti, jotta yhteyskatkon aikana olisi
mahdollisimman tuoreet tiedot käytettävissä.** Päivitys kestää pitkään.

#### Lainaaminen

Kun verkkoyhteys ei ole käytettävissä, mene Yhteydettömän tilan
lainaukseen Kohassa ja klikkaa _Lainaus_.

Lainaaminen aloitetaan lukemalla lainaajan kirjastokortti sivun yllä
olevaan laatikkooon. Jos näppäilet asiakastunnuksen, käytä isoja
kirjaimia. Asiakkaan tiedot, olemassaolevat lainat ja maksut tulevat
näytölle.

![](/assets/files/docs/Lainaus/Offline_4.png)

Lue lainattavan niteen viivakoodi ja anna eräpäivä. Jos et anna
eräpäivää, Koha muistuttaa asiasta.

![](/assets/files/docs/Lainaus/Offline_5.png)

Kun nide on lainattu, se ilmestyy asiakkaan tietoihin.

![](/assets/files/docs/Lainaus/Offline_6.png)

#### Kohan yhteydettömän tilan tietojen lataaminen

Kun nettiyhteys on taas käytettävissä, synkronoi yhteydettömän tilan
lainaukset (ja palautukset) klikkaamalla _Lähetystapahtumat_ (nuoli
ylöspäin) klikkaamalla _Odottavat yhteydettömän tilan toimet_. Linkin
yläpuolella voi lukea myös ettei ole odottavia tapahtumia, varmista
kuitenkin asia Odottavan yhteydettömän tilan toimet linkistä.

![](/assets/files/docs/Lainaus/Offline_7.png)  
![](/assets/files/docs/Lainaus/Offline_8.png)

Saat näytölle listan tapahtumista, jotka odottavat lataamista
tietokantaan.

![](/assets/files/docs/Lainaus/Offline_9.png)

Kun kaikista koneista on lähetetty yhteydettömän tilan lainaukset
tietokantaan, voit valita rastittamalla ne kaikki tai vain ne, jotka
haluat käsitellä Kohaan.

- Klikkaa _Käsittele_-nappia ja Koha tallentaa jokaisen toiminnon
  yksitellen. Jokaiselle toiminnolle (issue = lainaus, return =
  palautus) on oma rivinsä ja ilmoitus onnistuuko toiminnon
  tallentaminen Kohaan.

&gt;\* **Onnistui**, jos toiminto on tallennettu onnistuneesti  
&gt;\* **Asiakasta ei löytynyt**, jos asiakkaan kortin numero on
väärin  
&gt;\* **Nidettä ei löytynyt**, jos niteen viivaakoodi on väärin.  
&gt;\* **Nide ei ole lainassa**, jos palautit saatavilla olevan niteen.

Kun käsittely on valmis, saat yhteenvedon tapahtumista.

![](/assets/files/docs/Lainaus/Offline_10.png)

---
