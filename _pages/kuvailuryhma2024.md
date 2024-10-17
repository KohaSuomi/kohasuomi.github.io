---
layout: single
permalink: /kuvailuryhma2024
header:
  overlay_color: '#5e616c'
  overlay_image: /assets/images/cropped-pexels-photo-113850.jpeg
toc: true
title: 'Koha-Suomen kuvailuryhmän muistiot 2024'
---

## Kuvailuryhmän muistio 7/2024 ##

Aika: 2.10.2024 klo 13.15–14.30

Osallistujat: Mauri Aittaniemi (Lappi), Merja Hakulinen (Lumme), pj. Antti Heikkinen (OUTI), Pasi Hynninen (Helle), Suvi Kauranen (Kirkes), Päivi Knuutinen (Vaara), Marjukka Laapotti (Lastu), Marja Leskinen (Vaara), Tarja Mäkinen (Kyyti), Johanna Ranta (Kyyti), Anna Viitanen (Vaski), Anneli Österman (Koha-Suomi), Johanna Räisä (Koha-Suomi, kohdat 2-4)

### Asialista ###

#### 1.	Kokouksen avaus ja sihteerin valinta ####

Antti Heikkinen avasi kokouksen. Sihteerivuorossa oli Mauri Aittaniemi.

#### 2.	RDA-konversiot ####
<ul>
  <li><a href="https://github.com/KohaSuomi/Koha/issues/834" target="_blank">RDA-konversio tuotantoympäristöön</a> </li>
  <li>28.–29.9.: Vaara, OUTI, Siili, Helle</li>
  <li>5.–6.10.: Lumme, Kyyti, Vaski, Lappi</li>
  <li>Myöhemmin Kirkes ja Lastu</li>
  <li>TäTin konversio oli tehty. Konversiossa osakohteilta oli kadonnut 773 h-kenttä. Tämä oli johtunut siitä, että ISBD-konversiossa kenttä poistetaan, koska siinä on väärät tiedot. Nykyään kenttään merkitään kuitenkin emon 300a ja e-kenttien tiedot. Nämä oli kuitenkin jo korjattu.</li>
  <li>Helle: Tehdystä konversiosta ei oltu vielä huomattu virheitä.</li>
  <li>Vaara: Joitain pieniä virheitä oli syntynyt. Kirjastopalvelulta tulleissa tietueissa on ollut virheitä 336-, 337- ja 338-kentissä, koska 040 b -kenttä on puuttunut ja konversio on tullut 008-kentän perusteella. Konversion jälkeen oli korjattava n. 60–70 tietuetta, jotka olivat oikeasti suomenkielisiä (008/35-37=fin), mutta joiden kuvailukielenä oli 040b-kentässä ruotsi. Tällaisia tietueita, joiden 336-, 337- ja 338-kentissä (ja mahdollisesti muissakin) on nyt konversion jälkeen ruotsinkieliset termit, on muissakin kimpoissa.</li>
  <li>Joissakin 336-, 337- ja 338-kentissä voi olla vielä ISBD-ajan arvoja, joita voi korjailla virheitä huomatessaan. Nämä johtuivat lähinnä vaillinaisista kiinteiden kenttien arvoista tai 336- ja 337-kentissä olleista kirjoitusvirheistä.</li>
</ul>

#### 3.	YSO-konversio ####
<ul>
  <li><a href="https://github.com/KohaSuomi/Koha/issues/1040" target="_blank">YSA/YSO-konversion testausta</a> </li>
  <li>648-kenttä ja YSO-aikaan kuulumattomat termit -> Ei saada korjausta, vaan se on tehtävä itse. Konversio-ohjelmaa ei enää päivitetä Kansalliskirjaston toimesta. Antti oli ottanut yhteyttä Kansalliskirjastoon, ja konversio-ohjelman tekijät olivat jo nykyään muissa töissä. </li>
  <li>Päätettiin alustavasti, että YSO-konversiot tehdään versionvaihdon jälkeen ensi tammikuussa ja tarvittavat korjaukset tehdään itse konversion jälkeen.</li>
