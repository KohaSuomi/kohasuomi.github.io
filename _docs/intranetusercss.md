---
title: 'IntranetUserCSS'
permalink: /dokumentaatio/intranetusercss/
redirect_from:
  - /theme-setup/
toc: true
---

IntranetUserCSS-järjestelmäasetuksella pystyy "ohittamaan" Kohan CSS-määritykset ja esimerkiksi piilottamaan eri sivuilta elementtejä tai säätämään fontin kokoa ja väriä. Tämä on kevyempi tapa säätää näkymiä koskematta Kohan sivupohjiin.

Jokaisen kohdalle on merkitty, missä Koha-versiossa se toimii.


## Asiakkaat

### Piilota Asiakkaat-sivulla hausta osoite-hakuvaihtoehto

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 23.11

```
/* Piilota Asiakkaat-sivulla hausta osoite-hakuvaihtoehto */
body#pat_member #searchfieldstype option[value='full_address'] { display:none; }
body#pat_member #searchfieldstype_filter option[value='full_address'] { display:none; }
```

### Piilota asiakkaan kuva, jos asiakkaalla ei ole sellaista

Versio: 17.05

```
/* Piilota asiakkaan kuva, jos asiakkaalla ei ole sellaista */
li#patronbasics img[src$="blank.png"] { display: none !important; }
li.email { background: none !important; }
```

### "Kirjoitussuojaa" sotu-avain-kenttä

Sotu-avain-kentän voi "kirjoitussuojata" niin, että siihen pystyy Lisää sotu -toiminnolla lisäämään sotu-avaimen, mutta käyttäjä ei pysty muokkaamaan kentässä olevaa tietoa. Käyttäjä pystyy poistamaan tiedon kentän vieressä olevalla "Tyhjennä"-linkillä.

Huomioi, että patron_attr_4-osiossa oleva numero riippuu siitä, kuinka monentena sotu-avain on näytöllä. Esim. OUTI-kirjastoissa numerona on 3 ja Hellessä 4. Voit tarkistaa numeron klikkaamalla asiakkaan muokkausnäytöllä hiiren oikealla sotu-avain-kenttää ja valitsemalla "Inspect Element (Q)" (toimii ainakin Firefoxilla).

Tarpeellisuus: Suositeltava<br />
Versio: 23.11

```
body#pat_memberentrygen.pat textarea#patron_attr_4 { pointer-events: none; }
```

### Käyttäjätunnus-osion piilottaminen asiakkaan muokkausnäytöltä

Käyttäjätunnus-osion piilottaminen asiakkaan muokkausnäytöltä.

Versio: 17.05

```
/* Piilota Käyttäjätunnus-osio asiakkaan muokkausnäytöltä */
#pat_memberentrygen.pat fieldset#memberentry_userid { display:none; }
```

### Asiakasmääreen piilottaminen tiedot-näytöltä

Versio: 17.05

```
/* Piilota asiakasmääre tiedot-näytöltä */
div#patron-extended-attributes ol li:nth-child(1) { display:none; }
```

### Piilota asiakkaan ikä Tiedot-välilehdellä

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 23.11

```
/* Piilota asiakkaan ikä tiedot-näytöllä */
body#pat_moremember.pat span.age_years { display: none; }
```

### Piilota Näytä aina lainat reaaliaikaisesti -valinta

Tarpeellisuus: Suositeltava, parantaa suorituskykyä.<br />
Versio 23.11

```
/* Piilota Näytä aina lainat reaaliaikaisesti / Always show checkouts immediately -täppä. Piilottaa sekä lainaus- että tiedot-näytöltä. */
body#circ_circulation.circ input#issues-table-load-immediately { display: none; }
body#circ_circulation.circ label[for="issues-table-load-immediately"] { display: none; }
body#pat_moremember.pat input#issues-table-load-immediately { display: none; }
body#pat_moremember.pat label[for="issues-table-load-immediately"] { display: none; }
```

### Säädä Viesti asiakkaalle -viestin väriä

Tarpeellisuus: Vapaaehtoinen<br />
Versio 23.11

```
/* Säädä Viesti asiakkaalle -viestin väriä */
#messages.circmessage span { color:#009900; font-weight: bold;}
#messages.circmessage span.circ-hlt { color:#cc0000; }
```

### Piilota Tiedot-sivulla Alternative contact / Vaihtoehtoinen yhteys -osio

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 23.11

```
/* Piilota Tiedot-sivulla Alternative contact / Vaihtoehtoinen yhteys -osio */ 
#patron-alternative-contact,
#patron-alternative-contact + div { display:none; }
```

### Piilota asiakkaan tiedot -sivulta Alternate address/ Vaihtoehtoinen osoite -osio

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 23.11

```
/* Piilota asiakkaan tiedot -sivulta Alternate address/ Vaihtoehtoinen osoite -osio */
#patron-alternate-address,
#patron-alternate-address + div { display:none; }
```


### Piilota asiakkaan muokkauksessa Yhteystiedot-boksista vihjeet näkyvistä

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 23.11

