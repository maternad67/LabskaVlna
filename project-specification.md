# Projektová specifikace a datová základna: Labská Vlna 2027

## Identita festivalu

| Atribut | Hodnota |
| :--- | :--- |
| **Název** | Labská Vlna |
| **Ročník** | 1. ročník |
| **Lokalita** | Kemp u řeky, Kostelec nad Labem |
| **Datumový rozsah** | 18. června – 20. června 2027 (3 dny) |
| **Charakter festivalu** | Letní open-air festival elektronické hudby u vody |
| **Hlavní žánry nebo témata** | Techno, Drum & Bass, House, Trance, Dubstep |

## Účel webu

*   **K čemu web slouží:** Web je navržen jako hlavní informační portál a digitální průvodce pro návštěvníky nového festivalu elektronické hudby. Poskytuje detailní přehled o umělcích, slouží k nákupu vstupenek a funguje jako nezbytný nástroj pro orientaci v nočním programu přímo na místě.
*   **Hlavní cíle:** Prvotním cílem je nalákat fanoušky elektronické hudby na vizuálně atraktivní prezentaci festivalu a bezproblémově jim prodat vstupenky. Během samotné akce je cílem zajistit, aby se návštěvníci snadno orientovali v areálu i v harmonogramu a měli k dispozici veškeré logistické instrukce (stanování, doprava).
*   **Důležité akce uživatelů:**
    *   Výběr a nákup vhodného typu vstupenky (Standard, VIP, Jednodenní).
    *   Vyhledávání a filtrování konkrétních DJs podle subžánrů elektronické hudby.
    *   Procházení časového harmonogramu (Timetable) rozděleného podle scén (Riverbass Stage vs. Pulse Shelter).
    *   Sestavování vlastního osobního programu (ukládání setů do oblíbených).
    *   Zjišťování praktických informací pro bezproblémové kempování a dopravu do areálu.

## Cílové skupiny

1.  **Fanoušci elektronické hudby a Ravers (18–35 let)**
    *   **Potřeby:** Zjistit přesné časy setů svých oblíbených interpretů napříč scénami, aby dokázali plynule přecházet mezi pódii a nepropásli hlavní headlinery. Rychle nakoupit lístek.
    *   **Očekávání:** Responzivní, tmavý "dark mode" design, který neoslňuje v noci. Web se musí rychle načítat i v místech s horším mobilním signálem uprostřed davu.
    *   **Informace a funkce:** Přehledný ceník vstupenek, interaktivní Timetable s možností filtrace, detailní profily interpretů, možnost vytvořit si vlastní line-up.
2.  **Místní obyvatelé z okolí Kostelce a běžní návštěvníci kempu**
    *   **Potřeby:** Zjistit dopravní omezení, kapacity parkovišť, pravidla chování v kempu a informace o hlukových limitech (dokdy trvá noční produkce).
    *   **Očekávání:** Snadno dohledatelné oficiální informace bez nutnosti probírat se hudebním obsahem. Zřetelné kontakty na pořadatele.
    *   **Informace a funkce:** Přehledná sekce FAQ, mapa areálu s vyznačenými zónami a únikovými východy, jízdní řády kyvadlové dopravy.

## Informační architektura

**Struktura webu / sitemap:**
*   Úvodní stránka (Rozcestník, vizuál, aktuality)
*   Vstupenky (Ceník a možnosti nákupu)
*   Timetable (Časový harmonogram s rozdělením na dny a scény)
*   DJs / Line-up (Seznam 60 interpretů s filtrem žánrů)
    *   Detail interpreta
*   Scény (Kapacita a zaměření Riverbass Stage a Pulse Shelter)
*   Můj festival (Osobní program a uložené sety)
*   Info & Kemp (Doprava, ubytování, pravidla a FAQ)

**Hlavní navigace:** 
Trvale ukotvené menu v horní části webu: `Domů | Vstupenky | Timetable | DJs | Můj festival | Info & Kemp`.