</ul>

#### 4.	Melindan replikoinnit ja TäTin tietuemuokkaukset eivät välttämättä aina valu paikalliskantoihin asti, jos tietuetta päivitetään lyhyessä ajassa monta kertaa peräkkäin. ####

Antti kysyi, kuinka paljon valutuksia "menee ohi", ja miten pitäisi toimia, jotta tältä vältyttäisiin? Määrä tuntui olevan tuntematon. Johanna Räisä kertoi, että päivityksiä ei voi oikeastaan laittaa tapahtumaan tiheämmin eli alle minuutissa. Esim. osakohteellisissa tietueissa voi tulla ongelmia, jos päivitystiheys on hyvin nopea. Kun tietuetta muokataan uudelleen, pitäisi aina odottaa, että korjaus näkyy tietokannassa. Jos jonoon tallennetaan useita kertoja, vain ensimmäinen korjaus pääsee valumaan paikalliskantoihin. Ohjelma katsoo, että tietue on jo jonossa, eikä huoli viimeistä tallennusta mukaan. Johanna mietti, voisiko ohjelma toimia eri tavalla ja valuttaisi vasta viimeisen tallennuksen samasta tietueesta. Virheellisiä valumisia voi tulla enempikin, jos on ollut meneillään massakorjausajoja. Antti ottaa asian puheeksi seuraavassa Koha-Suomi-Melindan kokouksessa, voiko replikointia Melindasta TäTiin hidastaa sen verran, ettei syntyisi tällaisia tallennusjonoja.

#### 5.	TäTin RDA-konversion jälkeiset korjaukset ####
<ul>
  <li>Ruotsinkielisessä aineistossa suhdetermi konstnär -> framförande person, jos on kyse esittäjästä. </li>
  <li>336-, 337- ja 338-kentät, joihin on jäänyt ISBD-ajan arvot </li>
  <li>Konversiossa paljastui myös muita alun perin virheellisesti tehtyjä tietueita</li>
</ul>

#### 6.	Lisäpainoshuomautusten katoaminen paikalliskannan tietueista valumisten yhteydessä ####

Tästä keskusteltiin lyhyesti. Lisäpainoshuomautusten katoamista ei pidetty kovin vakavana asiana.

#### 7.	MARC-formaatin automaattinen päivittäminen ####
<ul>
  <li>Tiketissä: <a href="https://github.com/KohaSuomi/Koha/issues/1241" target="_blank">MARC-formaatin päivittäminen</a> </li>
  <li>Päivitys ei poista formaatista poistettuja kenttiä, koska silloin niissä mahdollisesti olevia tietoja ei pääse käsittelemään Kohassa kuvailueditoreilla ja tiedot myös katoavat, jos tietueen tallentaa. </li>
  <li>MARC-virheraportti ilmoittaa poistetuista kentistä, vaikka ne kuvailupohjissa vielä olisivatkin </li>
  <li>Esimerkiksi kentät 022 l ja m (ISSN-L ja peruttu ISSN-L) ovat poistuneet käytöstä kesäkuussa 2024. Tiedot laitetaan jatkossa kenttään 023. Melindassa poistuneiden kenttien tiedot on jo siirretty oikeisiin kenttiin. Keskusteltiin siitä, miten nämä korjaukset olisi järkevintä tehdä Kohassa. Korjataanko tietueet ensin ja poistetaan formaatista poistetut osakentät vasta sitten kuvailupohjista vai poistetaanko osakentät heti ja tehdään korjaukset myöhemmin esim. erillisillä korjausajoilla. Formaatista poistetut kentät säilyvät tietueissa niin kauan kuin niitä ei mennä avaamaan sellaiselle kuvailupohjalle, josta kyseiset kentät on poistettu. </li>
  <li>Todettiin, että olisi hyvä, jos kuvailupohjat ovat koko ajan tasalla eikä niissä ole formaatista poistettuja kenttiä </li>
  <li>Antti kysyy Pasi Kalliselta, voisiko automaattista päivitystoimintoa säätää siten, että formaatista poistetut kentät poistuvat kuvailupohjista päivityksen yhteydessä. Tässä on otettava kuitenkin huomioon, että pohjissa on tälläkin hetkellä formaattiin kuulumattomia kenttiä, kuten 090 tai jotkut 5- ja 9-osakentät, joita ei saisi poistaa pohjista. Selvitetään myös, onko mahdollista korjata 022 l ja m-kentät sisältävät tietueet koneellisesti vai pitääkö ne korjata käsin. Todennäköisesti tällaisia tietueita ei ole Koha-Suomen tietokannoissa kovin paljon.</li>
