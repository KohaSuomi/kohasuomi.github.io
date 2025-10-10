---
title: 'Kohan ohje suomeksi'
permalink: /dokumentaatio/kaukolainat/
redirect_from:
  - /theme-setup/
toc: true
---

# 14. Kaukolainaus

Kohan kaukolainamoduulilla pystyy hallinnoimaan asiakkaiden tekemiä kaukolainapyyntöjä. Osioon pääsee Kohan etusivulta Kaukolainapyynnöt-nappulasta tai Muita toimintoja -> Kaukolainapyynnöt. Toiminto näkyy vain, jos käyttäjällä on kaukolainoihin liittyvä käyttäjäoikeus.

## 14.1 Kaukolainapyynnön tekeminen

Kaukolainapyynnön voi tehdä Kaukolainamoduulin etusivulla kohdasta _Uusi kaukolainapyyntö_

![Kaukolainapyynnön lomake](/assets/files/docs/Kaukolainaus/kaukolainat1.png)

* Valitse kaukolainapyynnön tyyppi: Kirja, Luku, Lehti, Lehtiartikkeli, Opinnäytetyö, Kokous, DVD, Muu, Yleinen resurssi.
  * Kirja-tyyppinen pyyntö lisää tietokantaan tietueen syötetyillä tiedoilla käyttäen FA-kuvailupohjaa.
* Eri tyypit tuovat näkyville erilaisia kenttiä. Täytä tarpeelliset kentät.

![Kaukolainapyynnön teostiedot](/assets/files/docs/Kaukolainaus/kaukolainat2.png)

* Lisää tarvittaessa myös _Lisäkentät_ -kohtaan vapaamuotoisia tietoja
* Lisää lopuksi _Kirjastokortti, käyttäjätunnus tai sukunimi_ -kohtaan asiakkaan kirjastokortin numero ja _Noutokirjasto_ -kohtaan mistä kirjastosta hän noutaa kaukolainan.
  * Pyri käyttämään asiakkaan hakemiseen aina kirjastokortin numeroa, jotta pyyntö tallentuu oikealle asiakkaalle.

Kun tarvittavat tiedot on lisätty, valitse _Luo_, jolloin kaukolainapyyntö luodaan ja ohjelma siirtyy Kaukolainauksen etusivulle.

## 14.2 Kaukolainapyyntöjen listaus

Kaukolainamoduulin aloitussivulla listataan kaikki kaukolainapyynnöt. 

![Lista kaukolainoista](/assets/files/docs/Kaukolainaus/kaukolainat4.png)

Muilla moduulin sivuilla ollessa aloitussivulle pääsee _Näytä kaikki kaukolainat_ -napista.

![Näytä kaikki kaukolainat -nappi](/assets/files/docs/Kaukolainaus/kaukolainat3.png)

Kaukolainoja voi suodattaa vasemman reunan rajauksilla

![Rajauksilla voi suodattaa, mitä pyyntöjä näytetään](/assets/files/docs/Kaukolainaus/kaukolainat5.png)

## 14.3 Kaukolainapyyntöjen muokkaus

Valitse Muokkaa pyyntöä kaukolainapyyntöjen taulukon viimeisessä sarakkeessa tai ensimmäisestä sarakkeesta Pyynnön ID -numeroa. Riippuen pyynnön sen hetkisestä tilasta, voit nähdä kaikki tai osan seuraavista toiminnoista:

* Muokkaa pyyntöä
  * Voit muokata borrowernumberia, biblionumberia, kirjastoa ja lisätä huomautuksia. Jos on lisätty kaukolainapyyntöjen tiloja, voi niitäkin valita tässä näkymässä.
* Vahvista kaukolainapyyntö:
  * Tällä asetetaan pyynnön tilaksi "Pyydetty', jos pyyntöä ei ole tehty moduulin kautta.
* Pyydä yhteistyökumppaneilta
  * Tällä voi lähettää sähköpostilla pyynnön kaukolainakirjastoille.
* Vaihda toimittajaa (backend)
  * Tämä mahdollistaa pyynnön siirtämiseen toiseen backendiin.
* Poista pyyntö
  * Tällä saa poistettua pyynnön täysin. Pyynnön tietoja ei säilytetä Kohassa.
* Peruuta pyyntö
  * Tällä voi perua _Pyydetty_ ja _Pyydetty yhteistyökumppaneilta_ -tilat, jolloin pyynnön tilaksi asetetaan _Uusi_
* Merkitse valmiiksi
  * Tällä voi merkitä pyynnön valmiksi, kun pyydetty teos on esimerkiksi palautettu takaisin tilauskirjastoon tai artikkelikopio on luovutettu asiakkaalle.
* Muokkaa teoksen metatietoja
  * Täällä voi muokata pyydettävän teoksen tietoja.
* Näytä toimittajan metadata
  * Täällä voi katsoa pyydetyn teoksen tietoja, mutta ei muokata niitä.
* Kaukolainapyynnön loki
  * Tänne tallentuu pyyntöön liittyvät muutokset.
* Kommentit
  * Pyyntöön on mahdollista lisätä kommentteja, joilla voi seurata esimerkiksi pyynnön edistymistä ja tehtyjä työvaiheita. Kommentit ovat vain luettavissa ja ne tallennetaan aikajärjestyksessä. Kommentista näytetään tekijä, ajankohta ja sisältö. Jos pyyntöö liittyy kommentteja, näytetään niiden määrä kaukolainojen listauksessa aloitussivulla.
* Lainaus
  * Tämä toiminto on käytettävissä, mikäli CirculateILL-järjestelmäasetus on päällä. Tällä voi merkitä pyynnön asiakkaalle lainaan suoraan pyynnön tiedoista.

### 14.3.1 Pyyntöjen tilat

Kaukolainapyynnöillä voi olla seuraavanlaisia tiloja:

* Uusi pyyntö (NEW)
* Pyydetty (REQ)
* Pyydetty yhteistyökumppaneilta (GENREQ)
* Pyyntö peruutettu (REQREV)
* Peruutuspyyntö - asiakas on pyytänyt verkkokirjastossa pyynnön perumista (CANCREQ)
* Valmis (COMP)
* Lainattu (CHK)
* Palautettu kirjastoon (RET)
