# draft

# 🍕 Pizza Sales Analysis — Data Preprocessing

[![Project](https://img.shields.io/badge/MEXE_Electives_2-Midterm_Project-blue)](#-project-information)
[![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![Notebook](https://img.shields.io/badge/Notebook-Google_Colab%20%7C%20Jupyter-orange?logo=jupyter)](Pizza_Sales_Midterm_Project.ipynb)

A GitHub-ready academic project for preprocessing and exploring a Pizza Sales transaction dataset. The workflow is documented in a numbered, decision-based style inspired by the Antenor & Fornal Flight Price reference, while all project logic is specific to pizza sales.

> ⚠️ **Dataset notice:** The source file `pizza_sales.csv` was not included in the project package. Add the authentic dataset locally or upload it when prompted in Google Colab. Dataset-specific counts, cleaned CSV outputs, and key findings are intentionally not fabricated.

## 📑 Table of Contents

- [Project Information](#-project-information)
- [Project Overview](#-project-overview)
- [Repository Contents](#-repository-contents)
- [Preprocessing Workflow](#-preprocessing-workflow)
- [Visualizations](#-visualizations)
- [Outputs](#-outputs)
- [How to Run](#-how-to-run)
- [Dataset Attribution](#-dataset-attribution)
- [Team](#-team)

## 📋 1. Project Information

| Field | Details |
|---|---|
| 🎓 Course | MEXE Electives 2 |
| 📝 Project | Midterm Project on Data Preprocessing |
| 👥 Group Name | Manalo & Mercado |
| 🧑‍💻 Members | Manalo, Zuriel; Mercado, Rica Jean |
| 🍽️ Assigned Theme | Food |
| 🍕 Topic | Pizza Sales Analysis |

## 🔍 2. Project Overview

- 📂 **Dataset title:** `pizza_sales.csv`
- 🔗 **Dataset source:** Kaggle (https://www.kaggle.com/datasets/nextmillionaire/pizza-sales-dataset)
- ⚖️ **License / attribution:** Created and published on Kaggle by the user “nextmillionaire”. The license wasn’t visible when I opened the page, so check it on the original Kaggle page before using, modifying, or redistributing the data. Cite the author and the Kaggle link when you use it.

### 🎯 Objective

To analyze pizza order data to find sales patterns, examine the variables involved, and understand how a pizza business performs over time. The dataset contains detailed information about pizza orders, including pizza variants, quantities, pricing, dates, times, and categorization details. It can be used for exploratory data analysis, data cleaning, SQL practice, and data visualization.


## 🔄 3. Flowchart

- 🖼️ Embed your flowchart image here:

  ![Preprocessing Flowchart](flowchart/_Flowchart_Pair1Surname_Pair2Surname.png)

- 🔀 **Decisions in our flowchart:**

  | # | Decision diamond | Condition checked | ✅ YES branch | ❌ NO branch |
  |---|------------------|-------------------|--------------|-------------|
  | 1 | 🕳️ **Missing values?** | `df.isnull().sum() > 0` across any of the 12 columns | Handle missing values by column role (IDs & dates, pricing & quantity, categoricals, text), then continue | Skip to duplicate check |
  | 2 | 👯 **Duplicate rows?** | `df.duplicated().sum() > 0` | Deduplicate and consolidate order lines: drop exact full-row duplicates and resolve partial key collisions, then continue | Skip to data type conversion |
  | 3 | 📈 **Outliers detected?** | IQR / Z-score check on `quantity`, `unit_price`, `total_price` | Filter invalid records (invalid values, formula audit of `total_price = quantity × unit_price`) and cap statistical outliers, then continue | Skip to categorical encoding |
  | 4 | 📊 **More plots?** | `i < 10` | Return to the visualization loop: make plot, caption, save | Exit loop and go to **END** 🏁 |

- 🛠️ **Changes we made:**
  - 🔧 Changed ___ from ___ to ___ because ___.
  - ➕ Added ___ step that was not in the original flowchart because ___.
  - ➖ Removed ___ because the data had no ___.
