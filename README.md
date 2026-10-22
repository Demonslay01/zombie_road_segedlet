Három különálló, de azonos célú HTML-ről beszélünk:
1. Zombie Road – Karakterlap: digitális, interaktív játékoskarakter-lap.
2. Zombie Road – Harcvezérlő: mesélői harckezelő és szabálysegéd.
3. Zombie Road – Kalandkezelő: kalandok, jelenetek és történetszálak szervezésére szolgáló mesélői felület.
Mindhárom célja, hogy az asztali szerepjáték során csökkentse az adminisztrációt, gyorsítsa a játékvezetést, és kiváltsa a papíralapú nyilvántartás egy részét.

Alapvető tervezési elvek
A projektben következetesen az egyszerű, önálló működést részesítettük előnyben.
- Nincs szükség szerveroldali alkalmazásra vagy adatbázisra.
- A HTML-fájl közvetlenül megnyitható a böngészőben.
- Az adatok JSON-fájlokkal hordozhatók és visszaállíthatók.
- A felületet játék közbeni gyors használatra terveztük.
- A gyakran módosított számértékekhez közvetlen vezérlőgombok tartoznak.
- Az alkalmazások külön is használhatók, nem követelik meg egymás jelenlétét.
- A fejlesztés során elsődleges szempont a meglévő funkciók megőrzése és a fokozatos bővíthetőség.

2. Zombie Road – Interaktív karakterlap
Ez a leginkább játékosközpontú eszköz. Feladata a karakter adatainak, erőforrásainak, felszerelésének, képességeinek és jegyzeteinek kezelése.

A számszerű erőforrásokhoz + és − gombok tartoznak, így a játékosnak nem kell minden változásnál számot begépelnie.

Az értékek a megengedett tartományokon belül maradnak. A Kitartás például nem csökkenhet nulla alá.

A karakterlaphoz vizuális állapot- és tartományjelzőket is terveztünk, hogy a fontos értékek egy pillantással áttekinthetők legyenek.
Harci akciók és AP-kezelés
A karakterlap nem pusztán tárolja az AP-értéket, hanem a harci cselekvések használatát is támogatja.
- Az elérhető harci cselekvésekhez AP-költség tartozik.
- A kiválasztott cselekvés levonja a szükséges AP-t.
- A felület az aktuális AP-állapotot mutatja.
- Az „Új kör” gomb visszaállítja a körre járó AP-t.
- A harci súgó segíti a szabályok gyors értelmezését.
A harci súgót később a konkrét szabályszövegek részletes megjelenítésére is alkalmassá akartuk tenni.
Kockadobás és próbarendszer
A karakterlap többféle dobástámogatást kapott.

Hagyományos D6-dobás

CSS-alapú, látványos, háromdimenziós kockaanimációval működő dobás, amely 1 és 6 közötti véletlen eredményt ad.

A dobás önmagában nem módosítja a karakter adatait.

Szerencsedobás

Különálló dobási lehetőség a játék szerencsemechanikájának támogatására.

Hétpróbás dobássúgó

Részletes dobásszámítási segéd, amely megjeleníti:
- A számítás műveleti sorrendjét.
- A dobás köztes értékeit.
- Az alkalmazott módosítókat.
- A végső eredményt.
A cél, hogy a játékos a dobás eredményén túl annak kiszámítását is követni tudja.
Felszerelés és zseb
A karakterlap hét felszerelési helyet tartalmaz.

Ezek szabadon szerkeszthető szöveges mezők, így a játékos saját maga rögzítheti az eszközöket, fegyvereket és tárgyakat.

A felszereléstől elkülönített zseb/inventory rész is rendelkezésre áll.

Korábban felmerült egy előre összeállított, választható tárgylista lehetősége, de ezt későbbi fejlesztési ötletként kezeltük.

Strigulák és fejlődés
A karakterlap támogatja a karakter céljaihoz és fejlődéséhez kapcsolódó strigulák nyilvántartását.

A kialakított működés szerint három teljesített cél beváltható egy Kitartáspontért, a 14-es felső határ betartásával.

A beváltások külön naplózhatók, és a hozzájuk tartozó adatok a karakter JSON-mentésében is megmaradnak.

Karaktertörténet és Visszhang
A karakterlap külön szöveges területeket biztosít a karakter személyes hátteréhez.

Ide tartozik a karakter története, valamint a Zombie Road rendszerében használt Visszhang.

Ezek a szövegek a karakterrel együtt menthetők és visszatölthetők.

Karakterportré
A karakterlap képes saját karakterkép tárolására és megjelenítésére.

