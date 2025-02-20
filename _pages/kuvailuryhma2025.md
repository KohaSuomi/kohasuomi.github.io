---
layout: single
permalink: /kuvailuryhma2025
header:
  overlay_color: '#5e616c'
  overlay_image: /assets/images/cropped-pexels-photo-113850.jpeg
toc: true
title: 'Koha-Suomen kuvailuryhmän muistiot 2025'
---


## Kuvailuryhmän muistio 2/2025 ##

Aika: 13.2.2025 klo 13.15–14.05

Osallistujat: Mauri Aittaniemi (Lappi), Merja Hakulinen (Lumme), pj. Antti Heikkinen (OUTI), Pasi Hynninen (Helle), Suvi Kauranen (Kirkes), Päivi Knuutinen (Vaara), Marjukka Laapotti (Lastu), Marja Leskinen (Vaara), Johanna Ranta (Kyyti), Anna Viitanen (Vaski), Anneli Österman (Koha-Suomi), Johanna Räisä (Koha-Suomi, kohdat 2–4)

Poissa: Tarja Mäkinen (Kyyti)

### Asialista ###

#### 1.	Kokouksen avaus ja sihteerin valinta ####

Kokouksen sihteeriksi valittiin Marjukka Laapotti.

#### 2. YSA-YSO-konversiot ####
<ul>
 <li><a href="https://github.com/KohaSuomi/Koha/issues/390" target="_blank">YSA-YSO-konversio kaikille kimpoille </a> </li>
 <li><strong>Helle:</strong> Valmis </li>
 <li><strong>Kyyti:</strong> 9-osakentät poistettu asiasanakentistä, konversiota ei ole vielä tehty (Lisäys: 17.2. konversio käynnissä)</li>
 <li><strong>Lappi:</strong> 9-osakentät poistettu asiasanakentistä, konversiota ei ole vielä tehty (Lisäys: 20.2. konversio valmis)</li>
 <li><strong>Lumme:</strong> Konvertointi käynnissä (Lisäys: 17.2. konversio valmis)</li>
 <li><strong>OUTI:</strong> Valmis</li>
 <li><strong>Siili:</strong> Konversiota ei ole vielä tehty</li>
 <li><strong>TäTi:</strong> Valmis</li>
 <li><strong>Vaara:</strong> Valmis</li>
 <li><strong>Vaski:</strong> Konvertointi käynnissä (Lisäys: 20.2. konversio valmis)</li>
</ul>

Konversio tuottaa paljon error-log-tiedostoja eli virhelistoja. Niitä voi tarvittaessa yhdistellä Excelin Power Query -toiminnolla yhdeksi tiedostoksi. Tarvittaessa kannattaa jättää tyhjät 0 kt -tiedostot ottamatta mukaan.

#### 3.	YSO-konversion jälkityöt TäTissä ja paikalliskannoissa ####
<ul>
 <li>Käytiin läpi TäTin korjauslistoja. Listoille on merkitty erilaisia konversiossa löytyneitä virhetyyppejä. Keskusteltiin, mitä kannattaisi korjata ja millä tavalla. Kirjoitusvirheet on helppo korjata, paikallisia maantieteellisiä asiasanoja kannattaa ehkä säilyttää. Sekä TäTissä että paikalliskannoissa olisi järkevää korjata yksiselitteisiä virheitä, kuten slm-sanastoon kuuluvia termejä oikeaan 655-kenttään. Myös vanhentuneet termit kannattaa korjata, esimerkiksi videopelit > po. digitaaliset pelit. Tulevan KaTi-tietokannan kannalta pitäisi miettiä, kuinka tietokantojen yhdistyessä toimitaan asiasanojen kanssa. Kenttä 653 on indeksoitu hakuihin, joten kentässä olevat termit eivät vaikuta haettavuuteen. Oikea termi väärässä kentässä voi kuitenkin vaikuttaa hakuihin. Erämuokkaustyökalusta ei ole apua, koska sen avulla ei voi esimerkiksi siirtää asiasanaa toiseen kenttään indikaattoreineen, lisätä 2- ja 0-osakenttiä samaan kenttään a-osakentän kanssa eikä muuttaa indikaattoreita.</li>
