---
title: 'Kuitit ja viestipohjat'
permalink: /dokumentaatio/kuititjaviestit/
redirect_from:
  - /theme-setup/
toc: true
---

Tälle sivulle on koottu esimerkit erilaisista kuitti- ja viestipohjista. Testattu toimivaksi Kohan versiossa 22.11.

## HOLD_SLIP eli varauksen info- ja kuljetuskuitti

### Email-pohjaan

Tieto lisätään email-pohjaan. HTML-täppä paikoilleen.

#### Suomeksi

```
[% USE Branches %]

[% loggedinbranchname = Branches.GetName( Branches.GetLoggedInBranchcode() ) %]

[% IF loggedinbranchname == branch.branchname%]

<style type="text/css">
  h1 { font-family: arial; font-size: 20pt; }
  h2 { font-family: arial; font-size: 18pt; }
  p { font-family: arial; font-size: 12pt; }
</style>

<h1><<borrowers.othernames>></h1>
<h2>Viimeinen noutopäivä: <br />
<<reserves.expirationdate>></h2><br />
<h2 style="border: 2px solid; border-radius: 5px; padding-left: 5px; text-align: center; width: 198pt;">Muistathan lainata!</h2>
<br /><br />
<p>VARATTU NIDE</p>
<p><<biblio.author>><br />
<<biblio.title>> <<items.enumchron>><br />
<<items.barcode>><br />
Noutokirjasto: <<reserves.branchcode>></p>
```

#### Englanniksi

```
[% USE Branches %]

[% loggedinbranchname = Branches.GetName( Branches.GetLoggedInBranchcode() ) %]

[% IF loggedinbranchname == branch.branchname%]

<style type="text/css">
  h1 { font-family: arial; font-size: 20pt; }
  h2 { font-family: arial; font-size: 18pt; }
  p { font-family: arial; font-size: 12pt; }
</style>

<h1><<borrowers.othernames>></h1>
<h2>Last pickup date: <br />
<<reserves.expirationdate>></h2><br />
<h2 style="border: 2px solid; border-radius: 5px; padding-left: 5px; text-align: center; width: 198pt;">Remember to<br /> check out!</h2>
<br /><br />
<p>Reserved item</p>
<p><<biblio.author>><br />
<<biblio.title>> <<items.enumchron>><br />
<<items.barcode>><br />
Pick up library:  <<reserves.branchcode>></p>

<p>Date: <<today>></p>
<br/>
<p>You can change your hold identifier<br/>
at the OUTI Web Library:
<br/> outi.finna.fi</p>
<br/><br/><br/><br/><br/><br/><br/><br/>.

[% ELSE %]

<style type="text/css">
  h1 { font-family: arial; font-size: 20pt; }
  h2 { font-family: arial; font-size: 18pt; }
  h3 { font-family: arial; font-size: 16pt; }
  h4 { font-family: arial; font-size: 14pt; }
  p { font-family: arial; font-size: 10pt; }
</style>

<h2>Transfer to:<br />
<<branches.branchname>></h2>
<h3>Date: <<today>></h3>
<br />
<p>Item<br />
<<biblio.author>><br />
<<biblio.title>> <<items.enumchron>><br />
<<items.barcode>></p>

[% END %]

<br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/>.

```

## MEMBERSHIP_EXPIRY eli sähköpostiviesti tilin voimassaoloajan loppumisesta

### Email-pohjaan

Tieto lisätään email-pohjaan.

#### Suomeksi

```
Asiakas: <<borrowers.othernames>>

Kirjastokorttisi voimassoloaika on päättymässä <<borrowers.dateexpiry>>.

Ota yhteys kirjastoosi jatkaaksesi voimassaoloaikaa. Samalla tarkistamme yhteystietosi. Tarkistamme yhteystiedot kaikilta asiakkailtamme viiden vuoden välein. 

Ystävällisin terveisin

OUTI-kirjastot
www.outikirjastot.fi
```

#### Englanniksi

```
Customer: <<borrowers.othernames>>

The validity period of your library card is ending <<borrowers.dateexpiry>>. 

Please contact your library to continue the validity period. At the same time we check your contact information. We will check the contact information from all our customers every five years. 

Sincerely

OUTI Libraries
www.outikirjastot.fi
```

Asiakaslajin mukaan valikoituva viestipohja (virkailijalle eri viesti kuin asiakkaille):
```
[% IF "<<borrowers.categorycode>>" == "VIRKAILIJA" %]
Hei,

Koha-tunnuksen <<borrowers.cardnumber>> voimassaolo päättyy 30 päivän kuluttua. Mikäli työsuhde jatkuu, on pyydäthän esihenkilöä huolehtimaan tunnuksen voimassaolon jatkamisesta ennen <<borrowers.dateexpiry>>.

[% ELSE %]

Hei <<borrowers.firstname>>,  
 
on aika tarkistaa kirjastokorttisi <<borrowers.cardnumber>> asiakastiedot. Käythän kirjastossa päivittämässä tietosi ennen <<borrowers.dateexpiry>>. Voit ottaa yhteyttä kirjastoon myös sähköpostilla tai puhelimitse. Vaski-kirjastojen yhteystiedot löydät verkkokirjastosta www.vaskikirjastot.fi.
  
Tähän viestiin ei voi vastata. Otathan tarvittaessa yhteyttä omaan kirjastoosi.

[% END %]
```

Myös syntaksi ```[% IF borrower.categorycode == "VIRKAILIJA" %]``` viestin alussa ajaa saman asian kuin ```[% IF "<<borrowers.categorycode>>" == "VIRKAILIJA" %]```

## FINESLIP eli asiakkaan maksut

### Tuloste/Print-pohjaan

Tieto lisätään Tuloste/Print-pohjaan. HTML-täppä pitää laittaa paikoilleen.

#### Suomeksi

```
<style type="text/css">
  h1 { font-family: arial; font-size: 20pt; }
  h2 { font-family: arial; font-size: 18pt; }
  h3 { font-family: arial; font-size: 16pt; }
  h4 { font-family: arial; font-size: 14pt; }
  p { font-family: arial; font-size: 10pt; }
</style>
<h3><<branches.branchname>><br />
<<today>></h3>
<br /><br />
<h3>Kirjastomaksut:</h3>
<fines>
<p><<fines.date_due>> <<fines.description>>: <<fines.amount>> € </p>
</fines>
<p><b>Yhteensä:</b> <<total.amount>> €</p><br />
<p><<branches.branchfax>><br />
<<branches.branchphone>><br />
www.outikirjastot.fi</p>
```


#### Englanniksi

```
<style type="text/css">
  h1 { font-family: arial; font-size: 20pt; }
  h2 { font-family: arial; font-size: 18pt; }
  h3 { font-family: arial; font-size: 16pt; }
  h4 { font-family: arial; font-size: 14pt; }
  p { font-family: arial; font-size: 10pt; }
</style>
<h3><<branches.branchname>><br />
<<today>></h3>
<br /><br />
<h3>Fines:</h3>
<fines>
<p><<fines.date_due>> <<fines.description>>: <<fines.amount>> € </p>
</fines>
<p><b>Total:</b> <<total.amount>> €</p><br />
<p><<branches.branchfax>><br />
<<branches.branchphone>><br />
www.outikirjastot.fi</p>
```

