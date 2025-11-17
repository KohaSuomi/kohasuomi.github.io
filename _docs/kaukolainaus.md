---
title: 'Kaukolaina-moduulin käyttöönotto'
permalink: /dokumentaatio/kaukolainaus/
redirect_from:
  - /theme-setup/
toc: true
---

## Koha-config

Koha-config-tiedostoon (koha-conf.xml) pitää kehittäjien lisätä 'branch' blokkiin kirjastokoodi. 

Tarviiko lisätä kaikki ne kirjastot, jotka tulee käyttämään moduulia?

## Järjestelmäasetukset

Mene Ylläpito ->  Järjestelmäasetukset -> Kaukolainat

Asetuksen nimi|Valinta|Selite
---|---|---
ILLDefaultStaffEmail |Jätä tyhjäksi|Ei tarpeen
ILLSendStaffNotices |Jätä tyhjäksi|
CirclulateILL|Älä salli|Tämä sallii lainaamisen suoraan kaukolainapyynnön kautta ilman että mennään asiakkaan tietoihin ja manuaalisesti luetaan niteen viivakoodi. Tämä luo automaattisesti niteen ja sille viivakoodin. Tämä lisää kaukolainanpyynnön tietoihin näkyville Lainaus-napin, jolloin sen voi lainata ilman varsinaista lainaus-sivulla käymistä. 
ILLHiddenRequestStatuses |CANCELLED, EXPIRED| Kaukolainastatukset, joita pidetään valmiina, ja joita ei tulisi näyttää kaukolainamoduulissa: (erotetaan putki-merkillä). Jos jätetään tyhjäksi, kaikki kaukolainapyynnöt näytetään. Pyyntökoodit määritetään taustajärjestelmässä ja lisäaliaksia voi määrittää auktorisoidun arvon luokkaan ILL_STATUS_ALIAS.
ILLModule |Käytä|Tämä on ns. pääkytkin, jolla Kaukolaina-toiminto kytketään päälle ja pois päältä.
ILLModuleUnmediated |Älä salli|Vaatii toimiakseen Kohan oma verkkokirjaston (opac)
ILLPartnerCode|Kaukolainakirjasto-asiakastyyppi|Tämä tuo kaukolainapyynnön lähetykseen näkyville Kaukolainakirjasto-tyyppiset asiakastiedot, joilla on tiedoissaan sähköpostiosoite tallennettuna
ILLRequestsTabs | <img width="511" height="243" alt="kuva" src="https://github.com/user-attachments/assets/be6f5c99-3ecb-49ac-8a57-4acf5d532d3a" />|Asetuksella voi lisätä välilehtiä, joissa tietyn tilaiset pyynnöt näkyvät. Taulukon alapuolella esimerkkimääritys erillisen otsikon alla.
ILLDefaultStaffEmail | Jätä tyhjäksi | Tähän voi määrittää, mihin sähköpostiosoitteeseen lähetetään viestit, jos kirjastolle ei ole merkitty kaukolaina-osoitetta
ILLSendStaffNotices |Jätä tyhjäksi|Tähän voi määrittää, mitkä kaukolainojen tiloihin liittyvät viestit lähetetään henkilökunnalle sähköpostina. Voi myös halutessaan määrittää viestit, mutta ei ole pakko.
AutoILLBackendPriority | Ei anna valita mitään, koska ei ole asennettuna backendejä, joista voi tarkistaa saatavuuden|
ILLCheckAvailability |Älä tarkista|Ei tarpeen, koska meillä ei ole tähän tarvittavia yhteyksiä
ILLHistoryCheck |Älä tarkista|Kimpassa voidaan tarvittaessa laittaa tämä päälle, jos halutaan Kohan antavan ilmoituksen, että asiakkaalla on jo samalla ISBN:llä oleva kaukolainapyyntö. Ei estä tekemästä kuitenkaan uutta pyyntöä. Tarkista/Älä tarkista, onko asiakas tehnyt aiemmin kaukolainapyynnön samaan teokseen. Vertailu tehdään käyttäen seuraavia tunnuksia: DOI, Pubmed ID tai ISBN. Meillä käytännössä toimisi vain ISBN. 
ILLModuleDisclaimerByType|Jätä tyhjäksi|
ILLOpacbackends |Jätä tyhjäksi|Vaatisi toimiakseen Kohan oman verkkokirjaston (opacin)
ILLOpacUnauthenticatedRequest | Älä salli | Vaatisi toimiakseen Kohan oman verkkokirjaston (opacin)

### ILLRequestsTabs

```
- name: Pyydetyt
  status:
    - REQ
    - GENREQ
- name: Valmiit
  status:
    - COMP
```
### IntranetUserCSS 

Piilottaa asiakastiedon automaattisen ehdotuksen kaukolainapyyntöä tehdessä
```
/* ILL PatronAutoComplete -piilotus */ 
#illrequests.ill ul#ui-id-1 li.ui-menu-item { display: none; } 
```

**Poista** alla oleva rimpsu asetuksesta, koska Kaukolainaajat tarvitsevat näkyville Lainaus ja palautus -sivulle Myöhässä-raportin.

```
/* Piilota Myöhässä -raportti Lainaus ja palautus -sivulta 
*/ body#circ_circulation-home.circ a[href*="/cgi-bin/koha/circ/overdue.pl"] { display: none; }" -piilotus
```

### IntranetUserJS

