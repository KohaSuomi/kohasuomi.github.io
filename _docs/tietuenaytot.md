---
title: 'Tietuenäyttöjen mukautukset'
permalink: /dokumentaatio/tietuenaytot/
redirect_from:
  - /theme-setup/
toc: true
---

## Perustiedot-näyttö

Lisää näin: Työkalut -> Tietuenäyttöjen mukautukset -> Luo uusi -> StaffDetailPage alasvetovalikosta -> muista valita Publication date -kohtaan se päivä, mistä lähtien haluat määritysten näkyvän (valitse tämä päivä)

Englanniksi:
```
<!-- Aineistotyyppi -->
[% IF record.subfield('942' , 'c') %]
  <span class="results_summary materialtype">
      <span class="label">Material type: </span>
      [% record.subfield('942' , 'c') %]
  </span>
[% END %]

<!-- Sidosasu -->
[% SET qs = [] %]

[% FOREACH f IN record.fields %]
    [% IF f.tag == '020' %]
        [% FOREACH sf IN f.subfields %]
            [% IF sf.0 == 'q' %]
                [% qs.push(sf.1) %]
            [% END %]
        [% END %]
    [% END %]
[% END %]

[% IF qs.size %]
  <span class="results_summary binding">
      <span class="label">Binding form: </span>
      [% qs.join('; ') %]
  </span>
[% END %]

<!-- Ikäraja -->
[% IF record.subfield('049','c') %]
  <span class="results_summary agelimit">
      <span class="label">Age limit: </span>
      [% record.subfield('049','c') %]
  </span>
[% END %]

<!-- Tuottajan maa -->
[% SET values = [] %]

[% FOREACH f IN record.fields %]
  [% IF f.tag == '257' %]
    [% FOREACH sf IN f.subfields %]
      [% IF sf.0 == 'a' && sf.1 %]
        [% values.push(sf.1) %]
      [% END %]
    [% END %]
  [% END %]
[% END %]

[% IF values.size %]
  <span class="results_summary producing_country">
    <span class="label">Producing country: </span>
    [% values.join(', ') %]
  </span>
[% END %]


<!-- Ilmestymistiheys -->

[% IF record.subfield('310' , 'a') %]
  <span class="results_summary publication_frequency">
      <span class="label">Current publication frequency: </span>
      [% record.subfield('310' , 'a') %]
  </span>
[% END %]

<!-- Tiedostomuoto -->

[% vals = [] %]
[% FOREACH f IN record.fields %]
  [% IF f.tag == '347' %]
    [% FOREACH sf IN f.subfields %]
      [% IF sf.0 == 'b' %]
        [% vals.push(sf.1) %]
      [% END %]
    [% END %]
  [% END %]
[% END %]

[% IF vals.size %]
  <span class="results_summary encoding_format">
    <span class="label">Encoding format: </span>
    [% vals.join(', ') %]
  </span>
[% END %]

<!-- Liittyvä paikka -->

[% SET parts = [] %]
[% IF record.subfield('370','c'); parts.push(record.subfield('370','c')); END %]
[% IF record.subfield('370','f'); parts.push(record.subfield('370','f')); END %]
[% IF record.subfield('370','g'); parts.push(record.subfield('370','g')); END %]

[% IF parts.size %]
  <span class="results_summary associated_place">
      <span class="label">Associated place: </span>
      [% parts.join(', ') %]
  </span>
[% END %]

<!-- Esityskokoonpano -->
[% SET allparts = [] %]

[% FOREACH f IN record.fields %]
  [% IF f.tag != '382' %]
    [% NEXT %]
  [% END %]

  [% SET parts = [] %]
  [% SET prefix = '' %]

  [% FOREACH sf IN f.subfields %]

    [% IF sf.0 == '3' %]
      [% prefix = sf.1 _ ': ' %]

    [% ELSIF sf.0 == 'a' || sf.0 == 'b' %]
      [% parts.push(sf.1) %]

    [% ELSIF sf.0 == 'n' || sf.0 == 'e' %]
      [% SET idx = parts.size - 1 %]
      [% IF idx >= 0 %]
        [% parts.$idx = parts.$idx _ ' (' _ sf.1 _ ')' %]
      [% END %]

    [% END %]

  [% END %]

  [% IF parts.size %]
    [% allparts.push(prefix _ parts.join(', ')) %]
  [% END %]

[% END %]

[% IF allparts.size %]
  <span class="results_summary performance_medium">
    <span class="label">Performance medium: </span>
    [% allparts.join('; ') %]
  </span>
[% END %]

<!-- Tekijän ominaisuudet -->
[% SET parts = [] %]
[% IF record.subfield('386','m'); parts.push(record.subfield('386','m')); END %]
[% IF record.subfield('386','a'); parts.push(record.subfield('386','a')); END %]

[% IF parts.size %]
  <span class="results_summary creator_characteristics">
      <span class="label">Creator/contributor characteristics: </span>
      [% parts.join(': ') %]
  </span>
[% END %]

<!-- Luomisaika -->
[% SET values = [] %]

[% FOREACH f IN record.fields %]
  [% IF f.tag == '388' %]
    [% FOREACH sf IN f.subfields %]
      [% IF sf.0 == 'a' %]
        [% values.push(sf.1) %]
      [% END %]
    [% END %]
  [% END %]
[% END %]

[% IF values.size %]
  <span class="results_summary creation_time">
    <span class="label">Creation time: </span>
    [% values.join(', ') %]
  </span>
[% END %]
```

