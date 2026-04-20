---
layout: single
permalink: /kuvailuryhma2026
header:
  overlay_color: '#5e616c'
  overlay_image: /assets/images/cropped-pexels-photo-113850.jpeg
toc: true
title: 'Koha-Suomen kuvailuryhmän muistiot 2026'
---


## Kuvailuryhmän muistio 4/2026 ##

Aika: 15.4.2026 klo 13.15–14.40

Osallistujat: Mauri Aittaniemi (Lappi), Merja Hakulinen (Lumme), pj. Antti Heikkinen (OUTI), Pasi Hynninen (Helle), Marjukka Laapotti (Lastu), Marja Leskinen (Vaara), Tarja Mäkinen (Kyyti), Johanna Ranta (Kyyti), Anna Viitanen (Vaski), Timo Väisänen (Kirkes), Anneli Österman (Koha-Suomi)

Poissa: Päivi Knuutinen (Vaara)

### Asialista ###

#### 1.	Kokouksen avaus ja sihteerin valinta ####

Sihteerivuorossa Tarja Mäkinen.

#### 2.	Kansalliskirjaston suositukset vaatimusmäärittelyjen laatimiseen kirjastojärjestelmämuutoksissa ####
<ul>
  <li><a href="https://www.kiwi.fi/spaces/kuvailuyhteistyo/pages/543064557/Kansalliskirjaston+suositukset+vaatimusm%C3%A4%C3%A4rittelyjen+laatimiseen+kirjastoj%C3%A4rjestelm%C3%A4muutoksissa" target="_blank">Kansalliskirjaston suositukset vaatimusmäärittelyjen laatimiseen kirjastojärjestelmämuutoksissa </a> </li>
  <li>Hyvin tehdyt suositukset, ei herättänyt juurikaan keskustelua. </li>
</ul>

#### 3.	Versionpäivitys ####
<ul>
  <li>Meni pääsääntöisesti hyvin.</li>
  <li>Havaittuja ongelmia: </li>
  <ul>
  <li><a href="https://github.com/KohaSuomi/Koha/issues/2229" target="_blank">Tietuesiirtäjä lisäilee satunnaisesti ylimääräisiä 942c-kenttiä TäTissä </a> </li>
  <li><a href="https://github.com/KohaSuomi/Koha/issues/2212" target="_blank">Perustiedot-näytöllä ja hakutuloksissa näkyy tuplapilkku e-osakenttien välissä </a> </li>
  <li><a href="https://github.com/KohaSuomi/Koha/issues/2209" target="_blank">Järjestelmäasetus: AddbiblioHostFrameworkToComponentFramework </a> </li>
  <li><a href="https://github.com/KohaSuomi/Koha/issues/2269" target="_blank">MARC-virheraporttien linkit antavat "Error 404" OUTIssa ja TäTissä </a> </li>
  <li>Edelleen osa teksteistä näkyy Kohassa englanniksi. Asia ei korjaantunut päivityksessä. </li>
  </ul>
</ul>

#### 4.	Kuulumisia Koha-Suomi-Melinda-tilannepalaverista 11.3. ####
<ul>
  <li>TäTi-putki </li>
  <ul>
  <li>Toiminto, jossa Kirjastopalvelun tietueet siirretään/linkitetään automaattisesti erätuonnilla Melindaan.</li>
  <li>Katselmoinnit ovat taas alkaneet. Osakohteellisia tietueita ei oteta mukaan. </li>
  <li>Arviolta noin 4000 uutta tietuetta, noin 700 tietuetta jää transformeriin virheellisinä ja 37 000 tietuetta saa updaten (lähinnä TATI-low-tag ja SID-kenttään TäTin tietuenumero ja BTJ:n kontrollinumero), vanhimmat tietueet vuodelta 2016. </li>
  <li>Jos Melindassa on tuplatietue, ohjelma tekee valistuneen arvauksen siitä, kumpaan tietueeseen yhdistää. Tämä näyttäisi toimivan yllättävänkin hyvin. </li>
  <li>Katselmoinnin huomioita tähän mennessä: </li>
    <ul>
  <li>Yhdistettäessä kuvailukieli vaihtuu swe-> fin (tieteellisten kirjastojen alun perin kuvailemia) </li>
  <li>Osassa Melinda-tietueista Ruotsissa käytettävä kssb-luokitus mukana 084-kentässä (yleensä ensimmäinen toistuma) -> Kysytään Siskulta, voisiko sen poistaa. </li>
   </ul>
  </ul>
  <li>Kati-tietokanta: Tietueiden yhdistämisessä olisi mahdollista käyttää apuna Melindan Match-toimintoa eli verrataan tietueita Melinda-tietueeseen ja jos täsmää, otetaan Melinda-tietue. Jos Melindassa on kaksi tietuetta, pitäisi osata yhdistää siihen parempaan tietueeseen. </li>