</ul>

#### 8.	Metatietosanaston päivitykset ####

246i-kentän ”julkaistu aiemmin jne.” fraasit 775-kenttään -> korjaukset tehtävä käsin

#### 9.	Tikettejä ####
<ul>
  <li><a href="https://github.com/KohaSuomi/Koha/issues/1406" target="_blank">Vaari-tunnukset</a>  </li>
  <li><a href="https://github.com/KohaSuomi/Koha/issues/1419" target="_blank">Osakohteiden näkymisessä emokohteessa ongelmia, jos osakohteen taso on d</a> -> Ongelma oli vain Lastu-kirjastoissa. Kyseessä olivat 1970–1980-lukujen vanhat osakohdetietueet. Johanna Räisä oli korjannut näitä niin, että osakohteet näkyvät emon yhteydessä. </li>
  <li><a href="https://github.com/KohaSuomi/Koha/issues/454" target="_blank">Tilaustietueet eivät yhdisty aina oikein, kun 024a-kentästä tarkistetaan vain ensimmäinen osakenttä</a> -> Korjaus tulossa marraskuun versionvaihdon jälkeen</li>
</ul>

#### 10.	Muita asioita ####
<ul>
  <li>Vaarassa kaikki Kirjastopalvelun lähettämät korjaukset eivät ole siirtyneet paikalliskantaan asti. Yritetään selvittää, mistä tämä johtuu ja onko muillakin kimpoilla samanlaisia tapauksia. </li>
  <li>Seuraava Koha-Suomi-Melinda-tilannepalaveri 8.10. </li>
  <li>Melinda/Koha-koulutus torstaina 7.11. klo 13.00–15.30 </li>
  <li>Versionvaihto 18.11. -> Ei merkittäviä muutoksia kuvailuun </li>
  <li>Kirjastopalvelun asiakasohjausryhmän kokous 19.11. </li>
</ul>

#### 11.	Seuraava kokous keskiviikkona 6.11. Klo 13.15–14.45 ####


---
## Kuvailuryhmän muistio 6/2024 ##

Aika: 5.9.2024 klo 13.15–14.16

Osallistujat: Merja Hakulinen (Lumme), pj. Antti Heikkinen (OUTI), Pasi Hynninen (Helle), Suvi Kauranen (Kirkes), Päivi Knuutinen (Vaara), Marjukka Laapotti (Lastu), Marja Leskinen (Vaara), Johanna Ranta (Kyyti), Anna Viitanen (Vaski), Johanna Räisä (Koha-Suomi, kohta 2, klo 13.46 alkaen)

Poissa: Mauri Aittaniemi (Lappi), Tarja Mäkinen (Kyyti), Anneli Österman (Koha-Suomi)

### Asialista ###

#### 1.	Kokouksen avaus ja sihteerin valinta ####

Sihteerinä toimi Merja Hakulinen. Vuoro vaihdettiin Mauri Aittaniemen kanssa.

