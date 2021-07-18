# IndieGamesPlatform - Platforma za ljubitelje Indie igara
Đorđe Ognjenović, SW-2/2016
## Opis aplikacije
IndieGamesPlatform je platforma gde developeri mogu da postavljaju informacije i novosti (blog postove) o
svojim igrama. Ostali korisnici mogu da ocenjuju i komentarišu igre,
kao i da imaju listu omiljenih igara i listu želja. Takođe, korisnici mogu da pretražuju igre po tagovima, izdavačima i nazivu.
Uloge u sistemu su neregistrovani korisnik, registrovani korisnik, developer, administator (proširenje za diplomski).
## Funkcionalnosti
##### Neregistrovani korisnik:
* login
* registracija
* pregled podataka o igri
* pretrage
* pregled postova
##### Registrovani korisnik:
* sve što ima neregistrovani korisnik
* dodavanje igara u listu omiljenih igara
* dodavanje igara u listu želja
* ocenjivanje igara
* komentarisanje igara
* reagovanje na postove
##### Developer igre:
* sve što može registrovani korisnik
* dodavanje igrice
* objavljivanje postova
* izmena igrice
* brisanje igrice
* brisanje posta
* izmena posta
##### Administrator:
* brisanje postova
* brisanje igrice
* brisanje komentara

## Arhitektura aplikacije
Aplikacija se sastoji od mikroservisa koji će biti implementirani u
pythonu koristeći Flask, Pharo i Go programski jezik. Frontend će biti implementiran u React-u. Za baze podataka će biti korišćeni Postgres i MongoDB.

#### Mikroservisi:
* Mikroservis za korisnike (Python + Postgres) - omogućava korisniku login i registraciju
* Mikroservis za igre (Go + Postgres) - omogućava korisnicima funkcionalnosti vezane za igre
* Mikroservis za pretragu (Python + Postgres) - koristi istu bazu podataka kao i mikroservis za igre i omogućava pretragu
* Mikroservis za postove (Python + MongoDB) - omogućava korisnicima funkcionalnosti vezane za postove
* Mikroservis za ocenjivanje i komentare (Go + MongoDB) - omogućava korisnicima funkcionalnosti vezane za komentare i ocenjivanje
* Mikroservis za liste zelja i omiljene igre (Pharo + Postgres) - omogućava korisnicima funkcionalnosti vezane za liste omiljenih igara i zelja
* React klijent - komunicira sa svim ostalim mikroservisima