## DUEDGST eli Eräpäivämuistutus eräpäivänä

### Email-pohjaan

#### Suomeksi

```
Asiakastunnus: <<borrowers.cardnumber>>

Seuraavilla lainoilla on eräpäivä tänään: 

<<items.content>>


Lainat voi uusia osoitteessa https://outi.finna.fi/MyResearch/CheckedOut

Lainat voi uusia, jos niistä ei ole varauksia. Lainan voi uusia poikkeuksellisesti enintään kymmenen kertaa peräkkäin. Uusimiseen tarvitaan kirjastokortin numero ja pin-koodi.

Terveisin 
OUTI-kirjastot
<<branches.branchfax>>
http://www.outikirjastot.fi

ps. Verkkokirjastossa omaan kirjastokorttiin voi liittää myös muita kirjastokortteja, esimerkiksi lapsen tai muun perheenjäsenen kortin. Tämän toiminnon avulla liitetyn kortin tietoja pääsee tarkastelemaan ja muokkaamaan, uusimaan lainoja ja tekemään varauksia. Kortin liittämiseen tarvitsee tietää liitettävän kirjastokortin numero ja sen pin-koodi.
```

#### Englanniksi

```
Library card number: <<borrowers.cardnumber>>

The following items are due today:

<<items.content>>

You can renew your loans at https://outi.finna.fi/MyResearch/CheckedOut

You need your library card number and PIN for renewing.

Best regards
OUTI Libraries
<<branches.branchfax>>
http://www.outikirjastot.fi
```

## ISSUESLIP eli lainakuitti kaikista lainoista

### Email-pohjaan

Email-pohjaan. HTML-täppä paikoilleen.

#### Suomeksi

```
[% USE Price %]

<style type="text/css">
  h1 { font-family: arial; font-size: 20pt; }
  h2 { font-family: arial; font-size: 14pt; }
  h3 { font-family: arial; font-size: 18pt; }
  h4 { font-family: arial; font-size: 14pt; }
  p { font-family: arial; font-size: 10pt; }
</style>

<h3><<branches.branchname>><br />
<<today>></h3><br />

<h3>Kaikki lainassa olevat</h3>
<checkedout>
<p><<biblio.title>> <<items.enumchron>> / <<biblio.author>> <br />
Nidetunnus: <<items.barcode>><br />
Eräpäivä: <<issues.date_due | dateonly >><br />
Uusittu: <<issues.renewals_count>> / 7 kertaa
</p>
</checkedout>
<p>Yhteensä lainoja: [% checkouts.count %] 

<br/>
<h4>Myöhässä olevat</h4>
<overdue>
<p>
<<biblio.title>> / <<biblio.author>>  <br />
Nidetunnus: <<items.barcode>><br />
Eräpäivä: <<issues.date_due | dateonly >> <br />
Uusintakerrat: <<issues.renewals_count>>
</p>
</overdue>
<p>Yhteensä myöhässä: [% overdues.count %]
<br />
<p>Maksut:
[% SET balance = borrower.account.balance %]
[% balance | $Price %] €
<br>
<br>
<br>
<br>Lainat voi uusia puhelimitse p. <<branches.branchphone>>
<br>tai verkkokirjastossa: https://vaara.finna.fi
<br>Tutustu myös e-aineistoihimme!
<br /></p>
```

#### Englanniksi

```
[% USE Price %]

<style type="text/css">
  h1 { font-family: arial; font-size: 20pt; }
  h2 { font-family: arial; font-size: 14pt; }
  h3 { font-family: arial; font-size: 18pt; }
  h4 { font-family: arial; font-size: 14pt; }
  p { font-family: arial; font-size: 10pt; }
</style>

<h3><<branches.branchname>><br />
<<today>></h3><br />

<h2>All check outs</h2>
<checkedout>
<p><<biblio.title>> <<items.enumchron>> / <<biblio.author>> <br />
Barcode: <<items.barcode>><br />
Due date: <<issues.date_due | dateonly >><br />
Renewals: <<issues.renewals_count>>
</p>
</checkedout>

<p>Check outs: [% checkouts.count %][% IF checkouts.count > 1 %]
      check outs
[% ELSE %]
      check out
    [% END %] </p>
<br/>
<h4>Overdue</h4>
<overdue>
<p>
<<biblio.title>> / <<biblio.author>>  <br />
Barcode: <<items.barcode>><br />
Due date: <<issues.date_due | dateonly >> <br />
Renewals: <<issues.renewals_count>>
</overdue>
</p>
<p>Check outs: [% overdues.count %][% IF overdues.count > 1 %]
      check outs
[% ELSE %]
      check out
    [% END %] </p>

<br />
<p>Fines: 
[% SET balance = borrower.account.balance %]
[% IF balance > 0 %]
[% balance | $Price %] €.
[% END %]
[% IF balance < 0 %]
Credit  [% balance | $Price %] €.
[% END %]
<br /></p>
<p><<branches.branchfax>><br />
<<branches.branchphone>><br />
www.outikirjastot.fi</p>
<br />
```

## ISSUEQLSLIP eli lainakuitti päivän lainoista

### Email-pohjaan

Email-pohjaan. HTML-täppä paikoilleen.

#### Suomeksi

```
[% USE Price %]

<style type="text/css">
  h1 { font-family: arial; font-size: 20pt; }
  h2 { font-family: arial; font-size: 18pt; }
  h3 { font-family: arial; font-size: 16pt; }
  h4 { font-family: arial; font-size: 14pt; }
  p { font-family: arial; font-size: 10pt; }
</style>

<h3><<branches.branchname>><br />
<<today>></h3>
<br />
<h3>Lainattu tänään</h3>
<checkedout>
<p><<biblio.title>> <<items.enumchron>> / <<biblio.author>> <br />
Eräpäivä: <<issues.date_due | dateonly >>
</checkedout>
<br /><br />

<p>Yhteensä: [% checkouts.count %][% IF checkouts.count > 1 %]
      lainaa
[% ELSE %]
      laina
    [% END %] </p>
<p>Maksut:
[% SET balance = borrower.account.balance %]
[% IF balance > 0 %]
[% balance | $Price %] €.
[% END %]
[% IF balance < 0 %]
Asiakkaalla on hyvityksiä [% balance | $Price %] €.
[% END %]
</p>

<p><<branches.branchfax>>
<br /><<branches.branchphone>>
<br />www.outikirjastot.fi</p>
```

#### Englanniksi

