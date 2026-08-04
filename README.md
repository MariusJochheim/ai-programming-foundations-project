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

## Bias and Data Cleaning Reflection

Poor data-cleaning decisions could introduce bias into this analysis. For
example, removing every row with missing review information would
systematically exclude listings with no reviews and make reviewed listings
overrepresented. Similarly, deleting all unusually expensive listings could
underrepresent luxury properties and disproportionately affect neighbourhoods
such as Manhattan.

For this reason, missing `reviews_per_month` values were replaced with zero
only when the listing had zero recorded reviews. Missing review dates were
retained, and high but technically possible prices were not automatically
removed. The results for small groups, particularly shared rooms and Staten
Island listings, should still be interpreted cautiously because their sample
sizes are much smaller.

## Future Integration Reflections

### How would this workflow change for a machine-learning project?

A machine-learning workflow would require a clearly defined prediction target,
such as nightly price, followed by separate training, validation, and test
datasets. Data-cleaning and feature-transformation steps would need to be fitted
using only the training data to prevent information leakage. Categorical
variables would be encoded, numerical variables might be scaled or transformed,
and baseline models would be compared using appropriate evaluation metrics and
cross-validation.

### What preparation would be required for a neural network?

Before training a neural network, categorical variables such as room type and
neighbourhood group would need to be encoded, and numerical features would
normally be scaled. Skewed variables such as price might require a logarithmic
transformation. The prepared data would then be converted into tensors and
divided into mini-batches, with separate training, validation, and test sets.
Model architecture, regularization, stopping criteria, and evaluation metrics
would also need to be selected carefully.

### How could agentic automation support this workflow?

An agentic system could automate repetitive steps such as checking the input
schema, identifying new missing-value patterns, running validation checks,
recreating visualizations, and generating draft reports. It could also monitor
new dataset releases and flag changes in distributions or data quality.
However, destructive cleaning decisions and interpretations should require
human review because an automated agent may remove valid observations or draw
unsupported conclusions.