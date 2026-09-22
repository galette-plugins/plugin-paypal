---
title: Dokumentacija
description: Paypal integracija
---

> **Opozorilo**
> 
> PayPal opušča svojo podedovano integracijo standarda plačil prek spletnega
> mesta (WPS), pri čemer je popolna prekinitev obdelave transakcij predvidena za
> januar 2027. Ta vtičnik **ni združljiv** z nobeno drugo integracijo.

Ta vtičnik ponuja:

* možnost povezave zneska z vrsto prispevka,
* ustvarite obrazec za plačilo prek PayPala,
* zgodovina,
* samodejno shranjevanje transakcij po potrditvi.

![Nastavitve vtičnika Paypal](images/preferences.png)

![Paypal obrazec za plačilo](images/form.png)

![Paypal obrazec za plačilo (javno)](images/public_form.png)

> **Opozorilo**
> 
> Zaradi načina obdelave plačil prek PayPala, zlasti potrditve plačila, mora
> biti vaš primerek javno dostopen.

## Namestitev

Najprej prenesite vtičnik:

* [Pridobite najnovejši vtičnik
  Paypal!](https://github.com/galette-plugins/plugin-paypal/releases/latest)
* [Pridobite nočno gradnjo vtičnika
  Paypal!](https://github.com/galette-plugins/plugin-paypal/releases/tag/nightly)

Razširite prenesen arhiv v imenik Galette `plugins`. Na primer v Linuxu
(zamenjajte `{url}` in `{version}` s pravilnimi vrednostmi):

```bash
$ cd /var/www/html/galette/plugins
$ wget {url}
$ tar xjvf galette-plugin-paypal-{version}.tar.bz2
```

## Inicializacija baze podatkov

Za delovanje ta vtičnik potrebuje več tabel v bazi podatkov. Glejte [Vmesnik za
upravljanje vtičnikov
Galette](https://doc.galette.eu/en/master/plugins/index.html#plugins-managment).

In to je končano; vtičnik Paypal je nameščen :)

## Konfiguracija vtičnika

Ko je vtičnik nameščen, je v meni dodana skupina `Paypal` z nekaj novimi vnosi:

* `Plačilnica`: sama plačilnica, ki je dostopna kot javna stran,
* `Nastavitve`: nastavitve vtičnikov, dostopne skrbnikom in članom osebja.

Za pravilno delovanje morate vnesti zelo pomembno vrednost: kodo svojega Paypal
računa. Uporabite lahko e-poštni naslov, povezan z vašim Paypal računom (vendar
ga boste morali spremeniti v Galette, če se spremeni v Paypalu), ali pa svojo
identifikacijsko številko trgovca. Če želite najti svojo identifikacijsko
številko trgovca, se prijavite v Paypal in jo boste našli v nastavitvah računa.
Spreminjanje identifikacijske številke je dovoljeno samo skrbnikom.

Zaslon z nastavitvami omogoča tudi urejanje zneskov, povezanih z vrstami
prispevkov, in skrivanje nekaterih vrst.

Po tem lahko vsak uporabnik izbere vrsto prispevka, prilagodi znesek in plača s
svojega Paypal računa. Če je uporabnik prijavljen član in če je vrsta prispevka
podaljšanje članstva, se njegovo članstvo preračuna, ko bo plačilo potrjeno.
