# Network Intrusion Detection — CICIoT2023

A machine-learning notebook for **binary network traffic classification**: benign traffic (`0`) versus DDoS traffic (`1`), using selected CSV files from the CICIoT2023 dataset.

## Project contents

```text
network-intrusion-detection/
├── data/
│   ├── CICIoT2023/
│   └── README.md
├── notebooks/
│   └── network_intrusion_detection.ipynb
├── .gitignore
├── .gitattributes
├── LICENSE
├── README.md
└── requirements.txt
```

## What the notebook does

1. Checks for the required benign and DDoS CSV files.
2. Samples benign traffic and 12 DDoS traffic categories.
3. Cleans column names and replaces infinite numeric values with missing values.
4. Splits the data into stratified training and test sets.
5. Builds a preprocessing and Random Forest pipeline.
6. Evaluates a baseline model and a class-weighted model.
7. Tunes Random Forest hyperparameters with `RandomizedSearchCV`.
8. Compares accuracy, precision, recall, F1 score and ROC-AUC, and displays plots and per-attack-subtype results.

The notebook samples up to **350,000 benign rows** and **75,000 rows per DDoS subtype**. Actual row counts depend on the supplied CSV files.

## Requirements

- Python 3.9 or later (a recent Python 3 version is recommended)
- The packages listed in `requirements.txt`
- Jupyter Notebook or JupyterLab
- CICIoT2023 CSV files (not included in this repository)

## Setup

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/network-intrusion-detection.git
cd network-intrusion-detection
```

Replace `YOUR-USERNAME` with your GitHub username and adjust the repository name if you choose another one.

### 2. Create and activate a virtual environment (recommended)

Windows:

```bash
python -m venv .venv
.venv\Scripts\activate
```

macOS / Linux:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install dependencies

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### 4. Add the dataset locally

Download/obtain the CICIoT2023 dataset from its official source and place the required CSV files in:

```text
data/CICIoT2023/
```

See [`data/README.md`](data/README.md) for the exact filenames expected by the notebook. The dataset is intentionally excluded from Git because it can be very large and may have separate usage terms. Follow the dataset provider's license and citation requirements.

### 5. Run the notebook

```bash
jupyter notebook
```

Open `notebooks/network_intrusion_detection.ipynb` and run the cells from top to bottom.

## Notes

- The notebook uses a fixed random seed (`42`) for reproducible sampling and splitting.
- Hyperparameter tuning can take a significant amount of time and memory on a large dataset.
- Results depend on the exact dataset files, their versions, and the runtime environment.
- This is a research/educational project, not a production network-security system.
- No trained model file or measured performance result is included in this repository by default. Run the notebook to generate results.

## Dataset acknowledgement

This project uses the CICIoT2023 dataset. Please retain the dataset's original attribution, license terms and citation instructions when using or redistributing it. Add the exact dataset citation/reference here after confirming it from the source where you obtained the data.

## Author

Add your name, course/institution (if appropriate), and contact or portfolio link here.