Suomeksi:
```
<!-- Aineistotyyppi -->
[% IF record.subfield('942' , 'c') %]
  <span class="results_summary materialtype">
      <span class="label">Aineistotyyppi: </span>
      [% record.subfield('942' , 'c') %]
  </span>
[% END %]

<!-- Sidosasu -->
[% SET qs = [] %]

[% FOREACH f IN record.fields %]
    [% IF f.tag == '020' %]
        [% FOREACH sf IN f.subfields %]
            [% IF sf.0 == 'q' %]
                [% qs.push(sf.1) %]
            [% END %]
        [% END %]
    [% END %]
[% END %]

[% IF qs.size %]
  <span class="results_summary binding">
      <span class="label">Sidosasu: </span>
      [% qs.join('; ') %]
  </span>
[% END %]

<!-- Ikäraja -->
[% IF record.subfield('049','c') %]
  <span class="results_summary agelimit">
      <span class="label">Ikäraja: </span>
      [% record.subfield('049','c') %]
  </span>
[% END %]

<!-- Tuottajan maa -->
[% SET values = [] %]

[% FOREACH f IN record.fields %]
  [% IF f.tag == '257' %]
    [% FOREACH sf IN f.subfields %]
      [% IF sf.0 == 'a' && sf.1 %]
        [% values.push(sf.1) %]
      [% END %]
    [% END %]
  [% END %]
[% END %]

[% IF values.size %]
  <span class="results_summary producing_country">
    <span class="label">Tuottajan maa: </span>
    [% values.join(', ') %]
  </span>
[% END %]

<!-- Ilmestymistiheys -->
[% IF record.subfield('310' , 'a') %]
  <span class="results_summary publication_frequency">
      <span class="label">Nykyinen ilmestymistiheys: </span>
      [% record.subfield('310' , 'a') %]
  </span>
[% END %]

<!-- Tiedostomuoto -->
[% vals = [] %]
[% FOREACH f IN record.fields %]
  [% IF f.tag == '347' %]
    [% FOREACH sf IN f.subfields %]
      [% IF sf.0 == 'b' %]
        [% vals.push(sf.1) %]
      [% END %]
    [% END %]
  [% END %]
[% END %]

[% IF vals.size %]
  <span class="results_summary encoding_format">
    <span class="label">Tiedostomuoto: </span>
    [% vals.join(', ') %]
  </span>
[% END %]

<!-- Liittyvä paikka -->
[% SET parts = [] %]
[% IF record.subfield('370','c'); parts.push(record.subfield('370','c')); END %]
[% IF record.subfield('370','f'); parts.push(record.subfield('370','f')); END %]
[% IF record.subfield('370','g'); parts.push(record.subfield('370','g')); END %]

[% IF parts.size %]
  <span class="results_summary associated_place">
      <span class="label">Liittyvä paikka: </span>
      [% parts.join(', ') %]
  </span>
[% END %]


<!-- Esityskokoonpano -->
[% SET allparts = [] %]

[% FOREACH f IN record.fields %]
  [% IF f.tag != '382' %]
    [% NEXT %]
  [% END %]

  [% SET parts = [] %]
  [% SET prefix = '' %]

  [% FOREACH sf IN f.subfields %]

    [% IF sf.0 == '3' %]
      [% prefix = sf.1 _ ': ' %]

    [% ELSIF sf.0 == 'a' || sf.0 == 'b' %]
      [% parts.push(sf.1) %]

    [% ELSIF sf.0 == 'n' || sf.0 == 'e' %]
      [% SET idx = parts.size - 1 %]
      [% IF idx >= 0 %]
        [% parts.$idx = parts.$idx _ ' (' _ sf.1 _ ')' %]
      [% END %]

    [% END %]

  [% END %]

  [% IF parts.size %]
    [% allparts.push(prefix _ parts.join(', ')) %]
  [% END %]

[% END %]

[% IF allparts.size %]
  <span class="results_summary performance_medium">
    <span class="label">Esityskokoonpano: </span>
    [% allparts.join('; ') %]
  </span>
[% END %]

<!-- Tekijän ominaisuudet -->
[% SET parts = [] %]
[% IF record.subfield('386','m'); parts.push(record.subfield('386','m')); END %]
[% IF record.subfield('386','a'); parts.push(record.subfield('386','a')); END %]

[% IF parts.size %]
  <span class="results_summary creator_characteristics">
      <span class="label">Tekijän ominaisuudet: </span>
      [% parts.join(': ') %]
  </span>
[% END %]

<!-- Luomisaika -->
[% SET values = [] %]

[% FOREACH f IN record.fields %]
  [% IF f.tag == '388' %]
    [% FOREACH sf IN f.subfields %]
      [% IF sf.0 == 'a' %]
        [% values.push(sf.1) %]
      [% END %]
    [% END %]
  [% END %]
[% END %]

[% IF values.size %]
  <span class="results_summary creation_time">
    <span class="label">Luomisaika: </span>
    [% values.join(', ') %]
  </span>
[% END %]
```

