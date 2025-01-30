---
layout: single
permalink: /asiantuntijaryhma2025
hidden: true
header:
  overlay_color: '#5e616c'
  overlay_image: /assets/images/cropped-pexels-photo-113850.jpeg
toc: true
title: 'Koha-Suomen asiantuntijaryhmä 2025'
---

Tältä sivulta löydät Koha-Suomen asiantuntijaryhmän vuoden 2025 muistiot. Uusin muistio on aina ylimmäisenä.

Koha-Suomen asiantuntijaryhmään kuuluvat Leena Kinnunen (Lapin kirjasto), Noora Valkonen (OUTI-kirjastot), Päivi Knuutinen (Vaara-kirjastot), Hanna Ikonen (Lumme-kirjastot), Tuomas Kunttu (Kyyti-kirjastot), Katri Sillgren (Helle-kirjastot), Susanna Sandell (Vaski-kirjastot), Janne Seppänen (Lastu-kirjastot) sekä Riikka Mustajärvi (Kirkes-kirjastot). Koha-Suomesta mukana on puheenjohtajana Ari Mäkiranta ja asiantuntijoina Anneli Österman ja Kodo Korkalo.

Asiantuntijaryhmän valitsee kerran vuodessa Koha-Suomen hallitus.

## Esityslista 2/2025


Aika: 12.2.2025 klo 13<br />
Läsnä:

### Ajankohtaiset

### Kohan signumiin vain luokka ja pääsana

