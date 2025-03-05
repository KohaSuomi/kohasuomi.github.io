---
title: 'Kohan ohje suomeksi'
permalink: /dokumentaatio/maksut/
redirect_from:
  - /theme-setup/
toc: true
---
# 3. Maksut

Asiakkaalla voi olla julkisoikeudellisia ja yksityisoikeudellisia maksuja. 

**Julkisoikeudelliset maksut:**
- Myöhästymismaksut, palautuskehotusmaksut ja noutamattoman varauksen maksut.
- Vain julkisoikeudelliset maksut voivat aiheuttaa asiakkaalle lainauskiellon, jos maksut ylittävät lainauskieltorajan.
- Maksut vanhenevat 5 vuoden kulutta sitä seuraavan vuoden alussa.
- Vanhentuneiden maksujen mitätöintiajot ajetaan kimpoissa heti vuoden alussa. Ajot otettiin käyttöön vuoden 2024 alusta alkaen.

**Yksityisoikeudelliset maksut:**
- Kaikki muut asiakkaan maksuissa olevat maksut, esim. kaukopalvelumaksu, aineiston korvausmaksut, uuden kirjastokortin maksu.
- Maksut eivät vaikuta lainauskieltorajaan.
- Maksut vanhenevat 3 vuoden kuluttua.
- Vanhentuneiden maksujen mitätöintiajot ajetaan kimpoissa heti maksun vanhenemispäivän jälkeisenä yönä. Huom! Ajot otetaan käyttöön vuoden 2024 alusta alkaen.

Maksut näkyvät eriteltynä asiakkaan tiedoissa:
![](/assets/files/docs/Maksut/Maksuerittely.PNG)

Esimerkissä asiakkaalla on 19,50 € julkisoikeudellisia maksuja, jotka vaikuttavat lainauskieltorajaan. Asiakkaalla on maksuja yhteensä 31,50 €. Yhteissumma sisältää myös maksut, jotka eivät vaikuta lainauskieltoon. Esimerkkitapauksessa asiakkaalla on yksityisoikeudellisia maksu 12,00 €.

<br>

Asiakkaan maksuihin pääsee asiakkaan tiedoissa vasemassa reunassa olevasta palkista "Maksut" tai Huomio-kentässä
olevalla _Maksa_-näppäimellä.

<br>

Jos asiakkaalla on taattavia ja heillä on maksuja, heidän maksunsa näkyvät _Taattavien maksut_-välilehdellä. Välilehdellä on eroteltuina kirjastokorttien numeroilla asiakkaan taattavat ja heidän tileillään olevat maksut. Taattavan kirjastokortin numeroa klikkaamalla pääsee suoraan taattavan kortin tietoihin.

![](/assets/files/docs/Maksut/Taattavat02.png)


Huom! Jos kirjastossa on käytössä kassajärjestelmä, joka on
yhteydessä kirjastojärjestelmään, ohje löytyy kohdasta 3.5.

## 3.1. Tapahtumat -välilehti

Asiakkaan maksuhistoria näkyy maksuissa Tapahtumat-välilehdellä. Siellä näkyy
myöhästymismaksujen lisäksi kaikki Kohan kautta käsitellyt maksut, esim.
uusi kortti, noutamaton varaus, palautuskehotus, jne.

![](/assets/files/docs/Asiakkaat/Tapahtumat8.png)

Tällä näytöllä on seuraavat sarakkeet:

\- _Luotu:_ päiväys, jolloin maksu luotiin

\- _Päivitetty:_ päiväys, jolloin maksuriviä on päivitetty

\- _Maksun tyyppi:_ tapahtuman selite

\- _Maksujen kuvaus:_ tieto mistä niteestä maksu muodostuu ja myöhästyneen
niteen eräpäivä sekä linkki nidetietoon

\- _Viivakoodi:_ Niteen viivakoodi -linkki

\- _Eräpäivä:_ Lainan eräpäivä

\- _Palautuspvm:_ Lainan palautuspäivä

\- _Lainauspvm:_ Niteen lainauspäivä

\- _Lainauspiste:_ Kirjasto, josta nide on lainattu

\- _Kotikirjasto:_ Niteen kotikirjasto

\- _Huomautus:_ tähän tulee maksuun liittyvä huomautus esim. Online transaction-koodi, manuaalisesti lisätty tieto 

