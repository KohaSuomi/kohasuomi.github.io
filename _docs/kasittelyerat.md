---
title: 'Kohan ohje suomeksi'
permalink: /dokumentaatio/kasittelyerat/
redirect_from:
  - /theme-setup/
toc: true
---

# 13. Käsittelyerät

Tämä ohje on päivitetty version 25.05 mukaiseksi.

Käsittelyerät-toimintoon pääset kahta reittiä.

* Etusivun _Käsittelyerät_-napista
* Muita toimintoja -valikosta _Käsittelyerät_-linkistä.

![Käsittelyerät-osioon pääsee joko Muita toimintoja -valikosta tai etusivulta Hankinnat-nappulasta](/assets/files/docs/Kasittelyerat/kasittelyerat.png)

Käsittelyerät-toiminnolla pystyy seuraamaan erilaisia aineiston käsittelyyn liittyviä työkulkuja kuten sitomoon vientejä, ditigointia, muovitusta yms. Niteet lisätään ensin odotuslistalle, jonka jälkeen ne liitetään sopivaan käsittelyerään.

Jotta toimintoa voi käyttää, pitää se ensin aktivoida PreservationModule-järjestelmäasetuksesta. Myöskin odotuslistalle ja käsittelyerille pitää määrittää ei-lainata-tilan oletusarvot NOT_LOAN -auktorisoituun arvoon sekä  PreservationNotForLoanDefaultTrainIn ja PreservationNotForLoanWaitingListIn -järjestelmäasetuksiin. 

Huom! Odotuslistalle ja käsittelyerälle kannattaa olla omat erilliset arvonsa.

## 13.1 Asetukset

Asetuksissa voi määrittää kahdentyyppisiä toimintoja.

1. Yleisiin asetuksiin odotuslistan ja käsittelyerän NOT_LOAN -auktorisoidun arvon määritykset.
2. Käsittelypohjat, joissa määritetään, mitä tietoja käsittelyerässä olevista niteistä näytetään.

![Käsittelyerien asetukset](/assets/files/docs/Kasittelyerat/kasittelyerat1.png)

### 13.1.1 Yleiset asetukset

Yleisissä asetuksissa voi määrittää odotuslistan ja käsittelyerän oletusarvot NOT_LOAN -auktorisoidulle arvolle. Samat määritykset voi tehdä myös järjestelmäasetuksista _PreservationNotForLoanDefaultTrainIn_ ja _PreservationNotForLoanWaitingListIn_.

Odotuslistalle ja käsittelyerälle kannattaa olla omat erilliset arvonsa. Odotuslista-sivun nidetaulukko muodostetaan notforloan-arvon perusteella, joten ei kannata käyttää siinä arvona mitään yleisesti käytössä olevaa arvoa. Nidetaulukko voi silloin muodostua niin suureksi, että järjestelmä ei osaa käsitellä niteiden määrää. Odotuslistalle ei ole olemassa omaa tietokannan taulua vaan tiedot kerätään ns. lennossa notforloan-arvon perusteella.

### 13.1.2 Käsittelypohjat

Käsittelypohjissa määritetään, mitä tietoja niteistä näytetään käsittelyerässä. Ilman pohjaa niteestä näytetään vain viivakoodi. 

Luo uusi pohja _Lisää uusi käsittelypohja_ -napista.

![Käsittelypohjan luonti](/assets/files/docs/Kasittelyerat/kasittelyerat2.png)

* _Käsittelypohjan nimi_ näkyy alasvetovalikossa, kun valitaan soveltuvaa käsittelypohjaa käsittelyerälle.
* _Viestipohja kuitille_ -kohdasta valitaan, mitä viestipohjaa käytetään, kun tulostetaan käsittelyerän niteille kuitteja.
  * Jos tähän ei tee valintaa, ei niteille pysty tulostamaan kuitteja.
  * Voit käyttää joko oletusviestipohjaa PRES_TRAIN_ITEM tai luoda uuden. Muista silloin valita moduuliksi Käsittelyerät.
 
Käsittelypohjaan voi lisätä erilaisia ominaisuuksia, kuten nimeke ja tekijä. Lisää uusi ominaisuus valitsemalla _Lisää uusi määre_.

* _Nimi_: ominaisuuden/määreen nimi
* _Tyyppi_: Vaihtoehtoja on kolme: auktorisoitu arvo, tietokannan sarake tai vapaateksti
* _Valinnat_: Valintaan voi tulla eri vaihtoehtoja riippuen siitä, mitä on valittuna tyyppi-kohdassa.
  * Jos tyypissä on valittuna _auktorisoitu arvo_, tulee tähän lista järjestelmään tallennetuista auktorisoiduista arvoista.
  * Jos tyypissä on valittuna _tietokannan sarake_, tulee tähän lista käytettävissä olevista tietokannan sarakkeista, esim. biblio.title.
  * Jos tyypissä on valituna _Vapaateksti_, valintaa ei tule tarjolle.

Tallenna käsittelypohja _OK_-napista.

Huom! Tyyppi ja Valinnat -riveillä toimii tietojen täydennys, eli voit alkaa kirjoittamaan kenttään haluamaasi tietoa ja valikko ehdottaa sitä vastaavia vaihtoehtoja.

Käsittelypohjia voi muokata jälkikäteen, mutta muutokset eivät päivity käsittelyeriin, jotka jo käyttävät kyseistä pohjaa. Käsittelypohja kannattaa tehdä täysin valmiiksi ennen kuin sitä käytetään käsittelyerissä.

## 13.2 Odotuslista

Käsittelyerien työprosessi alkaa lisäämällä niteet odotuslistalle. Niteiden ei-lainata-tila muuttuu asetusten mukaiseksi ja ovat näin pois lainattavista. Niin kauan kuin niteen ei lainata -tila ei muutu, pysyy se odotuslistalla.

