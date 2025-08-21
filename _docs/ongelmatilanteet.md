---
title: 'Ohjeita ongelmatilanteisiin'
permalink: /dokumentaatio/ongelmatilanteet/
redirect_from:
  - /theme-setup/
toc: true
---

Tähän dokumenttiin kerätään kimppojen pääkäyttäjille tavallisimmat ongelmatilanteet ja neuvot niiden selvittämiseen.

## Koha ei aukea

Tarkista ensin:
* avautuvatko muut verkkosivut? 
  * **ei**, kyseessä on todennäköisesti tietoliikennevika ja yhteys otetaan paikalliseen atk-tukeen.
  * **kyllä**, tarkista onko kyseessä vain yksi Kohan osio vai kaikki/osa

* onko kyseessä kaikki Kohan osiot vai vain yksi (esim. hankinta)

* minkä virheilmoituksen saat?
  * KOHA IS STOPPED DUE TO CHECKSUM MISMATCH IN SYSTEM PREFERENCES. PLEASE CONTACT YOUR SYSTEM ADMINISTRATOR. -> Joku on säätänyt IntranetUserJS-järjestelmäasetusta ja tarkistussumma ei enää vastaa konfiguraatiossa olevaa. Soita järjestelmänkehittäjien päivystyspuhelimeen.

* toimiiko englanninkielisessä versiossa?

* kysele Matrixissa muilta pääkäyttäjiltä, onko muilla kimpoilla samaa ongelma

Jos yllä olevista ei ole apua, soita kehittäjien päivystysnumeroon, joka on pääkäyttäjillä tiedossa.

## Asiakasviesti ei ole lähtenyt

* onko asiakkaan yhteystiedot ja viestiasetukset oikein?

* tarkista asiakkaan tiedoista Ilmoitukset-välilehdeltä, onko viesti muodostunut
  * missä tilassa viesti on? (sent, failed, pending)
  * minkä muotoinen viesti on kyseessä? (email, sms, kirje)


* Jos yhteystiedot ja viestiasetukset ovat oikein, voit yrittää lähettää viestin uudelleen. Avaa ilmoitus ja paina linkkiä ”Lähetä uudelleen”. Viestit lähetetään uudelleen seuraavassa cron-ajossa.
* Jos yhteystiedot oli väärin, huomioi seuraavat asiat ennen uudelleen lähettämistä:
  * sähköpostiosoitteen muutos vaikuttaa vasta seuraaviin, uusiin, lähetettäviin viesteihin eli väärään osoitteeseen, epäonnistunutta sähköpostiviestiä ei kannata lähettää uudelleen. 
  * tekstiviestinumeron muutos vaikuttaa heti ja viestin voi lähettää uudelleen.

## Asiakasviesti on lähtenyt, mutta asiakas ei saa viestiä

### Tekstiviestit

* voiko asiakkaan puhelin(liittymä) vastaanottaa tekstiviestiä eli tuleeko tekstiviestejä muualta?
  * auttaako puhelimen uudelleenkäynnistys?
  * tuleeko viestit perille, jos asiakas käyttää sim-korttia toisessa puhelimessa?
* onko mahdollisesti asiakkaan puhelimessa esto kirjaston tekstiviesteille?

### Sähköpostiviestit

* onko viesti päätynyt roskapostikansioon tai johonkin muuhun automaattiseen kansioon kuten Uutiskirjeet.
* onko asiakkaalla viestin lajittelusääntöjä, jotka siirtävät viestin muualle kuin Saapuneet-kansioon
* asiakasta voi pyytää lisäämään viestin lähettäjän osoitteen (monesti kotikirjaston osoite tai se osoite, joka kirjaston tietoihin on merkitty lähettäjäksi) sallittujen/luotettujen listalle. Osassa sähköposteissa lähettäjän osoiteen lisääminen omaan osoitekirjaan myös auttaa. Näin sähköpostipalvelun tarjoaja tietää, että kyseessä ei ole roskaposti tai muuten epäilyttävä viesti.
* onko asiakkaalla tietoihin tallennetussa osoitteessa kääntö toiseen osoitteeseen? Alla erilaisia esimerkkitapauksia.
  * tiedoissa on iki.fi-päätteinen osoite, joka ohjaa viestit eteenpäin toiseen osoitteeseen, jolloin vastaanottava palvelu hylkää viestin.
  * kääntö toiseen osoitteeseen, jolloin käännön vastaanottajan palvelu hylkää viestin, esim. hotmailista outlookiin.
  * kääntö toiseen osoitteeseen, mutta viesti on päätynyt roskapostiin alkuperäisessä osoitteessa, jolloin sitä ei ole käännetty.

### Kirjeet

* jos käytössä on ekirje-palvelu, tarkista, onko kirjetiedosto päätynyt ekirje-toimittajalle ja onko kirjeet lähteneet heiltä eteenpäin.
  * kirjeet näkyvät Kohassa lähetettyinä, kun ne on toimitettu eteenpäin ekirjepalvelun toimittajalle.

## Lainaus/palautusautomaatti ei saa yhteyttä Kohaan

Tarkista:
* toimiiko verkkoyhteys?
  * Jos ei -> yhteys paikalliseen atk-tukeen
* toimiiko Koha?
  * jos ei -> yhteys järjestelmänkehittäjien päivystysnumeroon

* vika voi myös olla automaatin ohjelmistossa tai sen asetuksissa/määrittelyissä
  * ota yhteyttä automaatin toimittajaan

## Väärä eräpäivä

Tarkista:
* kirjaston eräpäiväkalenteri
* kirjautuneen käyttäjän koti/kirjautumiskirjasto
* laina- ja maksusäännöt
* lainaavan asiakkaan asiakastyyppi (eri asiakastyypeille voi olla erilaisia laina-aikoja) ja kotikirjasto.

## Kuitti ei tulostu

Tarkista:
* onko tulostin päällä?
  * sammuta tulostin ja anna olla kiinni n. 20 s ja käynnistä uudelleen.
* onko tulostimen ajurit asennettu?
* saako kuittitulostimelle tulostettua esim. Muistio-ohjelmasta?
* onko selaimen tulostusasetukset määritetty oikein? Tarkista [Kuittitulostuksen asetukset](https://koha-suomi.fi/dokumentaatio/kuittitulostuksen-asetukset/).
* onko kuittipohja määritetty oikein? Työkalut -> Ilmoitukset ja kuitit

## Hyllyvarauslistalle tulee niteitä, joita siellä ei kuuluisi olla

* tarkista lainasäännöt sekä niteen omistavalta kirjastolta että sen kirjaston säännöt, johon varaus on menossa
* jos kirjastolle tehdään yksikin sääntö, kaikki kirjaston yleissäännöstä poikkeavat säännöt kuten lyhytlainat pitää määrittää erikseen kyseiselle kirjastolle
