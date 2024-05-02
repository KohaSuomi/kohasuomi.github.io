---
layout: single
permalink: /kuvailuryhma2024
header:
  overlay_color: '#5e616c'
  overlay_image: /assets/images/cropped-pexels-photo-113850.jpeg
toc: true
title: 'Koha-Suomen kuvailuryhmän muistiot 2024'
---



## Kuvailuryhmän muistio 4/2024 ##

Aika: 7.4.2024 klo 14.00–15.15

Osallistujat: Mauri Aittaniemi (Lappi), Helena Backman-Karvonen (Helle), Merja Hakulinen (Lumme), pj. Antti Heikkinen (OUTI), Suvi Kauranen (Kirkes), Päivi Knuutinen (Vaara), Marjukka Laapotti (Lastu), Tarja Mäkinen (Kyyti), Johanna Ranta (Kyyti), Marja Soisalo (Vaara), Anna Viitanen (Vaski, poistui klo 15)

Poissa: Anneli Österman (Koha-Suomi)

### Asialista ###

#### 1.	Kokouksen avaus ja sihteerin valinta ####

Sihteerinä toimi Marja Soisalo.

#### 2. Kohan versionvaihto ja kuvailuun liittyvien toimintojen testaus paikalliskannoissa ja TäTissä ####
<ul>
    <li>Miten toimii? Onko huomattu mitään erikoista? - Kovin moni ei vielä ole testauksia tehnyt. Kaikki toiminnot eivät ole testikannoissa vielä päällä, mutta perus kuvailutoiminnot ovat kunnossa. </li>
    <li>TäTin toimintojen testaus: https://tati-next.koha-suomi.fi/  </li>
    <li>Mikropalvelun Melindaan vienti- ja tuontitoiminnot vaihtuvat myös uudelle tietuesiirtäjälle. Tätä testataan parhaillaan Testi-TäTissä. <a href="https://github.com/KohaSuomi/koha-plugin-broadcast-biblios/issues/4" target="_blank">Melinda-vientien ja -tuontien siirtäminen liitännäiseen </a> </li>
</ul>
 
#### 3. Kuulumisia Koha-Suomi-Melinda-työryhmän kokouksesta 9.4. ####
<ul>
    <li>TäTiputken kehitys: Jatketaan ehkä niin, että viedään Melindaan automaattisesti vain ne Kirjastopalvelun osakohteettomat tietueet, joita ei siellä vielä ole tai Melindassa on vain ennakkotietue. Korjaustietueiden käyttäytymistä pitäisi pohtia laajemmin. Päätettiin, että pohditaan TäTiputken selvitettäviä asioita pienemmällä porukalla. Mukana ainakin Antti Heikkinen, Anna Viitanen ja joku kehittäjistä. </li>
    <li>MARC-formaatin päivitykset. -> Kohan kuvailupohjat ovat jo muutaman version jäljessä. Olisi hyvä, jos ne voisi päivittää ajan tasalle versionvaihdon yhteydessä. Asia on viety jo aiemmin Annelin kautta Arille, mutta tästä ei ole olemassa tikettiä. </li>
    <li>Melinda-koulutus syyskuussa: Voisi käydä perustapaukset läpi ja sen lisäksi kyselytunti sekä ennakkokysymysten käsittelyä. </li>
    <li>Seuraava kokous tiistaina 21.5. –> Käsitellään mm. Melindan käyttäjäkyselyn tuloksia Koha-Suomen osalta ja niiden huomioimista koulutusten suunnittelussa. </li>
</ul>
  
#### 4. Kirjastopalvelun ja Melindan tietueet tuplana TäTissä ####
<ul>
    <li>Ks. Annan kysymys ”Kirjastopalvelun kuvailemia tietueita + Melindan tietueita tuplana” Teamsin Kysy kuvailusta -kanavalla 20.3.2024 </li>
    <li>Mistä johtuu, että TäTiin on jo kuvailtu Melinda-tietue, vaikka Kirjastopalvelultakin on kuvailu tulossa? Muuttuuko tietueiden kuvailustatus sillä välin, kun nimeke saapuu ja se primaarikuvaillaan? Saavatko kirjastot aineistoa eri aikoihin, esim. niin että jollakin on jokin nimeke jo kaksi kuukautta ennen muita? </li>
</ul>

Käytiin jonkin verran keskustelua Kirjastopalvelun kuvailulupauksista ja aikataulusta. Tehdään Koha-Suomen Teamsiin Kuvailu-kanavalle ohje/julkaisu asiaan liittyen.
 
