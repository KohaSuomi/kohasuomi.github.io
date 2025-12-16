---
layout: single
permalink: /kati
hidden: true
header:
  overlay_color: '#5e616c'
  overlay_image: /assets/images/cropped-pexels-photo-113850.jpeg
toc: true
title: 'KaTi työryhmä'
---

## KaTi 16.12. klo 14-15

Läsnä: Antti Heikkinen, Suvi Kauranen, Leena Kinnunen, Kodo Korkalo, Marjukka Laapotti, Kati Sillgren, Timo Torvinen, Anna Viitanen, Anneli Österman

### Tiedonhaku

- Kun kaikki tietueet ovat periaatteessa kaikissa Koha-installaatioissa, kuinka huolehtitaan siitä, että

  1. "Normaali" tiedonhaut eivät palauta suurta määrää tyhjiä kuvailutietueita ilman niteitä.  
  2. Hankinnassa ja täydennyskuvailussa olemassaolevat tietueet kuitenkin löydetään muokattaviksi.

- Miten sellaiset tietueet, joilla oikeasti ei ole niteitä tällä hetkellä?
  - Pseudokappale, eli näennäinen nide tietueelle, jolla ei oikeasti ole niteitä. Pääsääntöisesti hyödynnettänee tätä.
  - Merkintä kuvailutietueeseen, että tietue otetaan indeksoinnissa mukaan, vaikka niteitä ei olekkaan? Tämä koskisi sitten kaikkia paikallisia Koha-instansseja, joten tietue näkyisi siitä eteenpäin kaikissa niistä.
  - Nitettömät tietueet raporttiin monivalintamahdollisuus ja kartoitus + toimintasuunnitelma kimpoittain miten toimitaan kunkin aineistotyypin osalta.
     - Päivitetty raportti löytyy osoitteesta: https://koha-suomi.fi/dokumentaatio/raporttikirjasto/#niteett%C3%B6m%C3%A4t-nimekkeet-versio-2
  
### Finna

- Kuinka ratkaistaan tietueiden näkyvyys Finnassa? Sielläkään ei haluta että "tyhjät" tietueet palautuvat asiakkaille.
  - OAI/PMH, voidaanko Finnan päässä haravointi ja indeksointi tehdä niin että niteettömät tietueet eivät palaudu lainkaan vai pitääkö asia hoitaa Kohan OAI:n päässä?
  
  - Mahdollisesti voidaan:
   
     1. Hyödyntää Finnan niteettömien tietueiden piilotusmahdollisuutta.    
     2. Injektoida OAI-haravoinnissa kenttään 942n (Supress in OPAC) kuvailutietueen piilotustieto.
     
- Biblionumberit tulevat muuttumaan, joten uusi haravointi tarvitaan.
- Miten hoidetaan asiakkaiden suosikkilistat, kirjastojen vinkkilistat ym biblionumberien muuttuessa?
   - Tarvittanee vastaavuuslista [vanha biblionumber] -> [uusi biblionumber] Finnaan toimitettavaksi päivitysajoja varten.

### Melinda

- Tietueiden linkitykset (SID-kentät), miten biblionumbereiden uudelleenkirjoitus vaikuttaa näihin?

   - Ei välttämättä ongelma, koska 001 + 003 säilyvät.
   - Mahdolliset kontrollinumeroristiriidat jos useammille tietueille jää sama kontrollinumero. Tämä on kuitenkin ehkä melko harvinaista, koska tietueet on tarkoitus deduplikoida.

### Eteneminen

- Tilanteen kartoitus
  - Kuinka suuri osuus tietueista on täysin identtisiä? (Kirjastopalvelu, Melinda ym)
     - Miten toisistaan poikkeavia huomautuskenttiä käsitellään?
     - Milloin tietue on "riittävän identtinen"? Mitä itseasiassa halutaan tarkistaa?
     - Tarkistetaan Melindan täsmäytyssäännöt (Antti lupasi vilkaista)
     - Kuvailutietueiden laatu.
  - Niteettömät
     - Artikkelit ja sen semmoiset
     - Lappi-osaston aineisto Lapissa
     - Mitä kaikkea on ja miten toimitaan niiden kanssa?
     - Pääkäyttäjät voivat tarkistaa mitä on ja mahdollisesti ehdottaa miten voisi toimia.
  - Esineet ja muut kummallisuudet
     - Pääkäyttäjät voivat tarkistaa mitä on ja mahdollisesti ehdottaa miten voisi toimia.
  - Paikalliset asiasanat ja muu kimppa- tai jopa kirjastokohtainen "sälä".
     - 59x kentissä mahdolisesti?
     - 852 kentät mahdollisesti pois
     - Pääkäyttäjät voivat tarkistaa mitä on ja miten voisi toimia.

- Teknisesti voitaisiin esimerkiksi yhdistellä Testien kannat yhdeksi tekemättä tällä hetkellä yhdistelyä lainkaan. Silloin jokaisen kimpan tietue säilyisi ja niitä olisi testiympäristössä alustavasti mahdollista vertailla keskenään. Testit eivät kuitenkaan ole täysiä kopioita tuotannoista. Yhdistelyllä päästäisiin kuitenkin käytännössä testaamaan miten jaettujen kuvailutaulujen malli toimisi.
   - Tehdään yhdistely tällä tavalla. Toteutus tammikuussa 2026.