<li>Millainen tilanne Kirkes- ja Lastu-kirjastoissa on näiden osalta?</li>
<ul>
 <li>Kirkes-kirjastoissa tehtiin YSO-konversio 2021, silloin saatiin errog-logit. Virheitä on korjattu paljon, työ jaettiin kirjastojen kesken. Kohaan on tehty raportti, jolla voi listata 653-kentässä olevat termit, rivejä on nyt 17000.</li>
 <li>Lastu-kirjastossa tehtiin YSO-konversio vuonna 2021. Silloin ei saatu virhelistausta, mutta Auroraan tehdyllä raportilla saatiin listattua virheet ja tallennettua Excel-taulukkoon. Raportin tulos on tallennettu viimeksi ennen Kohan käyttöönottoa. Asiasanoja on korjattu oikeisiin kenttiin aina kun on ollut aikaa. Virherivejä on nyt 9700, joista yli 7000 on yksittäisiä esiintymiä.</li>
</ul>
 <li>OUTI:ssa on tehty raportti MARC-osakenttien sisältö ja esiintymistiheys. Sillä saa listattua mm. 653-kentässä esiintyvät asiasanat ja niiden määrät.</li>
 <li>Jos on suuria korjattavia massoja, korjauksiin tarvittavat skriptit ovat Johanna Räisän mukaan mahdollisia.</li>
 <li>Odotetaan, että kaikki tietokannat on konvertoitu. Palataan virhelistojen sisältöön ja asiasanojen korjaamiseen seuraavassa kokouksessa.</li>
</ul>

#### 4.	YSO-Aika-sanastoon liittyvät korjaukset ####
<ol>
 <li>Linkkien lisäys 0-osakenttiin 388- ja 648-kentissä </li>
 <li>648-kentän korjaus silloin kun kentässä vain jokin tietty vuosi tai ajanjakso (esim. 1945 tai 1939–1940) -> 2. indikaattorin arvo muutettava 7 -> 4 ja 2-osakenttä poistettava:</li>
  <ul>
 <li>648 #7 ‡a 1941-1944 ‡2 yso/fin -> 648 #4 ‡a 1941-1944</li>
 <li>648 #7 ‡a 19418 ‡2 yso/fin -> 648 #4 ‡a 1918</li>
</ul>
</ol>
<ul>
 <li>Tehdään näistä tiketit.</li>
</ul>

#### 5.	TäTin aineistotyypit ja kuvailupohjat ####
<ul>
 <li><a href="https://github.com/KohaSuomi/Koha/issues/1442" target="_blank">TäTiin käyttöön 942 c-kenttään MTYPE-arvot ja ne asettumaan automaattisesti </a> -> Etuna ehkä se, että tätä kautta saisi aina ajettua oikeat aineistotyypit paikalliskantojen tietueisiin, jos niissä on jostain syystä väärä (esim. hankintatietueen takia).</li>
<ul>
 <li>Pohdittiin, toimiiko automaattisesti myös Melindasta poimittaessa ja kuinka paikalliskannassa olevat 942-kentät säilyvät, kun tietueelle tulee päivitys.</li>
 <li>EditX-sanomissa MTYPE määräytyy kiinteiden kenttien mukaan, sama toiminto on saatavissa myös päiväpaketteihin. Kommentoidaan tikettiin, että asiaa voi edistää, jotta päästään myös testaamaan.</li>
 <li>Tulevassa KaTi-tietokannassa olisi helpompaa, jos MTYPE-arvo asettuisi automaattisesti.</li>
</ul>
 <li>Kuvailupohjien automaattinen vaihtuminen myös TäTiin?</li>
