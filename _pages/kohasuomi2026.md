---
title: 'Koha-Suomen vuoden 2026 muistiot'
header:
  overlay_color: '#5e616c'
  overlay_image: /assets/images/cropped-pexels-photo-113850.jpeg
permalink: /kohasuomi2026
redirect_from:
  - /theme-setup/
toc: true
hidden: true
---

Muistioiden laadinnassa voidaan hyödyntää huhtikuusta 2026 alkaen kielimalleihin ja GitHub APIin perustuvaa automaatiota. Muistiot kuitenkin tarkistetaan Koha-Suomen henkilökunnan toimesta.

## Viikko 16
Aika: Ma 13.4.2026<br />
Läsnä:

### Vastuuttomat tiketit
* [kaikki tiketit](https://github.com/issues?q=is%3Aopen+is%3Aissue+owner%3AKohaSuomi+archived%3Afalse+sort%3Aupdated-desc+no%3Aassignee+-repo%3AKohaSuomi%2FBugiton+-repo%3AKohaSuomi%2FFinna-kehitysehdotukset)

### Muut asiat

* Viikon 16 päivitys

### Viikolla 15 tehty

#### Emmi
* [Varausten vienti raportilta erämuokkaukseen epäonnistuu isoilla määrillä](https://github.com/KohaSuomi/Koha/issues/1980)
Yhteisöstä löytyi korjaus, jolla raporteilta on mahdollista viedä 400 kappaletta varauksia varaustyökaluun. Korjaus tuotu testattavaksi testeille.
* [Vaski: IntranetUserJS päivitys](https://github.com/KohaSuomi/Koha/issues/2245); Päivitys tehty yhdessä Vaskin pääkäyttäjän kanssa.
* [Lastu: Laskut jääneet lähtemättä](https://github.com/KohaSuomi/Koha/issues/2250); Selvitetty onko laskutusajossa tapahtunut meidän päässämme virhettä. Selvisi, että laskut ovat lähteneet meiltä onnistuneesti, mutta ne ovat jääneet lähtemättä vastaanottavalta palvelimelta eteenpäin. Kehotettu olemaan yhtydessä vastaanottajaan. 
* [Tilauksen peruutus ei varoita että niteet poistetaan](https://github.com/KohaSuomi/Koha/issues/2050); Yhteisöön viety ehdotus, jossa tilauksen perumisen yhteydessä ilmoitetaan, että tilaukseen liittyvät niteet poistetaan. Tätä ei ole vielä tuotu meille testattavaksi, odotetaan yhteisön kommentteja asiasta.
* Edellisen yhteydessä huomattu, että tilauksen epäonnistunut poisto voi aiheuttaa tuplaid:n items- ja deleteditems-tauluhin. Havainto raportoitu yhteisöön tiketissä [Bug 42303](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=42303) - Duplicate itemnumber in items and deleteditems table when order cancel fails

## Viikko 15

Maanantain viikkopalaveria ei pidetty pääsiäisen vuoksi. Vastuuttomat tiketit vastuutetaan ensi viikon palaverissa.

### Viikolla 14 tehty

#### Kodo
* [Ajastetut ajot testeillä](https://github.com/KohaSuomi/Koha/issues/2236);
testicronjobien perussetti listattu (OUTI-test), `update-holds-to-pull`-kuormariski huomioitu, syspref-ohjaus (**RunTestCronjobs**) toteutettu testiajojen määräaikaiseen päälle/pois-kytkentään.
* [Lappi: Omatoimikirjaston käyttökiellon asettaminen asiakkaalle](https://github.com/KohaSuomi/Koha/issues/2239);
estot asetettu.
* [Lappi: Listaus sip-palvelimelle yhteyden saavista automaateista](https://github.com/KohaSuomi/Koha/issues/2234);
kesken. SIP-palvelimelle väärällä RO-tunnuksella yhteyttä ottavat Lapin automaatit. Pyydetty SIP-palvelimelta lista yhteyttä ottavista automaateista rajauksen tekemiseksi.
Seuraavaksi SIP-lista ulos ja tunnusten/salasanojen tarkistus niille automaateille, jotka ottavat yhteyttä väärällä RO-tunnuksella.
* [Vaara: Ceepos kassajärjestelmän muutostyöt](https://github.com/KohaSuomi/Koha/issues/2235);
kesken, vanha IPsec-tunneli purettu, uusi liikennöinti kesken. Koha-päähän tarvitaan ceepos-yhteysosoitteen muutos + tarkistuspalaveri + testaus, eteneminen Meita/CPU:n aikataululla.
Seuraavaksi ceepos-yhteysosoitteen muutos Kohaan + yhteistestaus Meita/CPU:n kanssa (palaveri + testit).
* [/var/etc/hakemiston siivous](https://github.com/KohaSuomi/Koha-25x/issues/169);
siivottu, vanhat tiedostot siirretty `/var/etc/koha/old`-hakemistoon, jatkotoimet (sms_send + koha-conf → utility #105–#108); tiketti avattu takaisin kunnes liittyvät tiketit hoidettu.
Seuraavaksi utility-tikettien #105–#108 läpivienti ja tämän sulkeminen niiden jälkeen.
* [zebradb-konfigeissa roikkuu viittauksia jaettuun /home/koha/koha-dev:iin](https://github.com/KohaSuomi/koha-suomi-utility/issues/108);
viittaukset siivottu, konffit vaihdettu prod- ja test-roolien kontteihin.
* [Vanhat easticsearch-dumpit ja -hakemistot pois](https://github.com/KohaSuomi/koha-suomi-utility/issues/101);
indeksien dumppaus ja synkkaus siirretty versiopäivityksessä Elmalle; vanhat dumpit ja `elasticsearch.ondisk`-hakemistot poistettu tuotannoista ja varmistuksista. (tausta: [Elma tuotantoon](https://github.com/KohaSuomi/koha-suomi-utility/issues/30))
* [sms_send driverin siirto /var/koha/etc:stä tarkoituksenmukaisempaan paikkaan](https://github.com/KohaSuomi/koha-suomi-utility/issues/105);
sms_send todettu YAML-konffiksi (ei driveri) → jätetty etc:iin.
* [/home/koha hakemistossa perl5 modulihakemisto](https://github.com/KohaSuomi/koha-suomi-utility/issues/109);
korjaus tehty testeillä, `koha_perl_deps.pl` OK, OAI testaus vielä tekemättä.
* [MariaDB systemd service unitin korjaus](https://github.com/KohaSuomi/koha-suomi-utility/issues/70);
todettu, ettei palvelu käynnisty aina automaattisesti.
* [Vanhat tietokantadumpit pois](https://github.com/KohaSuomi/koha-suomi-utility/issues/104);
kesken, tiered dumppeihin siirtymisen jälkeen vanhat tietokantadumpit poistettava varmistusjärjestelmästä manuaalisesti, poistossa huomioitava säilytysajat (erityisesti LTS).
Seuraavana poistojen ajosuunnitelma (mitä poistetaan/mistä) + toteutus säilytysaikojen puitteissa + kuittaus tikettiin.
* [next-roolin konttipohja pitää uusia](https://github.com/KohaSuomi/koha-suomi-utility/issues/110);
kesken, next-roolin konttipohja päivitettävä vastaamaan maaliskuu 2026 -versionvaihdon jälkeisiä tuotantoja ennen seuraavaa versiopäivitystä.
Seuraavana erot tuotanto ↔ next -konttipohja kartoitetaan ja konttipohja päivitetään vastaamaan nykyisiä tuotantoja.
* [LimitRequestBody-asetuksen muuttaminen palvelimella](https://github.com/KohaSuomi/koha-suomi-utility/issues/69);
kesken, Apachen `LimitRequestBody` ei rajoittava (apache “unlimited”). Myös HAProxyyn suunnitellut `tune.bufsize`/`tune.maxrewrite`-muutokset päätetty jättää tekemättä, koska ongelma muuttui Koha 3/2026 -versiossa ja epäonnistuu myös pienillä määrillä (vika ei todennäköisesti HAProxyssä).
Seuraavana toisto pienellä aineistolla + lokien keruu (Koha + LB/HAProxy) ja rajaus, onko kyse request-koosta vai sovellus-/backend-ongelmasta.

#### Johanna
* [Fix subroutine warning](https://github.com/KohaSuomi/koha-plugin-broadcast-biblios/commit/40ada99) (koha-plugin-broadcast-biblios - master)
* [Revert "Find active record with 035z"](https://github.com/KohaSuomi/koha-plugin-broadcast-biblios/commit/a962e9c) (koha-plugin-broadcast-biblios - ks25)
* [Fix subroutine warning](https://github.com/KohaSuomi/koha-plugin-broadcast-biblios/commit/625fff6) (koha-plugin-broadcast-biblios - ks25)
* [Revert "Limit 035z from search"](https://github.com/KohaSuomi/koha-plugin-broadcast-biblios/commit/736cb20) (koha-plugin-broadcast-biblios - ks25)
* [Revert "Add system-control-number-cancelled to queryparser"](https://github.com/KohaSuomi/koha-plugin-broadcast-biblios/commit/cc83c81) (koha-plugin-broadcast-biblios - ks25)
* [Rename script](https://github.com/KohaSuomi/koha-plugin-broadcast-biblios/commit/3e8add5) (koha-plugin-broadcast-biblios - master)
* [Merge branch 'ks25' of https://github.com/KohaSuomi/koha-plugin-broadcast-biblios into ks25](https://github.com/KohaSuomi/koha-plugin-broadcast-biblios/commit/0b1ad54) (koha-plugin-broadcast-biblios - ks25)
* [Rename script](https://github.com/KohaSuomi/koha-plugin-broadcast-biblios/commit/e1ebbf3) (koha-plugin-broadcast-biblios - ks25)
* [Rollback for parameter push](https://github.com/KohaSuomi/koha-plugin-report-services/commit/bce6a84) (koha-plugin-report-services - ks25)
* [KOHA-2232: Improve parameter input and error logging](https://github.com/KohaSuomi/koha-plugin-report-services/commit/12e2d3b) (koha-plugin-report-services - master)
* [KOHA-2232: Improve parameter input and error logging](https://github.com/KohaSuomi/koha-plugin-report-services/commit/3b36d8f) (koha-plugin-report-services - ks25)
* [Create github-weekly-summary.pl and README](https://github.com/KohaSuomi/koha-suomi-utility/commit/c6a2a35) (koha-suomi-utility - development, master)
* [Rename format_markdown as format_standard and update README](https://github.com/KohaSuomi/koha-suomi-utility/commit/37ebc86) (koha-suomi-utility - development, master)
* [Create just-for-fun and add educational scripts](https://github.com/KohaSuomi/koha-suomi-utility/commit/d0833af) (koha-suomi-utility - development, master)
* [Rename username variable example for weekly summary](https://github.com/KohaSuomi/koha-suomi-utility/commit/8766a65) (koha-suomi-utility - development, master)
* [Fetch commits across all branches not just default](https://github.com/KohaSuomi/koha-suomi-utility/commit/1cb7d9d) (koha-suomi-utility - development, master)
* [Update kohasuomi2026.md with recent changes](https://github.com/KohaSuomi/kohasuomi.github.io/commit/423bde7) (kohasuomi.github.io - master)
* [Change text in note](https://github.com/KohaSuomi/kohasuomi.github.io/commit/deac7eb) (kohasuomi.github.io - master)
* [Update kohasuomi2026.md with notes](https://github.com/KohaSuomi/kohasuomi.github.io/commit/d927a5d) (kohasuomi.github.io - master)
* [Document updates on Koha system issues and fixes](https://github.com/KohaSuomi/kohasuomi.github.io/commit/649c7b1) (kohasuomi.github.io - master)
* [Fix formatting](https://github.com/KohaSuomi/kohasuomi.github.io/commit/8f3402a) (kohasuomi.github.io - master)
* [Fix punctuation in issue responsibility note](https://github.com/KohaSuomi/kohasuomi.github.io/commit/57b1cea) (kohasuomi.github.io - master)
* [KohaSuomi/Koha - Tietueen Varaukset-välilehdellä englannikielisiä termejä ](https://github.com/KohaSuomi/Koha/issues/1492);
Vastuutettu: johannaraisa.
Kommentti: Tähän on tägit testeillä, mutta taitaa vaatia kielitiedostojen tekemisen.
* [KohaSuomi/Koha - Tietuesiirtäjä lisäilee satunnaisesti ylimääräisiä 942c-kenttiä TäTissä](https://github.com/KohaSuomi/Koha/issues/2229);
Vastuutettu: johannaraisa.
* [KohaSuomi/Koha - Vaski: Raporttien ajaminen Raportterin kautta epäonnistunut](https://github.com/KohaSuomi/Koha/issues/2232);
Vastuutettu: johannaraisa.
Kommentti: Olen parannellut sitä muuttujien ja virheiden käsittelyä, saa ainakin lokittamaan paremmin. Testasin jo testillä, sitä ei oikein pysty muut testaamaan, joten laitan sen tuonne tuotantoon ja katsellaan mitä siellä näkyy.
Kommentti: Toinen mitä mietin, että voisiko olla niin, että se raportti ei palauta mitään, ei siis ole dataa sille päivälle tarjolla ja antaa virheellisesti 500 virheen.
* [KohaSuomi/Koha - Käyttöoikeuksia voi asettaa vain tietyille asiakastyypeille](https://github.com/KohaSuomi/Koha/issues/2237);
Tiketti avattu.
* [KohaSuomi/Koha - Rinnakkaisvaraus - Bug 15516 - Allow to place a hold on first available item from a group of titles](https://github.com/KohaSuomi/Koha/issues/2241);
Vastuutettu: johannaraisa.
Kommentti: Siirsin tämän tiketin Koha-repoon, ei enää liity versiovaihtoon.
* [KohaSuomi/Koha-25x - Vaski: "Print slip and confirm" -painike ei toimi kun varauksen palauttaa ensimmäisen kerran](https://github.com/KohaSuomi/Koha-25x/issues/244);
Vastuutettu: johannaraisa.
Kommentti: Tämä on nyt tuotannossa.
* [KohaSuomi/Koha-25x - Varauksen palautuksesta kaksi erilaista varausmodaalia](https://github.com/KohaSuomi/Koha-25x/issues/245);
Vastuutettu: johannaraisa.
Kommentti: Tässä ei taida olla muuta kuin tuo, että se modaali näkyy englanniksi. Käännösongelmasta taisi olla toinen tiketti, joten voisiko tämän sulkea ja käsitellä asiaa siellä?
* [KohaSuomi/Koha-25x - Tietuesiirtäjä: Muutokset -popparin kenttien tiedot yhdelle riville](https://github.com/KohaSuomi/Koha-25x/issues/247);
Vastuutettu: johannaraisa.
Kommentti: Tämä on tuotannossa.
* [KohaSuomi/koha-plugin-broadcast-biblios - OAI-setin siivousskripti](https://github.com/KohaSuomi/koha-plugin-broadcast-biblios/issues/19);
Vastuutettu: johannaraisa, Anknite-cpu.
Kommentti: Tämä on ajettu Tätissä, vaatii vielä tarkistamisen ettei uusia synny ennen kuin suljen tiketin.
* [KohaSuomi/koha-plugin-report-services - Oma lokitiedosto raportterirajapintaan](https://github.com/KohaSuomi/koha-plugin-report-services/issues/13);
Tiketti suljettu.
* [KohaSuomi/koha-plugin-visual-label-tool - Virhekäsittelyt eivät toimi oikein](https://github.com/KohaSuomi/koha-plugin-visual-label-tool/issues/11);
Vastuutettu: johannaraisa.
Kommentti: Käännösten lisääminen liitännäiseen rikkoi muokkauksessa virheviestien näkymisen. Samalla parantelin virheviestejä, jotta niistä ymmärtäisi paremmin mikä on vikana.


## Viikko 14

Aika: Ma 30.3.2026<br />
Läsnä: Ari, Lari, Johanna, Anneli, Emmi, Pasi, Kodo

### Vastuuttomat tiketit
* [kaikki tiketit](https://github.com/issues?q=is%3Aopen+is%3Aissue+owner%3AKohaSuomi+archived%3Afalse+sort%3Aupdated-desc+no%3Aassignee+-repo%3AKohaSuomi%2FBugiton+-repo%3AKohaSuomi%2FFinna-kehitysehdotukset)

### Muut asiat
* Asioiden kirjaaminen palaverimuistioon on jäänyt retuperälle, kuinka tätä tilannetta voitaisiin parantaa ja missä laajuudessa asioita on hyvä kirjata? Nyt tehtyjen muutosten seuraaminen on hankalaa.
  * Kehittäjät kirjaavat tähän muistioon muiden tiedoksi asiat koko viikon ajalta.
* Päivitys ajetaan maanantai-iltana

### Viikolla 13 tehty

#### Anneli
* Tietuenäyttöjen mukautuksista raportoitiin ongelmia kentän 020q-osalta. Ongelma johtui siitä, että Template Toolkit -sääntö ei huomioinut sitä, että q-osakenttä voi toistua. Laitettu testattavaksi toistot huomioiva versio
* Kuvailusääntöihin on tehty muutos, jossa 800t-osakenttään aletaan kirjaamaan sarjan nimekkeen perään tieto "(teksti : nide)". Tämä rikkoo Sarja-tiedon hakulinkin, koska sarjaa haetaan t-kentän sisällön mukaisesti, esim. Myrskylän retket (teksti : nide). Kaikissa tietueissa ei kuitenkaan ole tuota uuden kuvailusäännön mukaista lisätietoa, joten ne eivät osu hakuun. Koitin ratkoa ongelmaa lisäämällä tietuenäyttöjen mukautus -työkalulla uuden Sarja-otsikon, joka tekee hakulinkin ilman tuota (teksti : nide) -lisäystä. Sain sen toimimaan, mutta huomasin sen jälkeen, että kuvailusääntöjen mukaan 800t-kenttään voidaan lisätä tietoja myös vähän toisessa muodossa, jos kyseessä on erikielisiä teoksia, esim. (teksti: nide : ruotsi). Tämä tieto tarkoittaa, että nykyinen regex ei toimi. Lisäksi ilmeisesti sarjatietoa haetaan myös 490-kentästä niissä tapauksissa, että sarjaan ei liity tekijää, eli silloin ei tehdä ollenkaan 800-kentän kirjausta. Tämä vaatii siis vielä pohdintaa.
* Eräpäivän siirto -työkalussa on ongelmana, että se näyttää esikatselussa uuden eräpäivän vain noin puolelle valituista. Eräpäivä kyllä muuttuu kaikille, vaikka tieto puuttuukin esikatselusta.
* Oulussa oli ongelma maksujen viennissä Ceepos-kassaan. Se epäonnistui välillä. Syyksi paljastui asiakkaan Lainaus-sivulla oleva Huomioi-kentän Maksa kaikki maksut -nappi, joka vei sellaiseen näkymään, jossa maksujen vienti Ceepokseen ei onnistu, koska osoitteessa ei ole mukana yksittäisten maksujen accountline_id:t. Pikakorjauksena kielletty käyttää kyseistä nappia ja Lari tekee kestävämmän korjauksen suoraan Ceepos-liitännäiseen eli piilottaa kyseisen nappulan.
* Lastussa oli lähtenyt asiakkaalle palautuskehotus, jossa ei ollut item-tägin sisälle muodostunut teostietoja. Epäilin ensin, että asiakas on ehtinyt palauttaa niteen siinä välissä, kun viesti on luotu, mutta ei vielä lähetetty. Teokset oli kuitenkin palautettu vasta viestin lähetyksen jälkeen, joten tämä teoria ei pitänyt paikkansa. Tämä saattaa jäädä mysteeriksi, koska muita vastaavia tapauksia ei message_queuesta löytynyt.
* OUTIssa ei ollut lähtenyt MEMBERSHIP_EXPIRY-viestejä. Todennäköinen syy on viestipohjassa ollut Template Toolkit -koodissa ollut virhe.
* Kyytistä ihmeteltiin, että Vanhentuneet varaukset -raportille ei tule enää tuloksia sen jälkeen kun ExpireReservesOnHolidays-järjestelmäasetukseen muutettiin heillä, että varausten ei sallita vanhentua kiinniolopäivinä (esim. viikonloppuisin). Raportti on kuitenkin rakennettu niin, että varaus on poistettu seuraavana päivänä sen expirationdatesta. Muuten siihen tulee mukaan muitakin kuin vanhentumisskriptin poistamia.
* Tein palautekyselyn pääkäyttäjille versionvaihdon sujumisesta. Mikä meni hyvin/huonosti, mitä voisi parantaa jne.
* Lumpeissa löytyi vielä neljä yli 20 merkkistä viivakoodia, jotka aiheuttivat Perustiedot-näytöllä virheilmoituksen. Nämä ohjeistettiin korjaamaan käsin.
* Vaarassa käyttäjällä ei näkynyt Perustiedot-näytöllä Tuo/Vie-nappi, ongelma korjaantui selaimen välimuistin tyhjennyksellä.
* TäTissä huomasin sellaisen ongelman, että jos IntranetUserJS: Generate PIN codes -liitännäinen on aktivoitu, mutta sinne ei ole määritetty mitään asiakastyyppejä, niin kaikille generoituu nelinumeroinen pin-koodi. Kävin epäaktivoimassa liitännäisen, koska sitä ei TäTissä tarvita.
* Suljin signum-muutokseen liittyviä tikettejä ja jätin auki lähinnä OUTIn muutokseen liittyvät. Ne tehdään sitten, kun OUTIssa on saatu vietyä päätökseen projektia varten tarvittavat muutokset.
* Kyytissä ja OUTIssa on tullut käyttäjiltä ilmoituksia, että he ovat saaneet Virhe 500 -ilmoituksen, kun ovat lainanneet toiselle asiakkaalle jo lainassa olevia niteitä ja valinneet valinnan "Muista istunnolle", että lainaesto ohitetaan. Testasimme tätä Pirkko-Liisan kanssa sekä testeillä että tuotannossa superlibraian-oikeuksilla, perusvirkailijaoikeuksilla sekä minimioikeuksisilla tunnuksilla emmekä saaneet toistettua virheilmoitusta. Ehdotin ongelman johtuvan välimuistiongelmasta ja että käyttäjät voisivat tyhjentää selaimen välimuistinsa ja yrittää uudelleen. [Tiketti Koha-25x #254](https://github.com/KohaSuomi/Koha-25x/issues/254)

#### Johanna
* [Bug 23269: Add missing translations](https://github.com/KohaSuomi/Koha-25x/commit/d8e8ae4) (Koha-25x - ksdev/ks-0274-on-0243-KOHA-1563-prioritize-holds)
* [Bug 39140: Add missing pickup library check](https://github.com/KohaSuomi/Koha-25x/commit/3d24e77) (Koha-25x - ksdev/ks-0274-on-0243-KOHA-1563-prioritize-holds)
* [Merge branch 'master' of https://github.com/KohaSuomi/koha-plugin-broadcast-biblios](https://github.com/KohaSuomi/koha-plugin-broadcast-biblios/commit/9718c6f) (koha-plugin-broadcast-biblios - master)
* [Fix col class](https://github.com/KohaSuomi/koha-plugin-broadcast-biblios/commit/274f68a) (koha-plugin-broadcast-biblios - master)
* [Remove file](https://github.com/KohaSuomi/koha-plugin-broadcast-biblios/commit/4c67cde) (koha-plugin-broadcast-biblios - master)
* [KOHA-2221: Fetch messages again when cancelling](https://github.com/KohaSuomi/koha-plugin-print-pdf-notices/commit/8a659dc) (koha-plugin-print-pdf-notices - master)
* [KPVLT-11: Improve error message](https://github.com/KohaSuomi/koha-plugin-visual-label-tool/commit/6de3a2c) (koha-plugin-visual-label-tool - master)
* [Fix fetching itemnumber for dropdown](https://github.com/KohaSuomi/koha-plugin-visual-label-tool/commit/7975de9) (koha-plugin-visual-label-tool - ks25, master)
* [KPVLT-11: Fix error handling and improve messages](https://github.com/KohaSuomi/koha-plugin-visual-label-tool/commit/1dbbddd) (koha-plugin-visual-label-tool - master)
* [Remove console.log](https://github.com/KohaSuomi/koha-plugin-visual-label-tool/commit/a0dca1e) (koha-plugin-visual-label-tool - master)
* [Add entry for ksdev/ks-0306-bug-40739-transfersblockcirc](https://github.com/KohaSuomi/koha-suomi-utility/commit/1097b4e) (koha-suomi-utility - master)
* [KohaSuomi/Koha - Siili: middle_name eli toinen nimi -kenttien tyhjennys](https://github.com/KohaSuomi/Koha/issues/2177);
Vastuutettu: johannaraisa, Anknite-cpu.
Kommentti: Nyt on tehty
* [KohaSuomi/Koha - Tarratulostuksessa ei saa luokkaa kirjaimella alkavasta signumista](https://github.com/KohaSuomi/Koha/issues/2197);
Vastuutettu: johannaraisa, Anknite-cpu.
* [KohaSuomi/Koha - Palautuksessa ei voi palauttaa useita kuljetettavia niteitä peräkkäin](https://github.com/KohaSuomi/Koha/issues/2200);
Vastuutettu: johannaraisa.
Kommentti: Tämä on nyt testeillä.
* [KohaSuomi/Koha - OUTI: Maksu ei siirtynyt Ceeposiin ja Koha antoi virheilmoituksen "Missing from configuration"](https://github.com/KohaSuomi/Koha/issues/2208);
Kommentti: Minkätyyppistä maksua tässä ollaan maksamassa? Vaikuttaa siltä ettei se payment_type ole oikein.
* [KohaSuomi/Koha - Lappi: Suomi.fi -viestien käyttöönotto](https://github.com/KohaSuomi/Koha/issues/2214);
Vastuutettu: johannaraisa.
* [KohaSuomi/Koha - Lappi: Testikantaan päälle kaukolainamoduuli](https://github.com/KohaSuomi/Koha/issues/2216);
Vastuutettu: johannaraisa.
Kommentti: Nyt on laitettu nämä testille.
* [KohaSuomi/Koha - Tulosta ilmoituksia -liitännäisessä peruuta-painiketta painaessa sivu ei päivity automaattisesti](https://github.com/KohaSuomi/Koha/issues/2221);
Vastuutettu: johannaraisa.
Kommentti: Testeillä on tähän korjaus, lataa sivu ctrl+F5:llä.
* [KohaSuomi/Koha-25x - Vaski: "Print slip and confirm" -painike ei toimi kun varauksen palauttaa ensimmäisen kerran](https://github.com/KohaSuomi/Koha-25x/issues/244);
Vastuutettu: johannaraisa.
Kommentti: Tämä on nyt testeillä testattavana.
Kommentti: Tähän löysin jo syyn, napin if-lauseesta puuttui kirjastopisteen tarkistus.
* [KohaSuomi/Koha-25x - Varauksen palautuksesta kaksi erilaista varausmodaalia](https://github.com/KohaSuomi/Koha-25x/issues/245);
Vastuutettu: johannaraisa.
Kommentti: Tuolle hold-found-modal-modaalille käännökset tehdään sillä uudella tavalla mitä käytetään myös asiakashakusivulla.
Kommentti: Vaskissa sekin näyttää olevan nyt englanniksi. Näyttävät laajentavan tuota tapaa tehdä käännöksiä, en tiedä auttaisiko tässä jos käynnistää plackin uudestaan.
* [KohaSuomi/Koha-25x - Tietuesiirtäjä: Muutokset -popparin kenttien tiedot yhdelle riville](https://github.com/KohaSuomi/Koha-25x/issues/247);
Vastuutettu: johannaraisa.
Kommentti: Tämä on testeillä, OUTIssa ei näyttänyt olevan tietueita listassa jossa tuo olisi näkynyt. Vaskilla kävin katsomassa ja näytti tälle,
Kommentti: Olen näköjään tämän jo neljä kuukautta sitten korjannut, mutta enää ei päde edes tuollainen määritelmä.
* [KohaSuomi/Koha-25x - Noutohyllyjen tuonti nextiltä testille](https://github.com/KohaSuomi/Koha-25x/issues/252);
Vastuutettu: johannaraisa.
Kommentti: Nyt on Vaskille kopioitu hyllyt nextiltä.
* [KohaSuomi/koha-plugin-visual-label-tool - Virhekäsittelyt eivät toimi oikein](https://github.com/KohaSuomi/koha-plugin-visual-label-tool/issues/11);
Tiketti avattu.
Vastuutettu: johannaraisa.
* [KohaSuomi/koha-suomi-utility - Tätin SRU server (z3950_responder.pl) ei käynnistynyt](https://github.com/KohaSuomi/koha-suomi-utility/issues/100);
Tiketti avattu.


#### Emmi
* Kirkesiin ajettu cn_sort-kenttien korjaus [Kirkes: tietokannassa virheellisiä cn_sort-kenttiä](https://github.com/KohaSuomi/Koha/issues/2024)
* Testeille tehty muutoksia indeksointijonon kokoon ja muutos dokumentoitu
* Laskutustyökaluun lisätty testi-vipu, jolla voi generoida testilaskuja palvelimelle. Laskut generoituvat erilliseen test-hakemistoon ja ne merkitään tietokantaan failed-tilaan. Lisäksi niille tule oma failure_code:nsa. [Laskutusliitännäinen: Test-vipu run_finvoices.pl ajoon](https://github.com/KohaSuomi/koha-plugin-overdue-tool/issues/35)
* Varaustyökaluun ei pysty tällä hetkellä viemään raportilla kuin alle 50 varausta. Ongelma näyttäisi poistuneen yhteisön versiossa 25.05.05, mutta korjaavaa committia ei ole vielä löytynyt. [Varausten vienti raportilta erämuokkaukseen epäonnistuu isoilla määrillä](https://github.com/KohaSuomi/Koha/issues/1980)

#### Lari

  Tiketit

  * [Yksityisoikeudellisten maksujen poistoajo ei päällä?](https://github.com/KohaSuomi/Koha/issues/2223) https://github.com/KohaSuomi/Koha/issues/2223
    [30.3.] Nämä ajot ovat olleet poikki kaikissa kimpoissa versionvaihdosta lähtien johtuen siitä, että ajastetun ajon $NEWTRIG-skripti puuttuu tuotannoista, eikä ajot siksi ole menneet läpi.

    [30.3.] Nyt kaikkin tuotantoihin on korjattu ajastettu ajo. Ajautuu siis ensi yöstä taas päivittäin ja missatut maksutkin tulevat käsiteltyä.

  * [Hyllyvarausraportille näppäintoiminto pudotusvalikkoihin](https://github.com/KohaSuomi/Koha/issues/2210) https://github.com/KohaSuomi/Koha/issues/2210
    [30.3.] Poistin holds-to-pull-skriptistä "zero-width space"-lisäykset jotta näppäinkomennot tarttuvat suodatusarvoihin ja tein mm. Hyllyssä- ja Noutopaikassa-sarakkeille kustomoidut filtterit. Testattavana testeillä.

    [30.3.] Lisäsin saman kustomoidun filtteröinnin käyttöön näille muillekin sarakkeille, millä on pudotusvalikko ja missä voi olla useampi arvo valittavana. Testattavana testeillä.

  * [Varauksen noutomuistutusilmoituksille sallittavat viestienvälitystavat](https://github.com/KohaSuomi/Koha/issues/2190) https://github.com/KohaSuomi/Koha/issues/2190
    [31.3.] Sovittiin kehittäjäpalsussa että siivotaan ei-halutut viestivalinnat pois asiakkailta tietokannasta ennemmin kuin muutetaan skriptin toimintaa (vipu tiettyjen toimitustapojen pakottamiseksi), jotta skripti toimii käyttöliittymässä näkyvien(/piilotettujen) valintojen mukaisesti. Ei maksa mittee.

  * [OUTI: Maksu ei siirtynyt Ceeposiin ja Koha antoi virheilmoituksen "Missing from configuration"](https://github.com/KohaSuomi/Koha/issues/2208) https://github.com/KohaSuomi/Koha/issues/2208
    [31.3.] Toimimaton nappi on piilotettu Lainausnäkymästä. Testattavana testeillä.

  * [Maksujen muodostus hidasta versionvaihdon jälkeen](https://github.com/KohaSuomi/Koha/issues/2233) https://github.com/KohaSuomi/Koha/issues/2233
    [1.4.] Tutkimusteni mukaan accountlines-tauluun on tullut versionvaihdossa uusi sarake old_issue_id ja issues/old_issues-tauluun checkin_library joilla voi olla merkitystä. Reserves-taulussa uutena deleted_biblionumber.

  * [Vaskille käyttöön versiopäivityksen yhteydessä varauksen noutomuistutuksen muutokset](https://github.com/KohaSuomi/Koha/issues/2198) https://github.com/KohaSuomi/Koha/issues/2198
    [1.4.] Ajettu days_in_advance NULL -> 1.

  * [Helle, asiakkaalle muodostunut Varauksen noutomuistutus voimassa olevasta lähiaikoina vanhenevasta varauksesta](https://github.com/KohaSuomi/Koha/issues/2227) https://github.com/KohaSuomi/Koha/issues/2227
    [1.4.] Lisäsin testeille noutomuistutusten luontiskriptiin ehdon, että vain varaukset, joiden tila on W"odottaa" käsitellään. https://github.com/KohaSuomi/Koha-25x/commit/bb3d199fc06dfeb9aa293498546327d525c198e2  Muutos viety testeille.

    [1.4.] Testaus:  Tee asiakkaalle kaksi varausta, jotka vanhenevat x päivän päästä ja tärppäytä toinen niistä. Varmista, että vanehenemispäivä on edelleen x päivän päästä. Tarkista, että noutomuistutus, joka muodostuu asiakkaalle valittuna ajankohtana sisältää vain tärpänneen varauksen.

  * [Self service-pluginin repositorion korvaaminen Koha-Suomen versiolla.](https://github.com/KohaSuomi/Koha/issues/1847) https://github.com/KohaSuomi/Koha/issues/1847
    [2.4.] Plugin on poistettu käytöstä.

  * [Lumme: uusien maksutyyppien lisäys mitätöintiajoon](https://github.com/KohaSuomi/Koha/issues/2143) https://github.com/KohaSuomi/Koha/issues/2143
    [2.4.] Maksutyypit on lisätty entisten lisäksi maksujen mitätöintiajoon. Ajautuvat joka päivä, joten huomenna poistuvat kaikki 3v ja sitä vanhemmat, joiden kuuluu poistua.

  * [SIP2-autentikointi lokittuu virheellisesti verkkokirjastossa tapahtuvaksi](https://github.com/KohaSuomi/Koha/issues/2079) https://github.com/KohaSuomi/Koha/issues/2079
    [2.4.] Muutos on tuotannoissa.

  * [EDItX Koodiin jääneen debuglokituksen poisto](https://github.com/KohaSuomi/koha-plugin-editx/issues/11) https://github.com/KohaSuomi/koha-plugin-editx/issues/11
    [2.4.] Tämä muutos koski EDItX-pluginia eikä SIPoHTTP:ta kuten tiketissä virheellisesti mainittiin. Korjaus on paikallaan tuotannoissa ja testeillä (ja nexteillä).

  Kommitit

  * KohaSuomi/Koha-25x
    * `6276f0d` [30.3.] KOHA-2210 Use custom filter plugin in template for filter typing and exact matches
    * `8c28b94` [30.3.] KOHA-2210 Use custom list filter for all dropdown columns
    * `bb3d199` [31.3.] Only deal with reserves with waiting status

  * KohaSuomi/koha-plugin-ceepos-integration
    * `fa7053e` [31.3.] KOHA-2208 hide paycollect button in circulation.pl that doesn't work with Ceepos

#### Kodo
* Koha versiopäivityksen yliheitto + ajot;
yliheitto ja ajot ajettu sunnuntain 2026-03-22 – maanantain 2026-03-23 välisenä yönä.
* [FacetSortingLocale-järjestelmäasetuksesta puuttuu kielivaihtoehdot](https://github.com/KohaSuomi/Koha-25x/issues/246);
tilanne kuvattu: ongelma ei ilmene testeillä; TäTi ja Siili ok; muissa kimpoissa kielivaihtoehdot näkyvät/puuttuvat vaihtelevasti. Kokeellinen korjaus tehty, mutta tulos laiha.
* [Lainaus ja palautus -sivujen sivuvalikossa väärä linkki](https://github.com/KohaSuomi/Koha-25x/issues/249);
linkki korjattu kiireellisenä tuotantoihin; pysyvämpi korjaus tehty ja tulossa buildissa tuotantoon; tiketti jätetty auki odottamaan tuotantoon päätymistä.
Seuraavana varmistus viikkopäivityksen jälkeen, että pysyvä korjaus on tuotannossa, ja tiketin sulku.
* [EDItX-plugin - koha-plugin-editx](https://github.com/KohaSuomi/Koha-25x/issues/83);
hankinta tuotti `HANK_`-alkuisia viivakoodeja kimpoissa joissa halutaan automaattigeneroitu viivakoodi, korjaus tehty EDItX-pluginille ja testattu toimivaksi.
Commitoitu ja pushattu, ei vaadi muita toimenpiteitä, seuranta mahdollisten uusien havaintojen varalta.
* [Vanhentuneiden varausten peruuttaminen (crontab)](https://github.com/KohaSuomi/Koha-25x/issues/204);
tilanne todettu tarkistettavaksi ensi viikolla, vanha cronjob deprekoitu ja turha, mutta ei toiminnallista haittaa.
Seuraavana crontab-rivien läpikäynti kimpoittain ja päätös vanhan rivin poistosta / uuden rivin varmistus.
* [99-sanomien käsittely SIP-palvelimen ohi](https://github.com/KohaSuomi/Koha-25x/issues/192);
Bibliothecan automaattien yhteensopivuusongelma (97 resend / checksum/sequence -epäily, mahdollinen rivinvaihto/carriage return -ero)
Korjauksen testauksesta sovittu Bibliothecan kanssa.
Seuraavana testaus Bibliothecan automaatilla, jotta korjaus voidaan validoida ennen uudelleenkäyttöönottoa.
* Runsaasti erilaisia SIP-tunnusongelmia monissa kimpoissa.
Tunnuksia putoillut kyydistä versiopäivityksessä, korjailtu sitä mukaa kun tulee vastaan.
Seuraavana tarkistettava kaikkien kimppojen sip-konfiguraatioiden oikeellisuus

## Viikko 13

Versionvaihdon vuoksi normaaliin viikkopalaveri aikaan pidettiin versionvaihdon tilannekatsaus.
  
## Viikko 12

Aika: Ma 16.3.2026<br />
Läsnä: Lari, Anneli, Johanna, Aleksi, Pasi, Ari, Kodo, Emmi

* Vastuuttomat tiketit
  * [ei-Koha25x-tiketit](https://github.com/issues?q=is%3Aopen%20is%3Aissue%20owner%3AKohaSuomi%20archived%3Afalse%20sort%3Aupdated-desc%20no%3Aassignee%20-repo%3AKohaSuomi%2FBugiton%20-repo%3AKohaSuomi%2FFinna-kehitysehdotukset%20-repo%3AKohaSuomi%2FKoha-25x)
  * [kaikki tiketit](https://github.com/issues?q=is%3Aopen+is%3Aissue+owner%3AKohaSuomi+archived%3Afalse+sort%3Aupdated-desc+no%3Aassignee+-repo%3AKohaSuomi%2FBugiton+-repo%3AKohaSuomi%2FFinna-kehitysehdotukset)

## Viikko 11

Aika: Ma 9.3.2026<br />
Läsnä: Ari, Emmi, Johanna, Aleksi, Lari, Kodo, Pasi

* Päivystysvuorot viikosta 12 alkaen
* Vastuuttomat tiketit
  * [ei-Koha25x-tiketit](https://github.com/issues?q=is%3Aopen%20is%3Aissue%20owner%3AKohaSuomi%20archived%3Afalse%20sort%3Aupdated-desc%20no%3Aassignee%20-repo%3AKohaSuomi%2FBugiton%20-repo%3AKohaSuomi%2FFinna-kehitysehdotukset%20-repo%3AKohaSuomi%2FKoha-25x)
  * [kaikki tiketit](https://github.com/issues?q=is%3Aopen+is%3Aissue+owner%3AKohaSuomi+archived%3Afalse+sort%3Aupdated-desc+no%3Aassignee+-repo%3AKohaSuomi%2FBugiton+-repo%3AKohaSuomi%2FFinna-kehitysehdotukset)
* Versionvaihdon tilannekatsaus, testien versionvaihtoon viikko

## Viikko 10

Aika: Ma 2.3.2026<br />
Läsnä: Ari, Emmi, Johanna, Aleksi, Lari, Anneli, Kodo

* Vastuuttomat tiketit
  * [ei-Koha25x-tiketit](https://github.com/issues?q=is%3Aopen%20is%3Aissue%20owner%3AKohaSuomi%20archived%3Afalse%20sort%3Aupdated-desc%20no%3Aassignee%20-repo%3AKohaSuomi%2FBugiton%20-repo%3AKohaSuomi%2FFinna-kehitysehdotukset%20-repo%3AKohaSuomi%2FKoha-25x)
  * [kaikki tiketit](https://github.com/issues?q=is%3Aopen+is%3Aissue+owner%3AKohaSuomi+archived%3Afalse+sort%3Aupdated-desc+no%3Aassignee+-repo%3AKohaSuomi%2FBugiton+-repo%3AKohaSuomi%2FFinna-kehitysehdotukset)


## Viikko 9

Aika: Ma 23.2.2026<br />
Läsnä: Anneli, Ari, Lari, Kodo, Emmi

* Vastuuttomat tiketit
  * [ei-Koha25x-tiketit](https://github.com/issues?q=is%3Aopen%20is%3Aissue%20owner%3AKohaSuomi%20archived%3Afalse%20sort%3Aupdated-desc%20no%3Aassignee%20-repo%3AKohaSuomi%2FBugiton%20-repo%3AKohaSuomi%2FFinna-kehitysehdotukset%20-repo%3AKohaSuomi%2FKoha-25x)
  * [kaikki tiketit](https://github.com/issues?q=is%3Aopen+is%3Aissue+owner%3AKohaSuomi+archived%3Afalse+sort%3Aupdated-desc+no%3Aassignee+-repo%3AKohaSuomi%2FBugiton+-repo%3AKohaSuomi%2FFinna-kehitysehdotukset)

## Viikko 8

Aika: Ma 16.2.2026<br />
Läsnä: Ari, Emmi, Johanna, Kodo, Anneli, Lari, Pasi

* Päivystysvuorot vko 9 eteenpäin
* Vastuuttomat tiketit
  * [ei-Koha25x-tiketit](https://github.com/issues?q=is%3Aopen%20is%3Aissue%20owner%3AKohaSuomi%20archived%3Afalse%20sort%3Aupdated-desc%20no%3Aassignee%20-repo%3AKohaSuomi%2FBugiton%20-repo%3AKohaSuomi%2FFinna-kehitysehdotukset%20-repo%3AKohaSuomi%2FKoha-25x)
  * [kaikki tiketit](https://github.com/issues?q=is%3Aopen+is%3Aissue+owner%3AKohaSuomi+archived%3Afalse+sort%3Aupdated-desc+no%3Aassignee+-repo%3AKohaSuomi%2FBugiton+-repo%3AKohaSuomi%2FFinna-kehitysehdotukset)
* Versionvaihdon tilannekatsaus, kun versionvaihtoon reilu kuukausi.
  * [Auki olevat tiketit](https://github.com/KohaSuomi/Koha-25x/issues)
  * [Avoimet tiloittain](https://github.com/orgs/KohaSuomi/projects/6/views/2)

## Viikko 7

Aika: Ma 9.2.2026<br />
Läsnä: Ari, Pasi, Lari, Emmi, Johanna, Kodo

* Vko 7 päivitys
  * Koha-tietoturvapaikka, tuotantoon tiistaina 10.2. aamulla.
* Vastuuttomat tiketit
  * [ei-Koha25x-tiketit](https://github.com/issues?q=is%3Aopen%20is%3Aissue%20owner%3AKohaSuomi%20archived%3Afalse%20sort%3Aupdated-desc%20no%3Aassignee%20-repo%3AKohaSuomi%2FBugiton%20-repo%3AKohaSuomi%2FFinna-kehitysehdotukset%20-repo%3AKohaSuomi%2FKoha-25x)
  * [kaikki tiketit](https://github.com/issues?q=is%3Aopen+is%3Aissue+owner%3AKohaSuomi+archived%3Afalse+sort%3Aupdated-desc+no%3Aassignee+-repo%3AKohaSuomi%2FBugiton+-repo%3AKohaSuomi%2FFinna-kehitysehdotukset)
* IntranetUserJS-rimpsujen päivitykset
  * Pääkäyttäjät tekee varsinaisen muutoksen, Koha-Suomen päivystäjä laskee uuden tarkisteen.
  * Tehdään ohjeistus (Emmi), päivitetään principio (Kodo)
* Meitä kiinnostavien yhteisö-tikettien koostaminen esim. Bugiton-tietovarantoon.
  * Avataan tiketti bugittomaan ja siihen linkki bugzillaan.
* OUTIn signum-kuvio
  * Käytetään asiantuntijaryhmässä, saataisiinko yhtenäinen käytäntö
  * Otettanee plugin matkaan tilapäisesti, työ on Outille maksullista

## Viikko 6

Aika: Ma 2.2.2026<br />
Läsnä: Ari, Anneli, Lari, Johanna, Kodo, Pasi

* Vastuuttomat tiketit
  * [ei-Koha25x-tiketit](https://github.com/issues?q=is%3Aopen%20is%3Aissue%20owner%3AKohaSuomi%20archived%3Afalse%20sort%3Aupdated-desc%20no%3Aassignee%20-repo%3AKohaSuomi%2FBugiton%20-repo%3AKohaSuomi%2FFinna-kehitysehdotukset%20-repo%3AKohaSuomi%2FKoha-25x)
  * [kaikki tiketit](https://github.com/issues?q=is%3Aopen+is%3Aissue+owner%3AKohaSuomi+archived%3Afalse+sort%3Aupdated-desc+no%3Aassignee+-repo%3AKohaSuomi%2FBugiton+-repo%3AKohaSuomi%2FFinna-kehitysehdotukset)

## Viikko 5

Aika: Ma 26.1.2026<br />
Läsnä: Ari, Anneli, Kodo, Emmi, Johanna, Lari, Pasi

* Vastuuttomat tiketit
  * [ei-Koha25x-tiketit](https://github.com/issues?q=is%3Aopen%20is%3Aissue%20owner%3AKohaSuomi%20archived%3Afalse%20sort%3Aupdated-desc%20no%3Aassignee%20-repo%3AKohaSuomi%2FBugiton%20-repo%3AKohaSuomi%2FFinna-kehitysehdotukset%20-repo%3AKohaSuomi%2FKoha-25x)
  * [kaikki tiketit](https://github.com/issues?q=is%3Aopen+is%3Aissue+owner%3AKohaSuomi+archived%3Afalse+sort%3Aupdated-desc+no%3Aassignee+-repo%3AKohaSuomi%2FBugiton+-repo%3AKohaSuomi%2FFinna-kehitysehdotukset)
* Rajapintojen salasanojen/tokenien kierrättäminen ulkoisissa palveluissa.
  * Pyydetään pääkäyttäjiä miettimään mitkä mahdolliset palvelut, ja uusimaan niiden salasanat säännöllisesti. 


## Viikko 4

Aika: Ma 19.1.2026<br />
Läsnä: Johanna, Pasi, Kodo, Ari, Lari ja Emmi

* Vastuuttomat tiketit
  * [ei-Koha25x-tiketit](https://github.com/issues?q=is%3Aopen%20is%3Aissue%20owner%3AKohaSuomi%20archived%3Afalse%20sort%3Aupdated-desc%20no%3Aassignee%20-repo%3AKohaSuomi%2FBugiton%20-repo%3AKohaSuomi%2FFinna-kehitysehdotukset%20-repo%3AKohaSuomi%2FKoha-25x)
  * [kaikki tiketit](https://github.com/issues?q=is%3Aopen+is%3Aissue+owner%3AKohaSuomi+archived%3Afalse+sort%3Aupdated-desc+no%3Aassignee+-repo%3AKohaSuomi%2FBugiton+-repo%3AKohaSuomi%2FFinna-kehitysehdotukset)
* Versionvaihdon tilannekatsaus, kun laajemmat testaukset ovat olleet käynnissä viikon.
  * [Auki olevat tiketit](https://github.com/KohaSuomi/Koha-25x/issues)
  * [Avoimet tiloittain](https://github.com/orgs/KohaSuomi/projects/6/views/2)

## Viikko 3

Aika: Ma 12.1.2026<br />
Läsnä: Pasi, Anneli, Emmi, Ari, Lari, Johanna, Kodo

* Vastuuttomat tiketit
  * [ei-Koha25x-tiketit](https://github.com/issues?q=is%3Aopen%20is%3Aissue%20owner%3AKohaSuomi%20archived%3Afalse%20sort%3Aupdated-desc%20no%3Aassignee%20-repo%3AKohaSuomi%2FBugiton%20-repo%3AKohaSuomi%2FFinna-kehitysehdotukset%20-repo%3AKohaSuomi%2FKoha-25x)
  * [kaikki tiketit](https://github.com/issues?q=is%3Aopen+is%3Aissue+owner%3AKohaSuomi+archived%3Afalse+sort%3Aupdated-desc+no%3Aassignee+-repo%3AKohaSuomi%2FBugiton+-repo%3AKohaSuomi%2FFinna-kehitysehdotukset)