A kialakított megoldás főbb jellemzői:
- Kép feltöltése a karakterhez.
- A portré megjelenítése a karakterlap felső részén.
- A kép eltávolításának lehetősége.
- WebP-formátumú tömörítés.
- Base64-alapú képtárolás.
- A kép beágyazása ugyanabba a JSON-fájlba, amely a karakter többi adatát tartalmazza.
Ez azt jelenti, hogy egyetlen karaktermentés a karakter adatait és portréját is tartalmazhatja. Nincs szükség külön képfájl kezelésére.

Többjegyzetes rendszer
A karakterlap egy önálló, több bejegyzést kezelő jegyzetmodullal bővült.

A játékos:
- Tetszőleges hosszúságú jegyzeteket írhat.
- Minden jegyzetnek külön címet adhat.
- Váltogathat a jegyzetei között.
- Kereshet a jegyzetekben.
- Szerkesztheti a meglévő tartalmat.
- Törölheti a szükségtelenné vált bejegyzéseket.
A jegyzetek a böngészős mentésbe és a JSON-exportba is bekerülnek.
Mentés és adatbiztonság
A karakterlap mentési rendszere több szinten működik.

JSON-export/import: a karakter adatai fájlba menthetők, majd később visszatölthetők.

Böngészős automatikus mentés: a karakter állapota helyileg megőrizhető, így a böngésző bezárása után is folytatható a munka.

Kiválasztott fájl frissítése: támogatott böngészőkben a felhasználó által kiválasztott JSON-fájl automatikus frissítésére is kialakítottunk megoldást.

Mentési emlékeztető: ötpercenként figyelmeztető felület jelenhet meg „Mentés most” és „Később” lehetőségekkel.

Mentési idő kijelzése: a felület követi, mennyi idő telt el az utolsó mentés óta.

A böngésző helyi mentése és a lemezre írt JSON nem azonos.
Az exportált JSON fájl a biztonsági mentés.

Vizuális megjelenés
A karakterlap kifejezetten erőteljes horrorhangulatú arculatot kapott.

Jellemzői a sötét háttér, koszos és szakadozott papírpanelek, fakó sárgásbarna és penészes szürke textúrák, vérfoltok, kopott felületek, vörös kiemelések és rétegzett árnyékok.

A cél egy digitális, megviselt túlélőnapló vagy zombiapokalipszist átélt karakterlap megjelenítése volt.

Navigáció: egy felül rögzített, vízszintes navigációs sávot választottunk, ikonokkal és feliratokkal. 

3. Zombie Road – Mesélői harcvezérlő
A harcvezérlő a mesélő munkáját támogatja. A cél a harc résztvevőinek, erőforrásainak, cselekvéseinek és eseményeinek központi kezelése.

Harc előkészítése
A mesélő összeállíthatja az adott összecsapás résztvevőit.

A rendszer játékoskaraktereket és szörnyeket egyaránt kezel, külön résztvevőlistával és harci állapotokkal.

A tervezés során szerepelt az előre rögzített játékosok gyors hozzáadása, illetve a hozzáadandó ellenfelek alapértelmezett darabszámának beállítása is.

Szörnyadatbázis
A harcvezérlő saját szörnyadatbázist tartalmaz, amelyből a mesélő ellenfeleket adhat az aktuális harchoz.

A szörnyekhez tartozó adatok és egyedi képességek segítik az ellenfelek kezelését anélkül, hogy minden tulajdonságot külön papíron kellene nyilvántartani.

Kezdeményezés és sorrend
A harcvezérlő kezeli a résztvevők cselekvési sorrendjét.
- A kezdeményezés a harc kezdetén kerül meghatározásra.
- A sorrend később kézzel módosítható.
- A körváltás nem generál automatikusan új sorrendet.
- A résztvevők állapota a harc során követhető.
Külön kértük, hogy az elhunyt résztvevők a listák végére kerüljenek, miközben az inaktív, de életben lévő szereplőket a rendszer ne kezelje halottként.

Akciópontok és cselekvések
A harcvezérlő 14 alapcselekvést kezelő szabálysegédet kapott, amelyet egyedi szörnyképességek egészítenek ki.

A cselekvésekhez AP-költségek tartoznak, amelyek segítik a harci erőforrások nyilvántartását.

A résztvevők „Cselekedett” állapottal jelölhetők. Külön fejlesztési igény volt, hogy a szörnyek AP-jának elfogyásakor ez a jelölés automatikusan megtörténjen.

A körváltás visszaállítja a megfelelő AP-értékeket és a körönként használható képességek állapotát.
Harci állapotok
A harcvezérlő különbséget tesz a résztvevők harci állapotai között.

A mesélő számára fontos, hogy egy szereplő aktív, már cselekedett, inaktív vagy halott állapotban van-e.

A felület célja, hogy ezek a különbségek gyorsan felismerhetők legyenek, és ne kelljen fejben követni a teljes harci adminisztrációt.

