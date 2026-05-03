# RQA pro interpretaci očních pohybů v kartografii 👁️🗺️
**Recurrence Quantification Analysis (RQA) for Eye-Tracking Data in Cartography**

Tento repozitář obsahuje interaktivní open-source analytický nástroj vyvinutý v jazyce Python v prostředí Google Colab[cite: 1]. Skript slouží ke zpracování, analýze a vizualizaci eye-tracking dat pomocí metod nelineární dynamiky, konkrétně Rekurentní kvantifikační analýzy (RQA)[cite: 1]. 

Nástroj vznikl jako praktický výstup bakalářské práce na **Katedře geoinformatiky Přírodovědecké fakulty Univerzity Palackého v Olomouci** (Autor: František Brandejs, Vedoucí: Mgr. Michaela Vojtěchovská)[cite: 1].

## 📌 Hlavní funkce
Nástroj nabízí komplexní pipeline od surových dat až po grafické výstupy, aniž by koncový uživatel musel zasahovat do zdrojového kódu (využívá grafické rozhraní `ipywidgets`)[cite: 1].

* **Sjednocení a úprava oblastí zájmu (AOI):** Automatická extrakce a možnost manuální reklasifikace překrývajících se AOI do sémantických kategorií[cite: 1].
* **Filtrace odlehlých hodnot (Outlierů):** Očištění dat pomocí metody mezikvartilového rozpětí (IQR) pro každý mapový stimul zvlášť[cite: 1].
* **Fyzický výpočet prahové vzdálenosti:** Algoritmus pro exaktní výpočet foveálního rádiusu (v pixelech) z fyzických parametrů monitoru a zorného úhlu respondenta[cite: 1].
* **Souběžný výpočet RQA metrik:** 
  * **AOI přístup (Kategorická RQA):** Rekurence na základě textové shody navštívených zón[cite: 1].
  * **XY přístup (Metrická RQA):** Rekurence na základě euklidovské vzdálenosti fixací[cite: 1].
* **Počítané metriky:** Recurrence Rate (RR), Determinismus (DET), Laminarita (LAM)[cite: 1].

## 📊 Vizualizační panel
Skript obsahuje interaktivní záložkové rozhraní pro vizualizaci výsledků[cite: 1]:
1. **Recurrence plot:** Čtvercová matice pro detailní kvalitativní trasování sekvence fixací v čase s barevným odlišením sémantických prvků mapy[cite: 1].
2. **Boxplot:** Kvantitativní srovnání distribuce metrik a mediánů mezi různými skupinami (např. experti vs. nováčci)[cite: 1].
3. **Scatter plot:** Korelační zobrazení Determinismu a Laminarity pro identifikaci vizuálních strategií[cite: 1].
4. **Radar plot:** Pavučinový graf pro rychlé zobrazení holistického průměrného kognitivního profilu[cite: 1].

## 📂 Struktura vstupních dat
Nástroj je primárně optimalizován pro `.csv` exporty z open-source webové aplikace **GazePlotter**[cite: 1].
Vstupní soubor fixací musí obsahovat následující sloupce[cite: 1]:
* `stimulus`: Název/ID mapového stimulu[cite: 1].
* `participant`: Unikátní identifikátor respondenta[cite: 1].
* `timestamp`: Časový údaj začátku fixace[cite: 1].
* `duration`: Doba trvání fixace[cite: 1].
* `eyemovementtype`: Typ očního pohybu (očekávají se pouze fixace)[cite: 1].
* `AOI`: Textový řetězec navštívené oblasti zájmu[cite: 1].
* `x` a `y`: Pixelové souřadnice fixace na monitoru[cite: 1].

Dále je vyžadována doplňková tabulka respondentů (`.csv`) s jejich rozřazením do skupin (např. úroveň kartografické expertízy)[cite: 1].

## 🚀 Jak nástroj používat (Quick Start)
1. Stáhněte si `.ipynb` soubor z tohoto repozitáře.
2. Otevřete soubor v prostředí [Google Colab](https://colab.research.google.com/).
3. Nahrajte svá data (fixace a tabulku respondentů) na svůj osobní Google Drive[cite: 1].
4. Spusťte první buňku pro import knihoven a propojení s Google Drive[cite: 1].
5. Postupujte postupně podle instrukcí v interaktivních formulářích jednotlivých buněk[cite: 1].

## 🛠 Použité knihovny
* `pandas` a `numpy` – manipulace s maticemi a datovými rámci[cite: 1].
* `scipy` – výpočet euklidovských vzdáleností (XY přístup)[cite: 1].
* `matplotlib` a `seaborn` – generování grafických výstupů a grafů[cite: 1].
* `ipywidgets` – tvorba interaktivního uživatelského rozhraní přímo v prohlížeči[cite: 1].

## 📜 Citace a reference
Pokud tento skript využijete ve svém výzkumu, prosím citujte původní bakalářskou práci:
> BRANDEJS, František. *Využití rekurentní kvantifikační analýzy pro interpretaci očních pohybů při čtení statických map*. Olomouc, 2026. Bakalářská práce. Univerzita Palackého v Olomouci, Přírodovědecká fakulta, Katedra geoinformatiky. Vedoucí práce Mgr. Michaela Vojtěchovská.

## 📄 Licence
Tento projekt je poskytován jako open-source. Pro více informací viz soubor `LICENSE`.