```
/* Piilota asiakkaan muokkauksessa Yhteystiedot-boksista vihjeet näkyvistä */ 
fieldset#memberentry_contact.rows div.hint { display: none; }
```

### Piilota maksujen mitätöintitäppä Asiakkaan tiedot- ja Lainaus-sivuilta

Tarpeellisuus: Suositeltava<br />
Versio: 23.11

```
/* Asiakkaan tiedot -sivulla lainat-taulu */
/* Piilota Poista myöhästymismaksut palautettaessa -täppä */
#pat_moremember #issues-table label[for="exemptfine"] { display:none; }
#pat_moremember #issues-table input#exemptfine { display:none; }

/* Lainaus-sivulla Asiakkaan lainat-taulu */
/* Piilota Poista myöhästymismaksut palautettaessa -täppä */
#circ_circulation #issues-table label[for="exemptfine"] { display:none; }
#circ_circulation #issues-table input#exemptfine { display:none; }
```

### Piilota asiakkaan tiedot -näytöltä muokkaa-linkit

Tarpeellisuus: Suositeltava<br />
Versio: 23.11

```
/* Piilota asiakkaan tiedot -näytöltä muokkaa-linkit. Jatkossa muokkaus onnistuu vain yläreunan Muokkaa-napista */
body#pat_moremember a[href*="&step="] { display: none; }
```

### Piilota Ei asiakas -takaaja -kohta asiakkaan muokkauksesta

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 23.11

```
/* Piilota Ei asiakas -takaaja -kohta asiakkaan muokkauksesta */
body#pat_memberentrygen.pat fieldset#non_patron_guarantor.rows { display:none; }
```

### Piilota Tarkista edelliset lainat -kohta asiakkaan muokkauksesta

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 23.11

```
/* Piilota Tarkista edelliset lainat -kohta asiakkaan muokkauksesta */
body#pat_memberentrygen.pat label[for="checkprevcheckout"] { display:none; }
body#pat_memberentrygen.pat select#checkprevcheckout { display:none; }
```

### Piilota Tarkista edelliset lainat -kohta asiakkaan tiedot-sivulla

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 23.11

```
/* Piilota asiakkaan tiedot -sivulta "Tarkista edelliset lainat" -kohta */
body#pat_moremember.pat li#patron-checkprev { display:none; }
```

### Piilota ennakkoilmoituksen valinnasta 0 päivän keston

Jos ennakkoilmoitukseen valitsee päiväksi 0, viesti ei lähde ollenkaan.

Tarpeellisuus: Suositeltava<br />
Versio: 23.11

```
/* Piilota ennakkoilmoituksen valinnasta 0 päivän keston. Käy lisäksi valitsemassa asiakastyyppien ylläpidossa asiakastyyppien viestiasetuksiin jotain muuta kuin 0 oletukseksi. Valinta tehtävä kaikille asiakastyypeille erikseen. */
body#pat_memberentrygen.pat fieldset#memberentry_messaging_prefs.rows option[value='0'] { display:none; }
```
### Piilota asiakkaan viestiasetuksista ennakkoilmoituksen viive -vaihtoehdoista 0 ja 8-30

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 23.11

```
/* Asiakkaan viestiasetukset, ennakkoilmoituksen viive-vaihtoehdoista arvot 0 ja 8-30 piiloon */
body#pat_memberentrygen.pat [name="2-DAYS"] :is([value='0'], [value='8'], [value='9'], [value='10'],
 [value='11'], [value='12'], [value='13'], [value='14'], [value='15'], [value='16'], [value='17'], [value='18'], [value='19'], [value='20'],
 [value='21'], [value='22'], [value='23'], [value='24'], [value='25'], [value='26'], [value='27'], [value='28'], [value='29'], [value='30']) { display:none; }
```

### Piilota käyttäjätilin huomautukset asiakaslomakkeelta (Tarkista osoite ja Kadonnut kortti)

Tarpeellisuus: Suositeltava<br />
Versio: 23.11

Suositeltava, koska näiden perusteella ei saa tulla lainakieltoa lain mukaan.
```
/* Piilota Käyttäjätilin huomautukset asiakaslomakkeelta (Tarkista osoite ja Kadonnut kortti) */ 
#pat_memberentrygen #memberentry_account_flags { display:none; }
```

### Piilota noutomuistutus asiakaslomakkeelta

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 23.11

```
/* Noutomuistutuksen piilotus asiakaslomakkeelta */
body#pat_memberentrygen #memberentry_messaging_prefs table tbody tr:last-child { display:none; }
```

### Piilota noutomuistutus tiedot-sivulta viestiasetuksista

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 23.11

```
/* Noutomuistutuksen piilotus tiedot-sivulta */
body#pat_moremember #patron-messaging-prefs table tbody tr:last-child { display:none; }
```

### Piilota Salli automaattinen uusinta -kohta

Asiakkaan lisäys/muokkausnäytöllä on kohta "Salli automaattinen uusinta", vaikka toiminto ei olisi sallittu laina- ja maksusäännöissä. Kohdan saa piiloon seuraavasti. Päivitys 8.4.2024: Tätä piilotusta ei enää tarvita, vaan tiedon saa piiloon BorrowerUnwantedField-järjestelmäasetukella valitsemalla autorenew_checkouts-kohdan.

