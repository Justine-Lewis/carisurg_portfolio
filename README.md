# CariSurg Portfolio

This repository contains my work for the CariSurg MedTech Pathways Virtual Programme. It documents my progress in applying software engineering, data analysis, literature review, and responsible AI practices to a healthcare-focused emergency triage project.

The project is based on a fictional Caribbean hospital scenario, Mercer General Hospital, where the Clinical AI & Innovation Unit is exploring whether machine learning can support emergency department triage and admission-risk prediction.

## Purpose

The purpose of this repository is to make my CariSurg work clear, organised, and audit-ready. A clinical or technical reviewer should be able to open the repository and understand:

* what the project is about;
* what work has been completed;
* where the notebooks and documents are stored;
* how the project is structured;
* which tools and libraries were used.

## Repository Structure

```text
carisurg-portfolio/
│
├── data/
│   └── README.md
│
├── docs/
│   ├── Week-1-Preliminary-Proposal.docx
│   └── Week-1-Memo.pdf
|   └── risk-register.csv

│
├── notebooks/
│   └── FinalWeek0_Notebook.ipynb
│
├── .gitignore
├── LICENSE
├── README.md
└── requirements.txt
```

## Folder Descriptions

### `data/`

This folder is reserved for dataset-related files. No real patient data or confidential clinical data should be committed to this repository.

The Week 0 dataset used for exploratory analysis should only be stored locally or in an approved private location if required by the programme.

### `notebooks/`

This folder contains Jupyter notebooks used for exploratory data analysis and technical exercises.

The Week 0 notebook focuses on basic emergency triage data exploration, including cleaning selected variables, visualising vital signs, and identifying simple at-risk patient logic.

### `docs/`

This folder contains written project documentation, including the Week 1 memo and preliminary proposal.

The Week 1 proposal explores the potential use of machine learning to support emergency department triage and admission-risk prediction in a Caribbean hospital context.

## Current Project Focus

The current project investigates whether early emergency department triage data could support admission-risk prediction using machine learning.

The proposed pilot compares:

* Logistic Regression as a baseline model;
* a stacking ensemble using Logistic Regression and Random Forest;
* model performance using metrics such as AUC-ROC, precision, recall, F1-score, and confusion matrix;
* interpretability using SHAP-based feature importance.

The project does not propose replacing emergency nurses or clinicians. Instead, it explores how AI-assisted decision support could provide an additional signal during triage while maintaining clinical oversight.

## Tools and Technologies

The repository may include work using:

* Python
* Jupyter Notebook
* pandas
* NumPy
* matplotlib
* scikit-learn
* Git and GitHub
* Zotero for reference management

## How to Run the Notebook

1. Clone the repository:

```bash
git clone https://github.com/YOUR-USERNAME/carisurg-portfolio.git
```

2. Move into the project folder:

```bash
cd carisurg-portfolio
```

3. Create and activate a virtual environment:

```bash
python -m venv venv
```

On Windows:

```bash
venv\Scripts\activate
```

On macOS/Linux:

```bash
source venv/bin/activate
```

4. Install the required libraries:

```bash
pip install -r requirements.txt
```

5. Open Jupyter Notebook:

```bash
jupyter notebook
```

6. Navigate to the `notebooks/` folder and open the Week 0 notebook.

## Data Privacy Notice

This repository should not contain real patient-identifiable data, confidential hospital records, passwords, API keys, or private credentials.

Any dataset used for programme exercises should be de-identified, synthetic, publicly shareable, or stored outside the public repository according to programme instructions.

## Documentation Standard

This repository is organised to support reproducibility and review. Work should be committed with clear messages, and major changes should be made through feature branches and pull requests.

## Author

Justine Lewis
BSc Computer Science
University of the West Indies, Mona
CariSurg MedTech Pathways Virtual Programme

## Licence

This repository is licensed under the MIT Licence.