\- _Summa:_ maksettavien maksujen kokonaissumma

\- _Maksettavaa:_ vielä maksamatta oleva määrä

\- _Toiminnot:_ Kimppakohtaisia eroja tämän sarakkeen painikkeissa.

![](/assets/files/docs/Asiakkaat/Toiminnot3.png)

- "Tulosta" vie ko. maksun tiedot tulostusnäkymään.

- "Tiedot" vie ko. maksun veloitustietoihin.

![](/assets/files/docs/Asiakkaat/Veloitustiedot.png)

- "Maksa" vie Maksa maksuja -välilehdelle maksamaan ko. yksittäisen maksun.

![](/assets/files/docs/Asiakkaat/Toiminnotmaksa.png)

- _Peruuta veloitus_ -painiketta painamalla ko. maksu peruuntuu.

![](/assets/files/docs/Asiakkaat/Peruutaveloitus.png)

- "Luo hyvitys"

![](/assets/files/docs/Asiakkaat/Luohyvitys2.png)

- "Mitätöi maksutapahtuma"

![](/assets/files/docs/Asiakkaat/Mitatoimaksutapahtuma.png)

Mitätöinnin jälkeen maksu näkyy uudella rivillä seuraavasti:

![](/assets/files/docs/Asiakkaat/Mitatoimaksutapahtuma2.png)

- "Käytä alennusta"

![](/assets/files/docs/Asiakkaat/Kaytaalennusta.png)

## 3.2. Maksa maksuja -välilehti

### 3.2.1 Maksujen maksaminen rivi kerrallaan

Jokaisen rivin maksu voidaan maksaa tai poistaa erikseen klikkaamalla
rivillä joko _Maksa_ tai _Poista_. Maksu voidaan maksaa kokonaan tai
osittain. Maksukäytännöissä voi olla kirjastokohtaisia eroja.

![](/assets/files/docs/Asiakkaat/maksurivi.png)

Maksun maksaminen riviltä kokonaan

\- Valitse _Maksa_ sen maksun kohdalla, mikä maksetaan

- Maksun summa tulee Maksettava summa -laatikkoon

\- Klikkaa _Hyväksy_.

- Maksu poistuu maksamattomista maksuista ja näkyy kokonaan maksettuna.

Maksun maksaminen riviltä osittain

![](/assets/files/docs/Asiakkaat/osamaksu2.png)

\- Valitse _Maksa_ sen maksun kohdalla, mikä maksetaan.

- Muokkaa summaa, joka tulee Maksettava summa -laatikkoon.
  
- Jos tarjottu rahamäärä on enemmän kuin maksettava summa, järjestelmä laskee vaihtorahan valmiiksi.
- Tarjottavan rahamäärän pitää olla vähintään sama, kuin maksettava summa.
  
- _Hyväksy_.

\- Loput maksusta jää Maksettava- sarakkeeseen Maksa
maksuja-välilehdelle.

### 3.2.2 Maksujen poistaminen rivi kerrallaan

\- Klikkaa Poista sen maksun kohdalta, joka poistetaan. Jatka
valitsemalla Poista tämä maksu.

![](/assets/files/docs/Asiakkaat/poistamaksu2.png)

Maksu siirtyy Maksa maksuja-välilehdeltä Tili-välilehdelle.

![](/assets/files/docs/Asiakkaat/poistettu2.png)

### 3.2.3. Maksa kaikki maksut

\- Klikkaa _Maksa kaikki_ -nappia.

\- Klikkaa _Hyväksy_.

### 3.2.4. Maksa jokin tietty summa maksuista

\- Klikkaa _Maksa kaikki_ -nappia.

- Kirjoita _Maksettava summa_ -laatikkoon asiakkaalta perimäsi rahamäärä.
  Kokonaisvelka näkyy Saatavia yhteensä -kohdassa.

![](/assets/files/docs/Asiakkaat/maksa2.png)

\- Klikkaa _Hyväksy_.

\- Maksu päivittyy kuittaamaan vanhimmat maksut ensin.

### 3.2.5. Maksa valitut maksut

\- Laita valintamerkki niiden maksujen kohdalle, jotka maksetaan,
klikkaa _Maksa valitut_.

![](/assets/files/docs/Asiakkaat/maksa33.png)