#### 2.	RDA-konversioiden tilanne ####
<ul>
  <li>TäTin RDA-konversio on torstaina 12.9.2024. </li>
  <li>Juhannuksen tienoilla valuneet tietueet koetetaan palauttaa alkuperäisiksi (<a href="https://github.com/KohaSuomi/Koha/issues/1298" target="_blank">Tiketti 1298</a>, Pasi Kallinen korjaa). </li>
  <li>Ruotsinkielisen aineiston konversio onnistuu, kun 040 b –osakentässä on kielimerkintä swe. Tämän takia ISBD-ajan ruotsin kielellä kuvailtuihin musiikkiaineistoihin ja äänikirjoihin on ennen konversiota lisättävä tietueiden erämuokkauksella 040b-kenttä, jossa on arvo swe. </li>
  <li>Ruotsinkielisillä konversiosäännöillä ajetaan tietueet, joiden 008/35-37 ja 041a = swe + 000/06 = a tai tietueessa on 040b=swe. </li>
  <li>Vaski, Kirkes ja Lastu haluavat myös uuden konversion (tehty kerran jo aikaisemmin), koska konversiossa päivitetään myös valmiita RDA-tietueita ajan tasalle. </li>
  <li>Konversioiden edistymistä voi seurata tiketissä: <a href="https://github.com/KohaSuomi/Koha/issues/834" target="_blank">RDA-konversio tuotantoympäristöön</a> </li>
</ul>

#### 3.	Kuulumiskierros ####
<ul>
  <li><b>Helle:</b> Kysymys kohdeviittauksista Kirjailijapoetiikat-kirjassa (9789518588644). Kirjastopalvelun mukaan kirjailijaviittauksia ei laiteta tietueeseen, silloin kun niitä tulisi enemmän kuin 20. Tämä ohjeistus on Fennicasta. Artikkelit löytyvät vain 505-kentästä, jolloin kohdehenkilön nimellä hakeminen on vaikeaa tai jopa mahdotonta. Yksi vaihtoehto olisi viitata valikoiden tärkeimpiin/kysytyimpiin kirjailijoihin. Sisku oli keskustellut asiasta ja uuden RDA:n myötä teos kuvailtaisiin kokonaisuutena eikä artikkelitasolla. Seurataan tilannetta. Siskun sähköpostiin kannattaa laittaa kysely, jotta saadaan virallinen vastaus (sisa-posti (at) helsinki.fi). </li>
  <li><b>Kirkes:</b>  Saisiko listan Marc-virheiden tärkeimmistä korjattavista asioista? Korjaustyön helpottamiseksi heillä on jo tehty useita raportteja. Todettiin, että 653-kenttää voi edelleen käyttää, jos termeille ei ole auktorisoitua asiasanaa. </li>
  <li><b>Kyyti:</b>  Ei erikoisia kuulumisia. </li>
  <li><b>Lastu:</b>  Liittyy Kohaan 30.9.2024. TäTi-tunnuksia vain Lahteen 4 henkilölle. </li>
  <li><b>Lumme:</b>  Ei erikoisia kuulumisia. </li>
  <li><b>OUTI:</b>  Tehty Marc-korjauksia. 006- ja 007-kenttien Marc-virheitä voi korjata tietueiden erämuokkauksella. Raporttikirjastossa on valmiita raportteja, joilla voi hakea tietynlaisia virheellisiä tietueita. Pitää vielä miettiä ohjeistusta näihin. Koha Teamsin Tietueiden massakorjaukset -taulukkoon on lisätty tieto niistä Marc-virheiden korjauksista, jotka voi tehdä erämuokkauksella. </li>
  <li><b>Vaara:</b>  Virheelliset valumiset harmittavat, samoin KP:n hitaus. Kokoelma-/poistopartio kiertää Vaaran kirjastoissa ohjeistamassa ja keskustelemassa mm. poistotyöstä. Moniviestin-paketteja on purettu osiksi ja tietueiden Marc-virheitä korjattu. </li>
  <li><b>Vaski:</b>  Musiikkitallenteina näkyneiden tietueiden kiinteät kentät ja aineistotyypit on korjattu kesän aikana. Tiketti 438 on jo suljettu, mutta sieltä löytyy Mikko Liimataisen tekemä ohjeistus erämuokkaukseen (007-kenttä): <a href="https://github.com/KohaSuomi/Koha/issues/438" target="_blank">Korjauksia osakohteiden aineistolajeihin (musiikkitallenne)</a> </li>