#### 5. TäTin erikoisuuksia ja niiden käsittelyohjeet ####
<ul>
    <li>Jos Merge-ohjelmalla yhdistää tietueita Melindassa, niin yhdistynyt tietue valuu TäTiin asti, mutta ei välttämättä enää paikalliskantoihin, koska 035a-kentän Melinda-tunnus on vaihtunut. Johanna Räisä tutkii, voiko aktivointiarvoksi lisätä myös 035z-kentän arvon. Kannattaa tehdä ensin Merge-yhdistely ja sen jälkeen vasta tuoda tietue TäTiin. </li>
    <li>Jos tietueella on useampi ISBN-tunnus 020a-kentissä tai eri versioiden EAN-koodeja 024a-kentissä, voi tapahtua väärin valumisia (esim. moniosaiset kirjasarjat tai DVD- ja Blu-ray-elokuvat). OUTIssa korjattiin vanhoja aktivointiarvoja, koska 020-kentistä oli aktivoitunut viimeisen eikä ensimmäisen toistuman ISBN-tunnus. (Yleensä ensimmäinen ISBN on sarjan osan ja toinen kokonaisuuden.). Jos tietueella on osan ja kokonaisuuden ISBN, kannattaa olla erityisen tarkkana ja mahdollisesti tarkistaa Finnan kautta, onko muilla Koha-Suomen kirjastoilla nimekettä. Muutoksista ilmoitettava niille Koha-Suomen kirjastoille, joilla tietuetta on. </li>
    <li>Ns. vanhemman aineiston käsittely TäTissä: TäTi- ja Melinda-tietueiden muokkaaminen ja tietueiden tuominen Melindasta aiheuttaa sen, että muokkaukset valuvat kaikkiin niihin tietokantoihin, joissa teosta löytyy. Tästä voi seurata aineistotyyppien, pääkirjausten ja pääluokkien muutoksia sekä osakohteiden valumisvirheitä. Vaikka paikalliskantoihin on laitettu päälle valutuksenesto vanhempien tietueiden kohdalle, niin esto ei välttämättä kuitenkaan aina pidä, jos tietueita tallennetaan paikalliskannassa uudestaan jostain syystä. </li>
    <li>Kokouksessa todettiin, että toisten kirjastojen nimekkeiden tarkistelu Finnan kautta on työlästä, joten suositeltavaa on, että ennemmin jokainen kimppa seuraa hyvin säännöllisesti tietokantansa tietuesiirtäjän siirtoraporttia, jotta mahdolliset väärin valumiset tai pääkirjausten muutokset saadaan nopeasti kiinni. Kuvailijoiden kannattaa kuitenkin aina pitää mielessä, että tietueiden käsittely ja tallentaminen TäTissä vaikuttaa kaikkiin niihin Koha-Suomen paikalliskantoihin, joista kyseistä nimekettä löytyy. Epävarmoissa tapauksissa kannattaa laittaa viestiä Koha Teamsin Kuvailukanavalle. </li>
</ul>
 
#### 6. Kehitysehdotus MARC-muokkausten pohjista ja Tietueiden muokkaus eräajona -toiminnosta ####
<ul>
    <li>Tietueiden muokkaus eräajona -toimintoa pitäisi parantaa, jotta tietueita voisi muokkailla enemmän itse, eikä kehittäjiä tarvitsisi vaivata niin paljon. </li>
    <li>Pitäisi pystyä muokkaamaan kiinteiden kenttien merkkipaikkoja (samat merkkipaikat, joita voi muokata kuvailupohjien editoreilla) </li>
    <li>Pitäisi pystyä tyhjentämään tiettyjä kiinteitä kenttiä kokonaan (006- ja 007-kentät) </li>
    <li>Pitäisi pystyä muokkaamaan indikaattoreita (tiketti yhteisössä: <a href="https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=21860" target="_blank">MARC modification templates cannot check or change indicators </a>) </li>
</ul>

Aurorassa käyttäjät voivat itse muokata kiinteitä kenttiä, joten periaatteessa tällaisen toiminnon kehittäminen pitäisi olla mahdollista. Viedään asia eteenpäin. 
 
#### 7. Kehitysehdotus: Pitäisikö TäTin ylärivillä olla linkkejä käytetyimpiin kuvailuohjeisiin tai -sivustoihin? ####
<ul>
    <li>Esim. MARC21, Melindan toimintaohje, RDA-kuvailu MARC 21 -formaatilla -sivusto, Metatietosanasto, YKL, mahdollisesti Mikropalvelun/uuden tietuesiirtäjän ohje yms. </li>
    <li>Lisätään TäTin yläriville tärkeimmät linkit. Asiasta jatketaan keskustelua Teamsissa, jossa voi ehdottaa tarpeellisia lisättäviä sivustojen linkkejä. Päivi lisää ne sitten TäTiin. </li>
</ul>
 
#### 8. Muita asioita #### 
<ul>
  <li>RDA-konversiot: Pyydetyt RDA-konversiosääntöjen korjaukset on tehty. Tehdään testausajo versionpäivityksen jälkeen. </li>
  <li>Teamsin Musiikin kuvailu -kanavalle perustaan viestiketju, johon ilmoitellaan osakohteiden käsittelyyn liittyviä ongelmia. Tästä voisi sitten jokainen tarkistaa, onko jotain ongelmaa havaittu jo aiemmin ja miten se on ehkä ratkaistu. </li>
  <li>Toimijanimien muutokset TäTi-tietueille: Kannattaa tuoda tietue Melindasta sillä silloin saadaan 500-kenttään huomautus nimimuutoksesta sekä 900-kentän tiedot. Samalla kannattaa viedä tietue Melindaan. </li>
</ul>
 