```
[% USE Price %]

<style type="text/css">
  h1 { font-family: arial; font-size: 20pt; }
  h2 { font-family: arial; font-size: 18pt; }
  h3 { font-family: arial; font-size: 16pt; }
  h4 { font-family: arial; font-size: 14pt; }
  p { font-family: arial; font-size: 10pt; }
</style>

<h3><<branches.branchname>><br />
<<today>></h3>
<br />
<h3>Check outs today</h3>
<checkedout>
<p><<biblio.title>> <<items.enumchron>> / <<biblio.author>> <br />
Du edate: <<issues.date_due | dateonly >>
</checkedout>
<br /><br />

<p>Checked out: [% checkouts.count %][% IF checkouts.count > 1 %]
      check outs
[% ELSE %]
      check out
    [% END %] </p>
<p>Fines:
[% SET balance = borrower.account.balance %]
[% IF balance > 0 %]
[% balance | $Price %] €.
[% END %]
[% IF balance < 0 %]
Credits [% balance | $Price %] €.
[% END %]
</p>

<p><<branches.branchfax>>
<br /><<branches.branchphone>>
<br />www.outikirjastot.fi</p>
```

## CHECKOUT eli Lainauskuitti sähköpostiin

### Email-pohjaan

#### Suomeksi

```
Lainasitte tänään <<branches.branchname>>sta  seuraavat teokset:

----
<<biblio.title>> <<items.enumchron>> / <<biblio.author>>,  eräpäivä: <<issues.date_due | dateonly >>
----


Terveisin OUTI-kirjastot
www.outikirjastot.fi
```

#### Englanniksi

```
You checked out from <<branches.branchname>> following items:

----
<<biblio.title>> <<items.enumchron>> / <<biblio.author>>,  due date: <<issues.date_due | dateonly >>
----


Best regards
OUTI Libraries
www.outikirjastot.fi
```

## HOLD eli Noutoilmoitus

### Email-pohjaan

#### Suomeksi

```
NOUTOILMOITUS                                        
<<today>>

Varaustunnuksesi on <<borrowers.othernames>>.

Varaamasi teos <<biblio.title>> <<biblioitems.number>> <<items.enumchron>> / <<biblio.author>> (<<items.barcode>>) on noudettavissa <<branches.branchname>>sta.

Varauksen viimeinen noutopäivä on <<reserves.expirationdate>>. 

Muistathan ottaa kirjastokortin mukaan varausta noutaessasi. Noutamattomasta varauksesta perimme yhden euron.


Terveisin 
<<branches.branchname>>
<<branches.branchaddress1>>
<<branches.branchzip>>  <<branches.branchcity>>
<<branches.branchphone>>
<<branches.branchreplyto>>
www.outikirjastot.fi
```

#### Englanniksi

```
Library pick-up notice 
<<today>>

Your library hold identifier is <<borrowers.othernames>>.

The item <<biblio.title>> <<biblioitems.number>> <<items.enumchron>> / <<biblio.author>> (nide <<items.barcode>>) is waiting for pickup at <<branches.branchname>>.

The last pick-up day is <<reserves.expirationdate>>. 

Please remember to take your library card with you when picking up your hold. If you do not pick up your hold, a fee of one euro will be charged.

Best regards
<<branches.branchname>>
<<branches.branchaddress1>>
<<branches.branchzip>>  <<branches.branchcity>>
<<branches.branchphone>>
<<branches.branchfax>>
<<branches.branchreplyto>>
www.outikirjastot.fi
```

### Tuloste/Print-pohjaan

E-kirjeeseen tulee osoitetiedot Paten toimintojen kautta, niitä ei määritetä viestipohjaan.

#### Suomeksi

```
NOUTOILMOITUS                                        
<<today>>

Varaustunnuksesi on <<borrowers.othernames>>.

Varaamasi teos <<biblio.title>> <<biblioitems.number>> <<items.enumchron>> / <<biblio.author>> (<<items.barcode>>) on noudettavissa <<branches.branchname>>sta.

Varauksen viimeinen noutopäivä on <<reserves.expirationdate>>. 

Muistathan ottaa kirjastokortin mukaan varausta noutaessasi. Noutamattomasta varauksesta perimme yhden euron.


Terveisin 
<<branches.branchname>>
<<branches.branchaddress1>>
<<branches.branchzip>>  <<branches.branchcity>>
<<branches.branchphone>>
<<branches.branchreplyto>>
www.outikirjastot.fi
```

#### Englanniksi

```
Your reservation is waiting for pickup. Your hold identifier is
<<borrowers.othernames>>.

Title: <<biblio.title>> <<biblioitems.number>> <<items.enumchron>> / <<biblio.author>> (<<items.barcode>>) is waiting at <<branches.branchname>>.
The last pick-up date is <<reserves.expirationdate>>.

Please remember to take your library card with you 
when picking up your hold. If you do not pick up your 
hold a fee of one euro will be charged.

Best regards 
OUTI Libraries
<<branches.branchphone>>
www.outikirjastot.fi
```

### SMS/Tekstiviesti-pohjaan

#### Suomeksi

```
Varaustunnuksellasi <<borrowers.othernames>> on noudettavissa varaus <<biblio.title>> <<items.enumchron>> <<biblioitems.number>> (<<items.barcode>>)  <<branches.branchname>>sta <<reserves.expirationdate>> asti.
```

#### Englanniksi

```
Your hold identifier is <<borrowers.othernames>>. Your hold <<biblio.title>> <<biblioitems.number>> <<items.enumchron>> (<<items.barcode>>) is waiting for you at <<branches.branchname>> until <<reserves.expirationdate>>. 
```

## CHECKINSLIP eli palautuskuitti

### Tuloste/Print-pohjaan

Tuloste/Print-pohjaan. HMTL-täppä pakoilleen.

#### Suomeksi

```
<style type="text/css">
  h1 { font-family: arial; font-size: 20pt; }
  h2 { font-family: arial; font-size: 18pt; }
  h3 { font-family: arial; font-size: 16pt; }
  h4 { font-family: arial; font-size: 14pt; }
  p { font-family: arial; font-size: 10pt; }
</style>

<h3>[% branch.branchname %]<br />
[% today | $KohaDates %]<br /></h3><br /><br />

<h3>Palautetut lainat</h3>

[% FOREACH checkin IN old_checkouts %] [% SET item = checkin.item %] <p> [% item.biblio.title %] [% item.enumchron %] [% item.biblio.author %] <br />
Nide: [% item.barcode %] <br />
</p>
[% END %]

<p>
<br /><<branches.branchfax>>
<br /><<branches.branchphone>>
<br />www.outikirjastot.fi</p>
<br />
```

#### Englanniksi

```
<style type="text/css">
  h1 { font-family: arial; font-size: 20pt; }
  h2 { font-family: arial; font-size: 18pt; }
  h3 { font-family: arial; font-size: 16pt; }
  h4 { font-family: arial; font-size: 14pt; }
  p { font-family: arial; font-size: 10pt; }
</style>

<h3>[% branch.branchname %]<br />
[% today | $KohaDates %]<br /></h3><br /><br />

<h3>Checkins</h3>

[% FOREACH checkin IN old_checkouts %] [% SET item = checkin.item %] <p> [% item.biblio.title %] [% item.enumchron %] [% item.biblio.author %] <br />
Barcode: [% item.barcode %] <br />
</p>
[% END %]

<p>
<br /><<branches.branchfax>>
<br /><<branches.branchphone>>
<br />www.outikirjastot.fi</p>
<br />
```