</ul>

#### 5.	Tikettejä ####
<ul>
  <li><a href="https://github.com/KohaSuomi/Koha/issues/2218" target="_blank">800-kenttä perustiedot-näytöllä </a> -> Tämä on Annelilla työn alla. </li>
  <li><a href="https://github.com/KohaSuomi/Koha/issues/458" target="_blank">Tuplatietue TäTissä, kun yrittää muokata tietuetta </a> </li>
  <li><a href="https://github.com/KohaSuomi/Koha/issues/2253" target="_blank">Jaetun kuvailutietovarannon muodostaminen testeille </a> </li> 
  <li><a href="https://github.com/KohaSuomi/Koha/issues/2030" target="_blank">942c-kenttä ei päivity, kun pohjaa vaihtaa </a> -> Kysytään vielä Lumpeesta, miten usein näitä tulee vastaan. Kannattaako tehdä kehitysehdotus tästä? Yksi samankaltainen tiketti jo hylättiin, koska kyseessä on sen verran satunnainen ongelma. </li>
  <li>Edellä mainittuun kenttään liittyvä ongelma: kun TäTistä tekee Z39.50/SRU-haun, aineistotyyppi häviää 942c-kentästä paikalliskannassa. Melindasta tuotaessa ei ole tätä ongelmaa. Tehdään tiketti tästä: <a href="https://github.com/KohaSuomi/Koha/issues/2261" target="_blank">942$c-kentän tieto "putoaa" toisinaan tietueita tuotaessa Z39.50-haulla TäTistä </a> </li>
</ul>

#### 6.	Muita asioita ####
<ul>
  <li>Kuvailuryhmään tarvittaisiin Päivi Knuutisen tilalle pääkäyttäjä. Anneli lupasi ottaa asian puheeksi seuraavassa pääkäyttäjien kokouksessa. </li>
  <li>Paikalliskantojen tietueet, joissa loppupiste- tai kaksoispistevirheitä 264-kentissä – onko kukaan ehtinyt tarkastella? -> Vaskissa, Kyytissä ja OUTIssa tutkittu asiaa – virheitä vähemmän kuin TäTissä. </li>
  <li>Kuvailustandardiryhmän muistiosta 1.4.2026: Esineet: Kumea tekee MARC-pohjaisen minimiohjeen esineiden kirjastokuvailua varten ja konsultoi Siskua esineiden tyypittelyyn liittyen (genre-, aihe yms. sisällönkuvailuasiat). </li>
  <li>Kuvailukoulutus 1/2026 tiistaina 21.4.2026 klo 13.00–14.30, aiheena Kuvailutietueiden muokkaus eräajona, muokkauspohjien teko. Linkki koulutukseen löytyy <a href="https://github.com/KohaSuomi/Koha/discussions/2171" target="_blank">tiedotesivulta</a>. </li>
  <li>TäTi-postin siivous seuraavaan kokoukseen mennessä, poistetaan siis vanhat postit. </li>
</ul>

#### 7.	Seuraava kokous keskiviikkona 20.5. klo 13.15. ####


---
## Kuvailuryhmän muistio 3/2026 ##

Aika: 10.3.2026 klo 13.15–13.47

Osallistujat: Mauri Aittaniemi (Lappi), Merja Hakulinen (Lumme), pj. Antti Heikkinen (OUTI), Pasi Hynninen (Helle), Päivi Knuutinen (Vaara), Marjukka Laapotti (Lastu), Tarja Mäkinen (Kyyti), Johanna Ranta (Kyyti), Anna Viitanen (Vaski), Timo Väisänen (Kirkes)