#### 9. Seuraava kokous torstaina 16.5. klo 13.15 ####


---
## Kuvailuryhmän muistio 3/2024 ##

Aika: 14.3.2024 klo 13.15–14.51

Osallistujat: Mauri Aittaniemi (Lappi), Merja Hakulinen (Lumme), pj. Antti Heikkinen (OUTI), Pasi Hynninen (Helle), Suvi Kauranen (Kirkes), Päivi Knuutinen (Vaara), Marjukka Laapotti (Lastu), Tarja Mäkinen (Kyyti), Johanna Ranta (Kyyti), Marja Soisalo (Vaara), Anna Viitanen (Vaski), Johanna Räisä ja Emmi Takkinen (Koha-Suomi, kohdat 2-3)

Poissa: Anneli Österman (Koha-Suomi)

### Asialista ###

#### 1.	Kokouksen avaus ja sihteerin valinta ####

Sihteerivuorossa oli Johanna Ranta.

#### 2.	RDA-konversioiden eteneminen ja toimintasuunnitelma ####
<ul>
  <li>Ruotsinkielisen aineiston konversio: käytetäänkö suomen- vai ruotsinkielistä ohjelmaa? Vanhemmissa tietueissa kuvailun kielenä suomi, ruotsi tullut Kirjastopalvelun kuvailemien tietueiden myötä. Suomen kielellä kuvailluista tietueista tulee sekakielisiä, jos ne konvertoidaan ruotsinkielisellä ohjelmalla. Kaikissa tietokannoissa olisi ehkä hyvä valita sama taktiikka. </li>
  <li>Suomenkielisen kuvailun lyhenteiden avaaminen ja sanojen kääntäminen ruotsiksi ei ole helppoa. 336–338- ja 300-kenttien käännöksissä on se merkittävä ero, että 33x:n termejä on vain tietty tunnettu määrä ja ne esiintyvät aina samassa muodossa, kun taas 300-kentässä on paljon laajemmin erilaisia termejä ja niiden sanamuotoja. </li>
  <li>Tarvitaan varmaan vielä kolmaskin testikierros, jotta säännöt toimivat hyvin </li>
  <li>Konversiosäännöissä on nyt mukana sellaisiakin korjauksia, jotka voisi tehdä valmiille RDA-tietueille (esim. kansityypit ja kielen alkukirjaimen muuttaminen tietyissä kentissä). Nämä kyseiset korjausajot pitäisi tehdä myös niille tietokannoille, jotka ovat jo RDA:ta (Kirkes, Lastu ja Vaski). Vaskissa pitäisi myös konvertoida RDA:ksi sinne virheellisesti valuneet ISBD-tietueet. </li>
  <li>Jos tehdään konversio vain tietueille, jotka eivät jo ole RDA:ta, niin miten varmasti saadaan kaikki tietueet mukaan? </li>
  <li>Konversio tehdään Kohan versionvaihdoksen jälkeen. Tietueita voi ajaa öisin välivarastoista </li>
</ul>

#### 3.	Uusi tietuesiirtäjä ####
<ul>
  <li>Uudessa tietuesiirtäjässä on korjattu ongelmat, joita mikropalvelussa oli </li>
  <li>Tietuesiirtäjä on jo käytössä OUTIssa. Se on toiminut hyvin ja sitä voisi aktivoida muillekin kimpoille </li>
  <li>Vaski on valmis ottamaan tietuesiirtäjän käyttöön. Vaskin jälkeen on vuorossa Vaara. </li>
  <li>Kimpat voivat kommentoida tikettiin (<a href="https://github.com/KohaSuomi/Koha/issues/915" target="_blank">Valutuksen siirtäminen broadcast biblios liitännäiselle.</a>), milloin haluavat ottaa käyttöön uuden tietuesiirtäjän. Siihen siirrytään viimeistään versionvaihdoksen yhteydessä. </li>
</ul>

#### 4.	Kuulumiskierros ####

Onko huomattu muutoksia liittyen Kirjastopalvelun uuteen linjaukseen, jonka mukaan se kuvailee vain sellaisen aineiston, jonka on tilannut vähintään kolme kimppaa?

