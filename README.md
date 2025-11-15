# COVID-19 Clinical Trials Analysis & Classification

## Project Overview
This project focuses on analyzing and classifying **COVID-19 clinical trial data** to uncover trends and predict the **study phase** of each trial using both structured and unstructured (text-based) information.

The work was completed as part of a **virtual data science internship project**, aiming to demonstrate the end-to-end workflow of real-world data analysis and supervised learning — from preprocessing to model evaluation.

---

## Dataset
The dataset contains information about **clinical trials conducted during the COVID-19 pandemic**, including:
- Study title and description  
- Interventions and outcome measures  
- Study phase (target variable)  
- Enrollment numbers, start date, and age information  

### Sample Columns
| Column | Description |
|:--------|:-------------|
| `Title` | Title of the clinical study |
| `Interventions` | Details about treatments or vaccines used |
| `Outcome Measures` | Study outcome descriptions |
| `Enrollment` | Number of participants enrolled |
| `Start Date` | Date when the trial began |
| `Phase` | Phase of clinical trial (target) |
| `Age` | Participant age range |

---

## Data Preprocessing

### Steps Performed:
1. **Missing Value Handling** — Replaced nulls in categorical/text fields with `"Unknown"`.
2. **Text Cleaning** — 
   - Lowercasing text  
   - Removing punctuation, digits, and stopwords  
   - Lemmatization using `spaCy`  
3. **Age Feature Engineering** —  
   - Extracted `min_age` and `max_age`  
   - Created categorical `Age_Group` (e.g., *Child*, *Adult*, *Older Adult*)  
   - Dropped original age-related columns post-encoding  
4. **Date Processing** —  
   - Extracted the `Year` from `Start Date` for temporal analysis  
5. **Final Save** — Produced a clean dataset ready for analysis and modeling.

---

## Exploratory Data Analysis (EDA)

Exploratory analysis was performed to understand data trends, distributions, and relationships between study characteristics.

### Key Visualizations:
- **Distribution of Trials by Year:** Demonstrated surge in research during 2020–2021.
- **Top Interventions and Conditions:** Showed vaccine- and drug-related studies dominating the dataset.
- **Phase Distribution:** Identified imbalance between early and late-phase trials.
- **Time-Series Trends:** Highlighted the evolution of COVID-19 studies over time.
- **Map Visualization:** Plotted a choropleth map showing the count of trials in the world map by each country.


---

## Model Development

### Objective
To classify each trial into its **study phase** and **study type** based on structured and textual information.

### Input Features
- Textual: `Title`, `Interventions`, `Outcome Measures` (TF-IDF vectorized)  
- Structured: `Enrollment`, `Year`, `Age_Group`

### Target Variable
- `Phase` (Categorical), `Study Type`(Categorical)

---