<ul>
 <li>Päätettiin antaa tämän asian vielä odottaa. </li>
 <li>Paikalliskantojen osalta on tehty kehitysehdotus: <a href="https://github.com/KohaSuomi/Koha/issues/1659" target="_blank">Kuvailupohjan ja aineistotyypin vaihtuminen automaattisesti kiinteämittaisten kenttien mukaan </a> </li>
</ul>
</ul>

#### 6.	Muita asioita ####
<ul>
 <li>Tiedoksi Vaskin tiketti: <a href="https://github.com/KohaSuomi/Koha/issues/1660" target="_blank">Asteri-liitännäisen käytöstä tietueen muokkauksessa tulee virhe 500 -ilmoitus paikalliskannassa </a> </li>
 <li>Ensimmäinen kuvailukoulutus tiistaina 11.3. klo 13.00–14.30 </li>
 <li>Koha-Suomi-Melinda-työryhmän kokous 11.3. klo 14.30–15.30 </li>
 <li><a href="https://github.com/KohaSuomi/Koha/discussions/1665" target="_blank">Koha-seminaari 27.-28.3.2025 Turussa </a> </li>
</ul>

#### 7.	Seuraava kokous 12.3.2025 Klo 13.15 ####


---
## Kuvailuryhmän muistio 1/2025 ##

Aika: 15.1.2025 klo 13.15–14.44

Osallistujat: Mauri Aittaniemi (Lappi), Merja Hakulinen (Lumme), pj. Antti Heikkinen (OUTI), Eeva Hulkkonen (Lastu), Pasi Hynninen (Helle), Suvi Kauranen (Kirkes), Marja Leskinen (Vaara), Tarja Mäkinen (Kyyti), Johanna Ranta (Kyyti), Anna Viitanen (Vaski), Anneli Österman (Koha-Suomi), Johanna Räisä (Koha-Suomi, kohta 2)

Poissa: Päivi Knuutinen (Vaara), Marjukka Laapotti (Lastu)

### Asialista ###

#### 1.	Kokouksen avaus ja sihteerin valinta ####

Sihteeriksi valittiin Marja Leskinen.

#### 2. YSA-YSO-konversiot ####
<ul>
 <li><a href="https://github.com/KohaSuomi/Koha/issues/390" target="_blank">YSA-YSO-konversio kaikille kimpoille </a> </li>
 <li>Konversiotestauksia tehty OUTIssa ja Vaskissa: <a href="https://github.com/KohaSuomi/Koha/issues/1040" target="_blank">YSA/YSO-konversion testausta </a> </li>
 <li>Jos asiasanaketjuissa on 9-osakentässä Kohan auktoriteettinumero ja termi on useassa ketjussa, monistuu termi turhaan. Mietitään, saadaanko jollain ajolla numerot pois. 
 <p> -> Tehdään tiketti. Anneli tekee raportin, jolla voi hakea 9-osakentän sisältävät tietueet. 9-osakentät poistetaan sitten tarvittavista kentistä tietueiden erämuokkaus -toiminnolla.</p> </li>
 <li>Konversio ei lisää YSO-ajan termeihin linkkejä. Näille on suunniteltava/tehtävä oma korjausajo konversion jälkeen.</li>
 <li>Konversiot tehdään perusmäärityksillä eikä käytetä mitään vipuja.</li>
 <li>Ensin konvertoidaan TäTi ja sen jälkeen paikalliskannat. Tietuemassoja ajetaan öisin, jolloin niiden käsittely ei haittaa muuta toimintaa.</li>
 <li>Konversiosta saadaan virhetaulukot, jotka lähetetään kimpoille ajojen jälkeen.</li>
 <li>Mietitään vielä, kuinka hoidetaan TäTin siivous konversion jälkeen.</li>
 <li>Johanna Räisä alkaa valmistelemaan TäTin konversiota. Kun TäTi on konvertoitu, paikalliskannoissa pitää ensin poistaa asiasanakentistä Kohan auktoriteettinumeroita sisältävä 9-osakentät, ennen kuin konversiot voidaan suorittaa. Välttämättä kaikissa paikalliskannoissa ei ole näitä tapauksia, mutta tämä on kuitenkin hyvä vielä tarkistaa raporteilla ennen konversioita.</li>