<ul>
  <li><b>Helle:</b> Ei ole huomattu isoja muutoksia Kirjastopalvelun toiminnassa. </li>
  <li><b>Kirkes:</b> On edistytty viime syksystä kuvailuasioissa, siirtoraportin läpikäymistä mietitty ja Marc-virheiden korjaustaulukkoa alettu käydä läpi. </li>
  <li><b>Kyyti:</b> Ei ole huomattu suurempaa muutosta Kirjastopalvelun toiminnassa. </li>
  <li><b>Lappi:</b> Hyllyyn tulee enemmän Kirjastopalvelun kirjoja, joihin ei tule kuvailua. Pääkirjasto on menossa taas remonttiin, kestää vuoden. </li>
  <li><b>Lastu:</b> Tutustutaan Kohaan, kuvailua ei ole vielä paljon kokeiltu. Kirjastopalvelun toiminnassa ei koeta tapahtuneen suurta muutosta entiseen, tuntuu, että heillä on aiempaa enemmän han. kaluuksia saada kuvailukappaletta. </li>
  <li><b>Lumme:</b> Ei mitään ihmeellistä ongelmaa Kirjastopalveluun liittyen, omakustanteissa voi kestää kauan ennen kuin kuvailu tulee. Marc-virheraportti lyhentynyt, 1/5 jäljellä alkuperäisestä listasta. </li>
  <li><b>OUTI:</b></li>
    <ul>
    <li>TäTi/Melinda-kuvailijoiden määrää vähennetty: Kuusamo jää pois, jatkossa primaarikuvailu vain Oulussa ja Raahessa. Oulu kuvailee oman aineistonsa lisäksi muiden OUTI-kirjastojen painetun aineiston ja nuotit, Raahe muiden OUTI-kirjastojen AV-aineiston ja lautapelit oman aineistonsa lisäksi. Kuvailijoita on nyt 7 kpl. </li>
    <li>Kirjastopalvelun toiminta on ollut jonkin verran epämääräistä. Joissakin tapauksissa ensin ilmoitetaan, ettei kuvailua tule, mutta sitten kuitenkin jossain vaiheessa kuvailustatus muuttuu. Äänitteiden kohdalla ei voi luottaa siihen, jos statuksen kohdalla on viiva. Oulussa on kysytty pariin tällaiseen tapaukseen kuvailua, ja vastaus on ollut, ettei kuulu kuvailupalvelun piiriin. Kuitenkin seuraavalla viikolla levyä on tarjottu viikkolistoilla ja kuvailu onkin tulossa.</li>
    <li>Ouluun on viime aikoina hankittu paljon vanhempia elokuvia, joiden EAN-koodilla löytyy kyllä valmiita tietueita, mutta niissä on yleensä vain eri jakaja. Tämä on aiheuttanut pohdiskeluja uusien tietueiden tekemisen kannattavuudesta.</li>
    <li>Valutushässäkkä keskiviikkona 21.2.: TäTissä poistettiin vanhemmista tietueista eräajona 942 $c-kentän aineistolajeja, koska osa niistä oli vanhentuneita. Vanhentuneet aineistotyypit 942 $c-kentissä johtivat siihen, että jos tietue valui uudestaan TäTistä paikalliskantaan, niin 942 $c-kentät eivät päivittyneet vaan niissä näkyi edelleen vanhat arvot (esim. CDM), jolloin aineistotyyppi näkyi tyhjänä paikalliskannan Perustiedot-näytöllä. Eräajojen seurauksena tietueet valuivat kuitenkin uudestaan OUTIin (ja osa myös ainakin Vaskiin), koska valutuksen eston aikaraja ei pitänyt jostakin syystä. OUTIin tehtiin tietueiden valutusraportin pohjalta uusi raportti, jonka mukaan TäTistä valui n. 5000 emotietuetta ja niiden mahdolliset osakohteet. Raportin pohjalta osa tietueista on jo saatu korjattua. Suurin osa valuneista oli OUTIn alun perin TäTiin kuvailemia, joten onneksi kovin suurta vahinkoa ei syntynyt. Joukossa oli kuitenkin tietueita, joita oli myöhemmin muokattu tai korjattu OUTIssa, muttei TäTissä, jolloin nämä muutokset ja korjaukset katosivat. Lisäksi jos TäTissä oli tuplatietueita, niin näistä OUTI-tietueen päälle valui eri tietue kuin OUTIssa alun perin, esim. BTJ:n tietueen päälle TäTi-tupla. Joukossa oli myös täysin virheellisiä valumisia, jos OUTIn tietueella oli väärä aktivoitumisarvo tai jollakin tietueella oli monta ISBN-tunnusta, esim. moniosaiset kirjat ja moniviestimet. Kehittäjiltä on pyydetty raporttia, jolla saisi kätevästi kiinni väärin valuneet tietueet tai joissa muuttui pääkirjaukset, mutta ainakaan Kohan raporteilla ei ole mahdollista tehdä sellaista muutosraporttia, jossa näkyisi 100- ja 245-kenttien vanha ja uusi arvo tai useampi 020/024-kentän toistuma. Johanna Räisä tutkii, voisiko tietuesiirtäjän raporttiin kehittää jonkinlaisen suodatuksen näiden muutosten osalta. Tietuesiirtäjän raportin ansiosta saatiin kuitenkin kiinni ja korjattua ne tietueet, joilla oli jostain syystä ollut OUTIssa väärä määrä osakohteita. (Tietuesiirtäjä ei päästä läpi niitä tietueita, joiden osakohteiden määrä ei täsmää paikalliskannassa ja TäTissä.) Tämän koko tapahtuman opetuksena on, että TäTissä ei pidä mennä tekemään mitään suuria eräajoja niitä ensin testaamatta ja ilmoittamatta kaikille muille kimpoille (jatkossa päätetään näistä Kuvailuryhmän kokouksissa). Lisäksi kun muokkaa tietueita paikalliskannassa, pitää aina muistaa tarkistaa, onko tietue TäTissäkin ja tehdä korjaus ensisijaisesti myös siellä. Myös TäTin tuplatietueet olisi hyvä saada poistettua.</li>
    <li>TäTistä valuu joka päivä sen verran paljon tietueita ja niiden muokkauksia, että on vaikeaa pysyä enää kartalla siitä, mikä on oikea korjaus ja mikä ei. Uuden aineiston kohdalla, kun on kerran tietueen tarkistanut, ei voi olla varma, pysyykö se kauan virheettömänä. Tehdyt korjaukset eivät myöskään välttämättä pysy tietueissa. Lisäksi edelleen tulee vastaan tapauksia, joissa jokin tietue on tuotu Melindasta TäTiin (joko KP:n tietueen päälle tai omaksi tietueekseen), mutta sitä ei ole korjattu eikä viety takaisin Melindaan. Jos Melinda-tietueen tuo TäTiin, niin se pitää muistaa aina tarkistaa ja korjata tarvittaessa sekä viedä Mikropalvelulla takaisin Melindaan, jotta tietueet pysyvät ajan tasalla eikä kukaan muokkaa vahingossa vanhentunutta tietuetta TäTissä. Ylipäänsä voisi olla hyvä katsoa Melinda-tietue läpi jo ennen sen poimimista TäTiin. Kaikkien pitäisi olla tarkkana sen suhteen mitä tekee TäTissä, koska muutokset valuvat herkästi kaikkialle. Jos tulee vastaan outoja tapauksia, joille ei oikein tiedä mitä tehdä, niin näistä voisi kysyä esim. Koha Teamsin Kuvailukanavalla. Tällöin saataisiin mahdolliset ongelmat muidenkin tietoon, jos jatkossa tulee vastaan samanlaisia tapauksia.</li>
    </ul>
  <li><b>Vaara:</b> Kirjastopalvelulla paljon ongelmia kuvailukappaleen saamisessa. Kun kuvailun saapuminen viipyy, joku kyllästyy odottamaan ja poimii TäTiin puutteellisesti luetteloidun Melinda-tietueen, mistä se valuu paikalliskantoihin. Kirjastopalvelulla ollut epäjohdonmukaisuutta julkaisuvuoden merkitsemisessä. Pieniä ja suuria virheitä kuvailuissa paljon, niiden reklamointi vie aikaa. </li>
  <li><b>Vaski:</b> Kirjastopalvelun kuvailussa ei ole huomattu suurempaa muutosta. Vaskissa on kuvailijavaje yhden kuvailijan lähdettyä Kansalliskirjastoon. Tehtäviä on jäänyt siksi roikkumaan enemmän kuin yleensä. Puppe-työkalu otettu käyttöön. Musiikkitallenteina näkyviä osakohteita ei ole edelleenkään korjattu.</li>
