# PaDEL-Descriptor Dependencies

This folder contains the Java-based engines required to calculate molecular fingerprints from SMILES strings. These descriptors serve as the numerical input for the machine learning model to predict bioactivity.

### Contents
* **`PaDEL-Descriptor.jar`**: The main executable library used to process chemical structures.
* **`PubchemFingerprint.xml`**: The configuration file defining the specific fingerprints used by the model.
* **`lib/`**: Directory containing essential Java dependency libraries.

### Requirements
To use these files via the `app.py` script, the host system must have **Java JRE (Runtime Environment)** installed and properly configured in the system path.