Tarpeellisuus: Ei tarpeellinen<br />
Versio: 22.11

```
/* Automatic renewal / Automaattinen uusinta -checkboxi piiloon */
body#circ_circulation #set-automatic-renewal { display: none; }
```

### Asiakkaan tietoruudun piilotus asiakastiedoista vasemmasta reunasta

Tarpeellisuus: Ei tarpeen<br />
Versio: 21.11<br />
Asiantuntijaryhmä on päättänyt, että tietoruutu on näkyvillä, jotta tilin lukkiutuminen näkyy virkailijalle.

```
/* Asiakkaan tietoruudun piilotus vasemmasta reunasta */
div.patroninfo { display: none; }
```

### Piilota asiakastietojen tulosta-valikosta Asiakastietojen yhteenveto

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 23.11

```
/* Piilota asiakastietojen tulosta-valikosta Asiakastietojen yhteenveto */ 
body#pat_moremember.pat ul.dropdown-menu li:nth-child(1) a.printslip {display: none}
body#circ_circulation.circ ul.dropdown-menu li:nth-child(1) a.printslip { display: none; }
```

### Piilota asiakastietojen tulosta-valikosta Tulosta erääntyneet -valinnat

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 23.11

```
/* Piilota asiakastietojen tulosta-valikosta Tulosta erääntyneet */ 
body#pat_moremember.pat ul.dropdown-menu li:nth-child(4) a#print_overdues { display: none; }
body#circ_circulation.circ ul.dropdown-menu li:nth-child(4) a#print_overdues { display: none; }
```

### Piilota Näytä takaajalle lainat ja Näytä takaajalle maksut -kohdat Tiedot-näytöltä

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 22.11

```
/* Piilota Näytä takaajalle lainat ja Näytä takaajalle maksut -tiedot */
#patron-privacyguarantor + li { display: none; }
#patron-privacyguarantor { display: none; }
```

### Säädä Lisää viesti -popparin alasvetovalikon leveyttä

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 23.11

Säätö tehdään sekä lainaus- että tiedot-sivulle.

```
/* Säädä Lisää viesti -popupissa valikon leveys kapeammaksi lainaus- ja tiedot-näytöillä */
body#pat_moremember.pat.modal-open select#select_patron_messages { width: 556px; }
body#circ_circulation.circ.modal-open select#select_patron_messages { width: 556px; }
```

### Piilota kirjautumistunnusosio asiakaslomakkeelta

Tarpeellisuus: Suositeltava<br />
Versio: 23.11

```
/* Piilota kirjautumistunnusosio asiakaslomakkeelta. BorrowerUnwantedFields-asetuksella saa userid:n ja passwordin piiloon, mutta ei salasanan vanhenemispäivä-kenttää. Tosin, salasnan vanhenemispäivä -kenttä näkyy vain superlibrarian-oikeuksisille. */
body#pat_memberentrygen.pat #memberentry_userid.rows { display:none; }
```

### Piilota käyttäjänimi-kenttä salasananvaihto-sivulta

Tarpeellisuus: Suositeltava<br />
Versio: 23.11

```
/*Käyttäjänimi-kentän piilotus salasananvaihto-sivulla*/
/* /cgi-bin/koha/members/member-password.pl?member=?????? */
form[action="/cgi-bin/koha/members/member-password.pl"] ol li:nth-child(1) {
  display: none;
}
```

### Piilota Ensisijainen yhteydenottotapa -valinta asiakkaan muokkauksesta

Tarpeellisuus: Suositeltava<br />
Versio: 23.11

```
/* Piilota Ensisijainen yhteydenottotapa -valinta asiakkaan muokkauksesta */
body#pat_memberentrygen.pat select#primary_contact_method.noEnterSubmit { display: none; }
body#pat_memberentrygen.pat label[for="primary_contact_method"] { display: none; }
```

### Piilota Muut määreet ja tunnukset -kohta asiakkaan muokkauksesta

Tällä piilotetaan asiakkaan muokkausnäytöltä Muut määreet ja tunnukset -osio. Tämä voi olla tarpeen, jos osion kaikki määreet on siirretty JS-rimpsuilla toiseen kohtaan lomaketta ja osio jää tyhjäksi.

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 23.11

```
/* Piilota Muut määreet ja tunnukset -kohta asiakkaan muokkauksesta. Tämä voi olla tarpeen, jos kaikki määreet on siirretty toiseen kohtaan lomaketta. */
body#pat_memberentrygen.pat fieldset#memberentry_patron_attributes.rows { display:none; }
```

---

## Asiakkaat-sivu

### Säädä Selaa sukunimen mukaan -kohdan kirjaimet isommaksi ja harvemmaksi

Tarpeellisuus: Suositeltava<br />
Versio: 23.11

```
/* Säädä Selaa sukunimen mukaan -kohdan kirjaimet isommaksi ja harvemmaksi */
#pcard_members_search div.browse a,
body#pat_member.pat div.browse a {
  padding:0 0.35em;
  font-size:larger;
}
```

