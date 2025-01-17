---
title: 'Kohan ohje suomeksi'
permalink: /dokumentaatio/lainaus/
redirect_from:
  - /theme-setup/
toc: true
---

# 2. Lainaus ja palautus

Käytä lainaustoiminnoissa Firefox-selainta, jolla voit määrittää asiakaskuitit 
tulostumaan automaattisesti (ohje kohdassa *11. Kuittitulostuksen
asetukset*). Koha-Suomi suosittelee Firefox ESR-version käyttöä.

Lainauksen toimintoihin pääset useilla eri tavoilla. Virkailijaliittymän
etusivulla olevista pikakuvakkeista pääset ohjelman eri toimintoihin,
mm. Lainaus- ja Palautus -sivun toimintoihin. Voi olla, että kimpassasi on piilotettu sivulta toimintoja, joita ei ole nähty tarpeellisiksi. *Lainaus ja palautus* -sivun toimintoihin pääset
jokaisen sivun yläreunassa olevasta linkistä.

![](/assets/files/docs/Lainaus/lainaus.PNG)

Ohjelmassa toimivat pikanäppäimet:

- Hae tietokannasta: *Alt+Q*
- Lainaus: *Alt+U*
- Palautus: *Alt+R*
- Lainakuitti: *Alt+P*
- Ilmoitusikkunoissa olevat kirjainvihjeet: *Alt+Shift+kirjain* aktivoi kyseisen painikkeen. Esim. jos painikkeessa lukee _Kyllä (Y)_, saa Kyllä-painikkeen valittua painamalla näppäimistöltä Alt+Shift+y.
  
  ![](/assets/files/docs/Lainaus/kirjainvihje.PNG)

## 2.1. Lainaus

Aloita lainaaminen lukemalla asiakkaan kirjastokortin viivakoodi
*Lainaus*-kenttään tai hakemalla asiakasta hänen nimellä.
Toimi kirjastossasi sovittujen käytäntöjen mukaan.

![](/assets/files/docs/Lainaus/lainaus_asiakastunnus.PNG)

Lue lainattavan niteen viivakoodi nidekenttään.

![](/assets/files/docs/Lainaus/lainaaminen.PNG)

- Viimeksi lainatun niteen tiedot näet *Lainassa*-kentässä.
- Jos klikkaat täpän kohtaan *Näytä aina lainat reaaliaikaisesti*, lainaustilanteessa kaikki asiakkaan lainat näkyvät näytöllä. Tämä valinta voi olla piilotettuna kimpassasi.

![](/assets/files/docs/Lainaus/Näytä_lainat_reaaliaikaisesti.PNG)

**Tärkeää:**

- Monet viivakoodinlukijat lähettävät automaattisesti rivinvaihdon,
  joten *Lainaus*-painiketta ei tarvitse välttämättä klikata sen jälkeen, kun olet lukenut lainattavan niteen viivakoodin Lainaus-kenttään.
- Jos niteen viivakoodia ei löydy, saat ilmoituksen:

  ![](/assets/files/docs/Lainaus/lainausviesti6.PNG)

 - Tarkista niteen viivakoodi, onko se oikein.

**Lainausasetukset**

- Kimpassasi käytössä olevat lainausasetukset saat näkyville klikkaamalla viivakoodi-kentän lopussa olevaa valikko-kuvaketta.

![](/assets/files/docs/Lainaus/lainausasetukset.PNG)

- Asetuksissa on mahdollista määritellä lainattavalle aineistolle muu
  eräpäivä kuin oletuseräpäivä. Tämä vaihtoehto tulee näkyviin vain,
  jos järjestelmäasetuksissa on määritelty, että virkailijalla on
  oikeus muuttaa eräpäivää lainatessa.
- Jos kimpalla on käytössä *Automaattinen uusinta*, ohjelma uusii
  lainatut teokset automaattisesti lainasääntöjen mukaisesti.
- Toiminnolla *Älä lyhennä laina-aikaa varausten määrän pohjalta*
  voi ohittaa järjestelmäasetuksen, jolla lyhennetään laina-aikaa, jos
  teoksen varausmäärä menee asetuksissa määritellyn rajan yli. Valinta tulee näkyviin vain kimpoissa, jossa tämä järjestelmäasetus on käytössä.

### 2.1.1 Kuittien tulostaminen

Kun olet lainannut kaikki asiakkaan lainat, voit tulostaa lainauskuitin
eri tavoilla. Toimi kimppasi käytäntöjen mukaan.

Kuitin voit tulostaa:
- Painamalla näppäimistöltä *Enter*. (Huom.
  kimppasi järjestelmäasetuksista riippuen, Enter voi myös tyhjentää
  asiakastiedot).
- Painamalla pikanäppäimiä *Alt+P*.
- Lainauskentän oikeassa yläkulmassa näkyvästä tulostimen kuvasta.
  
  ![](/assets/files/docs/Lainaus/tulostin.PNG)
  
- Asiakastietojen yläpuolelta olevasta *Tulosta*-valikosta valitsemalla *Tänään lainatut*.
  
![](/assets/files/docs/Lainaus/tulostakuitti.PNG)

*Tulosta*-valikossa on näkyvillä tulostusvaihtoehdot, jotka ovat kimpassasi otettu käyttöön:
- *Asiakastietojen yhteenveto*: A4-tuloste asiakastiedoista,
  lainoista, varauksista ja maksettavista maksuista.<br>
  Jos selaimelle, jolla käytät Kohaa, on määritelty kuitit tulostumaan automaattisesti kuittitulostimelle, kannattaa yhteenveto tulostaa jostain toisesta selaimesta A4:lle.
- *Tulosta kuitti*: tulostaa kaikki asiakkaan lainat kuitille.
  Tulosteessa erotellaan myöhässä olevat lainat oman otsikon alle.
- *Tänään lainatut*: tulostaa tänään lainattujen ja uusittujen
  lainojen tiedot kuitille.
- *Tulosta asiakkaan maksut*: tulostaa asiakkaan maksut kuitille.
- *Tulosta erääntyneet*: tulostaa erääntyneet lainat, jos asiakkaalla on myöhässä olevia lainoja.
- *Tulosta palautuskuitti*: tulostaa kuitin asiakkaan kuluvana päivänä palautetuista lainoista.<br>
  Huom! Jos asiakkaan lainahistoria anonymisoidaan eli asiakas haluaa, ettei hänen lainahistoriaa tallenneta, asiakkaalle ei pysty tulostamaan palautuskuittia. Asiakkaan tiedoissa Tulosta-valikkoon ei tule näkyville toimintoa *Tulosta palautuskuitti*.

Kimpan pääkäyttäjät voivat muokata kuiteille tulostuvia tietoja.

### 2.1.2 Asiakastietojen tyhjennys näytöltä

Kun lopetat lainaamisen, näytöltä on hyvä tyhjeentää asiakkaan tiedot.
Näytön voit tyhjentää kahdella tavalla:

- Painamalla *Enter*. (Huom! Kimpan asetuksista riippuen, Enter voi tulostaa myös
  asiakkaan lainakuitin).
- Klikkaamalla *X-merkkiä* lainauskentän oikeasta yläkulmasta.

![](/assets/files/docs/Lainaus/tyhjennys.PNG)

---

## 2.2 Lainaamisen estot