</ul>

#### 5.	Kuvailuryhmän vuosisuunnitelma 2024 ja tavoitteet ####

Tämän vuoden tavoite: TäTin ”käytössäännöt” selviksi kaikille kuvailijoille.

#### 6.	Tikettejä ####
<ul>
  <li>Valutuksen esto -toimintoa on korjattu. Seurataan, toimiiko nyt jatkossa paremmin. <a href="https://github.com/KohaSuomi/Koha/issues/844" target="_blank">Osakenttään 942b merkitty valutuksen esto ei aina toimi</a> </li>
  <li><a href="https://github.com/KohaSuomi/Koha/issues/1097" target="_blank">Raporttipyyntö: Virheellisesti valuneet tietueet</a> -> Jos tietueella on useampi 020-kenttä, miten estetään väärän tietueen valuminen sen päälle. </li>
  <li><a href="https://github.com/KohaSuomi/Koha/issues/1096" target="_blank">Voiko saada palauttamaan tietueen ennalleen, kun sen päälle on valunut konvertoimaton ISBD-tietue?</a> -> On mahdollista. Pitää vain ilmoittaa tietuenumero ja se lokin aika, mihin halutaan palauttaa, koska samasta tietueesta voi olla useampia muokkauslokimerkintöjä. </li>
  <li><a href="https://github.com/KohaSuomi/Koha/issues/373" target="_blank">Finto-liitännäinen Metatietosanastosta</a> -> odotetaan Metatietosanaston mahdollisia uudistuvaan RDA:han liittyviä muutoksia </li>
</ul>

#### 7.	Muita asioita ####
<ul>
  <li>Koha Teamsin Kuvailukanavalla olevaan Tietueiden massakorjausajot -taulukkoon on lisätty uusi välilehti, johon on koottu tällä hetkellä kesken olevat kuvailuasioihin liittyvät tiketit. Näin pystytään paremmin seuraamaan, mitä on kesken ja mitä niistä olisi hyvä priorisoida. Jatkossa voisi ainakin asiantuntijaryhmän kautta pyrkiä vaikuttamaan niiden edistymiseen. </li>
  <li>Seuraava Koha-Suomi-Melinda-työryhmän kokous 9.4. </li>
  <li>Kirjastopalvelun asiakasohjausryhmän etäkokous 23.4. </li>
</ul>

#### 8.	Seuraava kokous keskiviikkona 17.4. klo 13.15 ####


---
## Kuvailuryhmän muistio 2/2024 ##