Signum-työryhmä on nyt kokoontunut kolmesti ja tutkinut, testannut ja pohtinut [tiketin #923](https://github.com/KohaSuomi/Koha/issues/923) ehdotusta, että Kohan signumiin eli items.itemcallnumber-kenttään laitettaisiin vain luokka ja pääsana ja tullut siihen päätöksen, että ehdottaa asiantuntijaryhmälle ehdotuksen hyväksymistä.

Muutoksen etuja:

- Selkeys saatavuustiedoissa:
	- virkailija-Kohan saatavuustiedoissa näkyisi luokka ja pääsana, muut tarvittavat tiedot näkyvät viereisistä sarakkeista. Esim. nyt signumissa näkyvä PK kertoo että kyse on pääkirjastosta, mutta ei minkä kunnan pääkirjasto
	- varsinkin Finnassa signumissa näkyvät lyhenteet ovat täysin tarpeettomia asiakkaille. Luokka ja pääsana riittää.
- Seuraavia Koha-Suomen omia säätöjä saataisiin rutkasti yksinkertaistettua
	- Signum- ja pääsanapluginit https://github.com/KohaSuomi/Koha-23x/issues/17
	- Luokitusoppaissa omia järjestelysääntö-plugineja https://github.com/KohaSuomi/Koha-23x/issues/21
- Niteiden erämuokkauksessa ei enää ilmenisi sitä ongelmaa, ettei se osaa päivittää signumia esim. hyllypaikkaa muutettaessa. Vain erämuokkaus ja uusi tarra. Ei enää signumien muokkausta yksi kerrallaan.

Mihin ei vaikuta:
- tarroihin, niihin saadaan jatkossakin samat tiedot kuin tähänkin mennessä.

Mihin vaikuttaa:
- Perustiedot-näytöllä hyllypaikka- ja kirjasto-tieto katsottava kotikirjasto-sarakkeesta.
- Kaikkialla Kohassa, missä on "Luokka"-sarake, näkyy jatkossa vain luokka ja pääsana. Tarkistettava kimpoissa, että hyllypaikka-sarake on tarvittaessa näkyvillä eikä sitä ole piilotettu taulun asetuksissa.
- raportit ja viestipohjat tarkistettava, että niissä on jatkossa tarvittavat tiedot, jos on käytetty items.itemcallnumber-kentän tietoja.
- automaattien lajittelut: hyllypaikkatieto voidaan välittää bin-arvona SIP2SortBinMapping-järjestelmäasetuksen avulla
- tarratulostimen tarrapohjat pitää säätää niin, että tarvittavat tiedot saadaan tarroille. Lopputulos voi olla hieman erilainen kuin aiemmin, jos kirjastossa on lisätty käsin hyllypaikkatiedon yhteyteen esim. kirjasto- tai kokoelmatietoja, mutta tarrapohjalle saa tarvittaessa esim. kirjastolyhenteen tai kokoelmakoodin (selkokielisenä tai koodina).
- signum- ja pääsanaliitännäisistä voidaan suurimmasta osasta luopua ja tilalle tulee/tehdään vain yksi, joka muodostaa items.itemcallnumber-kenttään signumin muodossa "luokka pääsana".
- luokitusoppaiden järjestelysääntö-liitännäisissä voidaan luopua outi-mallisesta liitännäisestä.
- Finnassa nidetiedot selkeytyvät, kun saatavuustiedoista poistuu erilaiset lyhenteet
![kuva](https://github.com/user-attachments/assets/329c0bbb-e06b-41cc-a4f6-1283fad97b77)
- niteiden erämuokkauksessa pystyy kattavammin muokkaamaan signumeja, koska ei tarvitse huomioida hyllypaikkaa.


Muutoksen mahdollisia haittoja:
- voi aiheuttaa työjärjestysmuutoksia esim. tarratulostuksessa
- voi aiheuttaa muutoksia tarran ulkonäköön
- voi aiheuttaa muutoksia viestien sisältöön

### Käsiteltävät tiketit

* [Huollettavan asiakastiedon muokkaus: Asiakastakaaja-osion Suhde-arvo valmiiksi valituksi #302](https://github.com/KohaSuomi/Koha/issues/302)
  * Tehdäänkö JS-liitännäinen?
* [Tarratulostukseen mahdollisuus jakaa viivakoodeja toiselle käyttäjälle #1558](https://github.com/KohaSuomi/Koha/issues/1558)
* [Tarratulostukseen mahdollisuus ohittaa tietty kokoelmakoodi #1561](https://github.com/KohaSuomi/Koha/issues/1561)
* [Tarratulostukseen numerointi #1614](https://github.com/KohaSuomi/Koha/issues/1614)
* [Asiakastietoon muodostumaan automaattisesti Kohassa ja Finnassa näkyvä viesti liittyen omien tietojen tarkistamiseen #1573](https://github.com/KohaSuomi/Koha/issues/1573)
* [Yli 50 epäonnistunutta kirjautumista ei kirjaudu lokille eikä siitä aiheutuvaa rajoitusta muodostu asiakkaan tietoihin. #1635](https://github.com/KohaSuomi/Koha/issues/1635)



## Muistio 1/2025

Aika: 8.1.2025 klo 13<br />
Läsnä: Ari Mäkiranta, Anneli Österman ja Kodo Korkalo (Koha-Suomi) Kati Sillgren (Helle-kirjastot), Anni Rajala ja Susanna Sandell (Vaski-kirjastot), Janne Seppänen (Lastu-kirjastot), Noora Valkonen (OUTI-kirjastot), Riikka Mustajärvi (Kirkes-kirjastot), Hanna Ikonen (Lumme-kirjastot), Leena Kinnunen (Lapin kirjasto), Päivi Knuutinen (Vaara-kirjastot), Tuomas Kunttu (Kyyti-kirjastot)

### 1. Ajankohtaiset

Vuodenvaihteessa tehdään monenlaisia vuosittaisia ajoja kuten vuoden 2024 OKM-tilastot, julkisoikeudellisten maksujen vanhentamisajot sekä Teostolle lainatilastot. Myös epäaktiivisten asiakkaiden poistoajot ovat työn alla.

### 2. Seuraavan versionvaihdon ajankohta

Päätetään seuraavan versionvaihdon ajankohta. Jos vaihto tehdään entiseen tapaan toukokuussa, niin ehdolla on ollut aiemmissa kokouksissa viikkojen 20-21 maanantait. Lappi ja Siilinjärvi ilmoittanut ennakkoon, että kumpi tahansa viikko sopii. Vaski toivoo viikkoa 20.

Seuraavassa Kohan versiossa 24.11 on isoja muutoksia sivupohjien ylläpitoon, kun Bootstrap päivittyy versioon 5. Se muutos on edelleen yhteisössä osittain kesken, joten vaarana on, että otamme käyttöön huonosti toimivan järjestelmän.

Palvelimien ja Koha-asennusten käyttöjärjestelmät pitää päivittää täysin uuteen versioon, koska nykyisen käyttöjärjestelmän tukiaika päättyy 31.5.2025. Tämä on iso työ ja vie paljon työaikaresursseja.

**Päätös**: Vuonna 2025 ei tehdä versionpäivitystä. Varataan alustavasti aika versionvaihdolle maaliskuulle 2026. Kimpoissa selvitellään sopivat päivät.

### 3. Koha-seminaarin ohjelma

Ehdotuksia:
* OUTI: voisiko Turku esitellä kellutustyökalua
* taukojumppaa Koha-Suomen henkilökunnan toimesta
* Ari:
  * yhtiön toiminta
  * kyselee vielä tieteellisiltä aiheita
  * Esa-Pekka Kansalliskirjastosta
* Tiekartan painopistealueet: ryhmätyö?
* Karoliina Kanerva Kyytistä pitää lyhyen etäesityksen hallitustyöskentelystä
* Turku: RFID-haravatoteutuksen esittely
* Kaukolainamoduulin standardointi - missä mennään
* Bibframe - missä mennään
* Kellutuksen tilanne

### 4. Tiekartta

Käydään läpi tiekartta vuodelle 2025.

Liite: [Tiekartta2025.xlsx](https://github.com/user-attachments/files/18357482/Tiekartta2025.xlsx)

**Päätös**: Perustetaan ryhmä, joka tutustuu Kohan kaukolainamoduuliin. Mukaan Anneli ja kehittäjä Koha-Suomesta, Semenoffin Piia OUTIsta, Janne Seppänen Lastusta, Päivi Knuutinen Vaarasta. Muita halukkaita osallistujia voi ilmoittaa Annelille.

### 5. Vaski: noudettavien varausten käsittelyn nopeuttaminen

Susanna ja Anni esittelevät, mitä Vaski-kirjastoissa on suunniteltu noudettavien varausten käsittelyn nopeuttamiseksi.

**Päätös**: Käsittelyn nopeutus ei välttämättä vaadi isoja muutoksia Kohaan. Tarvetta voinee olla esimerkiksi noutoilmoitusten sisältöihin. Perustetaan ryhmä, joka miettii, miten varausten noudon prosesseja voisi virtaviivaistaa. Mukaan alustavasti Vaski, Lastu, Oulu. Kokoonkutsujana Susanna Sandell, eli ilmoittakaa hänelle, ketkä kaikki haluavat mukaan.


### 6. Kehitysehdotusten läpikäynti

* [Tarratulostukseen mahdollisuus jakaa viivakoodeja toiselle käyttäjälle #1558](https://github.com/KohaSuomi/Koha/issues/1558)
* [Tarratulostukseen mahdollisuus ohittaa tietty kokoelmakoodi #1561](https://github.com/KohaSuomi/Koha/issues/1561)

Siirretään käsittely seuraavaan kokoukseen.

### 7. PowerBI-vertaisryhmän tilannekatsaus

Ryhmään tarvittanee täydennystä jälkeenpäin mukaan liittyneistä kimpoista (Kirkes ja Lastu), Koha-Suomen edustus "kuunteluoppilaana" voisi ehkä olla myös hyvä, jotta Koha-Suomessakin tiedettäisiin ryhmän toiminnasta. Olisiko mahdollista tahdä ja julkaista PowerBI:tä varten vakiomuotoinen datasetti, jotta samaa työtä ei tarvitsisi tehdä kaikissa kimpoissa erikseen?

**Päätös:**
Ryhmää täydennetään ja Kirkeksestä mukaan tulee Uotilan Elina (Järvenpää). Lastusta kolme osallistumassa Lahdesta. Koha-Suomesta mukaan Emmi Takkinen, mutta seuraavaan palaveriin (ma 13.1.) osallistuu vapaan vuoksi joku muu kehittäjä.

### 8. KaTi-työryhmän perustaminen

Yhteiseen kuvailutietovarantoon siirtymistä varten tarvitaan työryhmä, jossa voidaan hahmotella esimerkiksi kuvailun työnjako ja tietueiden yhdistelysäännöt.

**Päätös**: Perustetaan ryhmä ja pyydetään kuvailuryhmää nimeämään ryhmän jäsenet. Koha-Suomen puolelta koollekutsujana ja koordinoijana Kodo. 

### 9. Muut asiat

* Hypernova on kysellyt, olisiko heidän asiakkaiden mahdollista poimia osakohteita TäTistä. Keskustellaan, onko tämä sopimusteknisesti ja teknisesti mahdollista.
  * Tekninen ongelma: meillä ei ole ulospäin aukiolevaa poimintayhteyttä ja sen toteuttaminen on työlästä ja laskutettavaa työtä.
  * Kimpat/kunnat ostavat kuvailutyötä Kirjastopalvelulta, onko sopimusteknisesti oikein jakaa dataa eteenpäin.
  * **Päätös**: Teknisesti ja sopimusteknisesti emme pysty avaamaan pääsyä TäTiin. Suosittelemme olemaan yhteydessä Melindaan poimintayhteyttä varten.
* Koha-workerien määrän dynaaminen säätäminen järjestelmään kohdistuvan kuorman mukaan tarvitsisi urhean pilottikimpan.
  * Lappi selvittää, voisiko he olla urhea pilottikimppa.
* Uutiskirjeen aikataulu ja vastuutus
  * Neljä kirjettä tuntui liian monelta viime vuonna, kimpoissa oli hankala keksiä sisältöä niin lyhyillä aikaväleillä.
  * Julkaistaan vuonna 2025 kaksi uutiskirjettä
    * maaliskuun loppu: Lastu keräysvastuussa
    * lokakuun loppu: Lumme keräysvastuussa
* Tikettien priorisointi -ryhmän järjestäytyminen
  * to 16.1. klo 13 tai ke 22.1. klo 14 

### 10. Seuraava kokous

Keskiviikkona 12.2.2025 klo 13-15.