</ul>

#### 4.	Kesän aikana tehdyt poistot, korjaukset ja kuvailupohjien muokkaukset TäTissä ####
<ul>
  <li>Poistettu tuplatietueita ja Melindasta poimittuja vanhoja ISBD-tietueita sekä vanhentuneita RDA-tietueita, joita ei ollut linkitetty Melindaan </li>
  <li>Tehty MARC-virheiden korjausta ja myös poistettu paljon Kirjastopalvelun vanhoja MARC-virheellisiä tietueita (lähinnä e-kirjoja ja -äänikirjoja) </li>
  <li>TäTissä on aika paljon itse kuvailtua teksti- ja muuta aineistoa, joissa on turhaan täytetty 006- tai 007-kentät. Näitä voisi ehkä korjailla konversioiden jälkeen. </li>
  <li>Kirja-pohjassa 340-kenttä (fyysinen tallenne) </li>
  <li>020 q-osakentästä on poistettu turhia termejä (tarkentava tieto) </li>
</ul>

#### 5.	Eri ohjeiden päivitys ja linkitys Melindan toimintaohjeeseen ####
<ul>
  <li>Mikropalvelu-termin vaihto Tietuesiirtäjä-termiin myös Kohan ohjeisiin </li>
  <li>Johanna Räisä muistutti, että GitHubissa on kaavio tietueen kulusta: <a href="https://github.com/KohaSuomi/koha-plugin-broadcast-biblios/wiki" target="_blank">Tietuesiirtäjän käyttöohje</a>, Tietuesiirtäjän ohje löytyy myös Koha ohje suomeksi -sivujen kautta: <a href="https://koha-suomi.fi/dokumentaatio/kuvailu/#512-tietueen-valuminen-t%C3%A4tist%C3%A4tietuesiirt%C3%A4j%C3%A4" target="_blank">5.1.2. Tietueen valuminen TäTistä/Tietuesiirtäjä</a> </li>
</ul>

#### 6.	Koha-Suomi-Melinda-tilannepalaveri 27.8. ####

Kuvailukoulutus suunniteltu nyt marraskuun alkuun. Ilmoittautuminen hyvissä ajoin lokakuussa, jotta ehditään käsitellä ennakkokysymykset ja laatia niihin vastaukset.

#### 7.	Tikettejä ####
<ul>
  <li><a href="https://github.com/KohaSuomi/Koha/issues/1241" target="_blank">MARC-formaatin päivittäminen</a> -> Päivitetty kesällä, mutta automaattinen päivitys toimi vasta syyskuun alussa. Versio on nyt viimeisin 37. </li>
  <li><a href="https://github.com/KohaSuomi/Koha-translations/issues/51" target="_blank">000-kentän editorissa on vanhat suomennokset merkkipaikkojen 07 ja 17 arvoille</a> -> Päivitetty 3.9. </li>
  <li><a href="https://github.com/KohaSuomi/Koha/issues/1338" target="_blank">Osakohteet valuneet ilman aineistotyyppiä</a> -> Korjauksia on tehty, muttei toimi täysin aukottomasti </li>
  <li><a href="https://github.com/KohaSuomi/Koha/issues/1298" target="_blank">Vanhoja kuvalutietoja valuu uusien päälle</a> -> Tietueiden palautusskripti tekeillä, korkea prioriteetti, jotta saadaan RDA-konversiot käyntiin </li>
  <li><a href="https://github.com/KohaSuomi/Koha/issues/1316" target="_blank">Vaara: 008-kenttien virheen korjaus</a> -> Kimpat kommentoivat GitHubissa, tarvitseeko heille tehdä tätä korjausta. </li>
  <li><a href="https://github.com/KohaSuomi/Koha/issues/1293" target="_blank">Lisää raportteja MARC-tietueiden korjauksia varten</a> -> Ks. <a href="https://koha-suomi.fi/dokumentaatio/raporttikirjasto/#kuvailu" target="_blank">Kohan raporttikirjasto</a> </li>
  <li><a href="https://github.com/KohaSuomi/Koha/issues/286" target="_blank">Siirtoraportti-toimintoon tieto, onko siirtoraportin tietue uusi täydellisesti kuvailtu tietue VAI jo olemassa olevan täydellisesti kuvaillun tietueen muutostietue</a> -> Kohaan on tehty oma erillinen raportti, joka näyttää ainoastaan tietueet, joiden 084-, 100-, 110-, 111- tai 245-kentissä on tapahtunut muutos. Raportti ei ota huomioon ennakkotietueiden päivittymistä. Käytössä jo ainakin OUTIssa ja Hellessä. Asennettu myös Vaaraan. </li>