Aika: 15.2.2024 klo 13.15–14.40

Osallistujat: Mauri Aittaniemi (Lappi), Merja Hakulinen (Lumme), pj. Antti Heikkinen (OUTI), Pasi Hynninen (Helle), Suvi Kauranen (Kirkes), Päivi Knuutinen (Vaara), Marjukka Laapotti (Lastu), Tarja Mäkinen (Kyyti), Johanna Ranta (Kyyti), Marja Soisalo (Vaara), Anna Viitanen (Vaski)

### Asialista ###

#### 1.	Kokouksen avaus ja sihteerin valinta ####

Sihteerivuorossa oli Tarja Mäkinen.

#### 2.	RDA-konversioiden eteneminen ####

Kansalliskirjastossa korjaukset vielä kesken. Odotetaan niiden valmistumista ennen kuin järjestetään toinen testikierros. Kannattaa huomata, että konversiossa vanhoilta tietueilta poistuu 245$h-kenttä. Kentässä on ilmaistu hakasuluissa yleismääre, mutta siihen voi olla eksynyt myös toiseen osakenttään kuuluvaa tietoa. OUTIssa on tehty raportteja, joilla voi tarvittaessa hakea tällaiset tietueet ja selata läpi, onko joukossa tietueita, jotka kannattaisi korjata ennen konversiota.

#### 3.	YSO-konversion testaustuloksia Vaskissa ####
<ul>
  <li><a href="https://github.com/KohaSuomi/Koha/issues/1040" target="_blank">YSA/YSO-konversion testausta</a> </li>
  <li>Kannattaa tutustua etukäteen, millaisia lokitiedostoja konversio-ohjelma tuottaa: <a href="https://www.kiwi.fi/display/ysall2yso/Konversio-ohjelman+lokitiedostot" target="_blank">YSA/YSO-konversio-ohjelman lokitiedostot</a> </li>
</ul>

Anna Viitanen kertoi Vaskin testaustuloksista – toimii niin hyvin kuin mahdollista. Virheet johtuneet siitä, että termit olivat virheellisiä tai vanhentuneita, eivät itse konversiosta. Osa virheellisistäkin oli konvertoitunut oikein. Jos yhdessä tietueessa oli ollut sama asiasana useaan kertaan eri asiasanaketjuissa, se oli konvertoidussa tietueessa siististi vain yhden kerran. Antti kysyy Kansalliskirjastosta vielä päivitystä 648-kentän konversiosääntöihin.

#### 4.	Melindan kuvailukoulutukset ####

Kimpoissa oli kyselty, millaista kuvailukoulutusta tarvittaisiin. Vastaukset vaihtelivat ja tuli ilmi, että kimppojen välillä on edelleen eroja siinä, miten kuvailu on järjestetty. Osassa kuvailu on keskitetty yhteen tai muutamaan kuntaan. Osassa kuvaillaan joka kunnassa. TäTi-tunnuksia on jaettu enemmän kuin mitä TäTiin kuvailevia oikeasti on. Eniten koulutusta toivottiin seuraavissa asioissa:
<ul>
  <li>kiinteämittaiset kentät</li>
  <li>osakohteet ja niiden käsittelyn ongelmatilanteet</li>
  <li>kertaus Kohassa kuvailusta</li>
  <li>esineet ja harvinaisemmat aineistotyypit</li>
  <li>Melinda-tietueiden käsittely</li>
  <li>Mikropalvelun toiminnot eli miten kuvailutiedot siirretään TäTistä Melindaan ja Melindasta TäTiin</li>
</ul>
  
#### 5.	TäTin ja paikalliskantojen emottomat osakohteet ####
<ul>
  <li><a href="https://github.com/KohaSuomi/Koha/issues/348" target="_blank">Emottomien osakohteiden poisto ajona</a> </li>
  <li>Raportissa myös luettelo virheellisistä osakohteista, joista osa pitäisi korjata </li>
  <li>ERROR:773w org "FI-Arto" does not match "FI-MELINDA" -> osakohteissa toinen 773w-kenttä, jossa linkki ARTO-tietokantaan. Kysytty Melindasta, mitä tarkoittaa. Vastattu, että jos Melindan osakohteissa on toinen 773w-kenttä, jossa on FI-Arton kontrollinumero, niin sen voi poistaa tietueista, jos Melinda-tietueen linkki on toimiva </li>
  <li>ERROR:ldr/7 is m -> osakohde monografiana, korjattava. Nykyään ei linkity enää emoon, vaikka emotietue on tietokannassa </li>
  <li>ERROR:773w org "FI-MELINDA" does not match "FI-TATI" -> Joko Melindaan vienti jäänyt vaillinaiseksi eli osakohteiden 003-kenttä jäänyt päivittymättä (FI-TATI -> FI-MELINDA), tai Melinda-tietueelle TäTissä tehtyjä uusia osakohteita, joita ei ole viety Melindaan. Nämä kannattaa korjata ensin TäTissä. Antti käy läpi TäTin virheraportin näiden osalta. </li>
  <li>TäTissä myös ERROR:773w org "FI-TATI" does not match "FI-MELINDA" -> Näissä tietueissa on jotain häikkää, joka pitää selvittää Melindan kanssa.</li>