Poissa: Marja Leskinen (Vaara), Anneli Österman (Koha-Suomi)

### Asialista ###

#### 1.	Kokouksen avaus ja sihteerin valinta ####

Sihteerivuorossa Marjukka Laapotti.

#### 2.	Kirjastokohtaisten kenttien sisältö ja muut kirjastokohtaiset huomautukset eri kentissä ####
<ul>
  <li>Päivi Knuutisen kokoama lista löytyy Oulun Koha Teamsin Kuvailu-kanavalta, KaTi-työryhmä-tiedostokansiosta. Sitä voi tarvittaessa vielä täydentää. Tiedoston nimi on ”Omat kuvailukentät kimpoissa”. </li>
  <li>Helle ja Siili: tiedot puuttuvat vielä listalta </li>
</ul>

#### 3.	Tuplatietueiden yhdistäminen ####
<ul>
  <li>Tuplatietueet ovat jatkuva ongelma muiden kirjastojen ja Kirjastopalvelun kuvailemien tietueiden välillä, koska kaikessa aineistossa Kirjastopalvelun mahdollisesta kuvailusta ei ole varmuutta. Tuplia on eniten vieraskielisessä aineistossa, peleissä ja äänitteissä. </li>
  <li>Ongelma ei poistu sillä, että Melinda-tietue poistetaan TäTistä ja Kirjastopalvelun tietue jätetään, koska Melinda-tietueen löytyminen tarkoittaa jo sitä, että jossakin paikalliskannassa se on. Nämä tulevat vastaan viimeistään sitten kun tietokannat yhdistetään. </li>
  <li>Ratkaistava myös KaTia varten, kun yhdistetään parhaimmillaan yli 11 tietuetta. Todettiin, että tuplatietueilla voi olla eri koodaustasoja (kenttä 000/17). Lisäksi tietueet voivat olla hybriditietueita tai kokonaan RDA:lla kuvailtuja. Mikä tietue näistä ”voittaa”? </li>
  <li>Milloin tietueet ovat riittävän identtiset, että ne voidaan yhdistää? Tärkeitä yhdistäviä tekijöitä ovat ainakin standarditunnus, aineistotyyppi ja nimeke. </li>
  <li>Miten toimitaan, jos kuvailuissa on paljon eroja? </li>
  <ul>
    <li>Sisällönkuvailun erot (lähinnä luokitus ja asiasanoitus, musiikkiaineistossa voi olla tapauksia, joissa genre on määritelty täysin eri tavalla riippuen kuvailijan tulkinnasta) </li>
    <li>Nimeketietojen ja pääkirjausten erot </li>
    <li>Toisistaan poikkeavat huomautuskentät </li>
  </ul>
-> Aloitettiin näiden pohtiminen, mutta asiaa kannattaa ehkä tutkia tarkemmin vasta sitten kun kaikkien tietokantojen yhdistämistä päästään kunnolla testaamaan.
</ul>

<ul>
  <li>Todettiin, että ei aleta yhdistämään tuplia TäTissä systemaattisesti, koska niitä on niin paljon. </li>
  <li>Sovittiin, että pyritään uutuusaineistoa käsiteltäessä yhdistämään tuplat saman tien. Melindan tietue jätetään, koska se on jo linkitetty ja löytyy jostakin paikalliskannasta. Sisällönkuvailua voidaan täydentää Kirjastopalvelun tietueen pohjalta. Jos tietueiden välillä on suuria eroja, esim. pääkirjauksissa, niin sitten käsiteltävään nimekkeeseen on perehdyttävä tarkemmin. Tarvittaessa voi tiedustella kuvailusta tietueiden alkuperäisiltä kuvailijoilta.<br>
(Huom. Jos Melinda-tietueessa on selviä virheitä, niin ne saa korjata, vaikka tietue olisi Kansalliskirjaston kattavalla tasolla kuvailema, kunhan korjauksista sitten ilmoittaa asianosaisille.)</li>
</ul>