Muuttaa asiakkaan lainat-taulussa Kaukolaina-sanan punaiseksi. Huomioi, että tarvitset tämän lisäämiseen avuksi kehittäjän.

```
// Kaukolaina-nidetyypin tekstin värin muutos asiakkaan lainoissa
$(document).ready(function() {
  $("#issues-table-load-now-button").on("click", function() {
    const observer = new MutationObserver(function(mutationsList) {
      mutationsList.forEach(function(mutation) {
        mutation.addedNodes.forEach(function(node) {
          if (node.nodeType === Node.ELEMENT_NODE) {
            const tdElements = node.querySelectorAll?.("td") || [];
            tdElements.forEach(function(td) {
              if (td.textContent.trim() === "Kaukolaina") {
                td.style.color = "red";
              }
            });
          }
        });
      });
    });

    observer.observe(document.body, {
      childList: true,
      subtree: true
    });

    // Katkaise tarkkailu 5 sekunnin kuluttua
    setTimeout(() => observer.disconnect(), 5000);
  });
});
```


## Kirjastojen tiedot

Lisää niille kirjastoille, jotka käyttävät kaukolainamoduulia _Kaukolainauksen sähköposti_ -kenttään sähköpostiosoite sekä _Huomautukset_-kenttään kaukolainauksen puhelinnumero, jotta tiedot saadaan tulostumaan kuiteille.

## Asiakastyyppien tiedot

Valitse asiakastyyppien ylläpidossa _Voi tehdä kaukolainapyynnön verkkokirjastossa_ -kohtaan "Ei". Tämä toiminnallisuus toimii vain Kohan omassa verkkokirjastossa.

## Auktorisoidut arvot

ILL_STATUS_ALIAS -auktorisoitu arvo. Lisää ainakin nämä arvot, mutta niitä voi tarvittaessa lisätä muitakin, jos käytäntö osoittaa sellaisten olevan tarpeellisia.

Tunnus|Kuvaus
---|---
ARRIVED|Saapunut
NOTIFIED|Noutoilmoitus lähetetty
EXPIRED|Noutamaton kaukolaina
CANCELLED|Asiakas perunut pyynnön
CHECKEDOUT|Lainattu asiakkaalle (Lisätieto, jota ei lisätä kuvaukseen: jos nide lisätään itse ja lainataan Kohan normaalin lainauksen kautta, ei tieto päivity Kaukolainamoduulin puolelle)
CLAIMED|Karhuttu
PATCHECKIN|Asiakas palauttanut


## Nidetyyppi

Lisää uusi nidetyyppi KAUKOLAINA, jota käytetään aina, kun kaukolainatilaukseen liittyvälle tietueelle lisätään nide ja se lainataan. Erillinen nidetyyppi mahdollistaa laina- ja maksusääntöjen tekemisen nidetyypin mukaan.

Tunnus: KAUKOLAINA<br />
Kuvaus: Kaukolaina<br />
Palautusviesti: Lisää tähän jonkinlainen huomautus, että kyseessä on kaukolaina ja tarvitsee erilaista käsittelyä.<br />
Palautusviestin tyyppi: Huomautus (tulee keltaisella pohjalla oleva huomautus palautuksessa, erottuu paremmin kuin viesti)

## Käyttäjäoikeudet

Kaukolaina-moduulin käyttäjä tarvitsee seuraavat käyttäjäoikeudet:

Käyttäjäoikeus|Tarvekuvaus
---|---
ill | jotta käyttäjä pääsee kaukopalvelumoduuliin
fast_cataloging  | jotta käyttäjä pystyy käsittelemään kaukolainamoduulin kautta luotuja tietueita/niteitä, joilla on FA-kuvailupohja käytössä
override_renewals | jotta käyttäjä pystyy tarvittaessa ohittamaan nidetyypille asetetun uusintojen määrän 0 (ks. laina- ja maksusäännöt)
overdues_report | jotta käyttäjä voi avata Myöhässä-raportin Lainaus ja palautus -sivulla (ks. myöhässä olevien seuranta)

## Laina- ja maksusäännöt

Iso taulukko
* Asiakastyyppi: Tee vähintään sääntö, joka koskee kaikkia asiakastyyppejä. Jos jollekin asiakastyypille on yksikin oma sääntö kaikkia kirjastoja koskevissa säännöissä, pitää kaukolaina-nidetyypille tehdä myös erikseen sääntö kyseiselle asiakastyypille.
* Nidetyyppi: Kaukolaina
* Sallittu lainamäärä: kimpan käyttösääntöjen mukaisesti
* Laina-aika: 28 vrk / kimpan käyttösääntöjen mukaisesti. Tähän kannattanee määrittää jotain, koska muuten Koha automaattisesti antaa eräpäiväksi lainauspäivän. Pääsääntöisesti virkailija valitsee itse lainaustilanteessa eräpäivän sen mukaan, mitä lähettävä kirjasto on sen määrittänyt.
* Uusintakerrat: 0, jotta asiakkaat eivät pysty uusimaan lainojaan verkkokirjastossa. Annetaan kuitenkin kaukopalvelua tekeville henkilöille käyttäjäoikeus, jolla he voivat ohittaa uusinnan estot.
* Uusinta-aika: 28 vrk / kimpan käytäntöjen mukaan samalla perusteella kuin laina-aika. Uusinnan eräpäivän voi tarvittaessa valita lainat-taulukon alapuolelta.
* Ei uusintaa ennen: kimppakohtaisesti päätettävissä
* Varauksia sallittu (yhteensä): 0
* Varauksia sallittu (päivittäin): 0
* Varauksia tietuetta kohti (määrä): 0
* Hyllyvaraukset sallittu: Jos yhtään ei ole saatavilla
* Verkkokirjaston nidevaraukset: Älä salli