Ruotsiksi:
```
<!-- Aineistotyyppi -->
[% IF record.subfield('942' , 'c') %]
  <span class="results_summary materialtype">
      <span class="label">Materialtyp: </span>
      [% record.subfield('942' , 'c') %]
  </span>
[% END %]

<!-- Sidosasu -->
[% SET qs = [] %]

[% FOREACH f IN record.fields %]
    [% IF f.tag == '020' %]
        [% FOREACH sf IN f.subfields %]
            [% IF sf.0 == 'q' %]
                [% qs.push(sf.1) %]
            [% END %]
        [% END %]
    [% END %]
[% END %]

[% IF qs.size %]
  <span class="results_summary binding">
      <span class="label">Bokbinding: </span>
      [% qs.join('; ') %]
  </span>
[% END %]

<!-- Ikäraja -->
[% IF record.subfield('049','c') %]
  <span class="results_summary agelimit">
      <span class="label">Åldersgräns: </span>
      [% record.subfield('049','c') %]
  </span>
[% END %]


<!-- Tuottajan maa -->
[% SET values = [] %]

[% FOREACH f IN record.fields %]
  [% IF f.tag == '257' %]
    [% FOREACH sf IN f.subfields %]
      [% IF sf.0 == 'a' && sf.1 %]
        [% values.push(sf.1) %]
      [% END %]
    [% END %]
  [% END %]
[% END %]

[% IF values.size %]
  <span class="results_summary producing_country">
    <span class="label">Land för produktionsenhet/-bolag: </span>
    [% values.join(', ') %]
  </span>
[% END %]


<!-- Ilmestymistiheys -->
[% IF record.subfield('310' , 'a') %]
  <span class="results_summary publication_frequency">
      <span class="label">Nuvarande utgivningsfrekvens: </span>
      [% record.subfield('310' , 'a') %]
  </span>
[% END %]

<!-- Tiedostomuoto -->
[% vals = [] %]
[% FOREACH f IN record.fields %]
  [% IF f.tag == '347' %]
    [% FOREACH sf IN f.subfields %]
      [% IF sf.0 == 'b' %]
        [% vals.push(sf.1) %]
      [% END %]
    [% END %]
  [% END %]
[% END %]

[% IF vals.size %]
  <span class="results_summary encoding_format">
    <span class="label">Format för kodning: </span>
    [% vals.join(', ') %]
  </span>
[% END %]

<!-- Liittyvä paikka -->
[% SET parts = [] %]
[% IF record.subfield('370','c'); parts.push(record.subfield('370','c')); END %]
[% IF record.subfield('370','f'); parts.push(record.subfield('370','f')); END %]
[% IF record.subfield('370','g'); parts.push(record.subfield('370','g')); END %]

[% IF parts.size %]
  <span class="results_summary associated_place">
      <span class="label">Associerad plats/ort: </span>
      [% parts.join(', ') %]
  </span>
[% END %]


<!-- Esityskokoonpano -->
<!-- Esityskokoonpano -->
[% SET allparts = [] %]

[% FOREACH f IN record.fields %]
  [% IF f.tag != '382' %]
    [% NEXT %]
  [% END %]

  [% SET parts = [] %]
  [% SET prefix = '' %]

  [% FOREACH sf IN f.subfields %]

    [% IF sf.0 == '3' %]
      [% prefix = sf.1 _ ': ' %]

    [% ELSIF sf.0 == 'a' || sf.0 == 'b' %]
      [% parts.push(sf.1) %]

    [% ELSIF sf.0 == 'n' || sf.0 == 'e' %]
      [% SET idx = parts.size - 1 %]
      [% IF idx >= 0 %]
        [% parts.$idx = parts.$idx _ ' (' _ sf.1 _ ')' %]
      [% END %]

    [% END %]

  [% END %]

  [% IF parts.size %]
    [% allparts.push(prefix _ parts.join(', ')) %]
  [% END %]

[% END %]

[% IF allparts.size %]
  <span class="results_summary performance_medium">
    <span class="label">Uppsättning för framförande av musikaliska verk: </span>
    [% allparts.join('; ') %]
  </span>
[% END %]


<!-- Tekijän ominaisuudet -->
[% SET parts = [] %]
[% IF record.subfield('386','m'); parts.push(record.subfield('386','m')); END %]
[% IF record.subfield('386','a'); parts.push(record.subfield('386','a')); END %]

[% IF parts.size %]
  <span class="results_summary creator_characteristics">
      <span class="label">Upphovs-/medverkandekategori: </span>
      [% parts.join(': ') %]
  </span>
[% END %]

<!-- Luomisaika -->
[% SET values = [] %]

[% FOREACH f IN record.fields %]
  [% IF f.tag == '388' %]
    [% FOREACH sf IN f.subfields %]
      [% IF sf.0 == 'a' %]
        [% values.push(sf.1) %]
      [% END %]
    [% END %]
  [% END %]
[% END %]

[% IF values.size %]
  <span class="results_summary creation_time">
    <span class="label">Tidsperiod under vilken verket/uttrycket ursprungligen skapades: </span>
    [% values.join(', ') %]
  </span>
[% END %]
```