Joissakin tilanteissa Koha estää lainaamasta aineistoa asiakkaalle, jos
estot ovat laitettu päälle kimppasi järjestelmäasetuksissa. Näissä tilanteissa
näytölle tulee huomautus lainaamisen eston syystä.

### 2.2.1 Asiakkaalla on liikaa maksuja

![](/assets/files/docs/Lainaus/liikaamaksuja.PNG)  
Esimerkissä asiakkaalla on lainauskieltoon vaikuttavia maksuja 20,20 € ja maksuja, jotka eivät vaikuta lainauskieltoon on 1,01 €.

Huom! Uusintatilanteessa ohjelma ei ilmoita, jos sallittujen maksujen
raja on ylittynyt.
{: .notice--warning}

### 2.2.2 Asiakkaalla on rajoitus (lainauskielto)

Voit tallentaa asiakkaalle rajoituksen, joka aiheuttaa lainauskiellon, esim. kun lasku on lähetetty. Rajoite voidaan lisätä asiakkaalle myös automaattisesti, kun lasku luodaan. 
Rajoitus voi olla voimassa toistaiseksi tai määräajan. 

Rajoituksen voit tallentaa asiakastietojen Muokkaa-sivulla kohdassa *Asiakkaan
rajoitukset*. Valitse *+Lisää rajoitus* -linkkiä.

![](/assets/files/docs/Lainaus/asiakkaan_rajoitukset.PNG) 

![](/assets/files/docs/Lainaus/asiakkaan_rajoituksen_tyyppi.PNG)
- *Tyyppi*-kenttään valitse rajoituksen tyyppi.
- *Kommentti/Viesti*-kenttään tallenna rajoiteen syy.  
- *Vanhenee*-kenttään aseta rajoitteen viimeinen voimassaolopäivä, jos rajoite on voimassa vain tietyn ajan. 

![](/assets/files/docs/Lainaus/rajoitteenlisäys1.PNG) 

tai asiakkaan tiedoissa välilehdellä *Rajoitukset*:

![](/assets/files/docs/Lainaus/rajoitteenlisäys.PNG) 

Asiakkaan muokkausnäytöllä rajoite tallentuu asiakkaalle, kun asiakkaan tiedot tallennetaan. Rajoitukset-välilehdellä rajoitus tallennetaan *Lisää rajoitus* -painikkeella.  
  
Asiakkaan Tiedot ja Lainaus -näytöillä rajoitus näkyy näin:
  
![](/assets/files/docs/Lainaus/rajoite1.PNG)

### 2.2.2.1 [Rajoite liiallisista kirjautumisyrityksistä](https://koha-suomi.fi/dokumentaatio/asiakkaat/#151014-rajoite-liiallisista-kirjautumisyrityksist%C3%A4)

### 2.2.2.2 Rajoitteen poistaminen

Rajoitteen voit poistaa asiakkaalta *Poista*-toiminnolla.

![](/assets/files/docs/Lainaus/rajoitteenpoisto.PNG)


### 2.2.3 Asiakkaan osoitetiedot ovat väärät

Jos asiakkan tiedoissa on päällä Tarkista osoite -asetus,
lainaus estyy. (Huom! Toiminto voi olla piilotettuna kimpassasi.) 

Lainaustilanteessa tulee huomautus:  

![](/assets/files/docs/Lainaus/tarkistaosoite.PNG)

Päivitä osoitetiedot asiakkaan muokkaussivulla. Aseta muokkaussivulla osioon *Käyttäjätilin huomautukset* kohtaan *Tarkista osoite* "Ei" ja tallenna asiakastietojen muokkaussivu.

![](/assets/files/docs/Lainaus/vaaraosoite1.PNG)

Toiminnon käyttäminen ei ole suositeltavaa, koska asiakas menee lainauskieltoon toiminnon ollessa päällä. 

### 2.2.4 Asiakkaan kirjastokortti on kadonnut

Kun asiakas ilmoittaa kirjastokorttinsa kadonneen, tallenna tieto asiakastietojen muokkaussivulla osioon *Käyttäjätilin huomautukset* kohtaan *Kortti kadonnut* "Kyllä".

![](/assets/files/docs/Lainaus/korttikadonnut1.PNG)

Lainaustilanteessa tulee huomautus:  
![](/assets/files/docs/Lainaus/korttikadonnut.PNG)

Kun asiakkaan kirjastokortti on kadonnut, toimi kimpassasi sovittujen
käytäntöjen mukaan.  

Huomautus poistuu, kun asiakastietojen muokkaussivulla osiossa 
*Käyttäjätilin huomautukset* vaihdat *Kortti kadonnut* -kohtaan vaihtoehdon
“Ei” ja tallennat asiakastiedot.

### 2.2.5 [Tili lukittu](https://koha-suomi.fi/dokumentaatio/asiakkaat/#151013-tili-lukittu)

---

## 2.3 Lainauksen viestit ja huomautukset

### 2.3.1 Huomautus liitteistä

Jos lainaat asiakkaalle niteen, joka sisältää useita osia ja tieto osista on
tallennettu niteen tietoihin kenttään 3 (Liitteiden määrä), saat
ilmoituksen, jossa kerrotaan montako osaa nide sisältää.

![](/assets/files/docs/Lainaus/huomsisallosta.PNG)

Joskus lainaustilanteessa näytölle voi tulla keltaisella pohjalla oleva huomautus. Nämä huomautukset on käsiteltävä/huomioitava aina ennen
lainaamisen jatkamista.

### 2.3.2 Aineisto on varattu toiselle asiakkaalle. Varaus ei ole jäänyt vielä kiinni.

![](/assets/files/docs/Lainaus/lainhuom1.PNG)

### 2.3.3 Nide on varaushyllyssä varattuna toiselle asiakkaalle.

![](/assets/files/docs/Lainaus/lainhuom2.PNG)

- Jos esimerkiksi toinen perheenjäsen haluaa lainata varatun
  aineiston, valitse *Peruuta varaus* ja klikkaa *Kyllä, lainaa
  (Y)*. Varaus poistuu alkuperäiseltä varaajalta.
- Jos valitset vaihtoehdon *Peruuta odottava-tila* ja klikkaat *Kyllä, lainaa
  (Y)*, alkuperäisen varaajan noutoa odottanut varaus muuttuu takaisin voimassaolevaksi.
  
### 2.3.4 Nide on jo lainassa tällä asiakkaalla.

![](/assets/files/docs/Lainaus/lainhuom4.PNG)

### 2.3.5 Nide on lainassa toisella asiakkaalla.

![](/assets/files/docs/Lainaus/lainhuom3.PNG)

### 2.3.6 Aineistoa ei lainata (niteen tila on “Ei lainattavissa”).

![](/assets/files/docs/Lainaus/lainhuom5.PNG)

- Lainauseston ohituksen salliminen määritellään järjestelmäasetuksissa. Välttämättä se ei ole päällä kimppasi kirjastossa.

### 2.3.7 Asiakkaalla on liian monta lainaa.

![](/assets/files/docs/Lainaus/lainhuom6.png)

- Lainauseston ohituksen salliminen määritellään järjestelmäasetuksissa. Välttämättä se ei ole päällä kimppasi kirjastossa.

### 2.3.8 Viivakoodia ei löytynyt.

![](/assets/files/docs/Lainaus/lainhuom7.PNG)