**Vztahy a popis jednotlivých částí:**
*   *Úvodní stránka:* Slouží jako rozcestník na nejdůležitější sekce s CTA tlačítkem k nákupu.
*   *Vstupenky:* Přehled typů lístků (Standard, VIP, Jednodenní) s možností okamžitého nákupu do košíku.
*   *Timetable:* Časová osa vystoupení. Kliknutím na set se otevře detail interpreta.
*   *DJs / Line-up:* Abecední seznam s možností filtrace (DnB, Techno, House). Proklik vede na samostatný profil interpreta, kde je zobrazen i čas a místo jeho vystoupení.
*   *Můj festival (Interaktivní část):* Zde se shromažďují sety, které si uživatel označil v programu hvězdičkou. Funguje to jako personalizovaný harmonogram.

**Zařazování programu po půlnoci (Datová vs. Prezentační logika):**
Datová základna webu ukládá kalendářní data přesně chronologicky (set v sobotu v 01:00 ráno má u sebe datum 19. 6.). Na uživatelském rozhraní (frontendu) v sekci Timetable se však tyto sety logicky řadí pod "Páteční večer", protože tvoří jeden souvislý programový blok (páteční program trvá od 18:00 do 04:00 následujícího dne).

## Uživatelské scénáře

**Scénář 1: Plánování nočního maratonu a uložení do vlastního programu**
*   **Typ uživatele:** Fanoušek Drum & Bass.
*   **Cíl:** Zjistit, v kolik hraje hlavní hvězda páteční DnB scény, uložit si ji a mít ji rychle po ruce.
*   **Výchozí situace:** Uživatel sedí s kamarády u stanu v pátek večer a na mobilním telefonu domlouvají, kdy vyrazí do areálu.
*   **Očekávaný výsledek:** Uživatel na webu otevře "Timetable", vybere páteční program a zaměří se na sloupec "Riverbass Stage". Zjistí, že hlavní set probíhá v čase 01:00 (v rámci pátečního nočního bloku) a klikne u něj na ikonu hvězdičky (uložit). Pro opětovné zobrazení svého výběru v průběhu noci uživatel kdykoliv klikne v navigaci na "Můj festival".

**Scénář 2: Objevování Techno producentů**
*   **Typ uživatele:** Milovník underground techna.
*   **Cíl:** Najít všechny Techno DJs v line-upu a seznámit se s jejich profily.
*   **Výchozí situace:** Uživatel si prohlíží web před nákupem lístku a chce zjistit, kolik "Techno" a "Hard Techno" jmen letos vystoupí.
*   **Očekávaný výsledek:** Přejde na stránku "DJs" přes hlavní navigaci. Klikne na filtr "Techno". Zobrazí se mu vyfiltrovaný seznam (např. interpret Kaelen, X-Form). Klikne na jedno z jmen a na stránce detailu si přečte profil a zjistí, že interpret hraje na "Pulse Shelter" scéně.

**Scénář 3: Informace o kyvadlové dopravě**
*   **Typ uživatele:** Návštěvník, který jede na festival poprvé vlakem.
*   **Cíl:** Zjistit, jak a v jakých intervalech se dostane z nádraží do areálu kempu.
*   **Výchozí situace:** Uživatel právě sedí ve vlaku směřujícím do Kostelce a potřebuje logistické instrukce k příjezdu.
*   **Očekávaný výsledek:** Uživatel klikne v navigaci na "Info & Kemp". V postranním menu zvolí sekci "Doprava", kde ihned vidí mapku nádraží, místo nástupu do kyvadlového autobusu a frekvenci jeho odjezdů.

**Scénář 4: Nákup vstupenky**
*   **Typ uživatele:** Nový zájemce o festival.
*   **Cíl:** Zjistit ceny a koupit lístek na celý víkend.
*   **Výchozí situace:** Uživatel zhlédl úvodní stránku, rozhodl se, že na akci pojede, a chce si rovnou zajistit vstup.
*   **Očekávaný výsledek:** V navigaci klikne na "Vstupenky", prohlédne si rozdíl mezi Standard a VIP passy, a u vybrané varianty klikne na "Koupit vstupenku", což ho navede na simulovanou platební bránu.
