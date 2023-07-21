---
title: 'Laskutustyökalu'
permalink: /dokumentaatio/laskutustyokalu/
redirect_from:
  - /theme-setup/
toc: true
---

Laskutustyökalulla voi tällä hetkellä luoda Finvoice- ja PDF-laskuja.

## Asennus ja päivitys

[Liitännäisen koodi GitHubissa](https://github.com/KohaSuomi/koha-plugin-overdue-tool/tree/22.xx).

![](/assets/files/docs/Ohjeet/laskutustyokalu.png)

## Käyttöönotto

Käyttöönotto vaatii muutamien asetusten lisäämistä.

* Käyttöoikeudet: Laskuttajat tarvitsevat seuraavat käyttäjäoikeudet: Plugins->tool, updatecharges, edit_borrowers ja edit_items. 
*HUOM! Muista lisätä käyttäjä myös liitännäisen asetukseen "Sallitut käyttäjät" (Yleiset-asetukset)!*

Laskuja varten täytyy lisätä ilmoituspohja, ODUECLAIM, joihin sisältö laitetaan *finvoice-*, *print-*, tai *pdf*-viestityypin pohjalle (muita tyyppejä on mm. Sähköposti, Tekstiviesti). finvoice-pohjaan määritellään Finvoice-sanoman sisältö ja pdf-pohjaan PDF-lasku HTML-muodossa. E-kirjeitä varten tehdään viestipohja ODUECLAIM-viestipohjaan print-pohjaan. ODUECLAIM-pohjaa muokkaamalla voidaan laskea osoitetietoja oikeaan kohtaan, tämä vaatii hieman html/css-tuntemusta. Viestipohjista on esimerkit saatavilla "Githubista":https://github.com/KohaSuomi/koha-plugin-overdue-tool/tree/21.11/Koha/Plugin/Fi/KohaSuomi/OverdueTool/examples. 

![](/assets/files/docs/Ohjeet/laskutustyokalu1.png)

### Viestipohjissa käytettävät tägit kootusti.

Laskutuspohjissa voi käyttää seuraavia tägejä.

Laskun numero: <<invoicenumber>><br />
Tilinumero: <<accountnumber>><br />
BIC: <<biccode>><br />
Laskun eräpäivä: <<invoice_duedate>><br />
Laskun eräpäivä (Finvoice muoto): <<finvoice_duedate>><br />
Viitenumero: <<referencenumber>><br />
Lainaajan nimi: <<issueborname>><br />
Lainaajan kirjastokortti: <<issueborbarcode>><br />
Maksettava yhteensä: <<totalfines>><br />
Y-tunnus: <<businessid>><br />
Laskuttajan nimi: <<grouplibrary>><br />
Laskuttajan osoite: <<groupaddress>><br />
Laskuttajan postinumero: <<groupzipcode>><br />
Laskuttajan postitoimipaikka: <<groupcity>><br />
Laskuttajan puhelinnumero: <<groupphone>><br />
Viimeiseksi lainatun niteen lainapäivä: <<lastitemissuedate>><br />
Viimeiseksi lainatun niteen eräpäivä: <<lastitemduedate>>


Teostiedot pitää "ympäröidä" <item> ja </item> tägeillä, jotta teostiedot tulostuvat laskulle. 

<item><br />
Eräpäivä: <<date_due>><br />
Teos: <<biblio.title>>  <<items.enumchron>> / <<biblio.author>><br />
Aineistotyyppi: <<biblioitems.itemtype>> <br />
Viivakoodi: <<items.barcode>><br />
Luokka: <<items.itemcallnumber>><br />
Korvaushinta: <<items.replacementprice>> €<br />
</item><br />

### Viestipohjat

[Esimerkit viestipohjista GitHubissa](https://github.com/KohaSuomi/koha-plugin-overdue-tool/tree/21.11/Koha/Plugin/Fi/KohaSuomi/OverdueTool/examples).

* FINVOICE-sanomaa varten käytetään ODUECLAIM-viestipohjassa finvoice-pohjaa/osiota.
* PDF-tulostusta käytettäessä käytetään ODUECLAIM-viestipohjaa ja viestin sisältö laitetaan pdf-pohjaan/osioon. Muista tehdä tarvittaessa kaikki kieliversiot. 
* E-kirjeenä lähtevien laskujen sisältö laitetaan ODUECLAIM-viestipohjaan *Tuloste*-pohjaan/osioon. Pohjaan laitetaan vain varsinainen viestin sisältö, ei lähettäjän tai vastaanottajan yhteystietoja. Viestin aihe -kentästä otetaan kirjeen "otsikko", joka tulostuu oikeaan yläreunaan. Muista tehdä tarvittaessa kaikki kieliversiot. Jos kieliversioita ei ole määritetty, käytetään Oletus-kielen tietoja.

### Määritys myöhästymisilmoituksiin

Myöhästymisilmoituksiin tulee määritellä sarake laskuille. Tästä asetuksesta käytetään vain viivettä, jolla haetaan laskutettava materiaali. Jos kaikilla kirjastoilla on sama viive, voi tehdä vain oletussäännön. Viestipohjakin pitää valita, koska ilman sitä tallennus ei onnistu.

![](/assets/files/docs/Ohjeet/laskutustyokalu2.png)

### Työkalun määrittäminen

Laskutustyökalu löytyy Työkalut -> Työkaluliitännäiset.

![](/assets/files/docs/Ohjeet/laskutustyokalu3.png)

Työkalun asetuksissa (Toiminnot -> Määrittely) voidaan säätää laskuja yleisellä ja laskutusryhmä kohtaisesti.
![](/assets/files/docs/Ohjeet/laskutustyokalu4.png)

Yleisissä asetuksissa voi määrittää seuraavia asioita:
* **Laskuttava kirjasto**: toimiiko laskuttavana kirjastona lainaava kirjasto vai niteen omistava kirjasto.
* **Näytä lainat eräpäivästä x kuukautta taaksepäin**: oletusasetus, kuinka vanhoja lainoja näytetään laskutustyökalussa.
* **Jätä laskuttamatta lainat, jotka ovat yli x vuotta vanhat**: oletusasetus, kuinka vanhoja laskuttamattomia lainoja näytetään laskutustyökalussa.
* **Laskutetun niteen "ei lainata"-tila**: määritä tähän laskutettavalle aineistolle asetettavan notforloan-tilan arvo. Se on aika yleisesti arvo 6.
* **Sallitut käyttäjät (borrowernumberit pilkulla erotettuna)**: kirjoita tähän niiden käyttäjien borrowernumberit, joilla on oikeus päästä laskutustyökaluun. Pääsy kannattaa sallia vain oikeasti laskutusta tekeville.

Ryhmäasetuksiin tulee näkyviin jokainen määritelty laskutusryhmä ja näkyvät asetukset ovat säädettävissä laskutusryhmäkohtaisesti.
  * laskutusryhmät määritetään liitännäisessä
  ![](/assets/files/docs/Ohjeet/laskutustyokalu5.png)
  * lisää kirjastot ryhmään alasvetovalikosta
  ![](/assets/files/docs/Ohjeet/laskutustyokalu6.png)

  * valitse ryhmän laskutustapa: Finvoice, E-lasku tai PDF-lasku
  ![](/assets/files/docs/Ohjeet/laskutustyokalu7.png)
    * **Finvoice** muodostaa laskuista finvoice-muotoisen xml-tiedoston, joka voidaan viedä kunnan laskutusjärjestelmään ja varsinaiset laksut lähetetään sieltä sitten asiakkalle.
    * **E-lasku** muodostaa asiakkaille e-kirjeenä lähetettävän laskun. Tämä vaatii, että kimpassa on käytössä e-kirjeiden lähetyspalvelu.
    * **PDF-lasku** muodostaa pdf-tiedoston/tiedostot, jotka laskuttaja voi itse tulostaa ja lähettää asiakkaille.

**Laskutusryhmän yhteystietoihin** voi lisätä tarpeelliset tiedot. HUOM! Tilinumero- ja BIC-tunnus-kentät ovat pakollisia kaikissa laskutusmuodoissa.
![](/assets/files/docs/Ohjeet/laskutustyokalu8.png)

**Viitenumerot** voivat olla kiinteitä tai juoksevia, kiinteän voi lisätä suoraan ODUECLAIM-pohjaan. Kunnan laskuttajilta tulee saada tiedot viitenumeroiden tekemiseen. *
* Juoksevaa viitenumeroa varten tarvitaan kehittäjän apua, plugin_data-tauluun pitää lisätä laskutusryhmälle siemenluku mistä viitenumero lasketaan. Siemennumero tulee lisätä OverdueTool-plugille ja plugin_key-kentän arvo pitää alkaa "REFNO_"
* ```INSERT INTO plugin_data (plugin_class, plugin_key, plugin_value) values ("Koha::Plugin::Fi::KohaSuomi::OverdueTool", "REFNO_<laskutusryhmän nimi>", "<siemenluku>");```
![](/assets/files/docs/Ohjeet/laskutustyokalu9.png)

**Rajoitus** voidaan asetettaa joko vain huollettavalle tai halutessa myös huoltajalle.
* Huomioi, että huoltajalle lisätty rajoite ei poistu automaattisesti, kun laskutetut aineistot palautetaan. Laskutettavalta asiakkaalta rajoite poistuu automaattisesti.
![](/assets/files/docs/Ohjeet/laskutustyokalu10.png)

**Niteen hinnan** voi lisätä asiakkaan maksuihin, mutta kannattaa huomioida, että jos käytössä on verkkokirjastossa verkkomaksumahdollisuus, asiakas voi vahingossa maksaa samat korvaushinnat sekä verkkomaksuna, että laskulla.
![](/assets/files/docs/Ohjeet/laskutustyokalu11.png)

Laskutettavista niteistä syntyneet **myöhästymismaksut** voidaan myös lisätä laskulle. Tässäkin kannattaa ottaa huomioon, että jos kimpalla on verkkokirjastossa käytössä verkkomaksutoiminto, voi asiakas maksaa myöhästymismaksut vahingossa kahteen kertaan.
![](/assets/files/docs/Ohjeet/laskutustyokalu12.png)

Jos laskutusryhmän laskuihin halutaan lisätä _Laskutuslisä_, syötä summa siihen tarkoitettuun kenttään.
![](/assets/files/docs/Ohjeet/laskutustyokalu13.png)

**Viesti asiakkaalle** -kenttään voit määrittää, minkälainen viesti laitetaan laskutetun asiakkaan (aikuisasiakas tai huoltaja) tietoihin. (Samanlainen viesti, mikä tulee Lisää viesti -toiminnolla)
![](/assets/files/docs/Ohjeet/laskutustyokalu14.png)

**Viesti huollettavalle tai virkaholhoojalle** -kenttään voit määrittää huollettavalle tai virkaholhoojalle lisättävän viestin.
![](/assets/files/docs/Ohjeet/laskutustyokalu15.png)

**Muuta takaajakäsittely (asiakastyypit pilkulla eroteltuna)** -kohdassa voi määrittää ne asiakastyypit, joilla on ns. virkaholhoojia. Jos tähän laitetaan asiakastyyppi, virkaholhoojan tiedot tallennetaan finvoice-sanomassa eriin kohtaan kuin se tapahtuisi "normaalissa" takaajakäsittelyssä. Tämä mahdollistaa laskutusjärjestelmissä virkaholhoojan tietojen viennin eri kenttiin kuin normaalitakaajan.
![](/assets/files/docs/Ohjeet/laskutustyokalu16.png)


## Laskujen tekeminen

Laskutustyökalu löytyy Työkaluista kohdasta Työkaluliitännäiset. Työkalu avautuu suoraan linkkiä klikkaamalla.

![](/assets/files/docs/Ohjeet/laskutustyokalu17.png)

* Laskutettava aineisto haetaan aikaväliltä. Sivulle tultaessa aikaväli muodostuu automaattisesti myöhästymisilmoituksissa olevan viiveen ja työkalun asetuksissa olevan "Näytä lainat eräpäivästä n kuukautta taaksepäin"-asetuksen mukaan. Aikaväliä voi muuttaa tarvittaessa.
* Laskutettava aineisto näkyy kunkin asiakkaan alla, tiedot saa auki asiakkaan tiedoissa olevasta nuolesta.
* Laskutettavasta aineistoista voi vielä tässä vaiheessa muokata korvaushintaa tai jättää jonkun aineiston pois laskulta ottamalla ruksin pois niteen kohdalta. Aineisto jolle ei ole määritelty korvaushintaa jätetään alustavasti pois laskulta, jos hinnan lisää aineisto laskutetaan. Jos hintatietoa muokkaa, tallennetaan uusi hinta myös niteen tietoihin.
* Kun on tarkistanut laskutettavan aineiston tiedot voi siitä luoda PDF:n, elasku-viestin tai Finvoice-sanoman. Tämä riippuu mitkä pohjat on lisätty laskutusryhmälle. Laskun luonti lisää niteille asetuksissa määritellyn "Laskutettu"-tilan. Jos sivun lataa uudestaan niin juuri äsken laskutettu aineisto ei enää näy listassa. Sen saa näkyviin kun valitsee "Näytä laskutetut".
** PDF:n, elasku-viestin ja Finvoice-sanoman luontiin käytetään käyttäjän kirjautumiskirjaston viestipohjaa. Jos laskuttaa kerralla useamman kirjaston aineistoa, pitää kirjautua siihen kirjastoon, jolle on luotu ODUECLAIM- tai FINVOICE-pohjat. Yleensä tämä on kunnan pääkirjasto.
* Tuloksia voi myös suodattaa asiakasryhmän ja minimisumman mukaan. Minimisumma kannattaa säätää nollaan, jotta mukaan tulee myös ne asiakkaat, joiden laskutettavien niteiden kaikki korvaushinnat ovat nolla tai tyhjä.

!Screenshot2021-12-22at13-46-46.png!

* Ennen PDF:n tulostamista pääsee esikatselu-näkymään, missä näkee sivun asettelun.
!2021-08-16at08-48-47Laskutustyökalu.png!

* Lasku luodaan asiakkaan ilmoituksiin, jolloin siitä jää jälki järjestelmään. Finvoice-sanomat lähetetään eteenpäin ajastetusti, joten korjauksia voidaan tehdä ennen lähetystä.

## Laskutettujen palautus

Kun asiakkaan kaikki laskutetut niteet palautetaan, poistuu asiakkaalta rajoite. Jos osaa laskutetuista niteistä ei palauteta, jää rajoite paikalleen. Niteille jää laskutettu-tila ja asiakkaan tietoihin tieto (viesti), että hänelle on lähettetty lasku. Nämä tiedot pitää poistaa manuaalisesti.
