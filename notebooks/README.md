## End-to-End Insurance Risk Analytics - Week 3

This project provides an end-to-end workflow for insurance risk analytics, focusing on data exploration, cleaning, and visualization using Python. The analysis leverages libraries such as pandas, numpy, matplotlib, seaborn, and plotly for both static and interactive insights.  
**Data Version Control (DVC)** is used to track and manage data files and pipeline stages.

---

## Table of Contents

- [Project Structure](#project-structure)
- [Setup Instructions](#setup-instructions)
- [Data Preparation](#data-preparation)
- [Usage](#usage)
- [Features](#features)
- [Example Visualizations](#example-visualizations)
- [Troubleshooting](#troubleshooting)
- [DVC Integration](#dvc-integration)
- [License](#license)
- [Author](#author)

---

## Project Structure

```
end-to-end-insurance-risk-analytics-week3/
│
├── notebooks/
│   └── Task1.ipynb         # Main Jupyter notebook for analysis and visualization
│   └── README.md           # Project documentation
├── MachineLearningRating_v3.txt   # Raw data file (tracked by DVC)
├── MachineLearningRating_v3.csv   # Cleaned CSV data (generated, tracked by DVC)
├── .dvc/                   # DVC cache and config
├── dvc.yaml                # DVC pipeline definition (if used)
└── ...
```

---

## Setup Instructions

1. **Clone the repository** (if applicable) or download the project files.

2. **Install required Python packages**  
   Open a terminal or a Jupyter notebook cell and run:
   ```
   pip install pandas numpy matplotlib seaborn plotly nbformat dvc
   ```

3. **Install DVC (if not already installed)**  
   ```
   pip install dvc
   ```

4. **Pull data files with DVC**  
   If you have access to the DVC remote storage, run:
   ```
   dvc pull
   ```
   This will download the tracked data files (e.g., `MachineLearningRating_v3.txt`, `MachineLearningRating_v3.csv`).

---

## Data Preparation

- The notebook includes a function to convert the raw `.txt` data to `.csv` format.
- Ensure `MachineLearningRating_v3.txt` is present in the project directory before running the notebook.
- The conversion function will generate `MachineLearningRating_v3.csv` for analysis.
- Both data files can be tracked and versioned using DVC.

---

## Usage

1. Open `notebooks/Task1.ipynb` in VS Code or JupyterLab.
2. Run all cells sequentially.
3. The notebook will:
   - Convert the raw data to CSV (if needed)
   - Load the data into a pandas DataFrame
   - Perform data summarization and quality checks
   - Generate a variety of visualizations for exploratory analysis

---

## Features

- **Data Summarization**
  - Descriptive statistics for numerical columns
  - Data type inspection
  - Missing value and duplicate detection

- **Visualization**
  - Histograms for numerical features
  - Bar plots for categorical features
  - Correlation heatmap
  - Scatterplots and boxplots for bivariate analysis
  - Interactive Plotly charts for trends and categorical distributions
  - Geographic choropleth for state-level premium analysis

- **Outlier Detection**
  - Boxplots for key numeric columns

---

# Visualizations

- **TotalPremium vs TotalClaim by AutoMake** (interactive scatter plot)
- **Monthly Premium Trends by Cover Type** (interactive line plot)
- **Top 10 Auto Makes** (bar plot)
- **Average Premium by State** (choropleth map)
- **Distribution of TotalPremium by CoverType** (boxplot)

---

## Troubleshooting

- **Plotly rendering issues:**  
  Ensure `nbformat` is installed and up to date:
  ```
  pip install --upgrade nbformat
  ```
- **Import errors:**  
  Double-check that all required packages are installed in your environment.
- **Data file not found:**  
  Make sure `MachineLearningRating_v3.txt` is in the project root or update the path in the notebook.
- **DVC issues:**  
  Ensure DVC is installed and configured. If you cannot pull data, check your remote storage access.

---

## DVC Integration

- **Track data files:**  
  To track a data file with DVC, run:
  ```
  dvc add MachineLearningRating_v3.txt
  dvc add MachineLearningRating_v3.csv
  ```
- **Commit DVC metadata:**  
  ```
  git add MachineLearningRating_v3.txt.dvc MachineLearningRating_v3.csv.dvc .gitignore
  git commit -m "Track data files with DVC"
  ```
- **Push data to remote storage:**  
  ```
  dvc remote add -d myremote <remote-storage-url>
  dvc push
  ```
- **Pull data from remote:**  
  ```
  dvc pull
  ```


