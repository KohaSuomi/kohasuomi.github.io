---
layout: single
permalink: /paakayttajat2025
header:
  overlay_color: '#5e616c'
  overlay_image: /assets/images/cropped-pexels-photo-113850.jpeg
toc: true
title: 'Koha-Suomen pääkäyttäjäryhmän muistiot 2025'
---

Koha-Suomen pääkäyttäjäryhmä kokoontuu kerran viikossa. Ylimmäisenä on aina uusin muistio.

## Viikko 6

Aika: 4.2.2025 klo 9.15<br />
Läsnä: Anneli Österman ja Pasi Kallinen (Koha-Suomi), Leena Kinnunen, Pia Kusmin (Lappi), Susanna Sandell (Vaski), Pirkko-Liisa Lauhikari, Katariina Pohto ja Piia Semenoff (OUTI), Janne Seppänen ja Lauri Hänninen (Lastu)

**Yhteiset**
* [Viikon 6 päivitys](https://github.com/KohaSuomi/Koha/discussions/1663)
* Omatoimikirjastojen estojen asettaminen
  * käytönesto ajastetaan tulemaan voimaan yöllä
  * pääkäyttäjät tarkistavat aamulla, että rajoitus on mennyt päälle ja ilmoittaa, jos ei ole. Rajoite laitetaan sitten käsin päällle.
* Testeillä on nähtävissä yksi ratkaisu liittyen [kehitysehdotus-tikettiin #886](https://github.com/KohaSuomi/Koha/issues/886). Keskustellaan, voiko ratkaisua ottaa käyttöön.
  * Ongelmana on, että itse lisättyjen fasettien otsikot eivät käänny, koska ne kuvaukset ovat tietokannassa, eikä käännösmekanismi osaa "katsoa" sinne.
  * testillä olevassa ehdotuksessa jokaiselle kielelle luodaan oma indeksi, joille sitten määritetään CSS:llä käännökset ja piilotetaan muut kuin käyttöliittymän kielivalinnan mukaiset kieliversiot.
  * ongelmana on myös se, että kielikoodeja ei saa käännettyä kuin liittämällä fasettiin auktorisoidun arvon, jolloin niille saa
    selkokielisen kuvauksen yhdellä kielellä (tai sitten auktorisoidun arvon kuvaukseen lisää kaikki versiot, joka voi olla sekavaa)
  * Päätös: Keskusteltiin, tarviiko käännöksiä tehdä ja päätettiin kokeilla ensin ilman käännöksiä fasettien otsikoihin ja kielikoodeihin. Ei tehdä omia Koha-Suomi-spesifejä säätöjä vaan pyritään saamaan yhteisön kautta fasetit käänneettäviksi. Pohditaan asiaa uudelleen, jos aiheesta saadaan palauttetta käyttäjiltä. 
* [Koha-seminaarin ilmoittautuminen avattu](https://github.com/KohaSuomi/Koha/discussions/1665). Ohjelma on vielä vajaavainen, mutta täydennetään niin pian kuin mahdollista.
* [Kohan ohje suomeksi -päivitys](https://github.com/KohaSuomi/Koha/issues/1488)
* [Ratkaisu ehdotettu](https://github.com/orgs/KohaSuomi/projects/4/views/15) -tilaisia tikettejä paljon. Muistattehan sulkea itse avaamanne tiketit (tai siirtää toiseen tilaan, jos eivät vielä toimikaan oikein). :)

Pohjoisesta etelään

**Lappi**
* Posion kirjaston väistön suunnittelu alkamassa, samoin Rovaniemen kirjaston paluu pääkirjastoon
* Nidetyyppien rajausta Rovaniemen kirjastolle selvitetään, liittyy vain Rovaniemellä käytössä olevaan laina-/nidekohtaiseen maksuun
* Kohaan vaihdettu kimpan logo, alaosaan jäi musta palkki
* Muuten rauhallista

**Vaski**
* Siirtyminen Turun seudullisen tapahtumakalenterin käyttöön verkkokirjastossa (Linked Events) 
*	Suunnittelemme käsin lisätty-maksutyypin poistamista, jotta ei olisi houkutusta lisätä ALVillisia maksuja järjestelmään. Mitätöi maksutapahtuma-toiminto on nyt piilotettuna, mutta piilotuksen poistoa suunnitellaan.

**OUTI**
* Pudasjärven kirjasto on luopumassa Ceepos-kassan käytöstä.
  * Riittänee, että poistamme Kohasta Pudasjärven maksurajapintaan liittyvät määritykset ja tuotteiston sekä kehittäjät poistavat Koha-palvelimelta kassaan liittyvät määritykset.
  * Teemme tiketin, kun asia ajankohtainen.
* Oulussa on pari kertaa tullut tapaus, että tietue on mennyt vähän kuin rikki tilanteessa, kun tietueelle on lisätty uusi nide Perustiedot-näytöltä Uusi nide -toiminnolla. OUTIssa on käytössä automaattinen nidetyyppiliitännäinen.
  * Käyttäjä oli tallentanut niteelle tarvittavat tiedot ja tämän jälkeen hän oli joutunut klikkailemaan useamman kerran nidetyyppikentän kolmea pistettä ennen kuin ohjelma oli antanut oikean nidetyypin kenttään. Tämän jälkeen käyttäjä oli tallentanut tietueen, mutta tallennuksessa oli tapahtunut jotain kummallista (?).
  * Tämän jälkeen molempien tapausten tietueet antoivat Internal server error -ilmoitusta. Tapauksessa 1 tietueen niteitä pääsi muokkaamaan. Tapauksessa 2 näkyville ei tullut enää yhtään tietueen nidettä.
  * Tapauksessa 2 Finnassa tietueelle tuli ilmoitus: "Järjestelmä pois käytöstä. Kirjastojärjestelmä on juuri nyt pois käytöstä. Saatavuustiedot eivät ole juuri nyt käytettävissä…”
  * Kun tutkimme ongelmaa, niteille oli molemmissa tapauksissa tallentunut nidetyypiksi KIRJA eli aivan kuin sinne olisi tullut jostain aineistotyypin Koha-tunnus.
  * Tapaus 1 ongelma saatiin korjattua, kun nidetyyppi korjattiin oikeaksi niteen muokkaussivulla. Tapaus 2 saatiin korjattua niteiden erämuokkauksella.
  * Tehdään tiketti, jos tapauksia alkaa ilmeneen muillakin.

**Lastu**
* Pohdittu miten varauksiin käytettäviä resursseja olisi mahdollista kehittää vähemmän työaikaa vieväksi Kohan avulla
* Muuten tavallista ylläpitoa

  
[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-6) - [Palaa sivun alkuun](/paakayttajat2025)

## Viikko 5

Aika: 28.1.2025 klo 9.15<br />
Läsnä: Anneli Österman, Kodo Korkalo ja Lari Strand (Koha-Suomi), Leena Kinnunen, Maria Joona ja Pia Kusmin (Lappi), Anni Mäki-Mantila ja Susanna Sandell (Vaski), Hanna Ikonen (Lumme), Katariina Pohto, Piia Semenoff ja Pirkko-Liisa Lauhikari (OUTI), Reetta Pihlaja (Siilinjärvi), Annika Helastila ja Elina Uotila (Kirkes), Auli Rantasalo ja Päivi Knuutinen (Vaara), Janne Seppänen ja Lauri Hänninen (Lastu)

**Yhteiset**
* [Viikon 5 päivitys](https://github.com/KohaSuomi/Koha/discussions/1648)
* Finna-kehitysedotusten prosessin selkeyttäminen. [Nykyisen prosessin kuvaus](https://github.com/KohaSuomi/Finna-kehitysehdotukset/wiki)
  * Kuinka monta kertaa vuodessa tavataan Kansalliskirjasto. Ehdotus: 6 kk välein tai tarpeen mukaan (jos esim isompi kehitystyö meneillään). Aina ennen Kansalliskirjaston tapaamista tehdään Finna-tikettien priorisointi Koha-Suomen kesken.
  * Tikettien priorisointipalaverin ja Kansalliskirjaston palaverin seuraava vetovastuu sopimatta. Olisiko jatkossa kiertävä? Seuraava vetäjä ja ajankohta sovitaan edellisessä priorisointipalaverissa. Vetäjä kutsuu koolle ja valmistelee molemmat palaverit.
  * Pitääkö ohje päivittää kun saadaan nämä sovittua? Vai mihin dokumentoidaan?
  * Seuraava vetäjä alustavasti Helle, vahvistus ensi viikolla.
  * Seuraava priorisointipalaveri toukokuun alussa. (Ennen kesälomia)
* Raportit YSO-konversion valmistelua varten [Raporttikirjastossa](https://koha-suomi.fi/dokumentaatio/raporttikirjasto/#raportti-yso-konversiota-varten) ja [tiketissä 1621](https://github.com/KohaSuomi/Koha/issues/1621#issuecomment-2612351054)
* EDItX-virheraportointi sähköpostiin ei ole toiminut versionpäivityksen jälkeen. Nyt korjattu.

Etelästä pohjoiseen

**Lappi**
* Kausijulkaisutietue oli poistettu ja sen mukana tilaukset ja niteet. Tietue palautettiin, mutta tilauset jouduttiin tekemään uudelleen. Tietue myös ilmestyi järjestelmäasetuksiin huomautuksena: tietue sekä taulussa biblio ja deletedbiblioitems. 
* Muutoin rauhallista, lähinnä käyttäjätunnusten päivityksiä.

**Vaski**
* Tuotiin esille Finna-kehitysehdotus siitä, että Finnan palautelomakkeen mukana välittyisi asiakkaan id Kohassa mikäli asiakas on palautetta jättäessään kirjautunut verkkokirjastoon. Idea sai ajatuksen tasolla kannatusta, mutta vaatii vielä miettimistä onko ehdotuksessa jotakin tietoturvan kannalta ongelmallista. Susanna tekee tiketin ja kehittäjät kommentoivat siihen pohdinnan jälkeen onko ehdotus toteutuskelpoinen.
* Normaalia ylläpitoa, joitakin epäonnistuneita EDItX-sanomia tullut nyt tammikuussa kun virheilmoituksia ei lähtenyt sähköpostiin. Osan uudelleenkäsittely oli jo lopetettu, joten Vaski tekee niistä tukipyynnöt.

**Lumme**
* Valmistellaan tulevaa asiakasrekisterin siivousajoa. Pitää vielä päättää, mitä tehdään laskutettavien kanssa.
* Finnan omissa tiedoissa olisi hyvä saada suosikkilistat aakkosjärjestykseen. Asiasta on tehty tiketti.

**OUTI**
* OKM-korjausajon jälkeen Oulussa huomattiin, että mm. kokoelma -tilasto oli uudessa OKM-tilastossa noin 1500 nidettä pienempi kuin alkuvuonna otetussa. Hankinnoissa oli myös pientä eroavaisuutta edelliseen ajoon mm. tietokirjallisuus oli vähentynyt ja kaunokirjallisuus oli miltei samassa määrin enentynyt.
  * Koska poistojen tilasto oli pysynyt täsmälleen samana molemmissa OKM-ajoissa, niin on luultavaa, että OKM-ajojen välillä on tehty poistoja, jotka ovat vaikuttaneet vuoden 2024 kokoelman kokoon. Ajojen välillä tehdyt poistot tilastoituvat vuoden 2025 poistoihin.
  * Hankinnan lukujen erot voisivat johtua siitä, että hankinnassa olevan aineiston luokkia on muutettu tietokirjaluokista kaunoluokkiin, jolloin tilastot muuttuivat ”ristiin” ajojen välillä.
  * Emmiltä saimme varmistuksen, että yllä luetellut arvelut luultavasti pitävät paikkansa, sillä tilastoja ei ole mahdollista "jäädyttää" tiettyyn hetkeen, koska ne otetaan kokoelmien ja hankintojen osalta tauluista, joissa tilanne elää koko ajan. Poistot, luokkien vaihdot, muutokset notforloan-arvoon, aineistolajiin, kieleen, niteen sijaintiin jne. vaikuttavat siihen, että tilastojen määrät voivat heitellä sen mukaan milloin tilasto on otettu.
* Raahen kaupunginkirjasto siirtyy tämän kevään aikana Varaamosta Timmiin.

**Siilinjärvi**
* Ei mainittavaa

**Kirkes**
* Normaaleja tukitöitä ja muita kiireitä.

**Vaara**
* On havaittu mm. 9-luokkalaisten asiakkaiden kirjastokorttien häviämistä tietokannasta. Vai eivätkö ole käyttäneet kortteja 5 vuoteen?

**Lastu**
* Hyllyvarauksiin käytettävät tabletit saatu Lahteen, alettu kartoittamaan kannettavia kuittareita ja viivakoodinlukijoita
* Muuten tavallista ylläpitoa
  
[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-5) - [Palaa sivun alkuun](/paakayttajat2025)

## Viikko 4

Aika: 21.1.2025 klo 9.15<br />
Läsnä: Pirkko-Liisa Lauhikari, Katariina Pohto, Piia Semenoff (OUTI), Iina Niemi (Vaski), Leena Kinnunen ja Pia Kusmin (Lappi), Kati Sillgren (Helle),  Anneli Österman ja Emmi Takkinen (Koha-Suomi), Reetta Pihlaja (Siilinjärvi), Janne Seppänen ja Lauri Hänninen (Lastu), Annika Helastila ja Elina Uotila (Kirkes), Tuomas Kunttu ja Roosa Väisänen (Kyyti), Hanna Ikonen (Lumme), Auli Rantasalo (Vaara)

**Yhteiset**
* [Viikon 4 päivitys](https://github.com/KohaSuomi/Koha/discussions/1630)
  * [OKM-tilastojen korjaukset](https://github.com/KohaSuomi/Koha/discussions/1628) - uudelleenajot käynnissä, Emmi tiedottaa edistymisestä Matrixissa.
* Kuvailupohjista kannattaa poistaa oletusarvot nidetyyppi-kentästä 952y,jos ne eivät ole oikeita nidetyyppejä. Osalla siellä saattaa olla arvoja tyyliin KI tai KIRJA, joita ei löydy nidetyypeistä.
  * Kysely, jolla saa etsittyä kuvailupohjat, joissa oletusarvo on asetettuna: ```select tagfield,tagsubfield,frameworkcode,defaultvalue from marc_subfield_structure where defaultvalue !="" and tagfield='952' and tagsubfield='y';```
* [Tiketti 302](https://github.com/KohaSuomi/Koha/issues/302) eli huoltajasuhde valmiiksi valituksi. Onko tälle tarvetta monessa kimpassa, viedäänkö asiantuntijaryhmään päätettäväksi, plugarisoidaanko?
  * Ominaisuudelle oli kiinnostusta, joten viedään asiantuntijaryhmään.
* Uusi raportteja (tai uudehkoja, ennen mainitsemattomia)
  * [Kuljetettavat varaukset, joita ei ole käsitelty Kohassa](https://koha-suomi.fi/dokumentaatio/raporttikirjasto/#kuljetettavat-varaukset-joita-ei-ole-k%C3%A4sitelty-kohassa)

Pohjoisesta etelään

**OUTI**
* Normaalia tukitöitä. Kohan ohje suomeksi päivitystä.

**Vaski**
* Ollaan kokeiltu koodia, jolla voi laittaa tietuenäytölle automaattisuodatuksen kirjautumisyksikköön (sijainti- tai kotikirjasto). Tässä vielä ongelmia joita tutkitaan.

**Lappi**
* Normaalia ylläpitoa ja Koha-ohjeen päivitystä.

**Siilinjärvi**
* Tutkittu poistettavien asiakkuuksien listausta. Tulossa olisi iso siivous: lähdössä on 27 000 41 000:sta!
* Raportin antamat oletusnidetyypit poistettu kuvailupohjista.

**Lastu**
* Sip2SortBinMapping-asetusta testailtu Larin kanssa, syy toimimattomuudelle löytynyt rivivaihtojen käsittelystä. Alkuperäinen tiketti: https://github.com/KohaSuomi/Koha/issues/1559
* Nidehaun tuloksiin toivottu mukaan niteen edellisestä havaintoa sekä niteen huomautuskenttiä. Yhteisöstä löytyi näille tiketit, kommentoitu sinne:
  * https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=13965
  * https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=13823
 
**Kirkes**
* Kadonneet osakohteet pelastettu. <a href="https://github.com/KohaSuomi/Koha/issues/1612#issuecomment-2602226804">#1612</a>
* Viestipohjien päivittämistä
* Työntekijä teki haun "Hae tietokannasta" -hakukentän kautta lehdelle El Pais semanal 2024 ja tarkensi hakua faseteista "14 vrk lehti". Tuli 403 -virheilmoitus:
Programming error - op 'cud-login' must not start with 'cud-' for GET https://kirkes.koha-suomi.fi/intranet/catalogue/search.pl?idx=kw&q=el%20pais%202024&op=cud-login&sort_by=pubdate_dsc&count=50&limit=itype:14VRKLE (referer: https://kirkes.koha-suomi.fi/cgi-bin/koha/catalogue/search.pl). Vastaavaa virhettä ei kuitenkaan onnistuttu toistamaan.

**Lumme**
* Käyty kuvailupohjia lävitse ja yhtenäistetty pakollisia kenttiä. Poistettu myös kenttien oletusarvoja, jotta tietueisiin ei tulisi virhe 500 -ilmoitusta.
* Lehtien vastaanotossa tuli ilmi, että vastaanotossa valittu päivämäärä muuttuu tallennuksen jälkeen päivämäärään 30.11.1899. Asiasta tehty tiketti #1636.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-4) - [Palaa sivun alkuun](/paakayttajat2025)

## Viikko 3

Aika: 14.1.2025 klo 9.15<br />
Läsnä: Leena Kinnunen ja Pia Kusmin (Lappi), Anneli Österman ja Pasi Kallinen (Koha-Suomi), Pirkko-Liisa Lauhikari ja Piia Semenoff (OUTI), Kati Sillgren (Helle), Hanna Ikonen (Lumme), Tuomas Kunttu (Kyyti), Annika Helastila ja Elina Uotila (Kirkes), Auli Rantasalo (Vaara), Janne Seppänen (Lastu)

**Yhteiset**
* LockExpiredDelay-järjestelmäasetukseen kaikilla 0 tai tyhjä siltä varalta, että aletaan ajamaan cleanup_database-cronia säännöllisesti.
* [Viikon 3 päivitys](https://github.com/KohaSuomi/Koha/discussions/1610)
* [Asiantuntijaryhmän kuulumiset](https://koha-suomi.fi/asiantuntijaryhma2025#muistio-12025)
* Muistutus deadlinesta: [Kohan ohje suomeksi -ohjeen päivitys](https://github.com/KohaSuomi/Koha/issues/1488) tammikuun loppuun mennessä.
* [TrackLastPatronActivityTriggers-asetukseen](https://github.com/KohaSuomi/Koha/issues/1606) uusi vaihtoehto ehdotettavaksi yhteisöön?
* [Hakutulosnäytön ei saatavana -termit](https://github.com/KohaSuomi/Koha-translations/issues/58#issuecomment-2589168299)
* Uusia raportteja:
  * [OKM-tilastojen mukainen hankintaraportti, joka listaa hankitut tietueet](https://koha-suomi.fi/dokumentaatio/raporttikirjasto/#okm-liit%C3%A4nn%C3%A4isen-mukainen-hankintaportti-joka-listaa-tietueet-jotka-on-hankittu-tietyll%C3%A4-aikav%C3%A4lill%C3%A4-tietyss%C3%A4-kirjastossa)
  * [Tietueet, joiden 008-kenttä ei ole 40 merkkiä pitkä](https://koha-suomi.fi/dokumentaatio/raporttikirjasto/#tietueet-joissa-008n-pituus-ei-ole-40-merkki%C3%A4)
  * [Tietueiden haku kiinteämittaisen kentän pituuden mukaan](https://koha-suomi.fi/dokumentaatio/raporttikirjasto/#tietueiden-haku-kiinte%C3%A4mittaisen-kent%C3%A4n-pituuden-mukaan)
    * Huom! Tämän käyttäminen voi olla vähän "kinkkistä" ja vaatii hoksaamista, miten raportti toimii ja miten merkkimäärät lasketaan raportin merkkimäärä-sarakkeeseen.

Etelästä pohjoiseen

**Lappi**
* Lopetettujen kirjastopistiden teettämiä töitä. Ongelmia tuli niteiden erämuokkauksessa. Vika korjaantunut päivityksessä.
* Koha-ohjeen päivitystä.
* Normaalia ylläpitoa.

**OUTI**
* Oulun yhdestä kirjastosta on tullut palautetta, että versiopäivityksen jälkeen heillä on tullut tapauksia, kun virkailija alkaa palauttamaan aineistoa, kun Kohassa on ehtinyt tulla timeout, tästä huolimatta Koha näyttäisi, että palautus olisi onnistunut. Tässä vaiheessa ei tule kuulemma kirjautumisikkunaa Kohaan. Virkailija tekee oletuksen, että laina oli palautunut, vaikka todellisuudessa näin ei ole tapahtunut. Vastaavaa tilannetta testattu Koha-tuessa, mutta ongelmaa ei ole saatu toistettua. Koha antaa aina ensin kirjautumisikkunan, jonka jälkeen Koha avautuu tyhjälle palautussivulle, eikä missään vaiheessa näy, että lainaa olisi palautettu. Kirjastoa on ohjeistettu tilanteisiin, kun Kohaa ei ole käytetty vähään aikaan. Pyydetty myös yksityiskohtainen kuvaus palautusprosessista, kun ongelma tulee seuraavan kerran eteen ja myös näytön kuva, jossa timeoutin jälkeen palautettu nide näkyy Palautus-sivulla palautettuna.
* Kuusamon kirjastosta tuli kyselyä, mistä voisi johtua raporttiliitännäisen vuoden 2024 tulevat erot koko vuoden lainatilastojen ja kuukausittain kerättyjen lainatilastojen välillä. Kuusamon pääkirjaston vuositilasto antaa 1551 isomman lainatilaston kuin kuukausittain kerätyt lainaluvut. Kuusamon kirjastoauton vuositilasto antaa taas 1575 lainaa pienemmän tilaston.
* Saimme asiakkaalta Finna-kehitysehdotuksen, että verkkokirjastossa voisi varata usean teoksen yhtäaikaa eli niitä voisi tiedonhaun tuloksista siirtää ns. koriin ja yhdellä kertaa varata kaikki korissa olevat teokset.
  * Piia tekee kehitysehdotuksen GitHubiin.
 
**Helle**
* Tietueen Niteet-välilehden lainassa olevan niteen uusintamäärä-tieto on aiheuttanut epäselvyyttä. Arvon on oletettu olevan niteen kaikkien lainojen uusintamäärä. Kentän nimi on suomeksi Uusintoja, ruotsiksi Aktuella omlån, englanniksi Current renewals. Tiketti suomenkielisen kenttänimen muutosehdotuksesta [Saisiko Tietueen Niteet -välilehden Uusintoja-kenttänimeen muutoksen](https://github.com/KohaSuomi/Koha-translations/issues/62)
* Nidehaku-hakutuloksessa näkyy niteen lainamäärä, uusintamäärää ei. Tiketti uusintamäärän näkymisestä [Saisiko Nidehaku-toiminnon hakutulokseen niteen lainojen uusintamäärät](https://github.com/KohaSuomi/Koha/issues/1617)

**Lumme**
* Tehtiin kehitysehdotus tarratulostukseen: tarratulostuksessa olisi hyvä näkyä numerointi myös tulostukseen tuotujen viivakoodien puolella. Lumpeissa on monia eri tarratulostuspohjia, niin tämä helpottaisi tarroja tulostavien työtä. Ehdotuksesta tehty tiketti.
* Tietueissa esiintynyt säännöllisesti virhe 500 -virhettä, koska niteissä on ollut joku päivämääränä 0000-00-00 tai väärä nidetyyppi. Ongelmaa selvitellään.
* Lyngsoen kirjakaappi antaa lainaan toiselle asiakkaalle varatun teoksen, mutta jättää varauksen varauksen tehneen asiakkaiden tietoihin odottaa-tilaan. Tästä asiakkaalle sitten kertyy maksuja, kun varausta ei ole noudettavana ja se vanhenee. Ongelma johtuu SIP-yhteydestä, koska siinä ei käsitellä ollenkaan varaustilaa. Ongelmasta tehty tiketti.

**Kyyti**
* Ilmeni ongelma, että virkailijat eivät voineet muuttaa asiakkaitten asiakastyyppiä [#1598](https://github.com/KohaSuomi/Koha/issues/1598)

**Kirkes**
* Järvenpäässä ollaan ottamassa käyttöön Canonin kirjastotulostusta. Ei toimi vielä, mutta päivitetään integraatiolistaus sitten, kun toimii.
* Osakohteita kadonnut luetteloidusta teoksesta.

**Lastu**
* Raindance-integraatio otettu Lahdessa käyttöön onnistuneesti
* Asiakkaita ihmetyttänyt Finnan varausjonon sija 0. Tämä tarkoittaa, että varaus/nide on käsittelyssä. Selvitellään voiko tämän ilmaista Finnassa muulla tavoin.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-3) - [Palaa sivun alkuun](/paakayttajat2025)

## Viikko 2

Aika: 7.1.2025 klo 9.15<br />
Läsnä: Leena Kinnunen, Pia Kusmin (Lappi), Katariina Pohto ja Pirkko-Liisa Lauhikari (OUTI), Hanna Ikonen (Lumme), Kati Sillgren (Helle), Anneli Österman ja Lari Strand (Koha-Suomi), Reetta Pihlaja (Siilinjärvi), Auli Rantasalo ja Hanna Hyttinen (Vaara)

**Yhteiset**
* [Viikon 2 päivitys](https://github.com/KohaSuomi/Koha/discussions/1595)
* [Tammikuun huoltotiedote](https://github.com/KohaSuomi/Koha/discussions/1594)

**Lappi**
* Normaalia ylläpitoa.

**OUTI**
* Julkisoikeudellisten maksujen vanhentamisajo tehtiin 3.1.2025 aamusta, koska ajon ajastus 1.1. oli ollut väärin OUTIssa.
* 7.1.2025 tuli voimaan uudet käyttösäännöt:
  * Noutamattoman varauksen maksu nousi 1 e -> 2 e.
  * Lainauskiellon maksuraja nousi 12 e -> 15 e.
  * Kaukolainamaksu nousi 1 e -> 2 e + mahdolliset lähettäjäkirjaston maksut. Maksua ei ole määritelty Kohaan.
* 7.1. aamulla hyllyvarauksia oli reilut 4500, joka on OUTIn ennätys. :)

**Lumme**
* Normaalia ylläpitoa.

**Helle**
* Maksukorotuksia vuodenvaihteessa: noutamaton varaus, lainan kertyvä päiväkohtainen myöhästymismaksu. Lisäksi lainauskiellon maksuraja nostettu, samoin lainakohtaisen myöhästymismaksun enimmäismäärä.

**Siilinjärvi**
* Ei mainittavaa
* Kyseltiin onko Helle saanut palautetta takautuvasti nousseista myöhästymismaksuista. Yriteään Siilissä tiedottaa asiasta kovasti ennen 1.2.2025.

**Vaara**
* Pääkäyttäjävaje tammikuun ajan, muuten ei mainittavaa



Pohjoisesta etelään

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2025#viikko-2) - [Palaa sivun alkuun](/paakayttajat2025)