</ul>

#### 6.	337a-kentän käännösvirhe ruotsinkielisissä RDA-tietueissa: oförmedlad -> omedierad ####
<ul>
  <li>TäTissä 2573 kpl -> korjataan joko RDA-konversiossa tai konversioiden jälkeen, kun on aikaa </li>
  <li>Voi korjata Tietueiden muokkaus eräajona -toiminnolla:</li>
    <ol>
    <li> Hae tietueet hakulausekkeella: media-type-term:oförmedlad </li>
    <li> Tarkista, ettei joukossa ole tietueita, joilla saattaa olla useampi 337-kenttä. Tällaiset tietueet kannattaa korjata käsin erikseen. </li>
    <li> Siirrä tietueet koriin </li>
    <li> Muokkaa tietueet eräajolla (Marc-muokkausten pohja: Päivitä olemassa oleva tai lisää uusi kenttä 337$a arvolla omedierad) </li>
    </ol>
</ul>

#### 7.	Moniviestimien kuvailu ####
<ul>
  <li>Moniviestinten primaarikuvailu on vähentynyt </li>
  <li>Toistaiseksi ei ole tarvetta päivittää moniviestimien kuvailupohjaa TäTissä </li>
</ul>

#### 8.	Muita asioita ####
<ul>
    <li>Toimijanimimuutosten päivitykset TäTissä (TäTissä on 5 vuotta vanhempia RDA-tietueita ja myös Melindaan linkittämättömiä Melinda-tietueita)</li>
  <ul>
  <li>olisi hyvä tarkistaa, onko tietue TäTissä, ja tehdä tarvittavat korjaukset siellä </li>
  <li>ei tuoda Melindasta TäTiin vanhoja, huonoja tietueita (omaan tietokantaan voi tuoda) </li>
  </ul>
    <li><a href="https://github.com/KohaSuomi/Koha/discussions/1068" target="_blank">Puppe-tilaustenvastaanottotyökalun esittely 21.2.</a> </li>
</ul>

#### 9.	Seuraava kokous To 14.3. klo 13.15 ####


---
## Kuvailuryhmän muistio 1/2024 ##

Aika: 25.1.2024 klo 13.15–14.41

Osallistujat: Mauri Aittaniemi (Lappi), Merja Hakulinen (Lumme), pj. Antti Heikkinen (OUTI), Pasi Hynninen (Helle), Päivi Knuutinen (Vaara), Sani Kuosmanen (Kirkes), Marjukka Laapotti (Lastu), Tarja Mäkinen (Kyyti), Johanna Ranta (Kyyti), Anna Viitanen (Vaski), Anneli Österman (Koha-Suomi), Johanna Räisä (Koha-Suomi, kohdat 2-4), Emmi Takkinen (Koha-Suomi, kohdat 2-4)

Poissa: Marja Soisalo (Vaara)

### Asialista ###

#### 1.	Kokouksen avaus ja sihteerin valinta ####

Päivi Knuutinen oli sihteerivuorossa ja valmistautunut tehtävään.

#### 2.	Tilannekatsaus RDA-konversioiden testituloksiin ####
<ul>
  <li>RDA-konversiossa testattujen nimekkeiden kohdalla on huomattu puutteita konversiosäännöissä etenkin ruotsin kielellä kuvailtujen nimekkeiden kohdalla. (Tiketti: <a href="https://github.com/KohaSuomi/Koha/issues/974" target="_blank">RDA-konversion testaus</a>)  </li>
  <li>Joistakin konversiovirheistä on hankala sanoa, johtuuko virhe itse tietueesta vai konversiosääntöjen puutteista.</li>
  <li>Kansalliskirjasto on luvannut päivittää konversiosääntöjään. Osa päivityksistä on jo tehty, muttei kaikkia. Antti kysyy Kansalliskirjastosta neuvoa virhetapausten selvittelyyn.</li>
  <li>Tietokantojen siivous- ja korjausajoja olisi syytä saada tehtyä ennen kuin RDA-konversio tehdään, jotta konversio onnistuisi paremmin ja jäisi vähemmän käsin korjattavaa tietoa. Päivi Knuutinen tekee tarvittaessa tiketit GitHubiin ja kukin kimppa saa kommentoida, tarvitseeko jonkin tietyn korjauksen omaan tietokantaansa.</li>
  <li>Todettiin, että jos nimeke on jo RDA-kuvailtu, sitä ei enää konvertoida, jolloin työ nopeutuu.</li>
  <li>Vaskissa voidaan testata YSA/YSO-konversiota ensimmäisenä, sillä siellä aineisto on jo RDA-muodossa. Päivi tekee tiketin, johon kerätään testattavia tietueita. [Lisäys 26.1.: Tiketti: <a href="https://github.com/KohaSuomi/Koha/issues/1040" target="_blank">YSA/YSO-konversion testausta</a>] </li>
</ul>

#### 3.	Uuden tietuesiirtäjän käyttöönotto ####
<ul>
  <li>Miten Vaaran ja Vaskin testaukset etenevät?</li>