## CHECKIN eli palautuskuitti sähköpostiin

### Email-pohjaan

#### Suomeksi

```
<<branches.branchname>>
<<today>>

Palautitte tänään seuraavat lainat:

----
<<biblio.title>> <<items.enumchron>> / <<biblio.author>> <<items.barcode>>
----

Terveisin OUTI-kirjastot
www.outikirjastot.fi
```

#### Englanniksi

```
<<branches.branchname>>
<<today>>

You checked in today:

----
<<biblio.title>> <<items.enumchron>> / <<biblio.author>> <<items.barcode>>
----

Best regards
OUTI Libraries
www.outikirjastot.fi
```

## OVERDUES_SLIP eli myöhässä olevat lainat kuitille

### Tuloste/Print-pohjaan

Tuloste/Print-pohjalle. HMTL-täppä paikoilleen.

#### Suomeksi

```
<style type="text/css">
  h1 { font-family: arial; font-size: 20pt; }
  h2 { font-family: arial; font-size: 18pt; }
  h3 { font-family: arial; font-size: 16pt; }
  h4 { font-family: arial; font-size: 14pt; }
  p { font-family: arial; font-size: 10pt; }
</style>

<h3>Myöhässä olevat lainat</h3>

<overdue>
<p><item>
<<biblio.title>> / <<biblio.author>>  <br />
Nidetunnus: <<items.barcode>><br />
Eräpäivä: <<issues.date_due>><br />
Uusintakerrat: <<issues.renewals>><br /><br /></item>
</p>
</overdue>

<p><<branches.branchfax>>
<br /><<branches.branchphone>>
<br />www.outikirjastot.fi</p>
```

#### Englanniksi

```
<style type="text/css">
  h1 { font-family: arial; font-size: 20pt; }
  h2 { font-family: arial; font-size: 18pt; }
  h3 { font-family: arial; font-size: 16pt; }
  h4 { font-family: arial; font-size: 14pt; }
  p { font-family: arial; font-size: 10pt; }
</style>

<h3>Overdues</h3>

<overdue>
<p><item>
<<biblio.title>> / <<biblio.author>>  <br />
Barcode: <<items.barcode>><br />
Due date: <<issues.date_due>><br />
Renewals: <<issues.renewals>><br /><br /></item>
</p>
</overdue>

<p><<branches.branchfax>>
<br /><<branches.branchphone>>
<br />www.outikirjastot.fi</p>
```

## ODUE1 eli ensimmäinen palautuskehotus

### Email/sähköposti-pohjaan

#### Suomeksi

```
Hyvä kirjaston asiakas 

Lainasi ovat myöhässä. 

Asiakastunnus: <<borrowers.cardnumber>>

Erääntyneet lainat:
----
<item>Nide: <<items.barcode>>, Aineistolaji: <<items.itype>>
Teos: <<biblio.title>> <<items.enumchron>> / <<biblio.author>>  
Eräpäivä: <<issues.date_due>>, Lainattu: <<issues.issuedate>>
</item>
----

Palautathan lainasi mahdollisimman pian. Voit uusia lainasi OUTI-verkkokirjastossa, jos niistä ei ole varauksia. Lainan voi uusia enintään 10 kertaa peräkkäin. OUTI-verkkokirjaston osoite: www.outikirjastot.fi

Myöhästymismaksut alkavat kertyä heti eräpäivän jälkeen. Lasten aineistosta ja lapsiasiakkaan lainoista ei mene myöhästymismaksua.

Perimme tämän muistutuksen lähettämisestä 1,50 euron huomautusmaksun.

Palauttamattomista lainoista lähetämme laskun.

Epäselvissä tapauksissa pyydämme ottamaan yhteyttä kirjastoon.


Ystävällisin terveisin

OUTI-kirjastot

<<branches.branchname>>
<<branches.branchfax>>
<<branches.branchphone>>
<<branches.branchreplyto>>
www.outikirjastot.fi
```

#### Englanniksi

```
Dear library user

Your loans are overdue.

Customer number:  <<borrowers.cardnumber>>

Overdue items:
----
<item>Itemnumber: <<items.barcode>>
Title: <<biblio.title>> <<items.enumchron>> / <<biblio.author>>  
Due date: <<issues.date_due>>, Checked out on: <<issues.issuedate>>, Item type: <<items.itype>>
</item>
---- 

Please return your overdue items as soon as possible. You can also renew them at the OUTI Web Library if there are no reservations. Loans can be renewed up to ten times.

The overdue fine starts to accrue immediately after the due date. Materials for children and material borrowed by customers under the age of 18 years are not subject to overdue fines.

We also charge 1,50 euro for sending this notification.

If you have any questions about these loans, please contact the library where you checked them out.

Best regards
OUTI Libraries
<<branches.branchname>>
<<branches.branchfax>>
<<branches.branchphone>>
<<branches.branchreplyto>>
www.outikirjastot.fi
```

### Tuloste/Print-pohjaan

E-kirjeessä asiakkaan yhteystiedot tulee Paten kautta, niitä ei määritetä viestipohjaan.

#### Suomeksi

```
Hyvä kirjaston asiakas. Lainasi ovat myöhässä. 

Erääntyneet lainat:
----
<item>Nide: <<items.barcode>>, Aineistolaji: <<biblioitems.itemtype>>
Teos: <<biblio.title>> <<items.enumchron>> / <<biblio.author>>  
Eräpäivä: <<issues.date_due>>, Lainattu: <<issues.issuedate>>
</item>
---- 

Palautathan lainasi mahdollisimman pian. Voit uusia lainasi 
OUTI-verkkokirjastossa osoitteessa www.outikirjastot.fi, 
jos niistä ei ole varauksia. Lainan voi uusia enintään 10
kertaa peräkkäin.

Myöhästymismaksut alkavat kertyä heti eräpäivän jälkeen.
Lasten aineistosta ja lapsiasiakkaiden lainoista ei mene
myöhästymismaksua.

Perimme tämän muistutuksen lähettämisestä 1,50 euron 
huomautusmaksun.

Epäselvissä tapauksissa pyydämme ottamaan yhteyttä kirjastoon.

Ystävällisin terveisin 
OUTI-kirjastot
<<branches.branchphone>>

Ilmoita kirjastoon sähköpostiosoitteesi tai lisää se OUTI-verkkokirjastossa,
niin saat tämän viestin nopeammin ja ekologisemmin.
```

#### Englanniksi