#### 4.	Tietueiden erämuokkaus ####
<ul>
  <li>TäTissä on yli tuhat tietuetta, joissa on loppupiste- tai kaksoispistevirheitä 264-kentissä. Osassa näistä on muitakin epämääräisyyksiä. Periaatteessa saisi korjattua erämuokkauksella, mutta se ei toimi parhaalla mahdollisella tavalla, jos/kun korjattavaa kenttää on toistettu. </li>
  <li>Välimerkkivirheillä ei ole käytännön merkitystä, mutta paikalliskannasta voi tarkistaa niiden määrän. Päätetään myöhemmin, mitä näille tehdään TäTissä. Pääkäyttäjiltä voi pyytää TäTistä löytyvät raportit: </li>
  <ul>
    <li>Tietueet, joissa valitun Marc-kentän lopussa on kaksoispiste ilman välilyöntiä </li>
    <li>Tietueet, joissa on valitun Marc-kentän lopussa ylimääräisiä välilyöntejä </li>
    <li>Tietueet, joissa 245a-kentän lopussa on ylimääräisiä :-merkkejä  </li>
  </ul>
</ul>

#### 5.	Muita asioita ####
<ul>
  <li>Koha-Suomi-Melinda-tilannepalaveri 11.3. Aiheena mm. TäTi-putki ja sen seuraavat askeleet. </li>
  <li>Tiketti: <a href="https://github.com/KohaSuomi/Koha/issues/2036" target="_blank">Melindaan vietäville osakohteille tarkistus, ettei niissä ole samoja 001-arvoja </a> -> Testattu ja toimii Täti-Nextillä. Tulee versiopäivityksessä käyttöön. </li>
  <li>Tiketti: <a href="https://github.com/KohaSuomi/koha-plugin-broadcast-biblios/issues/18" target="_blank">Lisätään FI-TATI "003/001"-vertailuun mukaan </a> </li>
  <ul>
    <li>Paikalliskantojen 001/003-kenttien aktivoituminen toimii ainoastaan FI-BTJ-tunnuksilla. Paikalliskantojen Nexteille on tehty versio testattavaksi, jossa myös FI-TATI-tunnukset aktivoituvat. Jos toimii, niin otetaan versiopäivityksen yhteydessä käyttöön. </li>
    <li>Testattu toimivaksi OUTI- ja TäTi-Nextillä. Tätä voi testata niin, että poimii TäTistä standarditunnuksettoman tietueen, jossa on 003- ja 001-kentissä TäTi-tunnukset ja tarkistaa sitten aktivoituivatko ne omassa kannassa ja löytääkö tietue vastintietueen TäTistä Tietuesiirtäjässä. </li>
  </ul>
  <li>YKN:n metatietoryhmän kokous 11.3. Aiheena mm. KAUNO:n ja YKL:n siirtyminen VAKE:lle ja niiden ylläpidon jatko. </li>
  <li>Kansallisten kuvailuryhmien kevään työpaja 26.3. Aiheena mm. esineiden kuvailu eri organisaatioissa. </li>
</ul>

#### 6.	Seuraava kokous keskiviikkona 15.4. klo 13.15. ####


---
## Kuvailuryhmän muistio 2/2026 ##

Aika: 11.2.2026 klo 13.15–14.45

Osallistujat: Mauri Aittaniemi (Lappi), Merja Hakulinen (Lumme), pj. Antti Heikkinen (OUTI), Pasi Hynninen (Helle), Päivi Knuutinen (Vaara), Marjukka Laapotti (Lastu), Marja Leskinen (Vaara), Tarja Mäkinen (Kyyti), Johanna Ranta (Kyyti), Anna Viitanen (Vaski), Timo Väisänen (Kirkes), Anneli Österman (Koha-Suomi)

### Asialista ###

#### 1.	Kokouksen avaus ja sihteerin valinta ####

Päivi Knuutinen sihteerivuorossa.

#### 2.	Kirjastokohtaisten kenttien sisältö ja muut kirjastokohtaiset huomautukset eri kentissä ####
<ul>
  <li>Käydään läpi kimppojen osalta ja mietitään, minne kootaan nämä tiedot </li>
  <li>Onko yhteistietokannassa vielä tarvetta kirjastokohtaisille huomautuksille, ja jos on, niin minne niitä laitetaan? </li>
</ul>

