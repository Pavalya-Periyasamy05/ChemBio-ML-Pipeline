#  Dataset: KRAS GTPase Bioactivity Pipeline

This directory contains the systematic progression of data from raw ChEMBL retrieval to processed features used for machine learning.

## File Descriptions

| Order | File Name | Description |
| :--- | :--- | :--- |
| **1** | **`bioactivity_data.csv`** | **Original Data:** Retrieved via the ChEMBL Python library for the KRAS target. Filtered for standard `IC50` types. |
| **2** | **`bioactivity_preprocessed_data.csv`** | **Preprocessed Data:** Missing values and duplicates removed. Molecules categorized into **active**, **inactive**, and **intermediate** classes based on IC50 thresholds. |
| **3** | **`Bioactivity_2Classes_Data.csv`** | **EDA Dataset:** Intermediate class removed. Includes Lipinski descriptors and $pIC_{50}$ conversions. Used for statistical analysis (Mann-Whitney U test) and visualizations. |
| **4** | **`Bioactivity_3Classes_Data.csv`** | **Modeling Prep:** Includes all 3 bioactivity classes. This serves as the input for calculating PaDEL descriptors. |
| **5** | **`Bioactivity_data_3class_pIC50_pubchem_fp.csv`** | **Final Features:** The output of PaDEL-Descriptor. Contains the full fingerprints and $pIC_{50}$ target variables used to train the model. |
| **6** | **`descriptor_list.csv`** | **Feature Selection:** Derived from File #5 by removing low-variance features to ensure the model focuses on the most informative structural keys. |
| **7** | **`results.zip`** | **Analytics:** Compressed archive containing saved EDA plots, statistical test results, and model performance metrics. |



##  Model Output

The final trained **Random Forest Regression Model** (`KRAS_GTPase_protein_inhibitor.pkl`) was generated using the processed data in File #5. Due to its file size (~84 MB), it is hosted in the **v1.0.0 Release** section rather than the main repository to ensure optimal performance.

##  Data Source
All bioactivity data was sourced from the **ChEMBL database**, a curated database of bioactive molecules with drug-like properties.