```
Dear library user

Your loans are overdue.

Overdue items:
----
<item>Itemnumber: <<items.barcode>>,  Item type: <<biblioitems.itemtype>>
Title: <<biblio.title>> <<items.enumchron>> / <<biblio.author>>  
Due date: <<issues.date_due>>, Checked out on: <<issues.issuedate>>
</item>
---- 
 
Please return your overdue items as soon as possible.
You can also renew them at the OUTI Web Library if there are no 
reservations. Loans can be renewed up to ten times.

The overdue fine starts to accrue immediately after the due date.
Materials for children and material borrowed by customers under 
the age of 18 years are not subject to overdue fines.

We also charge 1,50 euro for sending this notification.

If you have questions about these loans, please contact the library
where you checked them out.

Best regards

OUTI Libraries
http://www.outikirjastot.fi
<<branches.branchphone>>
```

## ODUE2 eli toinen palautuskehotus

### Email/sähköposti-pohjaan

#### Suomeksi

```
Hyvä kirjaston asiakas  

Seuraavat lainasi ovat edelleen palauttamatta. Tämä on toinen palautuskehotus.  

Asiakastunnus: <<borrowers.cardnumber>> 

Erääntyneet lainat: 

---- 

<item>Nide: <<items.barcode>>, Aineistolaji: <<items.itype>> 
Teos: <<biblio.title>> <<items.enumchron>> / <<biblio.author>>   
Eräpäivä: <<issues.date_due>>, Lainattu: <<issues.issuedate>> 
</item> 

---- 

Palautathan lainasi mahdollisimman pian. Voit uusia lainasi OUTI-verkkokirjastossa, jos niistä ei ole varauksia. Lainan voi uusia enintään 10 kertaa peräkkäin. OUTI-verkkokirjaston osoite: www.outikirjastot.fi 

Myöhästymismaksut alkavat kertyä heti eräpäivän jälkeen. Lasten aineistosta ja lapsiasiakkaan lainoista ei mene myöhästymismaksua.

Perimme tämän muistutuksen lähettämisestä 3 euron huomautusmaksun. 

Palauttamattomista lainoista lähetämme laskun. Laskun lähettäminen aiheuttaa lainauskiellon. Hoitamatta jäävä lasku voi johtaa perintään. 

Epäselvissä tapauksissa pyydämme ottamaan yhteyttä kirjastoon. 


Ystävällisin terveisin 

OUTI-kirjastot 

<<branches.branchname>> 
<<branches.branchfax>> 
<<branches.branchphone>> 
<<branches.branchreplyto>> 
www.outikirjastot.fi
```

#### Englanniksi

```
Dear library user

Your loans are still overdue. This is a second overdue notice. 

Customer number:  <<borrowers.cardnumber>> 

Overdue items: 
---- 
<item>Itemnumber: <<items.barcode>> 
Title: <<biblio.title>> <<items.enumchron>> / <<biblio.author>>   
Due date: <<issues.date_due>>, Checked out on: <<issues.issuedate>>, Item type: <<items.itype>> 
</item> 
----  

Please return your overdue items as soon as possible. You can also renew them at the OUTI Web Library if there are no reservations. Loans can be renewed up to ten times. 

The overdue fine starts to accrue immediately after the due date. Materials for children and material borrowed by customers under the age of 18 years are not subject to overdue fines.

We also charge 3 euro for sending this notification. 

Unless you return the items, you will receive an invoice of the overdue loans. Your library card will be blocked when the invoice is sent. Not taking care of the invoice can lead to collection of your debt. 

If you have any questions about these loans, please contact the library where you checked them out. 
  

Best regards 

OUTI Libraries 

<<branches.branchname>> 
<<branches.branchfax>> 
<<branches.branchphone>> 
<<branches.branchreplyto>> 
www.outikirjastot.fi
```

### Tuloste/Print-pohjaan

E-kirjeissä asiakkaan yhteystiedot haetaan Paten kautta, niitä ei lisätä viestipohjaan.

#### Suomeksi

```
Hyvä kirjaston asiakas 
 
Seuraavat lainasi ovat edelleen palauttamatta. Tämä on toinen palautuskehotus. 
 
Erääntyneet lainat: 
---- 
<item>Nide: <<items.barcode>>, Aineistolaji: <<biblioitems.itemtype>> 
Teos: <<biblio.title>> <<items.enumchron>> / <<biblio.author>>
Eräpäivä: <<issues.date_due>>, Lainattu: <<issues.issuedate>> 
</item> 
----  
 
Palautathan lainasi mahdollisimman pian. Voit uusia lainasi OUTI-verkkokirjastossa
osoitteessa www.outikirjastot.fi, jos niistä ei ole varauksia. Lainan voi uusia 
enintään 10 kertaa peräkkäin. 
 
Myöhästymismaksut alkavat kertyä heti eräpäivän jälkeen. Lasten aineistosta ja 
lapsiasiakkaan lainoista ei mene myöhästymismaksua.

Perimme tämän muistutuksen lähettämisestä 3 euron huomautusmaksun. 
 
Palauttamattomista lainoista lähetämme laskun. Laskun lähettäminen aiheuttaa lainauskiellon. Hoitamatta jäävä lasku voi johtaa perintään.    
 
Epäselvissä tapauksissa pyydämme ottamaan yhteyttä kirjastoon. 
 
Ystävällisin terveisin  
OUTI-kirjastot 
<<branches.branchphone>>

Ilmoita kirjastoon sähköpostiosoitteesi tai lisää se OUTI-verkkokirjastossa,
niin saat tämän viestin nopeammin ja ekologisemmin.
```

#### Englanniksi

```
Dear library user
 
Your loans are overdue. 
 
Overdue items: 
---- 
<item>Itemnumber: <<items.barcode>>,  Item type: <<biblioitems.itemtype>> 
Title: <<biblio.title>> <<items.enumchron>> / <<biblio.author>>   
Due date: <<issues.date_due>>, Checked out on: <<issues.issuedate>> 
</item> 
----  
  
Please return your overdue items as soon as possible. 
You can also renew them at the OUTI Web Library if there are no  
reservations. Loans can be renewed up to ten times. 
 
The overdue fine starts to accrue immediately after the due date.
Materials for children and material borrowed by customers under 
the age of 18 years are not subject to overdue fines.

We also charge 3 euros for sending this notification. 
 
Unless you return the items, you will receive an invoice  
of the overdue loans. Your library card will be blocked  
when the invoice is sent. Not taking care of the invoice  
can lead to collection of your debt. 
 
If you have questions about these loans, please contact the library 
where you checked them out. 
 
Best regards 
 
OUTI Libraries 
http://www.outikirjastot.fi 
<<branches.branchphone>>
```

## ODUECLAIM eli lasku

Katso laskutustyökalun ohjeet.

### Tuloste/Print-pohjaan

#### Suomeksi