</ul>

#### 3.	KaTi-työryhmä ####
<ul>
 <li>TäTistä tulee Koha-Suomen yleisten kirjastojen yhteinen tietuetietovaranto, johon yhdistetään paikalliskantojen kuvailutietueet. Paikalliskannoissa ei ole enää tietueita, vain saatavuus- ja lainaajatiedot. </li>
 <li>Työryhmä hahmottelee kuvailun työnjakoa, säännöt mitä tietoja paikalliskannoista siirretään ja mitä jätetään pois sekä päättää aikataulun, kun tehtävät ovat selvillä. </li>
 <li>Työryhmän vetäjänä toimii Kodo Korkalo (Koha-Suomi) ja jäseniksi nimettiin Anna Viitanen (Vaski), Antti Heikkinen (OUTI), Suvi Kauranen (Kirkes), Marjukka Laapotti (Lastu) sekä Kati Sillgren (Helle). </li>
</ul>

#### 4.	Koha-Suomen sisäisen peruskuvailukoulutuksen järjestäminen ####
<ul>
 <li>Koha-Suomen sisäinen koulutus päätettiin järjestää useamman lyhyen koulutuksen sarjana. Eri koulutuskerroilla keskitytään eri asioihin ja/tai aineistotyyppeihin tai jaetaan laajemmat kokonaisuudet useammalle kerralle. Jokaisella kerralla voi olla eri kouluttaja. Anneli hoitaa koulutusten tiedotuksen, tilaisuudet tallennetaan. </li>
 <li>Ensimmäinen koulutus järjestetään ti 11.3.2025 klo 13.00–14.30, jolloin käsitellään kirja-aineiston kuvailua. Pääasiallisena aiheena on se, kuinka toimitaan, kun Kirjastopalvelusta ei ole tulossa kuvailua mutta Melindassa on tietue ja kuinka näitä erilaisia Melinda-tietueita käsitellään. Kouluttajana toimii Anna Viitanen Vaskista. </li>
</ul>

#### 5.	Melinda-tietueiden tekijöiden auktorisointi ####
Jos Melindasta poimitaan vanha tietue, jonka tekijöitä ei ole auktorisoitu, niin poimitaanko tekijän auktoriteettitietue, jos sellainen on olemassa?

-> Suositellaan lisäämään Melindan tietueelle auktorisoitu arvo.

#### 6.	Teosten auktoriteettitietueet Asterista Kohaan ####
Kuinka tärkeä olisi saada Kohassa toimimaan teosauktoriteettitietueiden poiminta jo?
<ul>
 <li>Ei pidetty ajankohtaisena vaan seurataan asian etenemistä.</li>
 <li>Kansalliskirjasto järjestää keväällä viisiosaisen Teokset ja ekspressiot osana bibliografista kuvailua -työpajasarjan, johon on kannattaa osallistua.</li>
</ul>

#### 7.	Ruotsinkielisten kirjojen primaarikuvailu kirjapohjalla ####
Kentät, joissa auktorisoitujen arvojen valikko, mutta ei ruotsinkielisiä termejä (esim. 246i). Tuottaako ongelmia kuvailussa?

-> Ei ole tuottanut kohtuuttomia ongelmia. Antti lisää 340 l-kenttään ruotsinkieliset termit.