<ul>
  <li>Keskusteltiin asiasta ja kootaan kimppojen käytännöt yhteen, tiedot kokouksen sihteerille. Käytännössä kimpoilla oli kovin kirjava käytäntö paikallisten huomautusten osalta ja joitakin voi poistaa täysin, mutta on myös (johonkin kenttään siirrettäviä) säilytettäviä paikallisia tietoja. </li>
  <li>Kaikille yhteisestä 599a-kentän Daisy-merkinnästä voisi ehkä luopua, koska Celian äänikirja -tiedon saa nyt 942c-kentästä. Tätä ei kannata kuitenkaan tehdä ennen kuin OKM-tilastoinnin raporttityökalua on muokattu.</li>
</ul>

#### 3.	Finton sanastomuutosten seuranta ####
<ul>
  <li><a href="https://github.com/KohaSuomi/Koha/issues/511" target="_blank">Tietokannan tietojen siivousautomatiikkaa tietueille </a> </li>
  <li>Tarkasteltiin Antin aiemmin lähettämiä esimerkkitietueita ja -tapauksia. Lisätään tikettiin uusia huomioita puutteista, jos/kun niitä ilmenee. </li>
</ul>

#### 4.	Kuvailukoulutukset ####
<ul>
  <li>Tietueiden erämuokkaus ja muokkauspohjat: Päätettiin pitää koulutus 21.4. klo 13. Noin 1,5 tunnin koulutus tallennetaan. </li>
  <li>TäTi- ja Melinda-tietueiden yhdistäminen: Koulutuksen ajankohta jäi vielä auki. Todettiin, että 040d-kenttään merkitään tietoja yhdistävän kirjaston tunnus. </li>
</ul>

#### 5.	Emottomat osakohteet ####
<ul>
  <li>Suurin osa uusista paikalliskantojen emottomista osakohteista syntyy siitä, kun TäTiin tuodaan Melindasta emotietue, joka ehtii valua paikalliskantaan ennen osakohteita. Tämä katkaisee paikalliskannassa yhteyden ”vanhoihin” osakohteisiin ja ne jäävät roikkumaan ilman emoa. </li>
  <li>Emottomien osakohteiden raportilla oli myös tapauksia, joissa osakohteet linkittyvät Kohassa emoon, mutta niiden 773w-kentän lopussa on tietoihin kuulumattomia välimerkkejä, mikä aiheuttaa niiden virhelistalle joutumisen. </li>
  <li>TäTissä on tehty korjauksia, mutta osa on vielä kesken. </li>
  <li>Melindan tietueiden yhdistäminen Melindassa ei päivity oikein TäTiin vaan katkaisee yhteyden osakohteisiin, koska emotietueen 001-kenttään ei päivity oikea tunnus. </li>
  <li>Todella vanhat osakohteet kannattaa vain poistaa suoraan paikalliskannoista ilman sen kummempaa tutkimista. Vaikka emo sattuisikin olemaan vielä tallella, niin tuleva yhteistietokanta varmaan ratkaisee ainakin osan ongelmista. Tietueita voi täydentää tarvittaessa myös Melindasta.</li>
</ul>

#### 6.	800-kenttä perustiedot-näytöllä ####
Pääkäyttäjien muistiosta viikko 4: Kyyti: ”Perustietonäkymässä näkyy sarjatieto kentästä 800 ja sen kuvailusäännöt ovat muuttuneen siten, että sarjalinkin haku ei enää löydä sarjan vanhoja eri tavalla kuvailtuja osia. 490-kentässä sarja on kirjattu vanhalla tavalla ja jos se näkyisi perustietonäkymässä ja sarjan nimi olisi linkki löytyisi myös sarjan vanhat osat. Finnassa näkyy linkkeinä sekä 800 että 490. Anneli arveli, että tietuenäyttöjen mukautuksessa voisi kokeilla 490-kentän laittamista näkyville, mutta saako sen linkiksi, ei ole tietoa. Toinen vaihtoehto olisi laittaa kehitysehdotusta yhteisöön.”
<ul>
  <li>Pyritään saamaan 490-kentän sisältö perustietonäkymään, koska se on kaikille paljon informatiivisempi kuin 800-kentän tieto. Huomattava kuitenkin, että 490-kenttään merkitään sarjan nimi siinä muodossa kuin se on kirjassa, ja tässä voi olla vaihtelua eri osien välillä. </li>
  <li>Melinda ei tee takautuvia massakorjauksia 800-kentän sarjatietoihin.</li>