- Vaaran testaus ei ole toimiva, koska Vaaran testikanta on redusoitu. Vaskin testaustulokset ovat lupaavia.
  <li>Tietuesiirtäjään liittyvä tiketti (odotustilassa): <a href="https://github.com/KohaSuomi/Koha/issues/286" target="_blank">Siirtoraportti-toimintoon tieto, onko siirtoraportin tietue uusi täydellisesti kuvailtu tietue VAI jo olemassa olevan täydellisesti kuvaillun tietueen muutostietue</a> </li>
- Johanna Räisän mielestä tämä on mahdollista toteuttaa tavalla tai toisella.
  <li>Osakohteiden aineistotyypin lisäys vielä työn alla </li>
  <li>Asennus voidaan aloittaa yhdestä kimpasta, tarkastella tilannetta hetken aikaa ja sitten laajentaa muihin.</li>
</ul>

#### 4.	5- ja 9-osakenttien suojaukset Mikropalvelussa ####
<ul>
  <li>Pitäisikö poistaa, koska estävät niiden kenttien muokkaamisen, jotka sisältävät jommankumman osakentän?</li>
- Johanna Räisä miettii, miten voisi toteuttaa. Testattava.
  <li>Mikropalvelun toiminta siirtymässä uudelle liitännäiselle: <a href="https://github.com/KohaSuomi/koha-plugin-broadcast-biblios/issues/4" target="_blank">Melinda-vientien ja -tuontien siirtäminen liitännäiseen</a> </li>
</ul>

#### 5.	MARC-virheellisten tietueiden korjausajot ja muut massakorjaukset ####
<ul>
  <li>Taulukko Kohan massakorjauksista ja tikettien laadinta </li>
- Sovittiin, että käsitellään tulevissa kokouksissa aina muutama korjausehdotus kerrallaan, mitkä kimpoista tarvitsevat kyseiset korjausajot, ja tehdään näistä sitten tarvittaessa tiketit.
  <li>Kumean tekemät muutokset Metatietosanastossa tai Melindaan pyytämät korjausajot </li>
  <ul>
<li>Missä vaiheessa lisätään taulukkoon? </li>
-Päivitetään sitä mukaa kun näistä ilmoitetaan Kumean muistioissa.
<li>Sanaston muutosten vaikutukset kuvailupohjien valikkoihin: Jos esim. termi ”avattu nimeke” jää pois, poistetaanko auktorisoitujen arvojen valikosta heti? 
-> Vanhaa tietuetta muokatessa pitää huomata, että jos tietueessa on jokin vanhentunut termi, joka puuttuu valikosta, niin se katoaa, kun tietueen aukaisee valikon sisältävällä kuvailupohjalla. Termiä ei myöskään näy perustiedot-näytöllä, jos tietue on tallennettu valikon sisältävällä kuvailupohjalla.</li>
- Sovittiin, että valikot ajantasaistetaan.
  </ul>
</ul>

#### 6.	Kuulumisia Koha-Suomi-Melinda-työryhmän kokouksesta 24.1. ####
<ul>
  <li>TäTi-putken valmistelu etenee omalla painollaan. Seuraavaksi Kirjastopalvelun tietueet jaotellaan osakohteettomiin ja osakohteellisiin paketteihin ja testataan, miten niiden siirtäminen ja Melinda-tietueisiin yhdistäminen onnistuu.</li>
  <li>Kuvailukoulutusta mahdollisesti elo/syyskuussa, kun Lastun käyttöönotto on lähempänä.</li>
  <li>Seuraava työryhmän kokous 9.4.</li>
</ul>
-> Seuraavaan kokoukseen mennessä kukin kimppa miettii, millaista kuvailukoulutusta olisi tarpeen järjestää. Onko koulutus pelkästään Koha-Melinda-asioihin keskittyvä vai kuinka paljon itse kuvailuun keskittyvä? Tarvitaanko koulutusta esim. Kohan kuvailutyökalujen tai Mikropalvelun toiminnoista, Fennica/Viola- tai muiden Melinda-tietueiden käsittelystä vai joidenkin tiettyjen aineistolajien kuvailusta?


#### 7.	Tikettejä ####
<ul>
  <li><a href="https://github.com/KohaSuomi/Koha/issues/1006" target="_blank">Välimerkkiongelma Z39.50/SRU-haussa</a> </li>
  <li><a href="https://github.com/KohaSuomi/Koha/issues/998" target="_blank">Marc-virheiden korjausta kentästä 007-s</a> </li>
   - Kimppojen kommentoitava, halutaanko korjausajo omaan kimppaan.
</ul>

#### 8.	Muita asioita ####

TäTissä on paljon yksittäisiä MARC-virheitä, joita on muutamia/virhe. Kukin kimppa voisi korjata tällaisia virheitä itse, jos oman kirjaston tunnus näkyy tietuerivillä. 

#### 9.	Seuraavat kokoukset ####
<ul>
   <li>To 15.2. klo 13.15 </li>
   <li>To 14.3. klo 13.15 </li>
   <li>Ke 17.4. klo 13.15 </li>
   <li>To 16.5. klo 13.15 </li>
</ul>


