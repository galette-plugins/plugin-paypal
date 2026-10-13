---
title: Dokumentacija
description: Integracija s PayPalom
---

> **Upozorenje**
> 
> PayPal ukida staru integraciju Website Payments Standard (WPS), a potpuni
> prestanak obrade transakcija planiran je za siječanj 2027. Dodatak **nije
> kompatibilan** ni s jednom drugom integracijom.

Dodatak omogućuje:

* pridruživanje iznosa vrsti uplate,
* izradu obrasca za plaćanje putem PayPala,
* pregled povijesti,
* automatsko spremanje transakcije nakon potvrde.

![Postavke dodatka PayPal](images/preferences.png)

![Obrazac za plaćanje putem PayPala](images/form.png)

![Obrazac za plaćanje putem PayPala (javni)](images/public_form.png)

> **Upozorenje**
> 
> Zbog načina obrade PayPal plaćanja, posebno potvrde plaćanja, instalacija mora
> biti javno dostupna.

## Instalacija

Najprije preuzmite dodatak:

* [Preuzmite najnoviji dodatak
  PayPal!](https://github.com/galette-plugins/plugin-paypal/releases/latest)
* [Preuzmite noćnu razvojnu verziju dodatka
  PayPal!](https://github.com/galette-plugins/plugin-paypal/releases/tag/nightly)

Raspakirajte preuzetu arhivu u Galetteovu mapu `plugins`. Primjerice, na Linuxu
(zamijenite `{url}` i `{version}` odgovarajućim vrijednostima):

```bash
$ cd /var/www/html/galette/plugins
$ wget {url}
$ tar xjvf galette-plugin-paypal-{version}.tar.bz2
```

## Inicijalizacija baze podataka

Dodatak zahtijeva nekoliko tablica u bazi. Pogledajte [sučelje za upravljanje
dodacima
Galettea](https://doc.galette.eu/en/master/plugins/index.html#plugins-managment).

Gotovo; dodatak PayPal je instaliran :)

## Podešavanje dodatka

Nakon instalacije u izbornik se dodaje odjeljak `Paypal` s novim stavkama:

* `Obrazac za plaćanje`: sam obrazac, dostupan kao javna stranica,
* `Postavke`: postavke dodatka dostupne administratorima i upravi.

Za ispravan rad morate unijeti identifikator PayPal računa. Možete koristiti
povezanu adresu e-pošte, ali je tada treba promijeniti i u Galetteu ako je
promijenite u PayPalu, ili identifikator trgovca. Potonji ćete pronaći u
postavkama PayPal računa nakon prijave. Identifikator smiju mijenjati samo
administratori.

U postavkama možete uređivati iznose za vrste uplata i sakriti pojedine vrste.

Nakon toga svaki korisnik može odabrati vrstu uplate, prilagoditi iznos i
platiti svojim PayPal računom. Ako je korisnik prijavljeni član i odabrana vrsta
produljuje članstvo, članstvo se preračunava nakon potvrde plaćanja.