</ul>

#### 7.	Esineiden kuvailu ####
<ul>
  <li>Todettiin, että kimpoissa on erilaisia tapoja kuvailla esineitä jopa kimpan sisällä. Näiden yhdistäminen voi olla todella haastavaa. </li>
  <li>Yhteinen kuvailuohje esineille olisi hyvä olla olemassa. Asiaa todennäköisesti käsitellään tänä keväänä myös kansallisissa kuvailutyöryhmissä, joten seurataan tilannetta.</li>
</ul>

#### 8.	Muita asioita ####
<ul>
  <li>Tiketti <a href="https://github.com/KohaSuomi/Koha/issues/2011" target="_blank">Kun tietue luodaan kaukolainamoduulin kautta, ei noudeta FA-kuvailupohjan oletusarvoja </a> -> Mielenkiintoinen tiketti sen takia, että tässä tutkitaan nimiön oletusarvoihin liittyviä ongelmia. </li>
  <li>Selkokirjojen kuvailu on muuttunut. Nyt pääsanaksi valitaan alkuperäinen kirjoittaja (kuten ihan ensiksi oli tapana). Kirjastoilla on iso työ muuttaa vanhat tietueet nykykäytännön mukaiseksi. Melindassa ei näillä näkymin tehdä takautuvia korjauksia. - [Kokouksen jälkeen tullut tieto 16.2.]: Kirjastopalvelu ei tee takautuvia korjauksia tietueisiinsa. </li>
  <li>Teosten ja ekspressioiden kuvailussa käytetään paljon eri osakenttiä, jotka eivät ole kuitenkaan näkyvissä TäTin kuvailupohjien 600/610/611-kentissä (aiheena teos). Keskusteltiin, pitäisikö kenttiä lisätä näkyville tai piiloon kuvailupohjiin, mutta tällaiset kuvailutapaukset ovat sen verran harvinaisia, että ne voi tarvittaessa ottaa käyttöön oletuspohjan kautta. Kirja-pohjaan on kuitenkin lisätty näkyville 600t-kenttä. Osakenttiä voidaan lisätä tarvittaessa.</li>
</ul>

#### 9.	Seuraava kokous tiistaina 10.3. klo 13.15 ####


---
## Kuvailuryhmän muistio 1/2026 ##

Aika: 14.1.2026 klo 13.15-14.26

Osallistujat: Mauri Aittaniemi (Lappi), Merja Hakulinen (Lumme), pj. Antti Heikkinen (OUTI), Eeva Hulkkonen (Lastu), Pasi Hynninen (Helle), Marja Leskinen (Vaara), Tarja Mäkinen (Kyyti), Johanna Ranta (Kyyti), Anna Viitanen (Vaski), Timo Väisänen (Kirkes), Anneli Österman (Koha-Suomi)

Poissa: Marjukka Laapotti (Lastu), Päivi Knuutinen (Vaara)

### Asialista ###

#### 1.	Kokouksen avaus ja sihteerin valinta ####

Sihteeriksi valittiin Marja Leskinen. Kevään kokouksissa Kirkes-kirjastojen edustajana toimii Timo Väisänen Mäntsälästä.

#### 2.	KaTi-työryhmän kokoukset ####
<ul>
  <li>Muistiot Koha-Suomen sivuilla: <a href="https://koha-suomi.fi/kati" target="_blank">KaTi-työryhmä </a> </li>
  <li>Seuraavaan kokoukseen koontia paikallisten kuvailukenttien käytöstä kimppakohtaisesti.</li>
</ul>

#### 3.	Esineiden kuvailu ####
<ul>
  <li>Tulevan yhteistietokannan vuoksi olisi hyvä yhdistää esineiden kuvailua </li>
  <li>Todettiin, että esineiden kuvailu on ollut todella kirjavaa vuosien saatossa ja tietueiden yhdistäminen ei ole helppoa </li>
  <li>Seuraavaan kokoukseen mennessä jokainen voisi selvitellä, miten paljon ja millaisia esineitä omista tietokannoista löytyy ja miten niitä on kuvailtu. Onko mahdollista yhdistellä jo joitakin sisäisiä tuplatietueita.</li>