### Säädä Selaa sukunimen mukaan -kohdan kirjaimien taustaväri toiseksi, kun hiiri viedään kirjaimen kohdalle

Tarpeellisuus: Suositeltava<br />
Versio: 23.11

```
/* Säädä Selaa sukunimen mukaan -kohdan kirjaimien taustaväri toiseksi, kun hiiri viedään kirjaimen kohdalle */
#pcard_members_search .browse a:hover,
#pat_member .browse a:hover {
  background-color: #f3f4f4;
}
```

### Piilota asiakashaun "Kaikki"-vaihtoehto

Täällä pyritään estämään se, että virkailija ei vahingossa hae tietokannan kaikkia asiakastietoja listalle, jolloin kaikille listalla oleville tehdään muutoslokiin merkintä asiakastietojen katselusta.

Versio: 23.11<br />
Tarpeellisuus: Suositeltava

```
/* Piilota asiakashaun "Kaikki"-vaihtoehto*/
#memberresultst_length select option:last-child { display: none; }
```

### Piilota Asiakkaan pikalisäys -painike

Rimpsu piilottaa Asiakkaan pikalisäys -painikkeen. Kyseisellä lomakkeella ei ole kaikkia tarvittavia kenttiä näkyvissä, joten se on ainakin osalle kimpoista turha.

Versio 23.11<br />
Tarpeellisuus: Suositeltava

```
/* Piilota Asiakkaan pikalisäys -nappi */
body#pat_member.pat div#quick-add-new-patron-button.btn-group { display: none; }
```

### Piilota asiakashausta valikosta Lajittelu-vaihtoehdot

Versio 23.11<br />
Tarpeellisuus: Vapaaehtoinen

```
/* Piilota asiakashausta valikosta Lajittelu-vaihtoehdot */
body#pat_member.pat select#searchfieldstype_filter option[value='sort1'] { display:none; }
body#pat_member.pat select#searchfieldstype_filter option[value='sort2'] { display:none; }
```

---

## Lainaus ja palautus

### Lainaus ja palautus -osion etusivu

### Piilota uusinta-nappi

Piilota Lainaus ja palautus -osion etusivulta Uusinta-nappi. Toiminto ei noudata laina- ja maksusääntöjä, eikä ota huomioon varauksia, joten sitä ei kannata käyttää.

Versio: 23.11<br />
Tarpeellisuus: Suositeltava

```
/* Piilota uusinta-nappi lainaus- ja palautus -näkymässä */
body#circ_circulation-home a[href="/cgi-bin/koha/circ/renew.pl"] {
display: none;
}
```

### Lainaus

### Piilota "Älä lainaa ja tulosta kuitti" -nappula lainauksessa

Jos lainattavaan teokseen on varaus, antaa Koha ilmoituksen, jossa ilmoitetaan  varauksesta ja pitää päättää, mitä tehdään. Yksi vaihtoehto on "Älä lainaa ja tulosta", joka tulostaa varauksen infokuitin (hold_slip). Varaus ei kuitenkaan jää kiinni eikä nide mene kuljetustilaan, joten kuitti on turha ja aiheuttaa ennemminkin hämmennystä, kun siihen tulostuu asiakkaan tiedot ja varauksen viimeinen voimassaolopäivä (yleensä parin vuoden päässä). Alla olevalla rimpsulla saa napin piiloon.

Versio 23.11<br />
Tarpeellisuus: Suositeltava

```
/* Piilota Älä lainaa ja tulosta kuitti -nappula */
body#circ_circulation.circ button.print { display: none; }
```

### Piilota Automatic renewal / Automaattinen uusinta -checkbox

Versio: 21.11<br />
Versio: 22.11 Ei tarpeellinen, koska  AllowSetAutomaticRenewal -järjestelmäasetuksella saa täpän piiloon.

```
/* Automatic renewal / Automaattinen uusinta -checkboxi piiloon */
body#circ_circulation #set-automatic-renewal { display: none; }
```

### Palautus

### Piilota palautus-näytön asetukset

Versio: 22.11<br />
Tarpeellisuus: Suositeltava

```
/* Piilota Palautukset-sivulla palautusasetukset - varmista, ettei piilota muita vastaavia asetussäätöjä*/
body#circ_returns.circ i.fa.fa-sliders { display: none; }
body#circ_returns.circ div#forgive-overdue-fines.circ-setting { display: none; }
body#circ_returns.circ div#book-drop-mode.circ-setting { display: none; }
body#circ_returns.circ div.forgive-manual-hold-fees.circ-setting { display: none; }
```

### Piilota asiakkaan tiedot varaus-popupeista

Jotta turhia asiakastietojen katseluita saadaan vähennettyä, piilotetaan palautuksessa asiakkaan yhteystiedot varausten popupeista. Rimpsuista on kaksi eri versiota ja niitä käytetään riippuen siitä, onko käytössä varausten automaattinen kiinni jääminen vai ei.

Tarpeellisuus: Pakollinen<br />
Versio: 23.11