Oletusvaraussääntö nidetyypeittäin
 * tänne voi tarvittaessa lisätä palautussäännön Kaukolaina-nidetyypille, että se palaa lainaavaan (tilaavaan) kirjastoon tai kotikirjastoon, jolloin se käytännössä palautuu kaukolainan tilanneeseen kirjastoon.

Jos jollakin kirjastolla on kirjastokohtaisia lainasääntöjä, pitää nämä muistaa tehdä kaikille kirjastoille, joihin säännöt halutaan "purevan".

Jos asiakastyypille on yksikin oma sääntö kaikkia kirjastoja koskevissa säännöissä, pitää kaukolainasääntö tehdä myös erikseen kyseiselle asiakastyypille.

Jos kimpassa on asiakastyyppejä, joille ei haluta sallia kaukolainojen lainaamista, pitää asiakastyypille tehdä sääntö, jossa lainamäärä on 0. Esim. VIRKAILIJA-asiakastyyppi.

## Viestipohjat ja uudet viestiasetukset

### Viestiasetukset

Uudet viestiasetukset asiakastiedoissa:
* Kaukolainan saapumisilmoitus
* Kaukolaina ei saatavilla
* Kaukolaina on päivitetty

Nämä valitaan asiakaskohtaisesti tarvittaessa.

Jos on tarve estää esim. tekstiviesti-vaihtoehdon valitseminen näille viestipohjille, tehkää siitä tiketti, niin kehittäjät voivat poistaa sms-vaihtoehdon viestityyppi-vaihtoehdoista tietokannan taulusta.

### Viestipohjat suomeksi

#### ILL_REQUEST_UPDATE

Tämä viesti lähtee asiakkaalle, jos/kun kaukolainapyyntöä päivitetään/muutetaan.

Vain email-tyyppinen viesti, ei haluta lähettää tekstiviestinä. Tämä pohja kannattaa kopioida myös suomi.fi-palvelun kohdalle.

Viestin otsikko: Kaukolainapyyntöäsi on päivitetty
Viestityyppi: email ja suomifi

```
Hei [% borrower.firstname %],

kaukolainapyyntöäsi  [% ill_bib_title %] / [% ill_bib_author %] on päivitetty.

Päivitetyt tiedot:

[% additional_text %]

Ystävällisin terveisin

[% branch.branchname %]
[% branch.branchaddress1 %]
[% branch.branchzip %] [% branch.branchcity %]
[% branch.branchphone %]
[% branch.branchillemail %]
[% branch.branchemail %]
```

#### ILL_PICKUP_READY

Tämä on kaukolainan noutoilmoitus, jonka saa lähetettyä kaukolainapyynnön tiedoista.

Otsikko: Kaukolainan noutoilmoitus
Viestityyppi: email ja suomifi

```
Hei [% borrower.firstname %],

Pyytämäsi kaukolaina [% ill_bib_title %] / [% ill_bib_author %] on noudettavissa [% branch.branchname %]sta.

Kaukolainamaksu: [% IF illrequest.price_paid %][% illrequest.price_paid %][% ELSE %]8 €[% END %] 
Eräpäivä: [% IF illrequest.notesstaff %][% illrequest.notesstaff %][% ELSE %]-[% END %]

Terveisin

[% branch.branchname %]
[% branch.branchaddress1 %]
[% branch.branchzip %] [% branch.branchcity %]
[% branch.branchphone %]
[% branch.branchillemail %]
[% branch.branchemail %]
```

Otsikko: Kaukolainan noutoilmoitus
Viestityyppi: sms

```
Pyytämäsi kaukolaina [% ill_bib_title %] / [% ill_bib_author %] on noudettavissa [% branch.branchname %]sta. Kaukolainamaksu: [% IF illrequest.price_paid %][% illrequest.price_paid %][% ELSE %]8 €[% END %]. Eräpäivä: [% IF illrequest.notesstaff %][% illrequest.notesstaff %][% ELSE %]-[% END %]
```

#### ILL_PARTNER_REQ

Tällä voi lähettää kaukolainamoduulista sähköpostiviestin "yhteistyökumppaneille" ja pyytää heiltä asiakkaan pyytämää teosta. Viestiin tulee mukaan teostiedot ill_full_metadata-tägillä, tiedot järjestyvät viestissä otsikon mukaan aakkosiin.

Otsikko: Kaukolainapyyntö
Viestityyppi: email

```
Hei,

pyytäisimme kaukolainaksi seuraavan teoksen:

[% ill_full_metadata %]

Ystävällisin terveisin

[% branch.branchname %]
[% branch.branchaddress1 %]
[% branch.branchzip %] [% branch.branchcity %]
[% branch.branchphone %]
[% branch.branchillemail %]
```

#### ILL_REQUEST_UNAVAIL

Tämän viestin voi lähettää asiakkaalle, jos kaukolainapyyntöä ei voida toimittaa.

