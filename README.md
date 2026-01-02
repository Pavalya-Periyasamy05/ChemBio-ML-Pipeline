# ChemBio-ML-Pipeline: KRAS Bioactivity Prediction

An end-to-end computational drug discovery pipeline that automates the process of data acquisition, chemical space analysis, and bioactivity prediction for the **KRAS GTPase** protein.

>  **Interactive App:** Check the [`/app`](./app) directory for a ready-to-use Streamlit application for real-time bioactivity prediction.

---

##  Tech Stack & Tools

| Category | Tools & Libraries |
| :--- | :--- |
| **Data Acquisition** | `chembl_webresource_client` |
| **Cheminformatics** | `rdkit` (via `condacolab`), `padelpy` (Notebooks), **Native Java PaDEL JAR** (App) |
| **Machine Learning** | `scikit-learn` (Random Forest Regressor), `pickle` |
| **Data Analysis** | `pandas`, `numpy`, `matplotlib`, `seaborn`, `scipy` (Mann-Whitney U test) |
| **Deployment** | `streamlit`, Java JRE 8+ (required for descriptor calculation) |

---

##  Pipeline Overview

### 1. Data Acquisition & Cleaning
* **Retrieval:** Used the ChEMBL client to retrieve **5,760 compounds** targeting the KRAS protein.
* **Filtering:** Isolated compounds based on `IC50` standard types.
* **Refining:** Conducted thorough data cleaning, duplicate removal, and handled missing values.

### 2. Exploratory Data Analysis (EDA)
* **Lipinski's Rule:** Calculated molecular weight, LogP, and hydrogen bond donors/acceptors using `rdkit.Chem` descriptors.
* **Feature Transformation:** Converted `IC50` values to the logarithmic $pIC_{50}$ scale for better model performance.
* **Statistical Analysis:** Performed **Mann-Whitney U tests** to analyze significant differences between active and inactive chemical classes.
* **Visualization:** Created custom box plots and scatter plots to visualize the distribution of chemical space.



### 3. Feature Engineering & Modeling
* **Notebook Phase:** Utilized the `padelpy` Python library for rapid fingerprinting during experimentation.
* **Production Phase:** Implemented a direct `subprocess` bash command calling the **PaDEL-Descriptor JAR** file within the Streamlit app to ensure deployment stability.
* **ML Training:** Built and optimized a **Random Forest Regressor** to predict drug potency based on PubChem Fingerprints.

---

##  Repository Structure

* [`/app`](./app): Streamlit application source code, native Java dependencies, and deployment guide.
* [`/data`](./data): Evolution of the dataset from raw ChEMBL records to final ML-ready features.
* [`/notebooks`](./notebooks): Detailed Jupyter notebooks documenting the research, EDA, and model building phases.

---

##  Credits & Inspiration

This project was inspired by the bioinformatics tutorials developed by **Chanin Nantasenamat** (Data Professor). His methodology for computational drug discovery provided the architectural foundation for this KRAS-specific implementation.

---

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