#### 8. Tikettejä ####
<ul>
 <li>Nidehaku ja \ -merkki nimekkeessä: </li>
 <ul>
  <li><a href="https://github.com/KohaSuomi/Koha/issues/1549" target="_blank">Lappi: Nidehaku ei löydä Museokirjaston niteitä </a> </li>
  <li><a href="https://github.com/KohaSuomi/Koha/issues/1600" target="_blank">Lappi: Nidehaussa tulee virheilmoitus eikä tuloksia </a> </li>
  <li>Vikaan löytyi korjaus Koha-yhteisöstä ja se on tuotu jo tuotantoon</li>
 </ul>
 <li><a href="https://github.com/KohaSuomi/koha-plugin-broadcast-biblios/issues/15" target="_blank">Melinda tietueessa 19002432 FENNI-kenttä monistuu </a> 
   -> Korjaus on jo tuotannossa, mutta olisi hyvä seurata, miten diakriittejä sisältävät sanat käyttäytyvät Melindaan siirrettäessä. Monistuuko kentät vai siirtyvätkö täysin oikein. Ylipäänsä jos Melinda-tietueella on 5- tai 9-osakentissä joitakin arvoja, olisi hyvä aina tarkistaa, että 5- tai 9-osakentän sisältävät kentät siirtyvät oikein, eivätkä tuplaannu tai poistu tietueelta Melindaan viennin yhteydessä.</li>
 <li><a href="https://github.com/KohaSuomi/koha-plugin-broadcast-biblios/issues/13" target="_blank">Muokkaa 035a-kentän aktivoitumista valutuksessa </a> 
   -> On jo tuotannossa. 035a-kentän FI-BTJ-tunnus ei enää toimi aktivointiarvona.</li>
 <li><a href="https://github.com/KohaSuomi/koha-plugin-broadcast-biblios/issues/14" target="_blank">Hae tietueita 035z-kentällä </a> 
   -> Testattu TäTin ja OUTIn välillä, vaikuttaa toimivalta. Testattava vielä Melindan kanssa. </li>
</ul>

#### 9. Tikettiehdotuksia ####
<ul>
 <li>Kuvailupohjan vaihtuminen oikeaksi: Jos esim. hankintatietueen aineistotyyppi on kirja, mutta lopullinen kuvailtu tietue onkin nuotti, niin kuvailupohja ei vaihdu automaattisesti eikä myöskään aineistotyyppi.</li>
<p>-> On aiheuttanut ongelmia, tehdään tiketti. </p>
 <li>Tietokannassa joillakin tietueilla on 856-kentän kansikuva- ja kuvauslinkit useaan kertaan, jos ne valuvat Melinda-tietueen mukana. Koetaanko tämä ongelmaksi ja voisiko tälle tehdä jotakin? </li>
-> Ei koettu laajemmin ongelmaksi, ei tehdä tikettiä.
</ul>

#### 10. Osakohteiden Low-sync Melindassa ####
<ul>
 <li>Melindan toiminto, joka päivittää automaattisesti osakohteille emon low-tagin, jos sitä ei osakohteilla vielä ole.</li>
 <li>Tarkoittaa TäTissä sitä, että jos Melindasta Z39.50/SRU-haulla poimitun emotietueen vie Tietuesiirtäjällä takaisin Melindaan ilman osakohteita (eli osakohteita ei ole tuotu TäTiin Tietuesiirtäjällä sitä ennen), Low-sync-toiminto päivittää Melindassa emon osakohteille TATI-Low-tagin ja replikoi osakohteet sitten TäTiin. Tällaisissa tapauksissa Tietuesiirtäjän raportti ei näytä osakohteita ollenkaan.</li>
 <li>Tästä toiminnosta on hyvä olla tietoinen, mutta sitä ei ehkä välttämättä kannata hyödyntää osakohteiden poiminnassa Melindasta, vaan toimia mieluummin ohjeistetulla tavalla eli ensin poimitaan Z39.50/SRU-haulla emotietue Melindasta, sen jälkeen tuodaan osakohteet tietuesiirtäjällä, tehdään tarvittavat korjaukset emo- ja osakohdetietueisiin, ja tämän jälkeen viedään vasta emotietue osakohteineen Melindaan.</li>
</ul>

#### 11. Seuraavat kokoukset ####
<ul>
 <li>To 13.2. klo 13:15 </li>
 <li>Ke 12.3. klo 13:15 </li>
 <li>Ke 9.4. klo 13:15 </li>
 <li>Ke 14.5. klo 13:15 </li>
</ul>