Otsikko: Pyytämäsi kaukolaina ei ole saatavilla
Viestityyppi: email ja suomifi
```
Hei [% borrower.firstname %],

pyytämäsi kaukolaina [% ill_bib_title %] / [% ill_bib_author %] ei ole saatavilla.


Terveisin

[% branch.branchname %]
[% branch.branchaddress1 %]
[% branch.branchzip %] [% branch.branchcity %]
[% branch.branchphone %]
[% branch.branchillemail %]
[% branch.branchemail %]
```

Otsikko: Kaukolaina ei saatavilla
Viestityyppi: Sms

```
Hei [% borrower.firstname %],  pyytämäsi kaukolaina [% ill_bib_title %] / [% ill_bib_author %] ei ole saatavilla. Terveisin [% branch.branchname %]
```
#### ILL_SLIP

Tällä voi tulostaa asiakkaan tiedoissa ollessa kaukolainan "infokuitin", johon saadaan automaattisesti tulostumaan asiakkaan varaustunnus. Räätölöidyillä kuiteilla ei ole pääsyä kaukolaina-osion tietoihin, joten niitä tietoja ei saada automaattisesti. Sitä varten tulostettavalle lapulle on lisätty kohdat, joihin kaukolainan käsittelijä voi itse kirjoittaa tarvittavat teos ja lainatiedot. Tätä viestipohjaa varten pitää lisätä kirjastojen ylläpidossa tiedot _Kaukolainauksen sähköposti_ ja _Huomautukset_ -kenttiin (ks. Kirjastojen tiedot).

Uusi ilmoitus -> Asiakkaat (Räätälöity kuitti)

Otsikko: Kaukolainan infokuitti
Viestityyppi: Tulosta
Täppä html-kohtaan

```
<style type="text/css">
  h1 { font-family: arial; font-size: 20pt; }
  h2 { font-family: arial; font-size: 14pt; }
  p { font-family: arial; font-size: 10pt; }
</style>

<h1>Kaukolainan infokuitti</h1>

<br />
<h2>Asiakas: <<borrower-attribute:HOLDID>></h2><br /><br />

<p>
Eräpäivä: _______________________________<br /><br />

Teos: ___________________________________<br /><br />

Tekijä: __________________________________<br /><br />

Kaukolainan hinta: _______________________<br /><br />

Noutopaikka: __________________________<br /><br />

Kaukolainanumero: _____________________<br /><br />

Ilmoitustapa: ___________________________<br /><br />

</p>

<p>Jos haluat uusia kaukolainan, ole yhteydessä omaan kirjastoon.</p>
<p>Yhteystiedot: <<branches.branchname>>, <<branches.branchillemail>>, <<branches.branchnotes>></p>
```

### Viestipohjat ruotsiksi

#### ILL_REQUEST_UPDATE


Otsikko: Din fjärrlånebeställning har uppdaterats
Viestityyppi: email och suomifi
```
Hej [% borrower.firstname %]!  

Din fjärrlånebeställning gällande [% ill_bib_title %] / [% ill_bib_author %] har uppdaterats.  

De nya uppgifterna:  
[% additional_text %]

Med vänlig hälsning,
[% branch.branchname %]
[% branch.branchaddress1 %]
[% branch.branchzip %] [% branch.branchcity %]
[% branch.branchphone %]
[% branch.branchillemail %]
[% branch.branchemail %]
```

#### ILL_PICKUP_READY

Otsikko: Fjärrlån finns att hämta
Viestityyppi: email och suomifi
```
Hej [% borrower.firstname %]!  

Det fjärrlån du har beställt, [% ill_bib_title %] / [% ill_bib_author %], finns nu att hämta på [% branch.branchname %].  

Avgift för fjärrlånet: [% IF illrequest.price_paid %][% illrequest.price_paid %][% ELSE %]8 €[% END %] 
Förfallodag: [% IF illrequest.notesstaff %][% illrequest.notesstaff %][% ELSE %]-[% END %]

Med vänlig hälsning,
[% branch.branchname %]
[% branch.branchaddress1 %]
[% branch.branchzip %] [% branch.branchcity %]
[% branch.branchphone %]
[% branch.branchillemail %]
[% branch.branchemail %]
```


Otsikko: Fjärrlån finns att hämta
Viestityyppi: sms
```
Det fjärrlån du har beställt, [% ill_bib_title %] / [% ill_bib_author %], finns nu att hämta på [% branch.branchname %]. Avgift: [% IF illrequest.price_paid %][% illrequest.price_paid %][% ELSE %]8 €[% END %].Förfallodag: [% IF illrequest.notesstaff %][% illrequest.notesstaff %][% ELSE %]-[% END %]. Mvh [% branch.branchname %]
```

#### ILL_PARTNER_REQ

Otsikko: Beställning av fjärrlån
Viestityyppi: email

```
Hej!

Vi skulle vilja beställa följande verk som fjärrlån:
[% ill_full_metadata %]

Med vänlig hälsning,
[% branch.branchname %]
[% branch.branchaddress1 %]
[% branch.branchzip %] [% branch.branchcity %]
[% branch.branchphone %]
[% branch.branchillemail %]
```

#### ILL_REQUEST_UNAVAIL

Otsikko: Det fjärrlån du har beställt finns inte tillgängligt
Viestityyppi: email och suomifi