Varausten automaattinen kiinnijääminen päällä. HUOM! Alimmainen rivi korjattu toisenlaiseksi, koska aiempi versio piilotti palautuksessa oikean yläreunan valikosta kirjastovalinnan. Uudella versiossa piilottuu sähköpostiosoite, mutta laatikkoon jää näkyville listapallero.

```
/* Piilota varausruudusta asiakkaan yhteystiedot, kun käytössä automaattinen varauksen kiinni jääminen */ 
body#circ_returns.circ div.dialog.message.hold-auto-filled ul li:nth-child(4) { display: none; } /* Varaus palautuskirjastossa, puhelinnumero piiloon */
body#circ_returns.circ li.patronaddress1 { display: none; } 
body#circ_returns.circ li.patroncity { display: none; } 
body#circ_returns.circ a#boremail { display: none; }
```


Varausten automaattinen kiinnijääminen ei ole päällä

```
/* Piilota varauksen popparista asiakkaan yhteystiedot */
body#circ_returns.circ i.fa-solid.fa-sliders { display: none; }
body#circ_returns.circ div#forgive-overdue-fines.circ-setting { display: none; }
body#circ_returns.circ div#book-drop-mode.circ-setting { display: none; }
body#circ_returns.circ div.forgive-manual-hold-fees.circ-setting { display: none; }
```

### Laskutettu-merkintä palautuksessa isommaksi

Jos palautetaan laskutettu nide, siitä näkyvä ilmoitus on pieni. Alla olevalla css-säädöllä Laskutettu-ohjeistuksen kokoa saa säädettyä isommaksi.

Lisätty: 28.12.2022<br />
Tekijä: Anni Rajala<br />
Tarpeellisuus: Vapaaehtoinen<br />
Versio: 23.11

```
/* Säädä Laskutettu-merkintä palautuksessa isommaksi */
p.problem.ret_nflupdate { font-weight: 500; font-size: 22px; }
```

### Piilota varauksen palautuspopparista Älä huomioi -nappi

Tarpeellisuus: Suositeltava<br />
Versio: 22.11

```
/* Piilota varauksen palauttamisen yhteydessä popparista Älä huomioi -nappi (kun käytössä HoldsAutoFill-järjestelmäasetus) */
/* ja jo noudettavana olevan varauksen uudelleenpalautuksen yhteydessä popparista Poista varaus -nappi ja Peru kuljetus -nappi */
body#circ_returns.circ.modal-open button.btn.btn-default.deny { display: none; }
```

Vaihtoehtoinen versio, joka piilottaa myös Peruuta varaus -napin ja Peru kuljetus -napin.

```
/* Piilota varauksen palauttamisen yhteydessä popparista Älä huomioi -nappi, noudettavana olevan varauksen palautuksen yhteydessä popparista Poista varaus -nappi ja Peru kuljetus -nappi. Käytössä on varausten automaattinen kiinni jääminen. */
body#circ_returns.circ.modal-open button.btn.btn-default { display: none; } 
body#circ_returns.circ.modal-open button.btn.btn-default.deny.cancel-hold { display: none; } 
body#circ_returns.circ.modal-open button.btn.btn-default.approve { display: initial; }
body#circ_returns.circ.modal-open button.btn.btn-default.print { display: initial; }
body#circ_returns.circ.modal-open button.btn.btn-default.deny { display: initial; }
body#circ_returns.circ.modal-open button.btn.btn-default.submit.openWin { display: initial; }
```

Jos käytössä on nidepaketit, kannattaa edelliseen rimpsuun lisätä vielä loppuun tämä, jotta nidepaketin palautuksessa näkyvät Vahvista palautus ja Merkkaa puuttuvat niteet kadonneiksi -napit.

```
body#circ_returns.circ.modal-open div#[bundle-needsconfirmation-modal.modal.fade.audio-alert-action.block.in](http://bundle-needsconfirmation-modal.modal.fade.audio-alert-action.block.in/) button.btn.btn-default { display: initial; } /* Tuo näkyville nidepaketin palautuksessa Vahvista palautus ja Merkkaa puuttuvat niteet kadonneiksi -napin. Se piilottuu ensimmäisen rimpsun vuoksi */
```
---

## Maksut

### Piilota Luo hyvitys -välilehti asiakkaan maksuista 

Tarpeellisuus: Hyvin suositeltava<br />
Versio: 23.11

```
/* Piilota Luo hyvitys -välilehti asiakkaan maksuista */
li.manualcredit { display: none; }
body#pat_paycollect.pat a[href*="/cgi-bin/koha/members/mancredit.pl"] {
  display: none;
}
```

### Piilota oletusmaksuja asiakkaan lisää maksu -toiminnosta

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 23.11

```
/* Piilota maksutyyppejä asiakkaan lisää maksu -toiminnosta */
body#pat_maninvoice.pat option[value='NEW_CARD'] { display:none; }
body#pat_maninvoice.pat option[value='LOST'] { display:none; }
```

### Piilota asiakkaan Maksut/Tapahtumat-välilehdeltä Luo hyvitys -painike

Tarpeellisuus: Suositeltava<br />
Versio: 22.11

