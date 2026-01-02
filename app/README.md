KRAS Bioactivity Predictor (Streamlit App)
This folder contains the Streamlit application for real-time bioactivity prediction targeting the KRAS GTPase protein. This app allows users to input chemical structures (SMILES) and receive a predicted $pIC_{50}$ value based on the trained Random Forest Regressor model.
How to Run Locally
1. Download the model from the [v1.0.0 Release](../../releases/tag/v1.0.0).
2. Install Dependencies: Ensure you have the required libraries installed:
```bash
pip install -r requirements.txt
streamlit run app.py