```
Hej [% borrower.firstname %]!  

[% ill_bib_title %] / [% ill_bib_author %], som du hade beställt, finns tyvärr inte tillgängligt för fjärrlån. 

Med vänlig hälsning,

[% branch.branchname %]
[% branch.branchaddress1 %]
[% branch.branchzip %] [% branch.branchcity %]
[% branch.branchphone %]
[% branch.branchillemail %]
[% branch.branchemail %]
```

Otsikko: Det fjärrlån du har beställt finns inte tillgängligt
Viestityyppi: sms

```Hej [% borrower.firstname %]. [% ill_bib_title %] / [% ill_bib_author %], som du hade beställt, finns tyvärr inte tillgängligt för fjärrlån. Mvh [% branch.branchname %]```

#### ILL_SLIP

Uusi ilmoitus -> Asiakkaat (Räätälöity kuitti)

Otsikko: Kvitto på fjärrlån
Viestityyppi: Tulosta
Täppä html-kohtaan

```
<style type="text/css">
  h1 { font-family: arial; font-size: 20pt; }
  h2 { font-family: arial; font-size: 14pt; }
  p { font-family: arial; font-size: 10pt; }
</style>

<h1>Kvitto på fjärrlån</h1>

<br />
<h2>Låntagare: <<borrower-attribute:HOLDID>></h2><br /><br />

<p>
Förfallodag: _______________________________<br /><br />

Titel: ___________________________________<br /><br />

Författare: __________________________________<br /><br />

Fjärrlåneavgift: _______________________<br /><br />

Avhämtningsbibliotek: __________________________<br /><br />

Fjärrlånenummer: _____________________<br /><br />

Meddelande via: ___________________________<br /><br />

</p>

<p>Om du vill förnya fjärrlånet, ta kontakt med ditt eget bibliotek.</p>
<p>Kontaktuppgifter: <<branches.branchname>>, <<branches.branchillemail>>, <<branches.branchnotes>></p>
```
### Viestipohjat englanniksi

#### ILL_REQUEST_UPDATE 

Viestin otsikko: Your interlibrary loan request has been updated 
Viestityyppi: email ja suomifi

```
Hello [% borrower.firstname %], 

Your interlibrary loan [% ill_bib_title %] / [% ill_bib_author %] has been updated.  
 
Updated information: [% additional_text %] 

Best regards,  
[% branch.branchname %] 

[% branch.branchaddress1 %] 

[% branch.branchzip %] [% branch.branchcity %] 

[% branch.branchphone %] 

[% branch.branchillemail %] 

[% branch.branchemail %]
```

#### ILL_PICKUP_READY
Otsikko: Your interlibrary loan is ready for pick up 
Viestityypppi: email ja suomifi

```
Hello [% borrower.firstname %],
Your interlibrary loan [% ill_bib_title %] / [% ill_bib_author %] is ready for pick-up at [% branch.branchname %]. 

Interlibrary loan fee: [% IF illrequest.price_paid %][% illrequest.price_paid %][% ELSE %]8 €[% END %] 
Due date: [% IF illrequest.notesstaff %][% illrequest.notesstaff %][% ELSE %]-[% END %]

Best regards, 
[% branch.branchname %]
[% branch.branchaddress1 %]
[% branch.branchzip %] [% branch.branchcity %]
[% branch.branchphone %]
[% branch.branchillemail %]
[% branch.branchemail %]
```

#### ILL_PICKUP_READY
Otsikko: Interlibrary loan ready for pick up 
Viestityyppi: SMS

```
Your interlibrary loan [% ill_bib_title %] / [% ill_bib_author %] is ready for pick-up at [% branch.branchname %]. Interlibrary loan fee: [% IF illrequest.price_paid %][% illrequest.price_paid %][% ELSE %]8 €[% END %]. Due date: [% IF illrequest.notesstaff %][% illrequest.notesstaff %][% ELSE %]-[% END %]. Best regards, [% branch.branchname %]
```

#### ILL_PARTNER_REQ
Otsikko: Request for interlibrary loan
Viestityyppi: email

```
Hello,
We would like to request the following item from your collection as an interlibrary loan: 
[% ill_full_metadata %]
 
Best regards,
[% branch.branchname %]
[% branch.branchaddress1 %]
[% branch.branchzip %] [% branch.branchcity %]
[% branch.branchphone %]
[% branch.branchillemail %]
```

#### ILL_REQUEST_UNAVAIL
Viestin otsikko: The interlibrary loan you requested is not available
Viestityyppi: email ja suomifi

```
Hello [% borrower.firstname %],
The interlibrary loan you requested, [% ill_bib_title %] / [% ill_bib_author %] is not available. Your interlibrary loan request has been cancelled. 

Best regards, 
[% branch.branchname %]
[% branch.branchaddress1 %]
[% branch.branchzip %] [% branch.branchcity %]
[% branch.branchphone %]
[% branch.branchillemail %]
[% branch.branchemail %]
```

#### ILL_REQUEST_UNAVAIL
Otsikko: Your interlibrary loan request has been cancelled
Viestityyppi: SMS

```
Your interlibrary loan request has been cancelled since the title [% ill_bib_title %] / [% ill_bib_author %] is not available. Best regards, [% branch.branchname %]
```

#### ILL_SLIP

Uusi ilmoitus -> Asiakkaat (Räätälöity kuitti)
Otsikko: Interlibrary loan slip
Viestityyppi: Print
Täppä html-kohtaan

