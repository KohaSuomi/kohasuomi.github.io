---
title: 'Kohan ohje suomeksi'
permalink: /dokumentaatio/maksut/
redirect_from:
  - /theme-setup/
toc: true
---
# 3. Maksut

Asiakkaan maksuihin pääsee asiakkaan tiedoissa vasemassa reunassa olevasta palkista "Maksut" tai Huomio-kentässä
olevalla "Maksa"-näppäimellä.

Huom! Jos kirjastossa on käytössä kassajärjestelmä, joka on
yhteydessä kirjastojärjestelmään, ohje löytyy kohdasta 3.5.

## 3.1. Tapahtumat -välilehti

Asiakkaan maksuhistoria näkyy maksuissa Tapahtumat-välilehdellä. Siellä näkyy
myöhästymismaksujen lisäksi kaikki Kohan kautta käsitellyt maksut, esim.
uusi kortti, noutamaton varaus, palautuskehotus..

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

- "Tulosta" vie ko. maksun tiedot tulostusnäkymään

- "Tiedot" vie ko. maksun veloitustietoihin

![](/assets/files/docs/Asiakkaat/Veloitustiedot.png)

- "Maksa" vie Maksa maksuja -välilehdelle maksamaan ko. yksittäisen maksun.

![](/assets/files/docs/Asiakkaat/Toiminnotmaksa.png)

- "Peruuta veloitus" -painiketta painamalla ko. maksu peruuntuu.

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
rivillä joko Maksa tai Poista. Maksu voidaan maksaa kokonaan tai
osittain. Maksukäytännöissä voi olla kirjastokohtaisia eroja.

![](/assets/files/docs/Asiakkaat/maksurivi.png)

Maksun maksaminen riviltä kokonaan

\- Valitse Maksa sen maksun kohdalla, mikä maksetaan

- Maksun summa tulee Peri asiakkaalta: -laatikkoon

![](/assets/files/docs/Asiakkaat/periasiakkaalta.png)

\- Klikkaa Hyväksy

- Maksu poistuu maksamattomista maksuista ja näkyy kokonaan maksettuna.

Maksun maksaminen riviltä osittain

\- Valitse Maksa sen maksun kodalla, mikä maksetaan.

- Muokkaa summaa, joka tulee Peri asiakkaalta-laatikkoon. Hyväksy.

![](/assets/files/docs/Asiakkaat/osamaksu2.png)

\- Loput maksusta jää Maksettava- sarakkeeseen Maksa
maksuja-välilehdelle.

### 3.2.2 Maksujen poistaminen rivi kerrallaan

\- Klikkaa Poista sen maksun kohdalta, joka poistetaan. Jatka
valitsemalla Poista tämä maksu.

![](/assets/files/docs/Asiakkaat/poistamaksu2.png)

Maksu siirtyy Maksa maksuja-välilehdeltä Tili-välilehdelle.

![](/assets/files/docs/Asiakkaat/poistettu2.png)

### 3.2.3. Maksa kaikki maksut

\- Klikkaa Maksa kaikki -nappia.

\- Klikkaa Hyväksy

### 3.2.4. Maksa jokin tietty summa maksuista

\- Klikkaa Maksa kaikki -nappia.

- Kirjoita Peri asiakkaalta -laatikkoon asiakkaalta perimäsi rahamäärä.
  Kokonaisvelka näkyy Saatavia yhteensä -kohdassa.

![](/assets/files/docs/Asiakkaat/maksa2.png)

\- Klikkaa Hyväksy.

\- Maksu päivittyy kuittaamaan vanhimmat maksut ensin.

### 3.2.5. Maksa valitut maksut

\- Laita valintamerkki niiden maksujen kohdalle, jotka maksetaan,
klikkaa Maksa valitut.

![](/assets/files/docs/Asiakkaat/maksa3.png)

Valittujen maksujen summa näkyy Peri asiakkaalta -laatikossa.

![](/assets/files/docs/Asiakkaat/maksa4.png)

\- Klikkaa Hyväksy

- Maksu päivittyy kuittaamaan valitun maksun.

