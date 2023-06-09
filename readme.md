# Zápočet 1
## Simulátor základní části MS v ledním hokeji 2023

## https://github.com/hridel/fei23_zap1


Napište program v jazyce C, který bude simulovat základní část MS v ledním hokeji.

Nadefinujte vlastní strukturu představující záznam jednoho týmu v tabulce skupiny MS.
Struktura bude reflektovat data z CSV souboru disponujícího následujícími sloupci:
* _id_ (3 znaky)
* _team_ (název týmu)
* _group_ (skupina _A_ nebo _B_)
* _games_ (počet odehraných zápasů)
* _wins_ (počet výher v základní hrací době)
* _wins_ot_ (počet výher v prodloužení nebo v samostatných nájezdech)
* _losses_ (počet proher v základní hrací době)
* _losses_ot_ (počet proher v prodloužení nebo v samostatných nájezdech)
* _gf_ (počet vstřelených gólů)
* _ga_ (počet obdržených gólů)
* _pts_ (získané body)

Z přiloženého CSV (comma separated values) souboru [input.csv](data%2Finput.csv) načtěte týmy do dynamicky alokovaných polí pro dvě skupiny
(_skupina A_ a _skupina B_ jsou dány sloupcem `group`).

**Ukázka souboru:**

| id | team | group | games | wins | wins\_ot | losses\_ot | losses | gf | ga | pts |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| GER | Germany | A | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |

Dále připravte sadu funkcí pro simulování základní části turnaje:

* _odehraj skupinu_ – funkce přijme jako parametr ukazatel na příslušnou skupinu týmů, mezi kterými se odehraje vždy jeden zápas "každý s každým"
* _odehraj zápas_ – funkce přijme dva týmy ze skupiny a vygeneruje výsledek (skóre, výhra/prohra v základní části nebo
v prodloužení a počet bodů), aktualizuje data obou týmů. Výsledek zápasu vypíše na obrazovku.
    * rozdělování bodů: Na každý zápas jsou k dispozici celkem 3 body.
        * tým, který vyhraje v základní době, dostane 3 body
        * tým, který prohraje v základní době, dostane 0 bodů
        * pokud základní doba skončí remízou, prodlužuje se
            * tým, který vyhraje v prodloužení dostane 2 body
            * tým, který prohraje v prodloužení dostane 1 bod

V hlavním programu potom spusťte odehrání skupin a každou skupinu seřaďte sestupně podle klíče:
* počet bodů
* rozdíl skóre
* počet vstřelených branek

Utříděné skupiny s výslednými daty týmů vypište na obrazovku a zapište do CSV souboru.

---

_V programu proveďte smysluplné pojmenování potřebných proměnných a funkcí.
Do STAGu do odevzdávání semestrálních prací nahrajte ZIP soubor obsahující
zdrojové kódy (*.c, případně *.h) a výsledný CSV soubor, který je výstupem programu._
