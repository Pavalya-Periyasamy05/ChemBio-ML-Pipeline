
# KRAS Bioactivity Predictor (Streamlit App)

This folder contains the Streamlit application for real-time bioactivity prediction targeting the **KRAS GTPase** protein. This app allows users to input chemical structures (SMILES) and receive a predicted $pIC_{50}$ value based on the trained **Random Forest Regressor** model.

## How to Run Locally

1. **Download the Model:** The model file is large (82.3 MB) and is hosted in the [v1.0.0 Release](../../releases/tag/v1.0.0) section. Download `KRAS_GTPase_protein_inhibitor.pkl` and place it inside this `/app` folder.

2. **Install Dependencies:** Open your terminal in this folder and ensure you have the required libraries installed:
   ```bash
   pip install -r requirements.txt
3. **Launch the App:** Run the following command in your terminal to start the interface:
   ```bash
   streamlit run app.py