Harcnapló és zsákmány
A rendszer harcnaplót és zsákmánykezelést is tartalmaz.

A harcnapló az összecsapás eseményeinek követésére szolgál, a zsákmányrész pedig az összecsapás során megszerzett tárgyak és jutalmak kezelését támogatja.

Dobások és eredménykijelzés
A harcvezérlőben külön hangsúlyt kapott az utolsó dobás eredményének jól látható megjelenítése.

Ez a mesélői felületnél különösen fontos, mert a játékvezetőnek gyorsan kell értelmeznie a dobásokat, miközben a többi résztvevőre is figyel.
Adatkezelés
A harcvezérlő helyi böngészős mentést, valamint JSON-exportot és -importot használ.

A megoldás lehetővé teszi a harcállapotok tárolását és későbbi visszaállítását.

A harcvezérlő különálló HTML-alkalmazásként működik, nem függ a játékosok karakterlapjaitól.

4. Zombie Road – Mesélői kalandkezelő
A kalandkezelő a három alkalmazás közül a leginkább történetszervezésre koncentrál.

Nem automatikus történetgenerátor, hanem a mesélő által összeállított kalandok strukturált tárolására és játék közbeni használatára szolgáló felület.

Több kaland kezelése
A rendszer több kaland tárolását és kezelését támogatja.

Minden kaland saját jelenetekkel, történetszerkezettel és kapcsolódó tartalommal rendelkezhet.
Jelenetalapú felépítés
A kalandok alapvető építőelemei a jelenetek.

Egy jelenet nem merev sablon, hanem különféle tartalmi blokkokból összeállítható egység.

Ez lehetővé teszi, hogy a mesélő különböző típusú információkat rendezzen egy helyre: helyszínleírásokat, eseményeket, szereplőkkel kapcsolatos információkat, nyomokat, mesélői megjegyzéseket és lehetséges következményeket.
Fő történeti útvonal és elágazások
A tervezett történetkezelési modell egy ajánlott fő útvonalból és szabadon bejárható mellékágakból áll.

A kaland nem kizárólag lineárisan haladhat. A játékosok döntései más jelenetekhez és eltérő következményekhez vezethetnek.

A rendszer a mesélőnek ad szervezési eszközt, nem próbálja automatikusan eldönteni, merre kell haladnia a történetnek.
Terv és tényleges játékállapot
A kalandkezelő egyik fontos tervezési döntése a kétféle állapot elkülönítése:

Tervezett állapot: amit a mesélő előzetesen elkészített.

Aktuális játékállapot: ami a játékosok döntései és az események hatására ténylegesen kialakult.

A két állapot összekapcsolódik, de nem írja automatikusan felül egymást.

A következmények és állapotváltozások kezelését tudatosan a mesélő ellenőrzése alatt akartuk tartani.
Jelenettérkép
A kalandkezelő automatikusan megjeleníthető jelenettérképet kapott.

A térkép a jelenetek közötti kapcsolatokat szemlélteti, és támogatja a kalandon belüli navigációt.

A korábbi CSS- és SVG-tervezés alapján:
- A jelenetek csomópontként jelennek meg.
- A csomópontok összekötő vonalakkal kapcsolódnak egymáshoz.
- Az opcionális kapcsolatok szaggatott vonallal különíthetők el.
- Az aktuális jelenet kiemelt megjelenítést kap.
- A kijelölt jelenet külön vizuális jelölést használ.
- A térkép reszponzív kialakítású.
A szélesség kapcsán kifejezett elvárás volt, hogy a térkép ne legyen 720 pixelre korlátozva: szükség esetén ennél szélesebb, a rendelkezésre álló képernyőhöz igazodó területet is használhasson.
Mesélői nézet és szerkesztő
A kalandkezelő két eltérő felhasználási helyzetet támogat.

A szerkesztőnézetben a mesélő előkészítheti és módosíthatja a kaland tartalmát.

A játék közbeni mesélői nézet célja a fontos információk gyors előhívása és az aktuális jelenet követése.

A fejlesztési koncepcióban külön hangsúlyt kapott, hogy játék közben ne kelljen feleslegesen a szerkesztőfunkciókkal foglalkozni.
Tartalomtár, keresés és jegyzetek
A kalandkezelő tartalomtárat és keresési lehetőségeket is kapott.

A cél az volt, hogy a mesélő ne csak jelenetenként, hanem a teljes kaland tartalmában is tájékozódhasson.

A jelenetekhez kapcsolódó jegyzetek később önálló történeti tartalommá alakíthatók a tervezett munkafolyamat szerint.
Mentés és hordozhatóság
A kalandkezelő külön JSON-adatállományt használ.

A dokumentált funkciók között szerepel a JSON-import/export, a böngészős automatikus mentés és a tartalmak másolása.
