# python-projekt
# Használt Autók Piacának Adatelemzése (Kaggle Dataset)

Ez a projekt a használt autók piacának adatelemzését és vizualizációját mutatja be Python környezetben. A vizsgálat célja, hogy feltárja az árakat és az értékvesztést befolyásoló legfontosabb tényezőket, mint a futott kilométer, a jármű kora, az üzemanyagtípus és a sebességváltó fajtája.

## Használt Technológiák
* **Programozási nyelv:** Python 3 (Google Colab / Jupyter Notebook környezet)
* **Adatkezelés és tisztítás:** Pandas, NumPy, Regex (`re` modul)
* **Vizualizáció:** Plotly Express (interaktív diagramok)

## Adatforrás
Az adathalmaz a Kaggle "Used Cars Dataset" gyűjteményéből származik, amely indiai használt járművek részletes hirdetési adatait tartalmazza. 
* A projektben használt nyers adatfájl: `used_cars_dataset_v2.csv`
* *Megjegyzés:* Az elemzés előtt az adatbázis tisztításon esett át (szöveges karakterek, valutajelek és vesszők eltávolítása a numerikus oszlopokból Regex segítségével).

## Elemzési Kérdések és Főbb Eredmények

**1. Milyen kapcsolat van a futott kilométer (`kmDriven`) és a meghirdetett ár (`AskPrice`) között?** 
* **Módszer:** Korrelációszámítás és pontdiagram (Scatter plot).
* **Következtetés:** A NumPy segítségével kiszámolt negatív korrelációs együttható matematikailag is igazolja a vizuálisan látható trendet: a futott kilométerek növekedésével a járművek ára egyértelműen és arányosan csökken.

**2. Melyik az az 5 autómárka, amelyik a legdrágább az 5 évnél idősebb autók piacán?** 
* **Módszer:** Pandas adatcsűrés (`Age > 5`), csoportosítás (`groupby`) és oszlopdiagram (Bar chart).
* **Következtetés:** A diagram rávilágít arra, hogy a prémium márkák (pl. Mercedes-Benz, BMW, Audi) tartják a legmagasabb átlagárat az 5 évnél idősebb kategóriában is, jelentősen elszakadva a tömegmárkáktól.

**3. Milyen a különböző üzemanyagtípusok megoszlása a piacon?** 
* **Módszer:** Kategóriák összeszámolása (`value_counts`) és százalékos kördiagram (Pie chart).
* **Következtetés:** Az interaktív diagram pontosan megmutatja a dízel és benzines autók dominanciáját a piacon, míg az alternatív meghajtások (hibrid/CNG/elektromos) egyelőre csak kisebb szeletet képviselnek.

**4. Hogyan befolyásolja a sebességváltó típusa az árat a jármű korának függvényében?** 
* **Módszer:** Kétváltozós, színnel kódolt pontdiagram (Colored Scatter plot).
* **Következtetés:** Jól látható, hogy azonos életkor (évjárat) mellett az automata váltós modellek jellemzően egy magasabb ársávban helyezkednek el a manuális váltós társakhoz képest, és ez a felár az évek múlásával is megmarad.

**5. Mekkora értékvesztést jelent a tulajdonosok száma a 3 leggyakoribb márka esetében?** 
* **Módszer:** Dinamikus szűrés a top 3 márkára (`isin`), többszintű aggregáció, és többpaneles vonaldiagram (Faceted Line chart).
* **Következtetés:** A márkaspecifikus paneleken egyértelműen leolvasható, hogy a második tulajdonostól származó autók árgörbéje (értékvesztése) meredekebb, illetve alacsonyabbról indul, mint az első tulajdonosok által árult járműveké.

## Futtatási Instrukciók
1. Klónozza ezt a repository-t.
2. Győződjön meg róla, hogy a `used_cars_dataset_v2.csv` és a kód (`.ipynb`) egy mappában van (Google Colab használata esetén a Drive-os elérési útvonalat módosítani kell).
3. Telepítse a szükséges csomagokat: `pip install pandas numpy plotly`
4. Futtassa le a cellákat fentről lefelé az interaktív diagramok generálásához.