```
Lainaaja: <<issueborname>>, <<issueborbarcode>>

Pyydämme viipymättä palauttamaan tai korvaamaan erääntyneet lainat. 

<item>
Eräpäivä: <<date_due>>
Teos: <<biblio.title>>  <<items.enumchron>> 
Tekijä: <<biblio.author>>
Aineistotyyppi: <<biblioitems.itemtype>> 
Viivakoodi: <<items.barcode>>
Luokka: <<items.itemcallnumber>>
Korvaushinta: <<items.replacementprice>> €
</item>


Maksettava yhteensä: <<totalfines>> €
ALV: 0 %

Saaja: <<grouplibrary>>
<<groupaddress>>, <<groupzipcode>> <<groupcity>>
Puhelin: <<groupphone>>
Y-tunnus: <<businessid>>

Tilinumero: <<accountnumber>>
BIC: <<biccode>>

Viitenumero: <<referencenumber>>
Laskun eräpäivä: <<invoice_duedate>>
Maksuehto: 14 pv netto
Huomautusaika: 8 päivää

Viivästyskorko: Korkolain mukainen
Laskunumero: <<invoicenumber>>
```

### PDF-pohjaan

#### Suomeksi

```
<div class="header">
    <div class="sender">
        <div class="library">
            <p><ul class="info"><li><<branches.branchname>></li>
                <li><<branches.branchaddress1>></li>
                <li><<branches.branchzip>> <<branches.branchcity>></li>
                </ul></p>
        </div>
        <div class="billheader">
            <p><ul class="info"><li>Lasku</li>
                <li><<today>></li>
            </ul></p>
        </div>
    </div>
</div>
<div class="recipient">
    <p><ul class="info">
        <li><<borrowers.firstname>>  <<borrowers.surname>></li>
        <li><<borrowers.address>></li>
        <li><<borrowers.zipcode>> <<borrowers.city>></li>
    </ul></p>
</div>
<div class="content">
    <p><strong>Lainaajan nimi:</strong> <<issueborname>> <strong>Nro:</strong> <<issueborbarcode>></p>
    <p>Pyydämme teitä viipymättä palauttamaan tai korvaamaan erääntyneet lainat. Hoitamaton lasku siirtyy perintätoimiston hoidettavaksi.</p><br/>
    <table class="table">
        <thead>
            <tr>
            <th>Eräpäivä</th>
            <th>Teos</th>
            <th>Nidetiedot</th>
            <th>Korvaushinta</th>
            </tr>
        </thead>
        <tbody>
            <item>
                <tr>
                    <td><<date_due>></td>
                    <td><<biblio.title>>  <<items.enumchron>> / <<biblio.author>> </td>
                    <td><<biblioitems.itemtype>><br/><<items.barcode>><br/><<items.itemcallnumber>></td>
                    <td><<items.replacementprice>> €<br/></td>
                </tr>
            </item>
        </tbody>
    </table>
</div>
<div class="summary">
    <p><ul class="info">
    <li>MAKSETTAVA YHTEENSÄ: <<totalfines>> €</li>
    <li>ALV: 0 %</li>

    </ul></p>
</div>
<div class="ehdot">
<p>Saaja: <<grouplibrary>><br />
Osoite: <<groupaddress>>, <<groupzipcode>> <<groupcity>><br />
Puhelin: <<groupphone>><br />
Y-tunnus: <<businessid>>
<br />

Tilinumero: <<accountnumber>><br />
BIC: <<biccode>><br />
<br />
Viitenumero: <<referencenumber>><br />
Laskun eräpäivä: <<invoice_duedate>><br />
Maksuehto: 14 pv netto<br />
Huomautusaika: 8 päivää<br />
<br />
Viivästyskorko: Korkolain mukainen<br />
Laskunumero: <<invoicenumber>><br />
</p>
</div>
Laskunumero: <<invoicenumber>>
```

## ACCOUNTS_SUMMARY eli asiakkaan maksut

### Tulosta/Print-pohjaan

Koha-yhteisössä on toteutettu asiakkaan maksukuitti, joka korvaa aiemman Koha-Suomen oman FINESLIP-kuittipohjan. FINESLIP-kuittipohjan saa poistaa.

#### Suomeksi

Viestityyppi: Tulosta<br />
HTML-viesti: kyllä<br />
Viestin aihe: Maksukuitti<br />
Viestin sisältö:
```
[% USE Branches %]
[% USE Koha %]
[% USE KohaDates %]
[% USE Price %]
[% PROCESS 'accounts.inc' %]
<table>
  [% IF ( Koha.Preference('LibraryName') ) %]
    <tr>
      <th colspan='3' class='centerednames'>
        <h1>[% Koha.Preference('LibraryName') | html %]</h1>
      </th>
    </tr>
  [% END %]

  <tr>
    <th colspan='3' class='centerednames'>
      <h2>[% Branches.GetName( borrower.branchcode ) | html %]</h2>
    </th>
  </tr>

  <tr>
    <th colspan='3' class='centerednames'>
      <h3>Voimassa olevat maksut</h3>
    </th>
  </tr>

  [% IF borrower.account.outstanding_debits.total_outstanding %]
  <tr>
    <th>Päivämäärä</th>
    <th>Maksu</th>
    <th style="text-align:right;">Maksamatta</th>
  </tr>
  [% FOREACH debit IN borrower.account.outstanding_debits %]
  <tr>
    <td>[% debit.date | $KohaDates %]</td>
    <td>
      [% PROCESS account_type_description account=debit %]
      [%- IF debit.description %], [% debit.description | html %][% END %]
    </td>
    <td class='debit'>[% debit.amountoutstanding | $Price %]</td>
  </tr>
  [% END %]
  [% ELSE %]
  <tr>
    <td colspan=3'>Sinulla ei ole maksamattomia maksuja.</td>
  </tr>
  [% END %]

    <tfoot>
    <tr>
      <td colspan='2'>
        [% IF borrower.account.balance < 0 %]
         Creditiä yhteensä [% today | $KohaDates %]:
        [% ELSE %]
          Maksamattomia maksuja yhteensä [% today | $KohaDates %]:
        [% END %]
      </td>
      [% IF ( borrower.account.balance <= 0 ) %]<td class='credit'>[% borrower.account.balance * -1 | $Price %]</td>
      [% ELSE %]<td class='debit'>[% borrower.account.balance | $Price %]</td>[% END %]
    </tr>
  </tfoot>
</table>
```

#### Englanniksi

Viestityyppi: Tulosta<br />
HTML-viesti: kyllä<br />
Viestin aihe: Accounts summary<br />
Viestin sisältö:
```
[% USE Branches %]
[% USE Koha %]
[% USE KohaDates %]
[% USE Price %]
[% PROCESS 'accounts.inc' %]
<table>
  [% IF ( Koha.Preference('LibraryName') ) %]
    <tr>
      <th colspan='3' class='centerednames'>
        <h1>[% Koha.Preference('LibraryName') | html %]</h1>
      </th>
    </tr>
  [% END %]

  <tr>
    <th colspan='3' class='centerednames'>
      <h2>[% Branches.GetName( borrower.branchcode ) | html %]</h2>
    </th>
  </tr>

  <tr>
    <th colspan='3' class='centerednames'>
      <h3>Outstanding accounts</h3>
    </th>
  </tr>

  [% IF borrower.account.outstanding_debits.total_outstanding %]
  <tr>
    <th>Date</th>
    <th>Charge</th>
    <th style="text-align:right;">Amount outstanding</th>
  </tr>
  [% FOREACH debit IN borrower.account.outstanding_debits %]
  <tr>
    <td>[% debit.date | $KohaDates %]</td>
    <td>
      [% PROCESS account_type_description account=debit %]
      [%- IF debit.description %], [% debit.description | html %][% END %]
    </td>
    <td class='debit'>[% debit.amountoutstanding | $Price %]</td>
  </tr>
  [% END %]
  [% ELSE %]
  <tr>
    <td colspan='3'>There are no outstanding debts on your account.</td>
  </tr>
  [% END %]

    <tfoot>
    <tr>
      <td colspan='2'>
        [% IF borrower.account.balance < 0 %]
         Total credit as of [% today | $KohaDates %]:
        [% ELSE %]
          Total outstanding dues as of  [% today | $KohaDates %]:
        [% END %]
      </td>
      [% IF ( borrower.account.balance <= 0 ) %]<td class='credit'>[% borrower.account.balance * -1 | $Price %]</td>
      [% ELSE %]<td class='debit'>[% borrower.account.balance | $Price %]</td>[% END %]
    </tr>
  </tfoot>
</table>
```

