# Dataset attribution

This folder contains six open datasets used across the AI Analyst LAB course. Every dataset listed here is **open** under a license that permits redistribution. We include the original files locally so that participants can start analysis without hunting for downloads. Each subfolder name below maps to the course session(s) that use the dataset.

Where the upstream source also publishes a `README`, codebook, or guidance document, we include it alongside the data so the citation chain stays intact.

---

## 1. `bike_sharing/` — Bike Sharing Dataset

- **Used in:** Session 01 (Demand and operations analytics)
- **Source:** UCI Machine Learning Repository, dataset id **275**
- **Landing page:** [https://archive.ics.uci.edu/dataset/275/bike+sharing+dataset](https://archive.ics.uci.edu/dataset/275/bike+sharing+dataset)
- **License:** **Creative Commons Attribution 4.0 International (CC BY 4.0)** — [https://creativecommons.org/licenses/by/4.0/](https://creativecommons.org/licenses/by/4.0/)
- **Original authors / citation:**
  > Fanaee-T, Hadi, and Gama, Joao. *Event labeling combining ensemble detectors and background knowledge*. **Progress in Artificial Intelligence**, Springer Berlin Heidelberg, 2013, pp. 1–15. doi:[10.1007/s13748-013-0040-3](https://doi.org/10.1007/s13748-013-0040-3)
- **Files included:** `day.csv`, `hour.csv`, `Readme.txt`

---

## 2. `stats19_road_safety/` — Great Britain STATS19 Road Safety Open Data

- **Used in:** Session 02 (Risk assessment with probability)
- **Source:** UK Department for Transport (DfT), via [data.gov.uk](https://www.data.gov.uk/dataset/cb7ae6f0-4be6-4935-9277-47e5ce24a11f/road-accidents-safety-data)
- **Landing page:** [https://www.gov.uk/government/statistical-data-sets/road-safety-open-data](https://www.gov.uk/government/statistical-data-sets/road-safety-open-data)
- **License:** **Open Government Licence v3.0 (OGL v3.0)** — [https://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/](https://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/)
- **Required attribution wording (OGL):**
  > Contains public sector information licensed under the Open Government Licence v3.0.
- **Scope:** record-level data on personal injury road collisions reported to the police in Great Britain, recorded via the STATS19 reporting system. **Note:** STATS19 covers personal-injury collisions only — damage-only crashes and unreported incidents are systematically missing. The DfT also notes that severity classifications were re-based in 2016, so comparisons across that boundary should be treated carefully.
- **Year used:** 2024 (final, validated annual release available as of May 2026)
- **Files included:**
  - `dft-road-casualty-statistics-collision-2024.csv` — main collisions table (one row per collision)
  - `dft-road-casualty-statistics-casualty-2024.csv` — casualty table (one row per casualty)
  - `dft-road-casualty-statistics-vehicle-2024.csv` — vehicle table (one row per vehicle involved)

---

## 3. `upworthy_research_archive/` — The Upworthy Research Archive

- **Used in:** Session 03 (A/B testing in growth analytics)
- **Source:** Cornell University, hosted on the Open Science Framework
- **Landing page:** [https://osf.io/jd64p/](https://osf.io/jd64p/)
- **Project site:** [https://upworthy.natematias.com/](https://upworthy.natematias.com/)
- **License:** **Creative Commons Attribution 4.0 International (CC BY 4.0)** — [https://creativecommons.org/licenses/by/4.0/](https://creativecommons.org/licenses/by/4.0/)
- **Original authors / citation:**
  > Matias, J. N., Munger, K., Aubin Le Quéré, M. A., & Ebersole, C. (2021). The Upworthy Research Archive, a time series of 32,487 experiments in U.S. media. **Scientific Data**, 8, 195. doi:[10.1038/s41597-021-00934-7](https://doi.org/10.1038/s41597-021-00934-7)
- **Known caveat (do not skip when teaching):** the archive maintainers report a randomization issue affecting experiments deployed between **25 June 2013 and 10 January 2014**. They recommend avoiding *confirmatory* use of tests in that window. See the project site for details.
- **Files included:**
  - `upworthy-archive-exploratory-packages-03.12.2020.csv` — exploratory sample (intended for hypothesis generation)
  - `upworthy-archive-confirmatory-packages-03.12.2020.csv` — confirmatory sample (intended for hypothesis testing)
  - `upworthy-archive-holdout-packages-03.12.2020.csv` — holdout sample
  - `upworthy-archive-undeployed-packages-01.12.2021.csv` — undeployed packages
  - `Matias-Munger-Upworthy-Research-Archive-09.2019.pdf` — official data descriptor
  - `02.2021-create-research.samples.py` — original sample-creation script

---

## 4. `wine_quality/` — Wine Quality Dataset

- **Used in:** Session 04 (Drivers analysis), Session 08 (Regression tree)
- **Source:** UCI Machine Learning Repository, dataset id **186**
- **Landing page:** [https://archive.ics.uci.edu/dataset/186/wine+quality](https://archive.ics.uci.edu/dataset/186/wine+quality)
- **License:** **Creative Commons Attribution 4.0 International (CC BY 4.0)** — [https://creativecommons.org/licenses/by/4.0/](https://creativecommons.org/licenses/by/4.0/)
- **Original authors / citation:**
  > Cortez, Paulo; Cerdeira, A.; Almeida, F.; Matos, T.; Reis, J. *Modeling wine preferences by data mining from physicochemical properties*. **Decision Support Systems**, Elsevier, 47(4):547–553, 2009. doi:[10.1016/j.dss.2009.05.016](https://doi.org/10.1016/j.dss.2009.05.016)
- **Files included:** `winequality-red.csv`, `winequality-white.csv`, `winequality.names`

---

## 5. `iranian_churn/` — Iranian Churn Dataset

- **Used in:** Session 05 (Binomial regression / classification), Session 08 (Classification tree)
- **Source:** UCI Machine Learning Repository, dataset id **563**
- **Landing page:** [https://archive.ics.uci.edu/dataset/563/iranian+churn+dataset](https://archive.ics.uci.edu/dataset/563/iranian+churn+dataset)
- **License:** **Creative Commons Attribution 4.0 International (CC BY 4.0)** — [https://creativecommons.org/licenses/by/4.0/](https://creativecommons.org/licenses/by/4.0/)
- **Original authors / citation:**
  > Jafari-Marandi, Ruholla; Denton, Joshua; Idris, Adnan; Smith, Brian K.; Keramati, Abbas. *Optimum profit-driven churn decision making: innovative artificial neural networks in telecom industry*. **Neural Computing and Applications**, 32(18):14929–14962, 2020. doi:[10.1007/s00521-020-04850-6](https://doi.org/10.1007/s00521-020-04850-6)
- **Files included:** `Customer Churn.csv`

---

## 6. `wholesale_customers/` — Wholesale Customers Dataset

- **Used in:** Session 06 (k-means segmentation), Session 07 (t-SNE visualization)
- **Source:** UCI Machine Learning Repository, dataset id **292**
- **Landing page:** [https://archive.ics.uci.edu/dataset/292/wholesale+customers](https://archive.ics.uci.edu/dataset/292/wholesale+customers)
- **License:** **Creative Commons Attribution 4.0 International (CC BY 4.0)** — [https://creativecommons.org/licenses/by/4.0/](https://creativecommons.org/licenses/by/4.0/)
- **Original authors:** Margarida G. M. S. Cardoso (donor), instituto Universitário de Lisboa (ISCTE-IUL).
- **Files included:** `Wholesale customers data.csv`

---

## 7. `titanic/` — Titanic passenger dataset (teaching demo)

- **Used in:** Session 08 (Decision trees) — as the **introductory classification example only**, before the session moves on to the course's own datasets (Iranian Churn for classification, Wine Quality for regression).
- **Source:** the widely-redistributed *"Titanic: Machine Learning from Disaster"* training set (as popularised by Kaggle), itself derived from the passenger manifest compiled by the Department of Biostatistics at **Vanderbilt University** (Thomas Cason's cleaned edition), originating from **Encyclopedia Titanica**.
- **Nature / license:** the underlying records are **historical facts in the public domain** (the 1912 RMS Titanic passenger list). The dataset is distributed freely for educational use and is one of the most widely reused teaching datasets in machine learning.
- **Why it is here:** it gives absolute beginners a small, intuitive, two-class problem (`Survived` vs not) whose splits — *"was the passenger in first class?"*, *"female or male?"* — read like plain-English decision rules, which is exactly the intuition Session 08 is building before we apply trees to the course's own business data.
- **Files included:** `Titanic_train.csv` (891 passengers). Columns used in the session: `Survived` (target), `Pclass`, `Sex`, `Age`.

---

## A short note on responsible use in this course

- **Attribution is the price of CC BY 4.0.** When participants reuse any of these datasets in their portfolio, blog posts, or talks after the course, they must keep the citation visible.
- **STATS19 and Upworthy** both come with documented caveats — STATS19 covers police-reported personal-injury collisions only (a non-trivial subset of road incidents), and the Upworthy archive has a known randomization-issue window. Both course sessions surface these explicitly so participants learn to lead with limitations, not gloss over them.
- **No dataset in this folder was scraped or sourced from a third party without permission.** Each file traces back to its original publisher via the links above.
