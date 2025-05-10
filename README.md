🔐 Projekt: Inteligentný prístupový systém s čítačkou odtlačkov prstov a ovládaním cez Blynk
🧩 Základná myšlienka projektu
Tento projekt slúži ako moderný elektronický zámok, ktorý umožňuje bezpečný vstup pomocou odtlačku prsta. 
Využíva čítačku odtlačkov, ESP32 mikrokontrolér a mobilnú aplikáciu Blynk na diaľkové ovládanie a monitoring. Systém je určený pre dvere, skrinky, dielne, ale aj domácnosti, kde je požiadavka na jednoduché a rýchle, no zároveň bezpečné odomykanie.


🛠️ Použité komponenty
ESP32	Mozog celého systému – riadi komunikáciu, overovanie odtlačkov, logovanie a pripojenie na Wi-Fi.
Adafruit Fingerprint Sensor (FPM10A)	Snímač odtlačkov prstov – overuje identitu používateľa.
Blynk (mobilná aplikácia)	Slúži ako vzdialené rozhranie – zobrazuje stav, logy a umožňuje otvoriť zámok aj manuálne.
Elektromagnetický zámok (12V)	Fyzické zabezpečenie dverí, ovládané cez výstupný pin ESP32.
Relé 5V 250VAC 10A - Prepúšťa 12V do elektromagnetického zámku
SPIFFS (vstavaný súborový systém ESP32)	Slúži na ukladanie zoznamu používateľov s menom a ID.
RTC modul (virtuálny cez Blynk)	Načítava reálny dátum a čas pre logovanie prístupov.



📲 Ako to funguje?
Overenie identity cez odtlačok prsta
Zariadenie čaká na priloženie prsta
Overí prst cez senzor a databázu ID

Otvorenie zámku:
Po úspešnom overení sa na 3 sekundy aktivuje elektromagnetický zámok

Zobrazovanie informácií v Blynku:
Na V1: Stav priloženia prsta, chyba, alebo privítanie mena
Na V3: Log s ID, menom, dátumom a časom


Kedy je to možné využiť ?
🎯 Možnosti využitia
 Súkromná dielňa / sklad – obmedziť prístup iba na oprávnených ľudí
 Domáce použitie – inteligentné zamykanie dverí
 Školský projekt / prezentácia IoT – názorná ukážka IoT bezpečnosti v praxi

 
Bezpečnosť a legálnosť:

Lokálne uložené dáta
Systém neodosiela žiadne osobné údaje na internet
Systém je vhodný pre domáce použitie



Ak vieš preukázať, že:

1. Existuje oprávnený dôvod, napríklad:

vysoká úroveň bezpečnosti (napr. vstup do miestnosti s citlivými dátami, peniazmi, servermi),
kontrolovaný vstup na pracovisko kvôli ochrane majetku alebo bezpečnosti osôb.


2. Neexistuje menej invazívne riešenie:
Musíš zdokumentovať, že alternatívy ako karty, kódy, čipy nie sú dostatočne bezpečné alebo vhodné.

3. pracovanie je zákonné podľa GDPR a § 16 ods. 2 zákona č. 18/2018 Z.z.:
Biometrické údaje možno spracúvať, ak je to nevyhnutné na splnenie zákonnej povinnosti alebo oprávneného záujmu – a to musíš vedieť preukázať.
Zamestnancom musí byť poskytnutá alternatíva, ak by použitie biometrie nebolo úplne nevyhnutné.



Zápis nových používateľov:
Pomocou druhého skriptu je možné načítať nový prst, priradiť mu ID a meno (napr. "5: Jozef Novák"). Táto informácia sa uloží do interného úložiska (SPIFFS).

Diaľkové ovládanie zámku:
V aplikácii Blynk je tlačidlo (V2), ktorým možno zámok otvoriť manuálne – napr. ak príde kuriér alebo niekto zabudne otlačok.



📋 Funkcie systému
✅ Overenie identity pomocou otlačku prsta

✅ Zobrazenie správ v mobilnej aplikácii (napr. stav priloženia prsta, chýb)

✅ Automatické logovanie prístupov (ID, meno, dátum a čas)

✅ Ukladanie mien k ID pomocou SPIFFS

✅ Ovládanie zámku aj manuálne cez aplikáciu

✅ Všetky dáta zostávajú uložené aj po reštarte (vďaka SPIFFS)

✅ Ochrana proti neoprávnenému vstupu (nezaregistrovaný prst nemá prístup)