#### Ruotsiksi

Viestityyppi: Tulosta<br />
HTML-viesti: kyllä<br />
Viestin aihe: Avgifter<br />
Viestin sisältö:
```
[% USE Branches %]
[% USE Koha %]
[% USE KohaDates %]
[% USE Price %]
[% PROCESS 'accounts.inc' %]
<table>
  [% IF ( Koha.Preference('LibraryName') ) %]
    <tr>
      <th colspan='3' class='centerednames'>
        <h1>[% Koha.Preference('LibraryName') | html %]</h1>
      </th>
    </tr>
  [% END %]

  <tr>
    <th colspan='3' class='centerednames'>
      <h2>[% Branches.GetName( borrower.branchcode ) | html %]</h2>
    </th>
  </tr>

  <tr>
    <th colspan='3' class='centerednames'>
      <h3>Nuvarande avgifter</h3>
    </th>
  </tr>

  [% IF borrower.account.outstanding_debits.total_outstanding %]
  <tr>
    <th>Datum</th>
    <th>Förklaring</th>
    <th style="text-align:right;">Obetald avgift</th>
  </tr>
  [% FOREACH debit IN borrower.account.outstanding_debits %]
  <tr>
    <td>[% debit.date | $KohaDates %]</td>
    <td>
      [% PROCESS account_type_description account=debit %]
      [%- IF debit.description %], [% debit.description | html %][% END %]
    </td>
    <td class='debit'>[% debit.amountoutstanding | $Price %]</td>
  </tr>
  [% END %]
  [% ELSE %]
  <tr>
    <td colspan='3'>Du har inga obetalda avgifter.</td>
  </tr>
  [% END %]

    <tfoot>
    <tr>
      <td colspan='2'>
       Obetalda avgifter sammanlagt [% today | $KohaDates %]:
      </td>
     <td class='debit'>[% borrower.account.balance | $Price %]</td>
    </tr>
  </tfoot>
</table>
```

## 2FA_OTP_TOKEN

### Email-pohjaan

#### Suomeksi

Viestityyppi: Sähköposti<br />
HTML-viesti: ei<br />
Viestin aihe: Kaksivaiheisen kirjautumisen tunniste<br />
Viestin sisältö:
```
Hei,

Kaksivaiheisen kirjautumisen tunnisteesi on [% otp_token %]. 

Se on voimassa minuutin.
```

#### Englanniksi

Viestityyppi: Sähköposti<br />
HTML-viesti: ei<br />
Viestin aihe: Two-authentication step token<br />
Viestin sisältö:
```
Your authentication token is [% otp_token %].

It is valid one minute.
```

## 2FA_ENABLE

### Email-pohjaan

#### Suomeksi

Viestityyppi: Sähköposti<br />
HTML-viesti: ei<br />
Viestin aihe: Kaksivaiheinen kirjautuminen päällä<br />
Viestin sisältö:
```
Koha-käyttäjätunnuksellesi laitettiin juuri päälle kaksivaiheinen tunnistautuminen. Jos et tehnyt sitä itse, ota yhteys ylläpitoon.
```

#### Englanniksi

Viestityyppi: Sähköposti<br />
HTML-viesti: ei<br />
Viestin aihe: Confirmation of enabling two factor authentication<br />
Viestin sisältö:
```
Two factor authentication was enabled for your Koha account. If you did not do this yourself please contact your administrator.
```

## 2FA_DISABLE 

### Email-pohjaan

#### Suomeksi

Viestityyppi: Sähköposti<br />
HTML-viesti: ei<br />
Viestin aihe: Kaksivaiheinen kirjautuminen pois päältä<br />
Viestin sisältö:
```
Koha-käyttäjätunnuksesi kaksivaiheinen kirjautuminen otettiin pois päältä. Jos et tehnyt sitä itse, ota yhteys ylläpitoon.
```

#### Englanniksi

Viestityyppi: Sähköposti<br />
HTML-viesti: ei<br />
Viestin aihe: Two factor authentication disabled<br />
Viestin sisältö:
```
Two factor authentication was disabled for your Koha account. If you did not do this yourself please contact your administrator.
```

## PASSWORD_CHANGE

### Email-pohjaan

Tämän viestin lähettäminen vaatii, että se sallitaan järjestelmäasetuksessa NotifyPasswordChange.

#### Suomeksi

Viestityyppi: Sähköposti<br />
HTML-viesti: ei<br />
Viestin aihe: Kirjastokorttisi salasana vaihdettiin<br />
Viestin sisältö:
```
Kirjastokorttisi salasana vaihdettiin. Jos et tehnyt sitä itse tai et pyytänyt vaihtoa, ole yhteydessä kirjastoosi.

Ystävällisin terveisin

Vaara-kirjastot
```

#### Englanniksi

Viestityyppi: Sähköposti<br />
HTML-viesti: ei<br />
Viestin aihe: Notification of password change<br />
Viestin sisältö:
```
The password of your librarycard has been changed. If you did not change it yourself (or requested that change), please contact your library.

Best regards

Vaara-kirjastot
```

## HOLD_CHANGED 

Viestipohja liittyy järjestelmäasetukseen ExpireReservesAutoFill eli viesti lähetetään, jos sallitaan vanhentuneiden varausten jäädä automaattisesti kiinni seuraavaan jonossa olevaan varaukseen. Ei liene tarpeellinen.

## NEW_CURBSIDE_PICKUP

Viestillä ilmoitetaan asiakkaalle, että hänellä on noutopalvelussa valmiina nouto. Toiminto vielä tutkinnan alla, joten lisätään tähän pohja, jos joku päättää ottaa toiminnon käyttöön.

## OPAC_REG

Liittyy järjestelmäasetukseen  PatronSelfRegistration, jossa asiakkaat voivat itse rekisteröityä asiakkaaksi Kohan opacissa. Toimintoa ei voi käyttää, koska meillä ei ole käytössä Kohan omaa opacia.