### 3.2.6. Poista kaikki maksut

Klikkaa Poista kaikki maksut -nappia listauksen alapuolella

![](/assets/files/docs/Asiakkaat/maksa5.png)

\- Kaikki maksut poistuvat saatavista ja näkyvät poistettuina maksuina

### 3.2.7. Maksun peruminen

Jos vahingossa merkitset niteen maksun maksetuksi, voit kumota maksun
klikkaamalla Toiminnot-sarakkeessa Peruuta.

![](/assets/files/docs/Asiakkaat/maksa6.png)

\- Klikkauksen jälkeen tulee uusi rivi, jossa näkyy maksun peruutus

![](/assets/files/docs/Asiakkaat/maksa7.png)

Peruutuksen voi vielä perua klikkaamalla uudelleen “Peruuta”.

## 3.3. Lisää maksu -välilehti

Sellaisia maksuja, joita järjestelmä ei tee automaattisesti, voi
virkailija tallentaa Lisää maksu -välilehdellä.

![](/assets/files/docs/Asiakkaat/lisaamaksu.png)

\- Valitse ensin maksun tyypppi

- Jos maksu liittyy johonkin niteeseen, voit lisätä sen viivakoodin
  linkiksi niteeseen

Kuvaus-kenttään voi antaa maksun kuvauksen

![](/assets/files/docs/Asiakkaat/maksunkuvaus.png)

Summa-kenttäään annetaan pelkästään maksun määrä (vain numeroita ja
desimaaleja). Tallennuksen jälkeen maksu näkyy yhteenvedossa. 
Maksun voi maksaa myös samantien klikkaamalla "Tallenna ja maksa".

![](/assets/files/docs/Asiakkaat/maksunsumma.png)

## 3.4. Luo hyvitys -välilehti

Tämä toiminto luo asiakkaalle saldoon “plussasaldoa”. Hyvitystä voidaan
käyttää maksujen maksamiseen tai maksun anteeksiantoon. HUOM! Tarkista
ensin kirjastosi käytäntö plussasaldon lisäämisestä asiakkaalle. Tämän
käyttäminen ei ole sallittua mm. OUTI-kirjastoissa.

![](/assets/files/docs/Asiakkaat/hyvitys.png)

\- Valitse ensin hyvityksen tyyppi

\- Jos maksu liittyy johonkin tiettyyn niteeseen, lue niteen viivakoodi
Viivakoodi-kenttään

\- Kuvaus-kenttään voit kirjoittaa selityksen

- Anna Summa-kenttään vain numeroita ja desimaaleja, ei
  valuuttamerkkejä.

## 3.5. Maksujen maksaminen Ceepos-kassaliittymän kautta

### 3.5.1. Valmistelut ennen maksujen vastaanottoa

Avaa Kohassa asiakkaan *Maksa maksuja*-välilehti. Valitse sieltä ne
maksut, jotka asiakas maksaa ja klikkaa joko *Maksa kaikki* tai *Maksa
valitut*.

![](/assets/files/docs/Maksut/maksut1.png)

Maksutyyppi-kohtaan valitaan toimipistekoodi, ellei se ole jo siinä valmiina. Sen jälkeen 
klikkaa *Ceepos-maksu*.

![](/assets/files/docs/Maksut/maksut2.png)

### 3.5.2. Maksun lähettäminen kassaohjelmaan

Kun klikkaat *Ceepos-maksu*, tulee ilmoitus *Maksu lähetetty, käsittele kassassa!* Klikkaa *ok*.

![](/assets/files/docs/Maksut/maksut3.png)

Voit siirtyä Ceeposiin ja veloittaa asiakkaalta maksun. Toimi kirjaston Ceepos-ohjeiden mukaisesti
ja palaa sitten takaisin Kohaan, jossa asiakkaan maksut ovat
automaattisesti merkitty suoritetuiksi.

Ongelmatilanteissa ota yhteyttä joko oman kirjaston/kimpan Koha-tukeen
tai kirjastosi Ceepos-ohjelman pääkäyttäjään.