- Tarkista niteen viivakoodi, onko se oikein.

### 2.3.9 Lainattavan niteen tila on Kadonnut.

![](/assets/files/docs/Lainaus/lainhuom8.PNG)

- Järjestelmäasetuksissa voidaan määritellä, tuleeko kadonneeksi merkitystä niteestä huomautusta. Välttämättä se ei ole päällä kimppasi kirjastossa.

### 2.3.10 Lainattavalla niteellä on ikärajoitus, ja asiakas on liian nuori.

![](/assets/files/docs/Lainaus/lainhuom9.PNG)

- Ikärajoituksen ohituksen salliminen määritellään järjestelmäasetuksissa. Välttämättä se ei ole päällä kimppasi kirjastossa.

### 2.3.11 Lainattavalla teoksella on paljon varauksia, jonka takia lyhennetään laina-aikaa.

![](/assets/files/docs/Lainaus/lainhuom10.PNG)

- Laina-ajan lyhennys määritellään järjestelmäasetuksissa. Välttämättä se ei ole päällä kimppasi kirjastossa.

---

## 2.4 Asiakkaan lainat

*Lainassa*-painikkeesta saat näkyville asiakkaan kaikki lainat.  
![](/assets/files/docs/Lainaus/lainassa.PNG)

*Sarakkeet* -valikosta voit valita, mitä sarakkeita
Lainat-välilehdellä näytetään. Sarakkeen valinnoissa voi olla kimppakohtaisia eroja.

![](/assets/files/docs/Lainaus/sarakkeen_nakyvyys.PNG)

*Vie*-valikosta voit tulostaa, kopioida tai viedä asiakkaan lainat Excel- tai CSV-tiedostoiksi.

![](/assets/files/docs/Lainaus/vie.PNG)

Linkin takaa *Lainojen määrä nidetyypeittäin* näet asiakkaan kaikki lainat yhteenlaskettuna nidetyypeittäin.

Lainat-välilehdellä ensimmäisenä näkyvät tänään lainatut lainat.
Myöhässä olevien lainojen eräpäivät näkyvät punaisella.

![](/assets/files/docs/Lainaus/lainat_naytto.PNG)

### 2.4.1 Lainojen uusinta

Lainassa olevien niteiden laina-ajan voit uusia sen mukaan, mitä järjestelmän
ylläpidon laina- ja maksusäännöissä on määritelty.

Lainat voi uusia asiakkaan tiedoissa Lainat-välilehdellä tai Lainaus ja palautus -sivulla olevalla *Uusinta*-toiminnolla. Huom! Toiminto voi olla kimpassasi piilotettu.

Huom! Jos asiakkaalla on sallittujen maksujen raja ylittynyt, ohjelma ei huomauta siitä uusintatilanteessa.
{: .notice--warning}

#### 2.4.1.1 Lainojen uusinta asiakkaan tiedoissa olevalla Lainat-välilehdellä.

![](/assets/files/docs/Lainaus/uusinta.PNG)

- Uusinta-sarakkeesta näet, kuinka monta kertaa laina on uusittu.
- Myöhässä olevien lainojen eräpäivät näkyvät punaissella ja kuluvana päivänä erääntyvät lainat näkyvät boldattuna. Molempien lainojen uusinnan valintaruutu on jo oletuksena valittuna.
- Muiden uusittavien lainojen kohdalta (jotka voi uusia) ruksaa uusinnan valintaruutu ja klikkaa näytön alareunasta painiketta *Uusi valitut niteet* tai jos uusit kaikki lainat, klikkaa *Uusi kaikki*.
  
- Uusinta-sarakkeen yläreunassa olevalla toiminnolla “valitse kaikki”,
  voit valita uusittavaksi kaikki lainat, jotka on mahdollista uusia.
  Toiminto “ei valintaa” poistaa valinnat.
  
- Jos kimpassa on käytössä asetus, joka estää uusimisen samana päivänä
  uudestaan, tulee huomautus “Ei uusintaa ennen…”. Lainan voi uusia
  uudelleen kyseisen päivämäärän ja kellonajan jälkeen. Huomautus
  tulee, kun päivität Lainat-välilehden tai käyt välillä toisella
  sivulla.  
  ![](/assets/files/docs/Lainaus/uusinta6.PNG)
    
#### 2.4.1.2 Uusinta-toiminto Lainaus ja palautus -sivulla

- Huomio kirjastosi käyttösäännöt. Jos kirjaston käyttösäännöt edellyttävät kirjastokorttia
  uusintatilanteessa, tätä toimintoa ei tule silloin 
  käyttää. Toiminto voi olla myös piilotettuna kimpassasi.

![](/assets/files/docs/Lainaus/uusinta1.PNG)

Uusi lainat lukemalla niteen viivakoodi uusintakentään.
Voit antaa uusittaville lainoille halutessasi eri eräpäivän, kuin nidetyypin oletuslaina-aika on.

![](/assets/files/docs/Lainaus/uusinta2.PNG)

Jos niteen uusiminen onnistuu, saat ilmoituksen:

![](/assets/files/docs/Lainaus/uusinta3.PNG)

Jos nide ei ole lainassa, saat ilmoituksen:

![](/assets/files/docs/Lainaus/uusinta5.PNG)

Jos viivakoodia ei löydy, saat ilmoituksen:

![](/assets/files/docs/Lainaus/uusinta4.PNG)

 - Tarkista niteen viivakoodi, onko se oikein.

---

## 2.5 Asiakkaan varaukset

**Varaukset**-välilehdellä näet asiakkaan varaukset ja missä tilassa varaukset ovat. Ennen kuin varaus on jäänyt kiinni, voit vaihtaa varauksen noutopaikan, keskeyttää varauksen tai jatkaa keskeytetyn varauksen, mikäli toiminnnot
ovat sallittu järjestelmäasetuksissa. 

![](/assets/files/docs/Lainaus/varaukset2.PNG)

---

## 2.6 Asiakkaan rajoitukset, huomautukset ja viestit

### 2.6.1 Asiakkaan rajoitukset

Voit asettaa asiakkaalle rajoituksen, joka estää lainaamisen ja uusimisen. 

Rajoituksen voit lisätä Rajoitukset-välilehdellä tai asiakastietojen muokkausnäytöllä:

[Asiakkaalla on rajoitus](https://koha-suomi.fi/dokumentaatio/lainaus/#222-asiakkaalla-on-rajoitus-lainauskielto)

### 2.6.2 Huomautukset asiakastiedoissa

Voit tallentaa asiakastietojen muokkausnäytöllä asiakkaalle huomautuksia, jotka näkyvät verkkokirjastossa asiakkaan Omat tiedot -sivulla tai Kohassa asiakkaan Lainaus ja Tiedot -sivulla. 

![](/assets/files/docs/Lainaus/huomautukset1.PNG)

### 2.6.3 Viestit asiakastiedoissa

Voit lisätä asiakkaalle lyhyitä viestejä, jotka näkyvät asiakkaan Lainaus ja Tiedot -sivuilla.
Viestin voit lisätä joko toimintapainikkeesta **Lisää viesti** tai linkistä **+Lisää uusi viesti**.

[Lisää viesti](https://koha-suomi.fi/dokumentaatio/asiakkaat/#156-lis%C3%A4%C3%A4-viesti)


### 2.6.4 Vanhentunut asiakastieto

Jos asiakastiedot vaativat määräaikaistarkistuksen (parametreissä
määritelty), näyttöön tulee ilmoitus:

![](/assets/files/docs/Lainaus/vanhentunut.png)

Tarkista ja päivitä tarvittaessa asiakkaan yhteystiedot (osoite, puhelinnumero,
sähköpostiosoite, viestiasetukset). Jos tiedot ovat ajantasalla, klikkaa
*Uusinta*. Jos tiedot täytyy päivittää, muokkaa ja päivitä tiedot ensin linkistä *Muokkaa tietoja*.

Käyttöoikeuden voit jatkaa myös valikosta *Muita toimintoja*,
valitsemalla *Asiakkaan käyttöoikeuden jatkaminen*.

![](/assets/files/docs/Lainaus/vanhentunut2.PNG)

---

## 2.7 Palautus

Aineiston palauttamiseen pääset eri näyttöjen kautta.

![](/assets/files/docs/Lainaus/palautus.PNG)

Kaikista lainaustenvalvonnan toiminnoista on listaus *Lainaus ja
palautus* -sivulla, jonne pääset jokaisen sivun vasemmasta yläreunasta
olevasta linkistä.

### 2.7.1 Aineiston palauttaminen

Kun palautat aineistoa, lue niteen viivakoodi Palautus-kenttään.
Palautetun niteen tiedot tulevat näytölle.

![](/assets/files/docs/Lainaus/palautus1.PNG)

![](/assets/files/docs/Lainaus/sarakkeet.PNG)

*Sarakkeet*-valikosta voit valita, mitä tietoja Palautus-näytöllä näytetään. 
*Vie*-valikosta voit tulostaa, kopioida tai viedä palautetut niteet Excel- tai CSV-tiedostoiksi.

Jos teoksesta on varaus ja saat näytölle ilmoituksen: 

![](/assets/files/docs/Lainaus/maksuilmoitus.PNG)

Voit poistaa varauksen tällä sivulla ilman, että asiakkaalle tulee noutamattoman varauksen maksua. Jos palautetusta teoksesta ei ole varausta, ilmoitusta ei tarvitse huomioida.


### 2.7.2 Palautuksen viestit

#### 2.7.2.1 Toisen kirjaston aineiston palautus

Jos olet palauttamassa jonkun muun kirjaston aineistoa, saat viestin,
jossa ilmoitetaan mihin kirjastoon nide pitää kuljettaa.

![](/assets/files/docs/Lainaus/palautusviesti1.PNG)

- Palautuksen jälkeen niteen tilaksi muuttuu _Kuljetettavana_. Palautustaulukkoon tulee näkyville niteen kotikirjasto ja kuljetuksen syy.
   
  ![](/assets/files/docs/Lainaus/palautusviesti2024_1.png) 

- Nide pitää palauttaa vielä kotikirjastossa, jotta sen tilaksi muuttuu
  Saatavana-tila.

#### 2.7.2.2 Useita osia sisältävän niteen palautus

Jos palautat niteen, joka sisältää useita osia ja tieto osista on
tallennettu niteen tietoihin kenttään 3 (Liitteiden määrä), saat
ilmoituksen, jossa kerrotaan montako osaa nide sisältää.  
![](/assets/files/docs/Lainaus/palautusviesti9.PNG)


#### 2.7.2.3 Varatun niteen palautus

Järjestelmäasetuksissa voidaan määritellä, tulostetaanko varauksen info- ja kuljetuskuitti automaattisesti vai pitääkö virkailijan vahvistaa kuitin tulostaminen. 

***Varauksen infokuitin tulostaminen manuaalisesti***:

- Kun palautat niteen, josta on varaus, saat siitä ilmoituksen, jossa voi olla eri toimintovaihtoehtoja kimpan toimintatavoista ja asetuksista riippuen.

![](/assets/files/docs/Lainaus/palautusviesti10.PNG)

- Valitsemalla toiminnon *Vahvista varaus*, nide menee Odottaa kirjastossa -tilaan.
- Toiminnolla *Tulosta kuitti ja vahvista*, ohjelma tulostaa varauksen infokuitin ja muuttaa niteen Odottaa kirjastossa -tilaan. 
- Toiminnolla *Älä huomioi*, varaus säilyy asiakkaalla voimassa olevana.
- Jos palautat varatun niteen toistamiseen samalla näytöllä, voit saada ilmoituksen, jossa on mahdollista poistaa varaus toiminnolla *Poista varaus*. 

- Poistetusta varauksesta ei tallennu asiakkaalle noutamattoman varauksen maksua, kun poisto tehdään samalla palautusnäytöllä, kuin alkuperäinen palautus on tehty. Varausviestin taakse jää ilmoitus "Maksuja ei peritä käsin peruutetuista varauksista".

***Varauksen infokuitin tulostuminen automaattisesti***:

- Kun palautat niteen, josta on varaus, saat siitä ilmoituksen:

![](/assets/files/docs/Lainaus/palautusviesti3.PNG)

- Varauksen infokuitti tulostuu heti automaattisesti, kun olet palauttanut varatun niteen. 
- Jos palautat niteen toisen kerran, ohjelma vaatii manuaalisen varausilmoituksen kuittauksen.


#### 2.7.2.4 Varaus toisessa kirjastossa

Jos palautat niteen, josta on varaus jossain toisessa kirjastossa, saat
ilmoituksen ja tiedon, mihin kirjastoon nide pitää kuljettaa.

***Varauksen kuljetuskuitin tulostaminen manuaalisesti***:

![](/assets/files/docs/Lainaus/palautusviesti5.PNG)

- Valitsemalla *Vahvista varaus ja kuljetus*, vahvistat niteen kuljetettavaksi kirjastoon, missä on varauksen noutopaikka.
- Toiminnolla *Tulosta kuitti, kuljeta ja vahvista*, ohjelma tulostaa varauksen kuljetuskuitin ja merkitsee niteen kuljetustilaan kirjastoon, missä on varauksen noutopaikka. 
- Toiminnolla *Älä huomioi*, varaus säilyy asiakkaalla voimassa olevana.

***Varauksen kuljetuskuitin tulostuminen automaattisesti***:

![](/assets/files/docs/Lainaus/palautusviesti13.PNG)

- Kun palautat varatun niteen, tulostuu varauksen kuljetuskuitti heti automaattisesti.
- Nide menee kuljetustilaan kirjastoon, missä on varauksen noutopaikka.


#### 2.7.2.5 Asiakkaan maksut palautusnäytöllä

Jos järjestelmä on asetettu näyttämään maksut palautuksen yhteydessä,
saat keltapohjaisen ilmoituksen asiakkaan maksuista. *Maksa*-linkistä pääset suoraan asiakkaan maksuihin.
![](/assets/files/docs/Lainaus/palautusviesti7.png)


#### 2.7.2.6 Kadonneeksi merkityn niteen palauttaminen

Jos palautat kadonneeksi merkityn niteen, saat seuraavan ilmoituksen:  
![](/assets/files/docs/Lainaus/palautusviesti8.PNG)
- Kadonnut-tila poistuu niteeltä automaattisesti palautuksen yhteydessä, jos järjestelmäasetuksiin on näin määritelty. 


#### 2.7.2.7 Laskutetun niteen palauttaminen

Jos palautat niteen, joka on laskutettu, saat seuraavan ilmoituksen:
![](/assets/files/docs/Lainaus/palautusviesti12.PNG)

- Niteen laskutettutila ei poistu automaattisesti, jos järjestelmäasetuksissa on näin määritelty.

### 2.7.3 Palautusilmoitukset

Jos kimpassasi on käytössä *Palautusilmoitukset*, toiminto näkyy asiakkaan Lainat-välilehdellä. Jos *Palautusilmoitukset* eivät näy, saat sen näkyville Sarakkeet -valikosta. Toimintoa voit käyttää tilanteissa, kun asiakas ilmoittaa palauttaneensa lainan, joka näkyy vielä hänen lainoissaan. 

Klikkaa toimintoa *Ilmoitettu palautetuksi* ko. lainan kohdalla

![](/assets/files/docs/Lainaus/ilmoittaa_palauttaneensa.PNG)

Saat Huomautukset-näytön, johon voit halutessasi kirjata asiakkaan ilmoituksen palautuksesta. Klikkaa lopuksi *Ilmoita palautetuksi* -painiketta.

![](/assets/files/docs/Lainaus/ilmoittaa_palauttaneensa1.PNG)

Lainan Eräpäivä-sarakkeeseen tallentuu tieto "Ilmoittaa palauttaneensa" ja Palautusilmoitukset-sarakkeeseen ajankohta, jolloin palautusilmoitus on tallennettu.

![](/assets/files/docs/Lainaus/ilmoittaa_palauttaneensa2.PNG)

Palautusilmoitukset-välilehdellä näet palautetuksi ilmoitetun lainan tiedot. Toiminnot-valikosta voit muokata huomautuksia tai ratkaista/merkitä lainan löytyneeksi. 

![](/assets/files/docs/Lainaus/ilmoittaa_palauttaneensa3.PNG)

![](/assets/files/docs/Lainaus/ilmoittaa_palauttaneensa4.PNG)

Ratkaisuvaihtoehtoja ovat:
- Löytynyt kirjastosta
- Asiakas palautti

Valitse niteelle tarvittaessa myös uusi kadonnut-arvo. 

Jos palautat palautetuksi ilmoitetun niteen Palautus-toiminnolla, saat ilmoituksen, jossa voit myös ratkaista/merkitä lainan löytyneeksi.

![](/assets/files/docs/Lainaus/ilmoittaa_palauttaneensa5.PNG)

Järjestelmäasetuksiin voidaan määritellä, kuinka monen "ilmoittaa palauttaneensa" -lainan jälkeen ohjelma huomauttaa määrästä virkailijalle.

---
## 2.8 Uusinta

![](/assets/files/docs/Lainaus/uusinta1.PNG)

Lainaus ja palautus -sivun Uusinta-toiminto voi olla kimpassasi piilotettu pois näkyvistä. Jos lainojen uusinta on kimpassasi tällä sivulla mahdollista, on hyvä huomioida, ettei toiminto huomioi kimppasi laina- ja maksusääntöjen asetuksia ja rajoituksia. 
Lainat voi uusia myös asiakkaan Lainat-sivulla:
[Lainojen uusinta](https://koha-suomi.fi/dokumentaatio/lainaus/#241-lainojen-uusinta)

## 2.9. Aseta kirjasto

Oletuksena on, kun kirjaudut virkailijaliittymään, että kirjautumiskirjastoksi tulee oma kirjasto, joka on tallennettu käyttäjätunnuksesi tietoihin. 

Lainat, palautukset ja kaikki muut toiminnot rekisteröityvät tunnukselle valitun
kirjaston mukaan.
{: .notice--warning}

![](/assets/files/docs/Lainaus/kirjautuminen.PNG)

Kirjaston nimi näkyy virkailijaliittymän oikeassa yläreunassa.

![](/assets/files/docs/Lainaus/kirjastovalinta.PNG)

Jos työskentelet useammassa kirjastossa, pääset valitsemaan toisen kirjautumiskirjaston
_Aseta kirjasto_ -toiminnolla. Valitse kirjasto alasvetovalikosta ja klikkaa
*OK*.

![](/assets/files/docs/Lainaus/kirjastovalinta2.PNG)  

## 2.10 Varausjono

Tämä raportti näyttää kaikki varaukset, jotka kohdistuvat kirjastosi aineistoon. Raportti käyttää hyväksi kuljetusten painomatriisia, joka pitää olla määritelty kimppasi kirjastoille.

Tämä ei ole Koha-Suomen ylläpitämä raportti hyllyvarausten
käsittelyyn. Raportti ei välttämättä toimi kaikilta osin.
{: .notice--warning}

![](/assets/files/docs/Lainaus/varausjono.PNG)

- Valitse kirjasto, jonka paikalla olevia varattuja teoksia haet.
- Voit rajata raportin nidetyypin, kokoelman ja hyllypaikan mukaan.

![](/assets/files/docs/Lainaus/varausjono1.PNG)

Hakutuloksia voi suodattaa ja järjestellä yläreunan valikon avulla.
Näkyvillä olevia sarakkeita voi säätää *Sarakkeet*-valikosta ja tiedot voi viedä Excel- tai CSV-muotoon, kopioida ja tulostaa.

## 2.11 Hyllyvaraukset

Koha-Suomi suosittelee käyttämään tätä raporttia, kun
etsitään hyllyssä olevia varauksia.
{: .notice--warning}

**Huomaa myös:** Hyllyvarausraportti ei ole täysin reaaliaikainen,
vaikka se avautuukin nykyään nopeammin kuin ennen. Hyllyvarausraportin
tiedot haetaan tausta-ajolla, jonka kesto on varausten määrästä riippuen
muutamasta sekunnista useampaan minuuttiin. Tänä aikana käsiteltävien
niteiden ja varausten tiedot voivat muuttua ja listalle voi tulla
tietoa, joka ei pidä enää katseluhetkellä paikkansa. Tästä voi myös
johtua, että listalle voi päätyä tilanne, että toisesta kirjastosta
omaan kirjastoon kuljetettavana oleva nide näyttäisi olevan listan
mukaan hyllyssä omassa kirjastossa. Nide on palautettu kesken ajon ja
mennyt kuljetustilaan. Kuljetettavan niteen sijaintikirjastona on
tietokannassa kohdekirjasto. Tälle epäreaaliaikaisuudelle ei ikävä kyllä
voi tehdä mitään, koska tausta-ajolla kuluu työhön oma aikansa ja
tilanne taustalla muuttuu koko ajan, kun niteitä palautetaan lainasta
tai joku toinen ehtii palauttaa omassa hyllyssä paikalla olevan niteen.

Hyllyvaraukset raportilla pystyy hakemaan näytölle kaikki voimassa
olevat hyllyvaraukset. Raportin toimintaan on tehty Koha-Suomessa
muutoksia käyttäjien toiveiden perusteella.

Vinkkejä:

- Voit valita *Sarakkeet*-valikosta, mitä sarakkeita raportissa näytetään.
- Valitse kirjasto-sarakkeista (On shelf/Varaus) oma kirjasto, jolloin pystyt helposti
  tarkistamaan omassa kirjastossa paikalla olevat varaukset ja joiden
  noutopiste on myös oma kirjastosi.
- Kirjastolyhenne näkyy oranssin värisenä, jos nide löytyy varauksen noutokirjastosta.
- Samaan poimintaryhmään kuuluvat kirjastot näkyvät boldattuna, mihin varauksen noutokirjasto myös kuuluu. 
- Sivulla näytetään oletuksena 20 hyllyssä olevaa varausta. Valitse *Näytä_Kaikki*, jolloin saat samalle sivulle kaikki varaukset.
- Voit rajata listaa esimerkiksi materiaalin, hyllypaikan ja/tai kokoelman mukaan.
- Voit järjestää hakutuloksia otsikkorivin kaksisuuntaisista nuolista nousevaan tai laskevaan järjestykseen.
- Tarkista, ettei listalle ole jäänyt varauksia roikkumaan pitkäksi
  aikaa järjestämällä Varauspvm-sarake nousevasti, jolloin
  ylimmäiseksi tulee vanhimmat varaukset.

Listaus näyttää kaikki nimekkeet, joista on varauksia ja joilla on
niteitä saatavana. Ensimmäisenä kannattaa tarkistaa ne varaukset, joissa
noutokirjastona on oma kirjasto/oman kunnan toinen kirjasto.

![](/assets/files/docs/Lainaus/hyllyvaraus1.PNG)

Suodata sarakkeesta "On shelf" oman kirjastosi varaukset. Jos et ole tehnyt valintaa,
sarakkeessa näkyy _Ei mitään_ ja näkyvillä on kaikkien kimppasi kirjastojen hyllyssä olevat varaukset.

![](/assets/files/docs/Lainaus/hyllyvaraus2.PNG)


- *Vie*-valikosta voit viedä taulukon Excel- tai CSV-muotoon, kopioida tai tulostaa. Jos raportin haluaa välttämättä tulostaa, kannattaa se tehdä tämän toiminnon kautta, koska tiedot asettuu paperille tällöin paremmin.

## 2.12 Noudettavissa olevat varaukset

Tämä raportti näyttää kaikki kirjastossasi noutoa odottavat varaukset.

![](/assets/files/docs/Lainaus/kaikkinoudettavat.PNG)

Vanhentuneet varaukset eivät näy oikein tämän näytön välilehdellä "Varaukset odottaneet yli X päivää". Käytä Kohan raporttia "Vanhentuneet, noutamattomat varaukset" (tai vastaavaa), jos kimpassasi sellainen on käytössä. Pyydä tarvittaessa kimppasi pääkäyttäjää tekemään raportti Kohaan.
{: .notice--warning}


## 2.13 Varauksia per nide

Tällä raportilla voit hakea varausten määrän annettua nidemäärää kohti tietyllä aikavälillä.

![](/assets/files/docs/Lainaus/varauksiapernide.PNG)

Ohjelma ehdottaa lisää tilattavien niteiden määrän, jotta ehto täyttyisi.

![](/assets/files/docs/Lainaus/pernide.PNG)


## 2.14 Siirto-toiminto

Kirjastokimpassa voit siirtää niteitä toiseen kirjastoon käyttämällä
*Siirto*-työkalua.

- Valitse: Lainaus ja palautus -&gt; *Siirto*
  
![](/assets/files/docs/Lainaus/Siirto.PNG)  

Valitse alasvetovalikosta kirjasto, johon olet siirtämässä aineistoa ja
lue siirrettävän niteen viivakoodi *Syötä viivakoodi* -kenttään. Paina
lopuksi *OK*. Niteeseen tulee palauttaessa tieto, minne nide pitää kuljettaa.

![](/assets/files/docs/Lainaus/Siirto1_2.PNG)  

Tietueen perustiedot-näytöllä nide näkyy kuljetus-tilassa.

![](/assets/files/docs/Lainaus/Siirto1_3.PNG)  

Kun nide saapuu kohteeseen, se on siellä palautettava, jotta niteeltä poistuu kuljetus-tila. 
Palautuksessa tulee ilmoitus:

![](/assets/files/docs/Lainaus/Siirto1_4.PNG)

Nidettä ei ole pysyvästi siirretty kohdekirjastoon. Niteen kotikirjasto
ei muutu, mutta nykyinen paikka on toinen kirjasto.

![](/assets/files/docs/Lainaus/Siirto1_5.PNG)

## 2.15 Lähetettävät kuljetukset

Raportilla voit tarkistaa kirjastostasi lähetettävät niteet.

![](/assets/files/docs/Lainaus/lähetettävätkuljetukset.PNG)

## 2.16 Vastaanotettavat kuljetukset

Tällä raportilla näet niteet, jotka ovat kuljetuksessa
kirjastoosi.

![](/assets/files/docs/Lainaus/kuljetus.PNG)

## 2.17 Myöhässä

Tämä toiminto voi olla piilotettuna kimpassasi.

Varoitus: Tämä raportti vaatii paljon järjestelmäresursseja, jos tietokannassa on paljon myöhässä olevia lainoja.
{: .notice--warning}

Koska raportti voi viedä paljon resursseja, raportti kannattaa suodattaa mahdollisimman tarkasti. 

![](/assets/files/docs/Lainaus/myöhässä.PNG)


## 2.18 Myöhässä ja maksuja

Tämä toiminto voi olla piilotettuna kimpassasi.

Raportti antaa kaikki kirjastosi myöhässä olevat lainat. Voit hakea lainat hyllypaikan mukaan.

![](/assets/files/docs/Lainaus/myöhässä2.PNG)

---

## 2.19 Yhteydettämän tilan lainaus

Jos Koha ei toimi esim. verkkoyhteysvian vuoksi, voit käyttää poikkeustilanteissa lainaamiseen seuraavia ohjelmia:

1.  **Koha Offline Circulation -lainausohjelma** (KOC). Erillinen työpöytäsovellus
    yksittäiselle Windows-koneelle.

2.  **Koha Offline Circulation Tool** (KOCT).  Firefox-selaimen erillinen lisäosa. 

KOCT-lisäosa ei toistaiseksi toimi version 24.05 kanssa.
{: .notice--warning}

Käyttämäsi ohjelma kannattaa asentaa asiakaspalvelukoneelle jo etukäteen, jotta ongelmatilanteen tullessa se on heti käytettävissä. KOC-työpöytäsovelluksen asennus vaatii järjestelmänvalvojan oikeudet koneelle. Kuntasi käytännöistä riippuen voi olla, että paikallinen ICT-tuki pystyy tekemään vain asennuksen.  

Lainojen palautukset kannattaa tehdä vain Kohalla, kun järjestelmä taas toimii. Offline-ohjelmat eivät huomioi esim. jos palautettavaan teokseen on varaus.
{: .notice--warning}

### 2.19.1. Offline lainausohjelma Windowsille (KOC)

Kirjaudu Kohaan ja lataa työpöytäsovellus. Latauslinkin löydät Lainaus ja Palautus -sivulta.
   
![](/assets/files/docs/Lainaus/OfflineKOC.PNG)

Linkki menee nettisivulle, josta ohjelma ladataan. 

Valitse *KohaOfflineCirculation_Installer_1_3.exe*.

![](/assets/files/docs/Lainaus/OfflineKOC2.PNG)   

Tallenna tiedosto.
   
![](/assets/files/docs/Lainaus/OfflineKOC3.PNG)

Klikkaa selaimen oikeassa yläkulmassa näkyvää nuolta ja siitä avautuvaa tiedostoa.
   
![](/assets/files/docs/Lainaus/OfflineKOC4.PNG) <br />

![](/assets/files/docs/Lainaus/OfflineKOC4_1.PNG)

Ohjelma pyytää järjestelmänvalvojan kirjautumisen koneelle, jos sinulla ei ole asennukseen tarvittavia oikeuksia.
   
Ohjelman asennus alkaa, kun valitset *Next*.
   
![](/assets/files/docs/Lainaus/OfflineKOC7.PNG)

Hyväksy ohjelman ehdottama tallennustiedosto valitsemalla *Next*.
   
![](/assets/files/docs/Lainaus/OfflineKOC6.PNG)

Valitsemalla *Next*, ohjelman kuvake asennetaan Käynnistä-valikkkoon nimellä "Koha Offline Ciruclation".
   
![](/assets/files/docs/Lainaus/OfflineKOC8.PNG)

Ohjelman asennus alkaa, kun valitset *Install*.
    
![](/assets/files/docs/Lainaus/OfflineKOC9.PNG)

Kun asennus on valmis, valitse *Finish*.
  
![](/assets/files/docs/Lainaus/OfflineKOC10.PNG)

**Asennuksen jälkeen:**

Ohjelman pikakuvake pitäisi löytyä työpöydältä.

![](/assets/files/docs/Lainaus/OfflineKOC11.PNG)
  
Voit kiinnittää ohjelman pikakuvakkeen tehtäväpalkkiin "Käynnistä"-valikosta.

![](/assets/files/docs/Lainaus/OfflineKOC12.PNG)

Jos tehtäväpalkin väri on musta, voit vaihtaa palkin väriä, jolloin logo näkyy paremmin.


#### 2.19.1.1 Offline lainausohjelmalla lainaaminen

Kun klikkaat ohjelman auki, se on valmis käyttöön.
Lainaamiseen tarvitset vain "Issues"-välilehdellä olevia tietoja ja toimintoja eli asiakastunnuksen, lainattavan niteen tunnuksen ja OK-painikkeen.

![](/assets/files/docs/Lainaus/OfflineKOClainaus.PNG)

1. Lue asiakkaan kirjastokortin viivakoodi *Borrower Cardnumber* -kenttään.
2. Lue lainattavien niteiden nidetunnukset *Item Barcode* -kenttään. Nidetunnukset siirtyvät automaattisesti kenttään *Previously Scanned Barcodes*.
3. Kun kaikki asiakkaan lainaamat niteet on luettu, klikkaa lopuksi *OK*-painiketta.
4. **Ensimmäisen lainaajan jälkeen lainatiedot pitää tallentaa.**
5. Ohjelma ehdottaa tallennuspaikkaa.
   - Älä muuta tiedoston nimeä, joka koostuu päivämäärästä ja kellonajasta (vvvv-kk-pp tunti-minuutti-sekuntti sekunninsadasosa).
   - Valitse tallennuspaikaksi tiedosto, josta löydät tiedoston helposti ja johon on muillakin käyttäjillä tarvittaessa oikeus, jos esim. asiakaspalveluvuoro vaihtuu välissä ja toinen virkailija kirjautuu koneelle jatkaakseen Koha Offline Circulation -ohjelman käyttöä. Hyvä tallennuspaikka on esim. koneen C:-aseman temp-kansio.
  
![](/assets/files/docs/Lainaus/OfflineKOCtemp.PNG)

   - Lainojen tallennuksen jälkeen ohjelma palaa takaisin lainausnäytölle ja voit jatkaa lainaamista seuraaville asiakkaille.
   - Seuraavien asiakkaiden lainat tallentuvat aina samaan tiedostoon. Eri käyttäjien tallennetut tiedostot tallentuvat kukin omina tiedostoina valittuun kansioon.
   - Muista tallentaa jokaisen lainaajan lainat erikseen *OK*-painikkeella, muuten lainat tallentuvat aina edelliselle asiakkaalle.
     
Pidä mielessä mihin tallensit tiedoston, jotta löydät sen myöhemmin helposti. Voit ottaa tiedoston nimen ja sijainnin vaikka paperille ylös.
{: .notice--warning}

#### 2.19.1.2 Lainatietojen lataaminen ja lähettäminen tietokantaan

**Lähetä lainat tietokantaan heti, kun Koha taas toimii.** Jos lähetät lainat tietokantaan vasta päivän tai parin päästä, voi asiakkaalle kirjautua esim. aiheettomasti noutamattoman varauksen maksu, jos varattu aineisto lainataan viimesenä noutopäivänä Offline-lainauksella ja lainat siirretään Kohaan vasta seuraavana päivänä tai myöhemmin.

Hyvä on huomioida, että samassa kirjastossa kaikki offlinella lainatut ja ladatut lainat näkyvät kaikille ko. kirjaston virkailijolle yhteydettömän tilan jonossa ennen kuin lainat on siirretty käsittelyyn.
{: .notice--warning}  
Suositeltavaa on, että kirjastossa vain yksi virkailija käsittelee eli siirtää kaikki lainat Kohaan. Jos samat lainat siirretään Kohaan useamman kerran, Koha tulkitsee uudelleen lähetykset lainojen uusintoina ja asiakas menettää uusimiskertoja. Niteet, joitka eivät ole uusittavissa esim. Lyhytlainat, uudelleen lähetys muuttaa lainan eräpäiväksi kuluvan päivän, jolloin lainat on siirretty Kohaan.
{: .notice--warning}   

- Kun yhteydet taas toimivat, kirjaudu Kohaan.
- Lainaus ja palautus -sivulta valitse *Lähetä yhteydettömän tilan lainaustiedosto (*.koc)*.
   
![](/assets/files/docs/Lainaus/lainatiedostonlähetys.PNG)

- Etsi tallennettu tiedosto/tallennetut tiedostot *Selaa*-toiminnolla.
   
![](/assets/files/docs/Lainaus/OfflineKOClähetälainat.PNG)

Eri käyttäjien tallennetut tiedostot näkyvät kukin omina tiedostoina kaikille käyttäjille, jos tiedostot on tallennettu samaan kansioon.

![](/assets/files/docs/Lainaus/OfflineKOCtemptiedostot.PNG)

- Jos lähetettäviä tiedostoja on useampia, valite ensimmäinen .KOC-tiedosto ja klikkaa *Avaa*.

![](/assets/files/docs/Lainaus/OfflineKOCtemptiedostot4.PNG)

- Valitse *Lataa tiedosto*. 

![](/assets/files/docs/Lainaus/OfflineKOClataatiedosto.PNG)

- Valitse *Lisää yhteydettömän tilan jonoon*. 

![](/assets/files/docs/Lainaus/OfflineKOCjonoon.PNG)

- Saat tiedon, että tiedosto on ladattu. Jos sinulla on enemmän kuin yksi tiedosto ladattavana, valitse *Lähetä toinen KOC-tiedosto*. 

![](/assets/files/docs/Lainaus/OfflineKOCladattutiedosto.PNG)

- Etsi toinen tiedosto samalla tavalla kuin etsit ensimmäisen tiedoston *Selaa*-toiminnolla. Valitse toinen ladattava tiedosto ja lataa se. Lisää tiedosto yhteydettömän tilan jonoon. 

- Kun olet ladannut kaikki tiedostot, valitse *Näytä käsittelyä odottavat yhteydettömän tilan tapahtumat*. 

![](/assets/files/docs/Lainaus/OfflineKOCkäsittelyäodottavat.PNG)

- Saat listan lainoista, jotka pitää "käsitellä" (siirtää) tietokantaan. *Poista*-toiminnolla voit poistaa listalta lainat, joita et halua siirtää. *Valitse kaikki* -toiminnolla saat valittua siirrettävät lainat. Klikkaa lopuksi *Käsittele*. 

![](/assets/files/docs/Lainaus/OfflineKOCvalitselainat.PNG)

- Ohjelma lähettää lainaustiedot Kohaan ja listaa lähetetyt tiedot näytölle.

![](/assets/files/docs/Lainaus/OfflineKOClähetetyt.PNG)

Listalta löytyvät mahdolliset virheet esim. jos asiakkaan tunnus tai lainatun niteen tunnus on jouduttu näppäilemään käsin ja on tullut näppäilyvirheitä, eikä tietoja löydy Kohasta. Tällöin listalla on vajaita lainatietorivejä (viivakoodi puuttuu tai kortin numero puuttuu). Vajaat lainatietorivit kannattaa tutkia ja käsitellä manuaalisesti.


#### 2.19.1.3 Lähetettyjen tiedostojen poistaminen

Lopuksi tiedosto/tiedostot, johon Offline-lainat tallennettiin, pitää poistaa koneelta lopullisesti.
1. Hae tiedosto(t), johon tallensit lainat.
2. Valitse poistettava KOC-tiedosto aktiiviseksi ja paina sen jälkeen näppäimistöltä yhtä aikaa *Shift+Del* -näppäimiä. Ohjelma kysyy, "Haluatko varmasti poistaa tämän tiedoston lopullisesti?"
3. Valitse *Kyllä*.
   
![](/assets/files/docs/Lainaus/OfflineKOCtiedostonpoisto.PNG)

Tiedosto(t) on poistettava koneelta kokonaan, jotta seuraavalla kerralla kun käytät Offline-lainausta, et vahigossa tallenna uusia lainoja vanhaan tiedostoon tai lähetä vanhaa tiedostoa uudestaan Kohaan.
{: .notice--warning}



### 2.19.2 Koha Offline Circulation Tool (KOCT)

KOCT-lisäosa ei toistaiseksi toimi version 24.05 kanssa.
{: .notice--warning}

Firefox-selaimen lisäosaa voi käyttä myös tilanteissa, kun Koha ei toimi. Lisäosa on englanninkielinen.

Lainojen palautukset kannataa tehdä vain Kohalla, kun järjestelmä taas toimii. Offline-ohjelmat eivät huomioi esim. jos palautettavaan teokseen on varaus.
{: .notice--warning}

#### 2.19.2.1 Selaimen lisäosan asennus

Kirjaudu Kohaan ja lataa Firefoxin lisäosa Lainaus ja Palautus -sivulta linkistä *Lataa Firefox-selaimen lisäosa*. 

![](/assets/files/docs/Lainaus/KOCTlisäosa.PNG)

Linkki vie nettisivulle, josta lisäosan voi ladata. <br/>
Lataa lisäosa toiminnolla *Lisää Firefoxiin*.

![](/assets/files/docs/Lainaus/KOCTlataus.PNG)

Ohjelma varmistaa lisätäänkö Koha Offline Circulation Tool? Valitse *Lisää*.

![](/assets/files/docs/Lainaus/KOCTlataus2.PNG)

Lisäosan kuvake tulee näkyviin selaimen oikeaan yläkulmaan.

![](/assets/files/docs/Lainaus/KOCTkuvake.PNG)


#### 2.19.2.2 KOCT-lisäosan käytön aloitus

Avaa lisäosa selaimen oikessa yläkulmassa näkyästä pikakuvkkeesta.
Mene asetuksiin "settings page"-linkistä.

![](/assets/files/docs/Lainaus/KOCTasetukset.PNG)

![](/assets/files/docs/Lainaus/KOCTasetukset2.PNG)

Anna parametrit seuraavasti:
1. Kohtaan *Server*: anna kimppasi Koha-osoite.
2. Kohtaan *Login*: oma Koha-käyttäjätunnus
3. Kohtaan *Password*: käyttäjätunnuksesi salasana.
4. Toiminnolla *Test configuration* voit testata asetuksia. Sivusto pyytää Koha-varmenteen todennuksen, joka pitää olla asennettuna koneelle. Hyväksy varmenne *OK*:lla. Jos asetukset ovat oikein, saat tiedon "Configuration ok".
6. Valitse kohtaan "Branchcode" kirjasto, jossa työskentelet.
7. Valitse kohtaan "Commit Type" **Apply directly to Koha**.
8. Tallenna tiedot lopuksi painamalla *Save*.

Nyt laajennuksen perusnäytön pitäisi näyttää tältä:

![](/assets/files/docs/Lainaus/KOCTasetukset3.PNG)

Kun lopetat KOCT-lisäosan käytön, muista tyhjentää kohdasta "Configuration page" omat tiedot kohdista Username ja Password. Jokainen käyttäjä tallentaa omat tunnukset ohjelmalle. Kohtia Server ja Branchcode ei tarvitse muuttaa, kun käyttäjä vaihtuu.
{: .notice--warning}


#### 2.19.2.3 Lainaaminen KOCT-lisäosalla

Avaa KOCT-lisäosa selaimen oikessa yläkulmassa näkyästä pikakuvkkeesta.
Lue asiakastunnus Patron barcode -kenttään ja lainattavan niteen tunnus Item barcode -kentään. Lainat kirjautuvat automaattisesti Transaction-kohdan alla olevaan taulukkoon. Kun kaikki asiakkaan lainat on luettu, valitse *Clear cardnumber*.

![](/assets/files/docs/Lainaus/KOCTlainaus.PNG)

![](/assets/files/docs/Lainaus/KOCTlainaus2.PNG)

*Apply to koha* - vie lainat suoraan Kohaan, kun ohjelma taas toimii. Kun lähetys on onnistunut, saat ilmoituksen: "Current status: Transaction completed".

*Clear* - tyhjentää lainatut lainat (ohjelma varoittaa lainoista, joita ei ole viety Kohaan).

*Clear added* - tyhjentää lainatut lainat (ei varoita lainoista, joita ei ole viety Kohaan).

*Export data* - tallentaa koneen lainat koneen oletuskansioon (lainojen tallentaminen Kohaan tehdään tiedonsiirron kautta).


#### 2.19.2.4 Palauttaminen KOCT-lisäosalla (ei suositella)

Lainat pitää ladata Kohaan ensin, ennen palautuksia.
Lue palautettavan lainan nidetunnus kohtaan "Item barcode". Palautettavan niteen tieto siirtyy taulukkoon. Lähetä palautetut lainat Kohaan toiminnolla *Apply to Koha*. 

Jos palautat lainoja KOCT:lla, ne on palautettava uudelleen Kohassa, kun se taas toimii.
{: .notice--warning} 

![](/assets/files/docs/Lainaus/KOCTpalautus.PNG)

Kun lopetat ohjelman käytön, mene ensin "Configuration page" -sivulle ja tyhjennä parametreista omat kirjautumistietosi. <br/>
Sulje lopuksi selain.