### Seuraava kokous

- Sovitaan seuraava kokous doodlessa tammikuulle.

## KaTi aloituskokous 9.12. klo 14-15

Läsnä: Antti Heikkinen, Kodo Korkalo, Marjukka Laapotti, Kati Sillgren, Timo Torvinen, Anna Viitanen, Anneli Österman

### Tekniikka

- Kuvailuun liittyvien tietokantataulujen (biblio*) "shardaus" TäTiltä kimppojen Koha-instansseille

- Testattuna kuvailutietueiden näkyminen yhdestä pisteestä eri Koha-instansseille
  - Yhdistely tehtiin valitsemalla yksinkertaisesti pisin tietue ja liittämällä kaikki niteet siihen, eli sillee rautalankaa ja jeesusteippiä
  - Tiedonhakua ym ei juurikaan testattu/mietitty

- Tallennettavan ja varmistettavan datan määrä vähenee rajusti, kuvailutietueet muodostavat melko suuren osan Koha-kirjastojen datasta

- Edestakaisin siirreltävän datan määrä vähenee rajusti (valutuksesta voidaan luopua, paitsi tietenkin Melindan osalta)

### Kuvailu ja hankinta

- Miten ratkaistaan esimerkiksi kuvailutietueiden yhdistelyssä säilytettävät tiedot?
- Mitä asiasanoitusta otetaan mukaan yhdisteltäviin tietueisiin, mistä luovutaan?
  - Asiasanoituksen kieliversiot (suomi, ruotsi, saamen kielet, onko muita?) miten nämä suhtautuvat teoksen kieleen?
     - Ainakin Hellessä on lisätty ruotsinkielistä asiasanoitusta myös ei-ruotsinkieliselle aineistolle.
     - Pyrittänee mahdollisuuksien mukaan säilyttämään kaikkien yhdistettävien tietueiden asiasanoitus.
- Kaukolainamoduli
   - Kaukolainamoduli ei lisää tietueille 003 kenttää, joten sekaannusten ja väärien yhdistymisten vaara on olemassa. Kaukolainamodulia täytynee korjata siten että se lisää 003 kentät lisäämilleen tietueille.
   - Tiketöitävä erikseen, tai voi mahdollisesti korjaatua FA-kuvailupohjan käyttöönoton yhteydessä. FA-kuvailupohjan käyttö on työn alla.

- Miten hoidetaan esineiden ja muun "epätyypillisen" kirjastoaineiston (myös lehdet) kuvailu yhtenevästi, siten ettei meillä ole 400 kuvailutietuetta suksille?
  - Olemassaolevat yhdistetään mahdollisesti käsin.

- Missä kuvailu tehdään ja mitä työkaluja käyttäen?
  - Melinda, TäTi, paikalliskannat?
     - Tulevaisuudessa "vesiputousmalli" ja kansallinen kuvailuvaranto on toivottava kehityssuunta, mutta tässä vaiheessa ei ehkä ole järkevää vaatia kuvailijoita opettelemaan ensin Alephin käyttöä ja mutkia. Aleph on joka tapauksessa elinkaarensa päässä ja käytöstä poistuva järjestelmä.
     -Periaatteessa ei ole suurtakaan merkitystä, tehtäänkö kuvailu TäTissä vai paikalliskannoissa, tallennuspaikka on joka tapauksessa sama.
  - Koha vai joku muu kuvailujärjestelmä?
     - Koha lienee käytettävä järjestelmä, ainakin kunnes kuvailuun saadaan kansallinen ratkaisu.
  
- EDItX, onko tässä jotain huomioitavaa?
  - Hankintatietue tulee olemaan yhteiskannassa ja täsmäytys tehdään edelleen biblio* -taulujen kautta, joten ehkä ei vaikutusta
  
- Itse tehdyt hankintatietueet
  - Ensimmäinen "hankkija" tekee hankintatietueen, joka on siitä eteenpäin automaattisesti muidenkin hyödynnettävissä ja tarvittaessa täydennettävissä.
  
- Pupen tilausapuri
  - Muodostaa tietueita Kohaan esimerkiksi musiikkiaineistoille ja peleille. Rajapintana EDItX, joten pitäisi toimia ongelmitta.
  
- Oikeudet
  - Kuka saa käsitellä yhteistietokannassa olevia kuvailutietueita?
  - Kuvailijoiden määrä kimpoissa yleisesti ottaen vähenemään päin.
  - Karsinta? Kuka karsii ja millä kriteereillä?
  - Testataan vaatiiko tilauksen lisääminen tyhjästä tietueesta kuvailuoikeuden.
     - Annelin testauksen mukaan hankintaoikeus riittää, mutta tietuetta ei pysty ilman luettelointioikeutta muokkaamaan jälkikäteen.
     - Myös muita rajoituksia on olemassa, esimerkiksi jos ACQ-pohja on käytössä, ei kiinteämittaisia kenttiä pysty muuttamaan value builderien kautta. Kenttään voi kuitenkin kirjoittaa suoraan
     - Rajoitteet voitanee kuitenkin huomoida kuvailupohjan suunnittelussa.

### Seuraava kokous

- Tiistai 16.12. klo 14.