```
<style type="text/css">
  h1 { font-family: arial; font-size: 20pt; }
  h2 { font-family: arial; font-size: 14pt; }
  p { font-family: arial; font-size: 10pt; }
</style>
 
<h1>Interlibrary loan slip</h1>
 
<br />
<h2>Library member: <<borrower-attribute:HOLDID>></h2><br /><br />
 
<p>
Due date: _______________________________<br /><br />
 
Title: ___________________________________<br /><br />
 
Author: __________________________________<br /><br />
 
Interlibrary loan fee: _______________________<br /><br />
 
Pick-up library: __________________________<br /><br />
 
Order number: _____________________<br /><br />
 
Notification via: ___________________________<br /><br />
 
</p>
 
<p>If you want to renew your interlibrary loan, please contact your library.</p>
<p>Contact information: <<branches.branchname>>, <<branches.branchillemail>>, <<branches.branchnotes>></p>
```

## FA-kuvailupohja

Jos kaukolainapyynnöstä muodostuu Kohaan uusi tietue, käytetään siinä automaattisesti FA-nimistä eli Fast Add -kuvailupohjaa. Tätä varten luotiin "redusoidun" ACQ-kuvailupohjan pohjalta FA-pohja, johon asetettiin 942$n-kenttään oletusarvoksi 1, jolloin tietue piilottuu verkkokirjastosta hauista, mutta näkyy asiakkaan lainoissa.

Alla on FA-kuvailupohja, jonka voi viedä oman kimpan kuvailupohjiin vientitoiminnolla:

[export_FA.ods](https://github.com/user-attachments/files/22679865/export_FA.ods)

## Raportit

* myöhässä olevia kaukolainoja voi seurata Overdues-raportilla (vaatii overdues_report-oikeuden)
* luodaan raportteja sitä mukaa, kun toiminto on otettu käyttöön ja huomataan uusia tarpeita raporteille.

## Kuinka asiakkaat tekevät kaukolainapyyntöjä

Finnaan tehdään uudet lomakkeet kaukolainapyynnölle ja uusimislomakkeelle. Lisäksi pitää tehdä kielikäännöksiä.

### Lomakkeet

Alla olevat koodit viedään oman tuotannossa olevan näkymän tiedostoon local/config/vufind/FeedbackForms.yaml ja muokataan oman kimpan tietojen mukaisiksi.

HUOM! Lataa ensisijaisesti alla oleva txt-tiedosto, koska silloin koodin asettelu pysyy paremmin kasassa. Jos lomake ei tule näkyville siitä huolimatta, tarkista, että Finnan yaml-tiedostossa on sisennykset oikein.

HUOM2! Esimerkeissä on pyydetty asiakkaan kirjastokortin numeroa, mutta Koha-Suomi ei suosittele kirjastokortin numeron lähettämistä salaamattomana sähköpostina.

[Koodit_Finnaan_Kaukolainalomakkeet.txt](https://github.com/user-attachments/files/23226521/Koodit_Finnaan_Kaukolainalomakkeet.txt)


```
#Kaukolainapyyntölomake
    InterlibraryloanRequest:
        title: Interlibrary loan request form
        enabled: true
        onlyForLoggedUsers: true
        emailSubject: Kaukolainapyyntö asiakkaalta kirjastolle (%%Kirjasto%%)
        response: Thank you for your request
        hideSenderInfo: true
        help: 
            pre: feedback_help_interlibraryloan
            post: feedback_help_postinterlibraryloan
        fields:
          - name: Kirjasto
            type: select
            label: feedback_choose_library
            required: true
            recipient: true
            options:
              -
              - value: sähköposti@osoite.fi
                label: 4/Helle/ASK/
              - value: sähköposti@osoite.fi
                label: 4/Helle/HAN/
              - value: sähköposti@osoite.fi
                label: 4/Helle/PRV/
          - name: Julkaisun_nimi
            type: text
            label: helle/forms/title
            required: true
          - name: Tekijä(t)
            type: text
            label: helle/forms/author
            required: true
          - name: Artikkeli
            type: text
            label: helle/forms/article
            required: false
          - name: Nro/Vuosi
            type: text
            label: helle/forms/num
            required: false
          - name: Vuosikerta/Sivut
            type: text
            label: helle/forms/vol
            required: false
          - name: format
            type: select
            options:
              - 0/Book/
              - 1/Journal/Journal/
              - 1/Journal/Article/
              - 1/Video/BluRay/
              - 1/Sound/CD/
              - 1/Video/DVD/
              - 1/Other/Microfilm/
              - 1/Other/Other/
              - 0/MusicalScore/
              - 1/Journal/Newspaper/
              - 1/Video/VideoCassette/
              - 1/Game/VideoGame/
              - 1/Sound/SoundCassette/
              - 1/Sound/SoundDisc/
            label: Format
            required: true
          - name: Kieli
            type: text
            label: helle/forms/language
            required: false
          - name: ISBN/ISSN
            type: text
            label: helle/forms/isbn
            required: false
          - name: Saa_tilata_ulkomailta
            type: select
            options:
              -
              - helle/forms/orderabroadno
              - helle/forms/orderabroadyes
            required: false
            label: helle/forms/orderabroad
          - name: Tarvitaan_viimeistään/Muita_huomioita
            type: textarea
            label: helle/forms/needed
            required: false
          - name: Noutopaikka
            type: select
            options:
                -
                - 3/Helle/ASK/PK/
                - 3/Helle/RAS/BR/
                - 3/Helle/INK/DK/
                - 3/Helle/PRV/GK/
                - 3/Helle/HAN/PK/
                - 3/Helle/INK/PK/
                - 3/Helle/RAS/KA/
                - 3/Helle/PRV/KR/
                - 3/Helle/PRV/KV/
                - 3/Helle/LOV/BU/
                - 3/Helle/PRV/BU/
                - 3/Helle/RAS/BU/
                - 3/Helle/LAP/PK/
                - 3/Helle/HAN/LK/
                - 3/Helle/LOV/LK/
                - 3/Helle/LOV/PK/
                - 3/Helle/RAS/SV/
                - 3/Helle/MYR/PK/
                - 3/Helle/LOV/PE/
                - 3/Helle/RAS/PO/
                - 3/Helle/LAP/PO/
                - 3/Helle/PNK/PK/
                - 3/Helle/PRV/PK/
                - 3/Helle/PUK/PK/
                - 3/Helle/SIP/PK/
                - 3/Helle/SIU/PK/
                - 3/Helle/SIP/SK/
                - 3/Helle/RAS/EK/
                - 3/Helle/RAS/TE/
                - 3/Helle/LOV/TK/
            label: helle/forms/pickuplocation
            required: true
          - name: name
            type: text
            required: true
            label: helle/forms/name
          - name: username
            type: text
            required: true
            label: helle/forms/card
          - name: tel
            type: text
            required: false
            label: helle/forms/tel
          - name: email
            type: email
            label: helle/forms/email
          - name: contact
            type: select
            options:
              -
              - helle/forms/contact_bymail
              - helle/forms/contact_byphone
            label: helle/forms/pickup
            required: true
          - name: accept2
            type: checkbox
            options:
              - helle/forms/accept2
            required: true
```
```
 #Kaukolainan uusimispyyntölomake
    InterlibraryloanRenewRequest:
        title: Interlibrary loan renewal form
        enabled: true
        onlyForLoggedUsers: true
        emailSubject: Kaukolainan uusimispyyntö (%%Kirjasto%%)
        response: Thank you for your request
        hideSenderInfo: true
        help: 
            pre: feedback_help_interlibraryloan_renew
            post: feedback_help_postinterlibraryloan
        fields:
          - name: Kirjasto
            type: select
            label: feedback_choose_library
            required: true
            recipient: true
            options:
              - value: sähköposti@osoite.fi
                label: Kunnan pääkirjasto
              - value: sähköposti@osoite.fi
                label: Kunnan kirjasto
              - value: sähköposti@osoite.fi
                label: Kunnan pääkirjasto
          - name: Julkaisun_nimi
            type: text
            label: helle/forms/title
            required: true
          - name: Tekijä(t)
            type: text
            label: helle/forms/author
            required: true
          - name: ISBN/ISSN
            type: text
            label: helle/forms/isbn
            required: false
          - name: name
            type: text
            required: true
            label: helle/forms/name
          - name: username
            type: text
            required: true
            label: helle/forms/card
          - name: tel
            type: text
            required: false
            label: helle/forms/tel
          - name: email
            type: email
            label: helle/forms/email
          - name: contact
            type: select
            options:
              - 
              - helle/forms/contact_byphone
              - helle/forms/contact_bymail
            label: helle/forms/interlibrary_renewal
            required: true
          - name: accept
            type: checkbox
            options: 
              - helle/forms/accept2
            required: true
```

### Kielikäännökset

Finnan kielikäännöksiin viedään kaikki nämä ja tehdään niille halutut käännökset, tässä meidän (käännökset tarkistettu täällä Hellessä):

Interlibrary loan request form - Lomakkeen nimi

    EN: Interlibrary loan request form
    FI: Kaukolainapyyntölomake
    SV: Blankett för beställning av fjärrlån

Interlibrary loan renewal form - Lomakkeen nimi

    EN: Interlibrary loan renewal form
    FI: Kaukolainan uusimispyyntölomake
    SV: Blankett för förnyande av fjärrlån

Thank you for your request - Käännöksiin laitetaan viesti, jonka asiakas näkee, kun pyyntö on lähetetty. Huomioikaa, että jos teillä on jo samalla koodilla tehty kielikäännös, täytyy käyttää toista lausetta tässä koodina. Tämä viesti tulee näkyviin sekä pyyntö- että uusimislomakkeen lähettämisen jälkeen. Ruotsikäännös on hieman erilainen, koska sanavalintaa piti miettiä, kun kyseessä molemmat lomakkeet.

    EN: Thank you for your request. It will be processed as soon as possible.
    FI: Kiitos pyynnöstäsi. Se käsitellään mahdollisimman pian.
    SV: Tack för att du tog kontakt. Ditt ärende kommer att behandlas så snart som möjligt.

feedback_help_interlibraryloan - Haluttu selitysteksti kaukolainapyyntölomakkeeseen asiakkaalle ennen lomaketta.

    EN: With this form, you can send an interlibrary loan request to your local library. Before submitting your request, check Helle-Finna to see if the item is already available. You can only request items that are not available at Helle libraries.<br/><br/>Please fill in the required fields so that your request can be processed. <br/><br/>Please note! Interlibrary loans are subject to a fee. The fee is usually either €6 or €12, depending on which library the interlibrary loan comes from.<br/><br/>Item ordered through interlibrary loan usually arrives within two weeks, unless it is on loan or there are holds on it at the sending library. If the item is on hold for other customers, the delivery may take several weeks or even months.
    FI: Tällä lomakkeella voit lähettää kaukolainapyynnön omaan kirjastoosi. Ennen kuin teet pyynnön, tarkista Helle-Finnasta, onko teos jo jossakin kirjastossa. Kaukolainaksi voi tilata sellaista aineistoa, jota ei löydy Helle-kirjastoista.<br/><br/>Täytä pakolliset kentät, jotta pyyntösi tulee perille. <br/><br/>Huom! Kaukolainat ovat maksullisia. Maksu on yleensä joko 6 tai 12 euroa riippuen siitä, mistä kirjastosta kaukolaina tulee.<br/><br/>Kaukolainaksi tilattu aineisto saapuu yleensä kahden viikon sisällä, paitsi jos aineisto on lähettävässä kirjastossa lainassa tai siihen on varauksia. Jos kaukolainapyyntö joutuu varausjonoon, aineiston saapuminen voi kestää useita viikkoja tai jopa kuukausia.
    SV: Använd blanketten nedan för att skicka en fjärrlåneförfrågan till ditt lokala bibliotek. Innan du gör din beställning, kontrollera i Helle-Finna om materialet finns i Helle. Som fjärrlån kan du endast beställa material som inte finns på något av Helle-biblioteken.<br/><br/>Fyll i de obligatoriska uppgifterna för att din beställning ska kunna behandlas.<br/><br/>Observera att fjärrlån är avgiftsbelagda. Avgiften är vanligtvis 6 € eller 12 €, beroende på vilket bibliotek fjärrlånet kommer ifrån.<br/><br/>Ett fjärrlån kommer oftast inom två veckor, om inte materialet är utlånat eller reserverat. Om fjärrlånebeställningen ställs i reservationskö kan lånet dröja flera veckor, till och med månader.

feedback_help_postinterlibraryloan - Lomakkeen jälkeinen selitysteksti.

    EN: The information I provide will be stored for the purpose of processing my request and will be retained for the duration of the request processing. Helle Libraries' privacy policy.
    FI: Antamani tiedot tallennetaan pyynnön käsittelyä varten ja tietoja säilytetään pyynnön käsittelyn ajan. Helle-kirjastojen tietosuojaseloste.
    SV: Den information jag lämnar kommer att lagras i syfte att behandla min begäran och kommer att behållas under hela behandlingen av begäran. Helle Libraries integritetspolicy.

feedback_help_interlibraryloan_renew - Haluttu selitysteksti uusintapyyntölomakkeeseen asiakkaalle ennen lomaketta.

    EN: Use this form to request a renewal for an interlibrary loan that you have borrowed. Please, select the library through which you borrowed the interlibrary loan.
    FI: Tällä lomakkeella voit pyytää uusintaa kaukolainalle. Valitse oma kirjastosi, jonka kautta olet kaukolainan lainannut.
    SV: Använd denna blankett för att förnya dina fjärrlån. Välj det bibliotek genom vilket du lånade fjärrlånet.

helle/forms/accept2 - Lomakkeen lähetyksen Hyväksy-napin teksti. Meillä accept2, koska pelkkä accept käytössä jo hankintapyyntölomakkeessa, jossa oli eri teksti eikä sitä näin ollen haluttu käyttää.

    EN: I accept that my information will be stored and used according to the text above.
    FI: Hyväksyn tietojen tallentamisen yllä mainittuun käyttöön.
    SV: Jag godkänner att mina uppgifter sparas för detta bruk.

Kaikki kohdat, joissa on helle/forms/x viedään kielikäännöksiin ja näille tehdään se käännös, mikä tahdotaan asiakkaan näkevän lomakkeen kenttien otsikkona. "helle" vaihtuu oman kimpan nimeen. Otin itse käännökset osaan kenttiin Webkaken kentistä (meidän tilauslomake asiakkaalle on kolmella kielellä: https://webkake.kirjastot.fi/wtil/tilaus?pa_ullang=0&pa_ulid=25), osassa hyödynsin meidän hankintapyyntölomakkeeseen jo tehtyjä käännöksiä.

Esim. helle/forms/author

    EN: Author/Artist
    FI: Tekijä/Esittäjä
    SV: Författare/Artist

## Automaattien lajittelut

Nyt kun kaukolainaniteet lisätään Kohaan, niin myöskin palautusautomaatit alkavat ottamaan niitä vastaan. Sen estäminen teknisesti voi olla haastavaa, joten kannattaa tehdä palautusautomaateille vähintään sellainen sääntö, että kaukolainat päätyvät jonnekin "uudelleenkäsiteltävien" laariin, jolloin ne pienemmällä todennäköisyydellä menevät vahingossa oman kirjaston hyllyyn.

## Sisäinen ohjeistus -dokumentti

Käyttöönottotyöryhmä koosti käyttöohjeista myös sellaisen version, joka sisältää tarkempaa ja käytännönläheisempää ohjeistusta moduulin käyttäjille. Kyseessä on runko, jonka pohjalta kimpoissa/kirjastoissa voidaan luoda vielä tarkempi ohjeistus juuri omien käyttösääntöjen ja toimintatapojen pohjalta.

[Kaukolainaohjeistus.docx](https://github.com/user-attachments/files/23548887/Kaukolainaohjeistus.docx)
