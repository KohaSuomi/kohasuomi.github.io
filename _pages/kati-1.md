---
layout: single
permalink: /kati1
hidden: true
header:
  overlay_color: '#5e616c'
  overlay_image: /assets/images/cropped-pexels-photo-113850.jpeg
toc: true
title: 'KaTi yhteistietokanta'
---

# KaTi aloituskokous 9.12. klo 14-15

Läsnä: Antti Heikkinen, Kodo Korkalo, Marjukka Laapotti, Kati Sillgren, Timo Torvinen, Anna Viitanen, Anneli Österman

## Tekniikka

- Kuvailuun liittyvien tietokantataulujen (biblio*) "shardaus" TäTiltä kimppojen Koha-instansseille

- Testattuna kuvailutietueiden näkyminen yhdestä pisteestä eri Koha-instansseille
  - Yhdistely tehtiin valitsemalla yksinkertaisesti pisin tietue ja liittämällä kaikki niteet siihen, eli sillee rautalankaa ja jeesusteippiä
  - Tiedonhakua ym ei juurikaan testattu/mietitty

- Tallennettavan ja varmistettavan datan määrä vähenee rajusti, kuvailutietueet muodostavat melko suuren osan Koha-kirjastojen datasta

- Edestakaisin siirreltävän datan määrä vähenee rajusti (valutuksesta voidaan luopua, paitsi tietenkin Melindan osalta)

## Kuvailu ja hankinta

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

## Seuraava palaveri

- Tiistai 16.12. klo 14.
