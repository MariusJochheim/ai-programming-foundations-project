# New York City Airbnb Data Workflow

## Project Description

This project analyzes New York City Airbnb listing data using a reproducible
Python notebook workflow. It cleans the data, creates exploratory summaries, and
visualizes how listing prices and availability vary by neighbourhood group and
room type.

## What I Built

I built a Jupyter Notebook, `data_workflow.ipynb`, that:

- loads and inspects the dataset;
- cleans the Airbnb listing data;
- summarizes prices, availability, reviews, and host listing counts;
- creates labeled visualizations;
- records the main findings and limitations.

## Dataset

Dataset: [New York City Airbnb Open Data (2019)](https://www.kaggle.com/datasets/dgomonov/new-york-city-airbnb-open-data)

Place the downloaded CSV file here:

```text
dataset/AB_NYC_2019.csv
```

## How to Run the Project

Clone the repository and enter the project folder:

```bash
git clone https://github.com/MariusJochheim/ai-programming-foundations-project
cd ai-programming-foundations-project
```

Create and activate a virtual environment:

```bash
python3.12 -m venv .venv
source .venv/bin/activate
```

On Windows PowerShell, activate the environment with:

```powershell
.venv\Scripts\Activate.ps1
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Open Jupyter Notebook:

```bash
jupyter notebook
```

Open `data_workflow.ipynb` and run all cells from top to bottom.

## Create `requirements.txt`

After installing the project dependencies in your virtual environment, create or
update `requirements.txt` with:

```bash
pip freeze > requirements.txt
```