</ul>

#### 8.	Muita asioita ####
<ul>
  <li>Muistuttakaa tätejä ja poimijakuvailijoita siitä, että tarkistetaan ensin KP:n kuvailustatus. Jos kuvailu on tulossa KP:sta, Melindasta ei saa tuoda tietuetta tätiin -> tietueet tuplaantuvat. Melindasta voi tuoda tietueen suoraan paikalliskantoihin. </li>
  <li>BIBFRAME Workshop in Europe 2024 -konferenssi Helsingissä 17.-18.9.2024, myös etänä voi osallistua: <a href="https://www.kansalliskirjasto.fi/fi/tapahtumat/bibframe-workshop-europe-syyskuussa-helsingissa" target="_blank">BIBFRAME Workshop in Europe syyskuussa Helsingissä</a> </li>
</ul>

#### 9.	Syksyn kokousajat ####
<ul>
  <li>Ke 2.10. klo 13.15 </li>
  <li>Ke 6.11. klo 13.15 </li>
  <li>Ke 4.12. klo 13.15 </li>
</ul>


---
## Kuvailuryhmän muistio 5/2024 ##

Aika: 16.5.2024 klo 13.15–14.40

Osallistujat: Mauri Aittaniemi (Lappi), Pasi Hynninen (Helle), Merja Hakulinen (Lumme), pj. Antti Heikkinen (OUTI), Päivi Knuutinen (Vaara), Sani Kuosmanen (Kirkes), Tarja Mäkinen (Kyyti), Johanna Ranta (Kyyti), Anna Viitanen (Vaski), Anneli Österman (Koha-Suomi), Johanna Räisä ja Emmi Takkinen (Koha-Suomi, kohdat 2–4)

Poissa: Marjukka Laapotti (Lastu), Marja Leskinen (Vaara)

### Asialista ###

#### 1.	Kokouksen avaus ja sihteerin valinta ####

Kokouksen sihteeriksi valittiin Anna Viitanen.

#### 2.	Kohan versionvaihto ####
<ul>
  <li>Versionvaihdon jälkeen ei ole ollut isompia ongelmia. Tietueiden vieminen Melindaan ei vielä onnistu kaikissa kimpoissa. Tietuesiirtäjä Melindan ja TäTin välillä on saatu eilen toimimaan, mutta osassa kimppoja pääkäyttäjät eivät ole vielä tehneet kuvailijoiden tunnusten aktivointia. </li>
  <li>Melindan replikointi ollut pois päältä 6.5. lähtien. Melindassa tehtyjä muutoksia ei siis ole tämän jälkeen valunut TäTiin. [Lisäys 17.5.: Replikointi saatu taas toimimaan 17.5.] </li>
  <li>Tietuenäytön muutoslokista pystyy nyt pääkäyttäjätunnuksilla palauttamaan tietokantaan muokatun tietueen edellisen version. Tätä kokeillaan vielä testikannassa. </li>
</ul>