![Odotuslista](/assets/files/docs/Kasittelyerat/kasittelyerat3.png)

### 13.2.1 Odotuslistalle lisääminen

Lisää niteitä odotuslistalle _Lisää odotuslistalle_ -napista.

![Odotuslista](/assets/files/docs/Kasittelyerat/kasittelyerat3.png)

Avautuu ikkuna, johon voit joko lukea tai kirjoittaa halutut viivakoodit. Lisää viivakoodeja yksi per rivi ilman välimerkkejä. Jos viivakoodit lisätään virheellisesti, siirtyy vain alimmainen arvo odotuslistalle.

![Niteiden lisääminen odotuslistalle](/assets/files/docs/Kasittelyerat/kasittelyerat4.png)

Kun olet lisännyt halutut viivakoodit, valitse sitten _Save_. Näkymä palaa odotuslistan etusivulle.

Sivulle ilmestyy uusi nappi _Lisää viimeiset x nidettä käsittelyerään_, jota painamalla juuri viedyt niteet saa vietyä suoraan jo olemassa olevaan käsittelyerään.

## 13.3 Käsittelyerät

Käsittelyerät-välilehdellä voit lisätä ja seurata käsittelyeriäsi.

![Käsittelyerät-välilehti](/assets/files/docs/Kasittelyerat/kasittelyerat5.png)

Taulukossa listataan kaikki käsittelyerät. Taulukko pitää sisällään seuraavat tiedot:

* _Nimi_: Käsittelyerän nimi
* _Luotu_: Käsittelyerän luontipäivä
* _Suljettu_: Käsittelyerän sulkupäivä
* _Lähetetty_: Käsittelyerän lähetyspäivä
* _Vastaanotettu_: Käsittelyerän vastaanottopäivä
* _Toiminnot_:
  * _Muokkaa_-napista voit muokata käsittelyerän tietoja
  * _Poista_-napista voit poistaa käsittelyerän
  * _Lisää niteitä_ -napista voit lisätä käsittelyerään odotuslistalle olevia niteitä.
 
### 13.3.1 Uusi käsittelyerä

_Uusi käsittelyerä_ -nappulasta saat lisättyä käsittelyerän.

![Uusi käsittelyerä](/assets/files/docs/Kasittelyerat/kasittelyerat6.png)

* _Nimi_: Kuvaava nimi käsittelyerälle
* _Kuvaus_: Lisätietoja käsittelyerästä
* _Käsittelyerään lisätyn niteen tila_: Tähän tulee automaattisesti asetuksissa määritetty oletusarvo, mutta sen voi vaihtaa toiseksi valikosta.
* _Oletuskäsittelypohja_: Valitse sopiva käsittelypohja.

### 13.3.2 Niteiden lisääminen käsittelyerään

Voit lisätä niteitä käsittelyerään kahta kautta:

* Odotuslistalta  _Lisää viimeiset x nidettä käsittelyerään_ -napista sen jälkeen, kun olet lisännyt niteet odotuslistalle.
* Käsittelyerän kohdalta _Lisää niteitä_ -napista. Huomaa, että lisättävät niteet täytyy olla odotuslistalla.
![Lisää nide käsittelyerään Korjattavat](/assets/files/docs/Kasittelyerat/kasittelyerat7.png)
![Nide lisätty käsittelyerään](/assets/files/docs/Kasittelyerat/kasittelyerat8.png)

Niteet näkyvät käsittelyerässä taulukossa. Taulukon sarakkeet noudattavat valitun käsittelypohjan mukaisia määrittelyjä.

![Nide lisätty käsittelyerään](/assets/files/docs/Kasittelyerat/kasittelyerat9.png)

### 13.3.3 Käsittelyerän sulkeminen ja lähettäminen

Kun kaikki halutut niteet on lisätty käsittelyerään, valitse ylhäältä _Sulje_.

_Sulje_-napin tilalle tulee _Lähetä_-nappi ja käsittelyerään ei voi enää lisätä niteitä.

![Käsittelyerä suljettu](/assets/files/docs/Kasittelyerat/kasittelyerat10.png)

* Voit tässä vaiheessa halutessasi tulostaa niteille kuitin valitsemalla niteet ja valitsemalla _Tulosta kuitteja_.

Kun kaikki on valmista, valitse ylhäältä _Lähetä_, jolloin käsittelyerän Lähetetty-arvoon kirjautuu lähetyspäivä. Tästä näkee, milloin niteet on lähetetty tai viety käsiteltäväksi. Yläreunaan tulee _Lähetä_-napin tilalle _Vastaanota_-nappi.

![Käsittelyerä lähetetty](/assets/files/docs/Kasittelyerat/kasittelyerat11.png)

### 13.3.4 Käsittelyerän vastaanottaminen

Kun niteet palautuvat saamastaan käsittelystä, vastaanotetaan käsittelyerä _Vastaanota_-napilla.

![Käsittelyerä vastaanotettu](/assets/files/docs/Kasittelyerat/kasittelyerat12.png)

* _Vastaanotettu_-riville kirjautuu erän vastaanottopäivä.
* Käsittelyerän voi tässä vaiheessa halutessaan poistaa _Poista_-napista.

## 13.4 Niteeltä ei-lainata-tilan poistaminen

Käsittelyerän vastaanottaminen ei poista niteeltä sille asetettua ei-lainata-tilaa. Se pitää poistaa joko niteiden erämuokkauksella tai määrittää  UpdateNotForLoanStatusOnCheckin-järjestelmäasetukseen, että kyseinen tila poistetaan palautettaessa.