## OVERDUE_FINE_DESC

Tämä ei ole varsinaisesti viestipohja, vaan sillä säädellään, mitä tietoja säilytetään myöhästymismaksun _Kuvauksessa_, kun nide poistetaan.

Myöhästymismaksu ennen siihen liittyvän niteen poistoa:
![kuva](https://user-images.githubusercontent.com/33121325/223685774-d67db8f1-5cdd-421b-b340-0991463d2348.png)

Myöhästymismaksu niteen poiston jälkeen:
![kuva](https://user-images.githubusercontent.com/33121325/223685972-79bac0ac-390c-4bdf-8c8f-03ac7bfc7e7d.png)

Tähän voisi ainakin alustavasti laittaa nämä tiedot:

Viestityyppi: Tulosta
```
[% item.biblio.title %] [% checkout.date_due | $KohaDates %] [% item.barcode %]
```

## STAFF_PASSWORD_RESET

Tämä viestipohja liittyy toimintoon, jossa henkilökunta voi lähettää asiakkaalle sähköpostiviestin, jonka kautta asiakas voi vaihtaa salasanansa. Tämä vaatii Kohan opacin käytön, joten toimintoa ei voida käyttää. Vaatii toimiakseen myös asetuksen OpacResetPassword, jota ei voi laittaa päälle, koska se vaatii Kohan opacin käytön.

![kuva](https://user-images.githubusercontent.com/33121325/223687743-63a37599-07f0-465f-9379-e56177c5e960.png)

![kuva](https://user-images.githubusercontent.com/33121325/223687505-03a1c8f8-0887-46b6-8cf7-6955f346a5ce.png)

## ILL_REQUEST_UPDATE

Liittyy Kaukolaina-moduuliin, joka meillä ei ole käytössä.

## RECEIPT

Liittyy Myyntipiste-moduuliin, joka meillä ei ole käytössä.

## PICKUP_RECALLED_ITEM

Recall on eräänlainen korkean prioriteetin varaus, jonka asiakas voi tehdä (jos asetukset sen sallivat) lainassa olevaan aineistoon. Sen hetkiselle ainaajalle lähtee viesti uudesta eräpäivästä ja pyyntö palauttaa teos. Kun nide palautetaan, jää prioriteettivaraus kiinni ja siitä lähtee tällä pohjalla "noutoilmoitus" prioriteettivarauksen tekijälle. Tämä toiminto ei todennäköisesti sovi yleisten kirjastojen toimintaympäristöön.

Tälle on valmiina Kohassa englanninkielisenä seuraava viestipohja:

Viestityyppi: Sähköposti
```
Date: <<today>>

<<borrowers.firstname>> <<borrowers.surname>>,

A recall that you requested on the following item: <<biblio.title>> / <<biblio.author>> (<<items.barcode>>) is now ready for you to pick up at <<recalls.branchcode>>. Please pick up your item by <<recalls.expirationdate>>.

Thank you!
```

## RECALL_REQUESTER_DET

Recall on eräänlainen korkean prioriteetin varaus, jonka asiakas voi tehdä (jos asetukset sen sallivat) lainassa olevaan aineistoon. Sen hetkiselle lainaajalle lähtee viesti uudesta eräpäivästä ja pyyntö palauttaa teos ja kun se palautetaan, jää prioriteettivaraus kiinni ja siitä tulostuu tällä pohjalla "infokuitti". Tämä toiminto ei todennäköisesti sovi yleisten kirjastojen toimintaympäristöön.

Tälle on Kohassa valmiina englanninkielinen viestipohja.

Viestityyppi: Tulosta
```
Date: <<today>>

Recall for pickup at <<branches.branchname>>
<<borrowers.surname>>, <<borrowers.firstname>> (<<borrowers.cardnumber>>)
<<borrowers.phone>>
<<borrowers.streetnumber>> <<borrowers.address>>, <<borrowers.address2>>, <<borrowers.city>> <<borrowers.zipcode>>
<<borrowers.email>>

ITEM RECALLED
<<biblio.title>> by <<biblio.author>>
Barcode: <<items.barcode>>
Callnumber: <<items.itemcallnumber>>
Waiting since: <<recalls.waitingdate>>
Notes: <<recalls.recallnotes>>
```

## RETURN_RECALLED_ITEM

Recall on eräänlainen korkean prioriteetin varaus, jonka asiakas voi tehdä (jos asetukset sen sallivat) lainassa olevaan aineistoon. Sen hetkiselle lainaajalle lähtee viesti uudesta eräpäivästä ja pyyntö palauttaa teos tällä viestipohjalla. Tämä toiminto ei todennäköisesti sovi yleisten kirjastojen toimintaympäristöön.

Kohassa on valmiina englanninkielinen viestipohja tälle.

Viestityyppi: Sähköposti
```
Date: <<today>>

<<borrowers.firstname>> <<borrowers.surname>>,

A recall has been placed on the following item: <<biblio.title>> / <<biblio.author>> (<<items.barcode>>). The due date has been updated, and is now <<issues.date_due>>. Please return the item before the due date.

Thank you!
```

## WELCOME

Kohassa pystyy lähettämään automaattisesti tai asiakkaan tiedoista käsin asiakkaalle tervetuloviestin, jossa käytetään tätä viestipohjaa. Viestiin voi lisätä esim. linkin kirjaston käyttösääntöihin, verkkokirjastoon, e-kirjastoon yms.

### Email-pohjaan

#### Suomeksi

Viestityyppi: Sähköposti
HTML-viesti: kyllä
Viestin aihe: Tervetuloa Vaara-kirjastojen asiakkaaksi
```
[% USE Koha %]
Hei [% borrower.firstname %].

Tervetuloa Vaara-kirjastojen asiakkaaksi.

<a href='https://vaara.finna.fi'>Verkkokirjastossamme</a> voit uusia lainojasi, etsiä tietoa kirjaston kokoelmista ja tehdä varauksia.

Tutustuthan myös <a href='https://vaara.finna.fi/Content/asiakkaana#userrights'>käyttösääntöihimme</a>.

Jos sinulla on mitä tahansa kysyttävää kirjaston toiminnasta tai aineistostamme, ole meihin yhteydessä. <a href='https://vaara.finna.fi/Content/kirjastot'>Yhteystietomme löytyvät verkkokirjastosta</a>.

Ystävällisin terveisin

Vaara-kirjastot
```

#### Englanniksi

Viestityyppi: Sähköposti
HTML-viesti: kyllä
Viestin aihe: Welcome to Vaara Libraries
```
[% USE Koha %]
Hello [% borrower.firstname %].

Welcome to Vaara Libraries.

<a href='https://vaara.finna.fi'>In our web library</a> you can renew your loans, search for materials and make reservations.

Please read our <a href='https://vaara.finna.fi/Content/asiakkaana#userrights'>library rules of use</a>.

If you have any questions about our library or our services, please do not hesitate to contact us. <a href='https://vaara.finna.fi/Content/kirjastot'>Our contact info</a>.

Best regards

Vaara Libraries
```