#### 3.	Tietuesiirtäjän toiminta ####
<ul>
  <li>Tietuesiirtäjän toiminnassa on pieniä eroja Mikropalveluun verrattuna. Keskusteltiin muutoksista. Kannattaa tarkkailla toimintaa ja raportoida mahdollisista ongelmista. Antti päivittää vielä ohjeita. Jos ohjeille löytyy sopiva tallennuspaikka, lisätään niihin johtava linkki TäTin ”Kuvailijoille” -valikkoon. </li>
  <li>Aineistotyyppien muodostumisongelma on korjaantunut tiistain päivityksessä. Jos tämän suhteen on vielä ongelmia, kyse voi olla kimpan MARC-kenttien suojausasetuksista. </li>
  <li>Tietueiden valuminen tapahtuu aikaisempaa hitaammin. Vie/tuo -napin painaminen vie tietueen jonoon, jota käsitellään 5 minuutin välein. Näin pyritään estämään liian nopean valumisen aiheuttamat (osakohde)ongelmat. </li>
  <li>Kyytissä on edelleen valunut vanhoja tietueita. Ilmeisesti kyse on tietueista, joissa lainaus on muuttanut tietueen aikaleimaa. Valuminen toimii niin, että aikaleimaltaan uudemman paikalliskannan tietueen päälle ei pitäisi valua TäTistä tietuetta. Jos tällaista havaitsee, kannattaa tehdä tiketti. Paikalliskantojen asetuksissa saattaa olla eroja, jotka vaikuttavat valumiseen. </li>
</ul>

#### 4.	RDA-konversiot ja toimintasuunnitelma ####
<ul>
  <li>Konversiot tehdään kesän aikana. </li>
  <li>Päädyttiin siihen, että ruotsinkielisen tekstiaineiston (008 mp 35-37 /041a = swe + 000/06 = a) tietueet konvertoidaan kaikissa tietokannoissa ruotsiksi. </li>
  <li>Konversiosääntöihin on tehty Kansalliskirjastossa muutoksia. Antti on testannut korjattuja sääntöjä, korjauksia tarvitaan vielä lisää. </li>
  <li>RDA-konversiossa on mukana myös kansityyppien korjaus ja 240-kentän välimerkityksen / alkukirjaimen koon muutos. Nämä korjaantuvat konversiossa myös sellaisissa tietueissa, jotka jo ovat RDA:ta. Jo RDA-konvertoitujen tietokantojen kohdalla (Vaskin ja Kirkes) pitää miettiä, kuinka nämä korjaukset saataisiin tehtyä. </li>
  <li>Keskusteltiin siitä, missä järjestyksessä konversio kannattaa tehdä. Päädyttiin siihen, että konversio tehdään ensin TäTiin. Konversiossa tietueiden aikaleima muuttuu, joten tässä vaiheessa on erikseen estettävä tietueiden valuminen paikalliskantoihin. </li>
  <li>Konversio pystytään tekemään ilman että siitä on vaikutuksia tietokantojen käytölle. Konvertoidut tietueet tuodaan välivarastoon, josta niitä siirretään pienemmissä erissä tietokantoihin. </li>
</ul>

#### 5.	Kirjastopalvelun uudet käytännöt ja niiden vaikutukset ####
<ul>
  <li>Uutuutena Extranetissä on ”Oma lista” ja muutos kuvailupyyntöjen teossa. </li>
  <li>Jos Extranetissä lukee, että kuvailutietoja ei ole tulossa, olisi mahdollista tilata kuvailu erillisellä hinnalla. Tätä ei ole Koha-Suomen kirjastoissa harrastettu. </li>
  <li>Ongelmana on edelleen se, että kuvailustatus saattaa muuttua. </li>
  <li>Melindan ja Kirjastopalvelun elokuva- ja pelitietueissa on eroja. Osa Melinda-kirjastoista kuvailee nämä Kirjastopalvelua tarkemmin. Elokuvien kuvailussa erona on se, että Kirjastopalvelu tekee kuvailun kansien perusteella katsomatta tietoja tallenteelta. Kirjastopalvelun tietue on kuitenkin hyväksyttävä, vaikka Melindassa olisi tarjolla parempi tietue. Melindan tietueen siirtäminen TäTiin aiheuttaisi riskin tuplatietueista. </li>
  <li>Katsottiin Antin tekemää kaaviota Kirjastopalvelun tietueiden käsittelystä. Todettiin, että jos kuvailu on tulossa Kirjastopalvelulta, itse ei kannata kuvailla TäTiin, vaikka kuvailun saaminen kestäisi kauan. Aineiston voi käsitellä paikalliskannassa minitiedoilla lainauskuntoon tai siirtää Melindassa mahdollisesti olevan tietueen paikalliskantaan (ei Tätiin). </li>
  <li>Extranetissa kuvailustatuksen ”-” saaneet tapaukset ovat ongelmallisia. Näistä kannattaa joka tapauksessa tehdä kuvailupyyntö. </li>