## Hakutuloslista

Lisää näin: Työkalut -> Tietuenäyttöjen mukautukset -> Luo uusi -> StaffResultsPage alasvetovalikosta -> muista valita Publication date -kohtaan se päivä, mistä lähtien haluat määritysten näkyvän (valitse tämä päivä)

Suomeksi:
```
<!-- Aineistotyyppi -->
[% IF record.subfield('942' , 'c') %]
  <span class="results_summary materialtype">
      <span class="label">Aineistotyyppi: </span>
      [% record.subfield('942' , 'c') %]
  </span>
[% END %]

<!-- Sidosasu -->
[% SET qs = [] %]

[% FOREACH f IN record.fields %]
    [% IF f.tag == '020' %]
        [% FOREACH sf IN f.subfields %]
            [% IF sf.0 == 'q' %]
                [% qs.push(sf.1) %]
            [% END %]
        [% END %]
    [% END %]
[% END %]

[% IF qs.size %]
  <span class="results_summary binding">
      <span class="label">Sidosasu: </span>
      [% qs.join('; ') %]
  </span>
[% END %]

<!-- Ikäraja -->
[% IF record.subfield('049','c') %]
  <span class="results_summary agelimit">
      <span class="label">Ikäraja: </span>
      [% record.subfield('049','c') %]
  </span>
[% END %]

<!-- Muu luokitus -->
[% IF record.subfield('084' , 'a') %]
  <span class="results_summary ykl">
      <span class="label">Muu luokitus: </span>
      [% record.subfield('084' , 'a') %]
  </span>
[% END %]
```

