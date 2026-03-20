---
title: 'RDA ja poikkeava pääsana'
permalink: /dokumentaatio/rdanuotti/
redirect_from:
  - /theme-setup/
toc: true
---

Kun esim. nuottiin halutaan RDA-kuvailusäännöistä poikkeava pääsana signumiin ja tarralle, voi ottaa käyttöön sitä varten luodut liitännäiset. 
Lisäksi tarrapohjaan pitää tehdä lisäyksiä.

Tässä ratkaisussa tiedot poimitaan 942im-kentistä normaalien sääntöjen sijaan, jolloin kuvailija pystyy itse määrittämään, mitä tietoja signumiin ja tarralle tulee.

**Marraskuussa 2022 tehtiin muutos**, että kaikki pääsana-liitännäiset tarkistavat ensim 942m-kentän ja jos siellä ei ole sisältöä, toimitaan normaalin pääsana-käytännön mukaisesti.

**Versiossa 25.05** säilytettiin vain seuraavat signum- ja pääsanaliitännäiset:
* signum_builder_ks.pl
* fi_signumbuilder_942k_branchloc_942hm.pl (Vaaran tarve)

## Muutokset kuvailupohjaan

RDA:sta poikkeavia säätöjä ei tarvitse tehdä kaikelle aineistolle, vaan esimerkiksi vain nuottiaineistolle siinä tapauksessa, että RDAn mukainen tekijätieto ei vastaa hyllytyskäytäntöjä.

Esim. Nightwishin musiikkia sisältävä nuotti halutaan hyllyyn Nightwishin mukaisesti eikä säveltäjä Tuomas Holopaisen mukaisesti.

1. Luo uusi kuvailupohja
2. Tuo siihen attachment:export_NUOP.csv -tiedostosta tiedot valitsemalla kuvailupohjan oikeasta reunasta Toiminnot -> Tuo
3. Tarkista, että 
* näkyvillä on 942im-kentät
* 952o-kentässä on signum_builder_ks.pl

Voit tehdä muutokset myös käsin ilman kuvailupohjan tuontia.

## Muutokset tarrapohjiin

Lisää haluamiisi tarrapohjiin sille riville, johon yleensä tulee tekijätieto, ensimmäiseksi määritys 942$i ||

Eli näin:

![](/assets/files/docs/Ohjeet/rda.png)

Käytännössä tuo määrittää, että "hae tieto 942i-kentästä, jos siitä ei löydy, niin 100a-kentästä, jos siitä ei löydy 110a-kentästä, jos siitä ei löydy, niin 111a-kentästä".

## Miten kenttiä käytetään

Yllä määritettyjä 942im-kenttiä tarvitaan, jotta tarralle saadaan tulostettua "normaalista" pääsanasta poikkeava tieto.

![](/assets/files/docs/Ohjeet/rda1.png)
* i-kenttään kirjoitetaan kuvailusäännöistä poikkeava pääsana
* m-kenttään kirjoitetaan poikkeavasta pääsanasta kolme ensimmäistä merkkiä.

Poikkeavat merkinnät pitää saada myös niteen signumiin.

![](/assets/files/docs/Ohjeet/rda2.png)
* klikkaa signumin vieressä olevaa kolmea pistettä, jolloin tiedot haetaan 942m-kentistä normaalin pääsanasäännön sijaan.

Tarralla tieto näyttää sitten esim. OUTI-kirjastoissa tarrarullan pohjalla tältä:

![](/assets/files/docs/Ohjeet/rda3.png)

Ilman yllä mainittuja muutoksia tälle teokselle
![](/assets/files/docs/Ohjeet/rda4.png)

olisi tullut 

* Pääsanaksi: O'Connell, Finneas
* Pääasanan kolme ensimmäistä merkkiä O'C

Päivitetty: 20.3.2026