</ul>

#### 6.	Tulevia tapahtumia ####
<ul>
  <li>Koha-Suomi-Melinda-tilannepalaveri 21.5. </li>
  <li>YKN:n metatietoryhmän kokous 22.5. </li>
  <li>Kansalliskirjaston järjestämä kuvailukoulutusverkoston ensimmäinen kokous 24.5. </li>
  <ul>
  	<li>Antti pyydetty mukaan Koha-Suomen edustajana  </li>
   	<li>Lisätietoja: <a href="https://www.kiwi.fi/display/kuvailuyhteistyo/Kuvailukoulutusverkosto" target="_blank">Kuvailukoulutusverkosto </a>  </li>
    <li><a href="https://www.kiwi.fi/pages/viewpage.action?pageId=384631114" target="_blank">Asialista </a> </li>
  </ul>
  <li>Kuvailun tiedotuspäivä 29.5.2024 </li>
</ul>

#### 7.	Muita asioita ####
<ul>
  <li><a href="https://github.com/KohaSuomi/Koha/issues/1006" target="_blank">Välimerkkiongelma Z39.50/SRU-haussa </a> -> Tiketti on ratkaistu, muttei toimi vielä kaikkialla. Korjaus on tulossa kaikille tiistain (21.5.) päivityksessä. </li>
  <li>Nalkutin on päällä Tätissä. Antti testaa, onko Nalkuttimen tuplatietueita aiheuttanut ongelma saatu korjattua. [Lisäys 17.5.: Testattu 17.5. ja ongelma on edelleen olemassa] </li>
</ul>

#### 8.	Seuraava kokous ####

Syyskauden ensimmäinen kokous: 5.9. klo 13.15


---
## Kuvailuryhmän muistio 4/2024 ##

Aika: 17.4.2024 klo 14.00–15.15

Osallistujat: Mauri Aittaniemi (Lappi), Helena Backman-Karvonen (Helle), Merja Hakulinen (Lumme), pj. Antti Heikkinen (OUTI), Suvi Kauranen (Kirkes), Päivi Knuutinen (Vaara), Marjukka Laapotti (Lastu), Tarja Mäkinen (Kyyti), Johanna Ranta (Kyyti), Marja Soisalo (Vaara), Anna Viitanen (Vaski, poistui klo 15)

Poissa: Anneli Österman (Koha-Suomi)

### Asialista ###

#### 1.	Kokouksen avaus ja sihteerin valinta ####

Sihteerinä toimi Marja Soisalo.

#### 2. Kohan versionvaihto ja kuvailuun liittyvien toimintojen testaus paikalliskannoissa ja TäTissä ####
<ul>
    <li>Miten toimii? Onko huomattu mitään erikoista? - Kovin moni ei vielä ole testauksia tehnyt. Kaikki toiminnot eivät ole testikannoissa vielä päällä, mutta perus kuvailutoiminnot ovat kunnossa. </li>
    <li>TäTin toimintojen testaus: <a href="https://tati-next.koha-suomi.fi/" target="_blank">TäTi-next </a>  </li>
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