Valittujen maksujen summa näkyy Maksettava summa -laatikossa.

![](/assets/files/docs/Asiakkaat/maksa4.png)

\- Klikkaa _Hyväksy_.

- Maksu päivittyy kuittaamaan valitun maksun.

### 3.2.6. Poista kaikki maksut

Klikkaa _Poista kaikki maksut_ -nappia listauksen alapuolella

![](/assets/files/docs/Asiakkaat/maksa5.png)

\- Kaikki maksut poistuvat saatavista ja näkyvät poistettuina maksuina

### 3.2.7. Maksun peruminen

Jos vahingossa merkitset niteen maksun maksetuksi, voit kumota maksun
klikkaamalla Toiminnot-sarakkeessa _Peruuta_.

![](/assets/files/docs/Asiakkaat/maksa6.png)

\- Klikkauksen jälkeen tulee uusi rivi, jossa näkyy maksun peruutus

![](/assets/files/docs/Asiakkaat/maksa7.png)

Peruutuksen voi vielä perua klikkaamalla uudelleen _Peruuta_.

## 3.3. Luo maksu -välilehti

Sellaisia maksuja, joita järjestelmä ei tee automaattisesti, voi
virkailija tallentaa Luo maksu -välilehdellä.

![](/assets/files/docs/Asiakkaat/maksunkuvaus.png)

\- Valitse ensin maksun tyypppi.

- Jos maksu liittyy johonkin niteeseen, voit lisätä sen viivakoodin
  linkiksi niteeseen.

- Kuvaus-kenttään voi antaa maksun kuvauksen.

- Summa-kenttäään annetaan pelkästään maksun määrä (vain numeroita ja
desimaaleja).

- Määrä-kohtaan voi kirjata esim. kopioiden määrän. 
Ohjelma laskee summan automaattisesti.

- Tallennuksen jälkeen maksu näkyy yhteenvedossa. 
Maksun voi maksaa myös samantien klikkaamalla _Tallenna ja maksa_.

![](/assets/files/docs/Asiakkaat/maksunsumma.png)

## 3.4. Luo hyvitys -välilehti

Tämä toiminto luo asiakkaalle saldoon “plussasaldoa”. Hyvitystä voidaan
käyttää maksujen maksamiseen tai maksun anteeksiantoon. HUOM! Tarkista
ensin kirjastosi käytäntö plussasaldon lisäämisestä asiakkaalle. Tämän
käyttäminen ei ole sallittua mm. OUTI-kirjastoissa.

\- Valitse ensin hyvityksen tyyppi.

\- Jos maksu liittyy johonkin tiettyyn niteeseen, lue niteen viivakoodi
Viivakoodi-kenttään.

\- Kuvaus-kenttään voit kirjoittaa selityksen.

- Anna Summa-kenttään vain numeroita ja desimaaleja, ei
  valuuttamerkkejä.

## 3.5. Maksujen maksaminen Ceepos-kassaliittymän kautta

### 3.5.1. Valmistelut ennen maksujen vastaanottoa

Asiakkaan lainausnäytöllä valitse *Maksut*, sieltä löytyy *Maksa maksuja*-välilehti. Valitse sieltä ne
maksut, jotka asiakas maksaa ja klikkaa *Maksa valitut*.

![](/assets/files/docs/Maksut/maksut1.png)

*Maksutyyppi*-kohtaan valitaan toimipistekoodi, ellei se ole jo siinä valmiina. Sen jälkeen 
klikkaa *Ceepos-maksu*.

![](/assets/files/docs/Maksut/maksavalitutmaksut1.png)

### 3.5.2. Maksun lähettäminen kassaohjelmaan

Kun klikkaat *Ceepos-maksu*, tulee ilmoitus *Maksu lähetetty, käsittele kassassa!* Klikkaa *ok*.

![](/assets/files/docs/Maksut/maksut3.png)

Voit siirtyä Ceeposiin ja veloittaa asiakkaalta maksun. Toimi kirjaston Ceepos-ohjeiden mukaisesti
ja palaa sitten takaisin Kohaan, jossa asiakkaan maksut ovat
automaattisesti merkitty suoritetuiksi.

Ongelmatilanteissa ota yhteyttä joko oman kirjaston/kimpan Koha-tukeen
tai kirjastosi Ceepos-ohjelman pääkäyttäjään.