```
/* Piilota alennus, peruuta veloitus, luo hyvitys ja mitätöi maksutapahtuma -napit asiakkaan tilitapahtumat sivulta */
body#pat_borraccount button.discount-action { display: none; }
body#pat_borraccount button.cancel-action { display: none; }
body#pat_borraccount button.refund-action { display: none; }
body#pat_borraccount a.void-action { display: none; }
```

### Piilota asiakkaan Maksut/Tapahtumat-välilehdeltä

Piilota Maksut/Tapahtumat-välilehdeltä maksun tietojen tulostus-napit sekä Maksu-nappi. Liittyy tikettiin [Koha #476](https://github.com/KohaSuomi/Koha/issues/476).

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 22.11

```
body#pat_borraccount a.btn.btn-default.btn-xs.invoice-print-action { display: none; } /* Maksun tietojen tulostus-napin piilotus */
body#pat_borraccount a.btn.btn-default.btn-xs.pay-action { display: none; } /* Maksu-napin piilotus */
body#pat_borraccount a.btn.btn-default.btn-xs.receipt-print-action { display: none; } /* Maksutapahtuman tai maksun poiston kuitti */
```

## Tiedonhaku

### Tasaa otsikko ja tieto perustiedot-näytöllä samalle tasolle

Tarpeellisuus: Suositeltava (selkiyttää näkymää)<br />
Versio: 22.11

```
/* Tasaa otsikko ja tieto perustiedot-näytöllä samalle tasolle */
.label { vertical-align: inherit; }
```


### Fonttikokojen säätö isommaksi koko perustiedot-näytöllä

Tarpeellisuus: Vapaaehtoinen, käytä mielummin selaimen ctrl+ -toimintoa suurentamaan fontteja<br />
Versio: 21.11

```
/* Säädä perustiedot-näytön fonttikokoja isommaksi*/
#catalogue_detail_biblio { font-size:larger; }
```

### Otsikkorivin fonttikoko suuremmaksi

Tarpeellisuus: Ei tarpeen enää versiossa 22.11<br />
Versio: 21.11

```
/* Otsikkorivin (nimeke ja tekijä) fonttikoko suuremmaksi */
#catalogue_detail_biblio h1 { font-size: 16pt; }
```

### Seuraava- ja Edellinen -linkit pienemmiksi

Versio: 17.05, ei tarpeellinen versiossa 21.11, koska linkit muuttuneet nuoliksi

```
/* Seuraava- ja edellinen-linkit pienemmiksi, jotta ne mahtuvat niille sallittuun tilaan */
body#catalog_detail div.browse-prev-next { font-size:8.5pt; background-color:#ffffff; }
body#catalog_MARCdetail div.browse-prev-next { font-size:8.5pt; background-color:#ffffff;}
body#catlaog_labeledMARCdetail div.browse-prev-next { font-size:8.5pt; background-color:#ffffff;}
body#catalog_moredetail div.browse-prev-next { font-size:8.5pt; background-color:#ffffff;}
```


### Piilota kentät 336-338

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 22.11

```
/* Piilota perustiedot-näytöltä kentät 336-338 */
body#catalog_detail #content_type.results_summary { display: none; }
```

### Esityskokoonpanon järjestys näytöllä

Versio: 17.05

```
/* Esityskokoonpanon järjestys näytöllä */
.performance-medium span[class^="sf-"] + span[class^="sf-"]:before {
  content: ", ";
}
```

### Otsikot boldattuna mustalla

Tarpeellisuus: Suositeltava<br />
Versio: 22.11

```
/* Rivien otsikot boldilla perustiedot-näytöllä */
.results_summary .label { color: #333; font-weight: bold }
body#catalog_detail.catalog h5.author { font-weight: bold }
```

### Auktoriteettien MARC-näkymän säätöä

Versio: 17.05

```
/* Auktoriteettien MARC */
#authoritiestabs div.tag p { font-weight: normal; display: inline; font-family: monospace; }
#authoritiestabs div.tag .labelsubfield,
#authoritiestabs div.tag .labelsubfield b { font-weight: normal; font-family: sans-serif; }
#authoritiestabs div.tag .labelsubfield span { display:none; }
#authoritiestabs div.tag p .labelsubfield:hover span,
#authoritiestabs div.tag p:hover .labelsubfield span {  display: inline; float:right; border: 1px solid black; background-color:#f0f0f0; position:relative; top: -1em; right: 0; padding:1em; }
```

### Muokka hakutulos-näytön värejä

Versio: 17.05

```
/* Muokkaa hakutulos-näytön värejä */
.results_summary { color: #000111 !important; }
.results_summary span { color: #000000; font-weight: normal !important; }
.results_summary .label { color: #000000 !important; }
```

### Piilota Näytä kausijulkaisun tiedot -linkki

Versio: 17.05

```
span.results_summary.analytics { display: none; }
```

### Piilota perustiedot-näytöltä Osakohteet ja Näytä osakohteet -kohta kuvailutietojen osiosta

Versio: 22.11<br />
Tarpeellisuus: Vapaaehtoinen

```
/* Piilota perustiedot-näytöltä Osakohteet ja Näytä osakohteet -kohta kuvailutietojen osiosta. */
body#catalog_detail span.results_summary.analytics.analytic_monograph { display: none; }
body#catalog_detail span.results_summary.analytics.analytic_undefined { display: none; }
```

### Piilota Huomautus toimenpiteistä

Piilota perustiedot-näytöltä huomautus toimenpiteestä eli MARC-kentän 583-tieto.

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 22.11

```
/* Piilota Toimenpide-huomautus 583-kenttä perustiedot-näytöltä */
span.results_summary.actionnote { display: none; }
```

### Piilota tuplakansikuvat

Joskus luettelointitiedoissa on syystä tai toisesta useampi kansikuvalinkki. Jos haluaa, että näkyvillä on vain yksi kansikuva, saa muut piiloon seuraavalla rimpsulla.

Versio: 17.05

```
/* Piilota tuplakansikuvat */
.cover_image_container ~ .cover_image_container {
   display:none;
}
```


### Säädä kansikuvan kokoa

Alla on kolme versiota, joilla voi säätää kansikuvien kokoa. Ensimmäinen versio vaikuttaa sekä hakutuloslista-sivulle että perustiedot-sivulle. Toinen vaikuttaa vain hakutulostilsta-sivulle ja kolmas perustiedot-näytölle. 

Tarpeellisuus: Suositeltava<br />
Versio 22.11

Hakutuloslistalle ja perustiedot-näytölle:
```
/* Säädä hakutuloslistan ja perustiedot-näytön kansikuva tietyn kokoiseksi. Muuta pikselikoko tarvittaessa toiseksi. */
.bookcoverimg {
  width: 150px;
}
```

Vain hakutuloslistalle:
```
/* Säädä hakutuloslistan kansikuva tietyn kokoiseksi. Muuta pikselikoko tarvittaessa toiseksi. */
body#catalog_results.catalog .bookcoverimg {
  width: 150px;
}
```

Vain perustiedot-näytölle:
```
/* Säädä perustiedotnäytön kansikuva tietyn kokoiseksi. Muuta pikselikoko tarvittaessa toiseksi. */
body#catalog_detail.catalog .bookcoverimg {
  width: 270px;
}
```

### Piilota tarkassa haussa Lisärajaukset-osio

Tarpeellisuus: Vapaaehtoinen (huom. jos tämän piilottaa, menee piiloon osa indeksointityöryhmän päättämistä hakurajausvaihtoehdoista)<br />
Versio: 22.11

```
/* Tarkan haun Lisärajuslaatikon piilotus */ /* Toimii 17.2.2023 MLI */ /* Jos tämän laittaa päälle, menettää valikoihin lisätyt hakuehdot */
#catalog_advsearch #subtype { display:none; }
```

#### Piilota nidehaussa Inventaarionumero-sarake

Tarpeellisuus: Vapaaehtoinen<br />
Versio 22.11

```
/* Piilota inventaarionumero-sarake nidehaun tuloksissa */
body#catalog_itemsearch.catalog td:nth-child(13) { display: none; }
body#catalog_itemsearch.catalog th#item_inventoryno { display: none; }
```

#### Lisätty Piilota Nidetyyppi-sarake korissa

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 22.11, 23.11

```
/* Piilota Nidetyyppi-sarake korissa */
#cart_basket th:nth-child(3),
#cart_basket td:nth-child(3) { display: none; }
```


---

## Varaukset

### Lisää varauksenteko-sivulle huomautus valita noutokirjasto niteen kohdalta, jos tehdään nidevaraus

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 22.11

```
/* Lisää varauksenteko-sivulle huomautus valita noutokirjasto niteen kohdalta, jos tehdään nidevaraus. */
body#circ_request.catalog div.top.pager:after {
  content: "Valitse noutokirjasto niteen kohdalta, jos teet nidevarauksen.";
  color:red;
}
```

### Piilota varauksen teko -sivulta asiakkaiden selaaminen sukunimen mukaan

Tarpeellisuus: Suositeltava<br />
Versio: 22.11

```
/* Piilota varauksen teko -sivulta asiakkaiden selaaminen sukunimen mukaan */
body#circ_request.catalog div.browse { display: none; }
```
### Piilota Näytä aina varaukset -täppä varauksen teko -sivulla

Tarpeellisuus: Suositeltava<br />
Versio: 22.11

```
/* Piilota "Näytä aina varaukset" -täppä varauksenteko-sivulla, koska se ei toimi Koha-Suomi-muutosten vuoksi. */
body#circ_request.catalog label[for="always_show_holds"] { display:none; }
body#circ_request.catalog input#always_show_holds { display:none; }
```

### Säädä, kuinka leveä näytön pitää olla, jotta taulukoista piilotetaan sivulta toiselle siirtyminen

Tarpeellisuus: Suositeltava<br />
Versio: 22.11

```
/* Säädetään sitä, kuinka leveä näytön pitää olla, että taulukoista piilotetaan siirtyminen sivulta toiselle sivunumeroiden perusteella esim. varaustenteko-sivulla. Eli piilotetaan numerolinkit. */
@media only screen and (min-width: 1000px) {
    .dataTables_wrapper
        .dataTables_paginate
            span
                .paginate_button,
    .dataTables_wrapper
        .dataTables_paginate
            span
                .ellipsis {
                    display: inline-block;
                }
}
```

### Varauksen keskeytyksen korostus punaiseksi

Kun varaus on keskeytetty, muuttuu tällä säädöllä teksti keskeytetty-teksti punaiseksi ja keskeytys on helpompi havaita.

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 22.11

```
/* Varausten keskeytyksen korostus punaikseksi tietueen varaukset-sivulla */ 
#circ_request.catalog button[data-suspended="true"] + label { color:red; font-weight:bold !important;}
```

### Piilota monivarauksen teossa ensimmäinen sarake eli valintatäpät

Monivarauksen teossa valintaruudut eivät vaikuta siihen, tehdäänkö varaus teokseen vai ei, joten ne päätettiin piilottaa. Liittyy [tikettiin #780](https://github.com/KohaSuomi/Koha/issues/780).

Tarpeellisuus: Suositeltava<br />
Versio: 22.11

```
/* Piilota valintaruudut (1. sarake) monivarauksessa (request.pl) */
#requesttitles th:first-child,
#requesttitles td:first-child { display: none; }
```

---

## Kausijulkaisut

### Tasaa kausijulkaisujen vastaanotossa nidetiedot keskemmälle ruutua

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 22.11

```
/* Tasaa kausijulkaisujen vastaanotossa nidetiedot keskemmälle ruutua. */
body#ser_serials-edit.ser fieldset.rows ol li {display:block;}
body#ser_serials-edit.ser fieldset.rows ol li label {float: left; font-weight: 700; margin-right: 1rem; text-align: right;}
```

---

## Muita

### Muuta kaikissa taulukoissa rivin taustaväri, kun hiiri viedään rivin kohdalle

Tarpeellisuus: Suositeltava<br />
Versio: 22.11

```
/* Muuta kaikissa taulukoissa rivin taustaväri, kun hiiri viedään rivin kohdalle. */
tr:hover td { background-color:#f8fcf6 !important; }
```

### Korjataan päivämääräkentän leveys sopivaksi

Tarpeellisuus: Suositeltava. Ei todennäköisesti tarvita enää seuraavassa versiossa.<br />
Versio: 22.11

```
/* Korjataan päivämääräkenttien leveys sopivaksi. Tiketit 111 ja 119 */
.flatpickr-input {width: auto}
```

### Koha-logon piilotus virkailijaliittymän vasemmasta reunasta

Versio: 21.11

```
/* Piilota Kohan logo vasemmasta reunasta */
#container-main {
    /* Contains the news + both columns of links + pending box + userblock box */
    background-image:none;
}
```

### OpenDocument-vaihtoehdon piilotus raporteista

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 22.11

```
/* OpenDocumentin piilotus raporteista */ /* Toimii 16.5.2022 MLI */
body#rep_guided_reports_start.rep button#format + ul li:nth-child(3){display: none;}
```

### Kimpan logo näkyviin yläpalkkiin

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 22.11

```
/* Kimpan logo näkyviin yläreunaan */
/* Vaihda kuvan osoite oikeaksi, logojen osoitteet löytyvät osoitteesta https://github.com/KohaSuomi/Koha-22x/commit/c55dbc5f6b4a721361bc42529e6aa7865d31cee6 Voit myös säätää kuvan kokoa tarvittaessa. */
/* Yläkulman logon pienennys sopimaan yläpalkin tilaan. Toimii 6.3.2023 MLI */
#logo.navbar-brand:after {
  background-image: url(/koha-suomi-images/vaski-images/vaski-logo-transparent-white.png);
  background-size: 103px 30px;  
  display: block;
  width: 103px; 
  height: 30px;
  content:"";
}

/* Yläkulman Koha-logon piilotus */
.navbar-brand > img {
    display:none;
}
```

### Musta yläpalkki leveämmäksi

Tällä saa säädettyä mustan yläpalkin leveämmäksi, mutta huomioi, että se vaikuttaa myös alareunan palkin leveyteen samalla.

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 22.11

```
/* Musta yläpalkki leveämmäksi - tarvittaessa vain */
.navbar {
  height: 45px;
}
```
---

### Testiympäristön ulkoasun muutokset

Versio: 21.11

```
.gradient {
background-image: -webkit-gradient( linear, left top, left bottom, color-stop(0.1, rgb(255, 241, 186)), color-stop(0.99, rgb(255,255,255)) );
}

#header.navbar-default {
background: rgb(255, 241, 186);
}

#breadcrumbs {
background-color: #e3f2c8;
}

#searchheader {
background-color: #e3f2c8;
}

.navbar .nav > li > a {
color: #405b0e;
}

#menu ul > li > a {
background: linear-gradient(180deg,#e3f2c8 0,#e3f2c8 96%,#c1c1c1);
}

.ui-tabs .ui-tabs-nav li {
background: #e3f2c8 none;
}

fieldset {
  background-color: #fafde9;
}

ul.biglinks-list li a.icon_general {
border: solid 2px #b8ce97;
background-color: #fafbf4;
}

body {
background-color: #fff2dd;
}
```