Ruotsiksi:
```
<!-- Aineistotyyppi -->
[% IF record.subfield('942' , 'c') %]
  <span class="results_summary materialtype">
      <span class="label">Materialtyp: </span>
      [% record.subfield('942' , 'c') %]
  </span>
[% END %]

<!-- Sidosasu -->
[% SET qs = [] %]

[% FOREACH f IN record.fields %]
    [% IF f.tag == '020' %]
        [% FOREACH sf IN f.subfields %]
            [% IF sf.0 == 'q' %]
                [% qs.push(sf.1) %]
            [% END %]
        [% END %]
    [% END %]
[% END %]

[% IF qs.size %]
  <span class="results_summary binding">
      <span class="label">Bokbinding: </span>
      [% qs.join('; ') %]
  </span>
[% END %]

<!-- Ikäraja -->
[% IF record.subfield('049','c') %]
  <span class="results_summary agelimit">
      <span class="label">Åldersgräns: </span>
      [% record.subfield('049','c') %]
  </span>
[% END %]

<!-- Muu luokitus -->
[% IF record.subfield('084' , 'a') %]
  <span class="results_summary ykl">
      <span class="label">Annan klassificering: </span>
      [% record.subfield('084' , 'a') %]
  </span>
[% END %]
```

Englanniksi:
```
<!-- Aineistotyyppi -->
[% IF record.subfield('942' , 'c') %]
  <span class="results_summary materialtype">
      <span class="label">Material type: </span>
      [% record.subfield('942' , 'c') %]
  </span>
[% END %]

<!-- Sidosasu -->
[% SET qs = [] %]

[% FOREACH f IN record.fields %]
    [% IF f.tag == '020' %]
        [% FOREACH sf IN f.subfields %]
            [% IF sf.0 == 'q' %]
                [% qs.push(sf.1) %]
            [% END %]
        [% END %]
    [% END %]
[% END %]

[% IF qs.size %]
  <span class="results_summary binding">
      <span class="label">Binding form: </span>
      [% qs.join('; ') %]
  </span>
[% END %]

<!-- Ikäraja -->
[% IF record.subfield('049','c') %]
  <span class="results_summary agelimit">
      <span class="label">Age limit: </span>
      [% record.subfield('049','c') %]
  </span>
[% END %]

<!-- Muu luokitus -->
[% IF record.subfield('084' , 'a') %]
  <span class="results_summary ykl">
      <span class="label">Other classification: </span>
      [% record.subfield('084' , 'a') %]
  </span>
[% END %]
```
