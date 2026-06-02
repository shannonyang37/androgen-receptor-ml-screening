## **Androgen Receptor Binder Prediction and Drug Repurposing Using Random Forest**

### Project Overview
This project aims to develop a machine learning model capable of predicting androgen receptor (AR) binding activity and to apply the trained model for virtual screening of FDA-approved drugs for potential drug repurposing opportunities.
A Random Forest classifier was trained using known AR binders and non-binders represented by molecular fingerprints and physicochemical descriptors. The trained model was subsequently used to screen 1,366 FDA-approved compounds obtained from the ZINC20 database.

---
### Objectives
* Build a predictive model for androgen receptor binding
* Evaluate model performance using standard classfication metrics
* Screen FDA-approved drugs for potential AR-binding activity
* Identify compounds that may warrant further investigation through molecular docking and experimental validation

---
### Project Workflow
The pipeline is broken down into four Jupyter Notebooks:
1. **Data Acquisition (`1_data_acquisition.ipynb`):** Extracted bioactivity data (IC50) for the Androgen Receptor from the ChEMBL database via API.
2. **Molecular Filtering (`2_molecular_filtering.ipynb`):** Cleaned the dataset, calculated the Lipinski's Rule of Five, and filtered out unwanted structures and PAINs.
3. **Model Training (`3_model_training.ipynb`):** Computed molecular fingerprints and trained a Random Forest classifier. Compared the predictive performance of MACCS structural keys versus Morgan fingerprints.
4. **Virtual Screening (`4_virtual_screening.ipynb`):** Deployed the best-performing model to screen a subset of FDA-approved drugs from ZINC20, yielding a final list of top predicted candidates.

---
### Key Results
* The model trained on Morgan fingerprints performed better, achieving a ROC-AUC of 0.86.
* Examples of top predicted drugs include:
  * Progesterone	
  * Methyltestosterone	
  * Estradiol	
  * Oxandrolone	
  * Nandrolone decanoate	
  * Fluoxymesterone	
  * Megestrol acetate	

---
### Interpretation of Results
The virtual screening results show that the model predominantly prioritized steroidal compounds. This enrichment is consistent with the known biology of the androgen receptor, which naturally binds steroid-like ligands. As a result, the model appears to capture features associated with steroidal chemical space relevant to androgen receptor interaction.

However, the predictions should be interpreted with caution. The model is trained to predict androgen receptor binding and does not distinguish between agonists and antagonists. As a result, both androgenic compounds and anti-androgenic compounds may be assigned high probabilities.

Additionally, the observed ranking suggests that the model may partially rely on recognition of shared steroid scaffolds, which are common across multiple hormone classes (androgens, estrogens, progestins, and vitamin D analogues), rather than exclusively learning fine-grained determinants of functional activity.

Overall, the results demonstrate that the model is capable of enriching biologically relevant steroidal chemistry within a large drug library, but further analysis (e.g., docking, mechanism-based classification, or experimental validation) is required to assess therapeutic potential, particularly for applications such as prostate cancer treatment.

---
### Limitations and Future Work
* The model predicts androgen receptor (AR) binding affinity in a binary manner and does not distinguish between agonist, antagonist, or partial agonist activity.  
* Predictions may be influenced by scaffold bias, particularly structural similarity among steroidal compounds.  
* Further validation using molecular docking against androgen receptor structures is recommended to assess binding modes and interaction stability.  
* Future work includes hyperparameter optimization of the Random Forest model and benchmarking against other machine learning approaches (e.g., XGBoost, SVM, and neural networks).  

---
### Installation
Clone the repository and install dependencies:
'''bash

---
### Author
Yang Shann Wen

Learning Project: Androgen Receptor Binder Prediction and Drug Repurposing Using Random Forest