</ul>

#### 4.	Tietueet, joiden merkkipaikka 000/17 = z ####
<ul>
  <li>Liittyy tikettiin <a href="https://github.com/KohaSuomi/Koha/issues/1986" target="_blank">Lumme: Tietuesiirtäjä siirsi toistuvasti samoja kolmea tietuetta </a> -> Valutusvirhe korjattu Nexteille </li>
  <li>Anneli on tehnyt raportin, jolla löytyy TäTistä tietueet, joiden 000/17 = z. Tietueita 22 kpl. Päätettiin poistaa kyseiset tietueet TäTistä. </li>
  <li>Annelin tekemän raportin voi ottaa käyttöön myös paikalliskantoihin. Tarvittaessa tietueet voi korjata poimimalla Melindasta uuden tietueen vanhan päälle tai muuttaa merkkipaikan arvoksi 4.</li>
</ul>

#### 5.	Finton sanastomuutosten seuranta ####
<ul>
  <li><a href="https://github.com/KohaSuomi/Koha/issues/511" target="_blank">Tietokannan tietojen siivousautomatiikkaa tietueille </a></li>
  <li>Antti yrittää koota kaikista paikalliskannoista löytyviä nimekkeitä, että saadaan tieto toimiiko sanastomuutosten siivousautomatiikka paikalliskannoissa.</li>
</ul>

#### 6.	Kuvailukoulutukset ####
<ul>
  <li>Kevään aika pyritään järjestämään tietueiden erämuokkaukseen ja muokkauspohjiin liittyvä koulutustilaisuus. Anneli tekee aiheesta kyselyn. </li>
  <li>Myöhemmin järjestetään koulutus TäTi- ja Melinda-tietueiden yhdistämisestä. Koskee sekä tuplatietueiden yhdistämistä TäTissä että TäTissä olevan ja Melindassa olevan saman nimekkeen tietueiden yhdistämistä toisiinsa.</li>
</ul>

#### 7.	Muita asioita ####
<ul>
  <li>TäTi-nextiä voi alkaa testaamaan versiopäivityksen osalta osoitteessa <a href="https://tati-next.koha-suomi.fi" target="_blank">tati-next </a>. Toimintoja voi testata kuten paikallis-nexteissä. </li>
  <li>Vieraskielisen kaunokirjallisuuden luokkamuutokset tehty TäTissä kielien ukraina, somali ja turkki osalta. </li>
  <li>Melinda korjannut KAINU-tietokannan erätuonnista tulleita virheitä, kuten tupla 0-kentät. Korjaukset toivottavasti replikoituneet paikalliskantoihin asti. </li>
  <li>Melinda selvittelee, pitäisikö jonkin toisen Melinda-kirjaston Melinda-tietueelle lisäämien uusien osakohteiden replikoitua TäTiin. (Esim. tapaus, jossa Cd-levyn liitteenä olevan Blu-rayn osakohteet on lisätty tietueelle) </li>
  <li>Piki-kirjastoista saatu vastaus Kirjastopalvelun ruotsinkielisten tietueiden muokkaamisesta: Ruotsinkieliset tietueet käännetään suomeksi. Jos Melindassa ei ole nimekettä entuudestaan, Piki vie kääntämänsä tietueen Melindaan. Pikissä mietitään parhaillaan kuvailuprosessia ja he lupasivat pohtia, voisivatko jatkossa viedä Kirjastopalvelun tietueet ruotsinkielisenä Melindaan. Seurataan tilannetta ja kysellään myöhemmin, onko asia edennyt. </li>
</ul>

#### 8.	Seuraavat kokoukset ####
Kevään kokousajat ovat:
<ul>
  <li>Ke 11.2. klo 13.15. - 14.45 </li>
  <li>Ti 10.3. klo 13.15. - 14.45 </li>
  <li>Ke 15.4. klo 13.15. - 14.45 </li>
  <li>Ke 20.5. klo 13.15. - 14.45 </li>
</ul>

