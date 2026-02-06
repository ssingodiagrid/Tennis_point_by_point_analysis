# Tennis Point-by-Point Analysis
![Alt Text](/Users/ssingodia/Downloads/Tennis/image.png)

A comprehensive data analysis project investigating ATP tennis match dynamics through point-by-point (pbp) data. This project explores critical factors that influence match outcomes, including first-set advantage, player resilience, match duration, and the relationship between match intensity and duration.

## Project Overview

This project analyzes ATP professional tennis matches using detailed point-by-point data to uncover patterns and insights about competitive tennis. The analysis is structured around four key research questions, each examining different aspects of match dynamics and player performance.

## Dataset

- **Source**: ATP Main Archive Point-by-Point Data
- **File**: `Notebook/Data/pbp_matches_atp_main_archive.csv`
- **Format**: Point-by-point match records with detailed scoring information
- **Processed Data**: `Notebook/Cleaned_dataset.csv`

## Project Structure

```
Tennis/
├── README.md                          # Project documentation
├── Notebook/
│   ├── Data/
│   │   └── pbp_matches_atp_main_archive.csv    # Raw ATP match data
│   ├── Cleaning.ipynb                 # Data cleaning and validation pipeline
│   ├── Cleaned_dataset.csv            # Processed dataset (output from cleaning)
│   ├── Overall_analysis.ipynb         # Comprehensive statistical summary
│   ├── Analysis_1.ipynb               # Duration analysis by set count
│   ├── Analysis_2.ipynb               # First set advantage study
│   ├── Analysis_3.ipynb               # Player resilience and comebacks
│   ├── Analysis_4.ipynb               # Match intensity vs. duration
│   ├── visual1_first_set_advantage.png
│   ├── visual2_duration_dist.png
│   ├── visual4_resilience.png
│   └── visual5_points_vs_duration.png
├── report/
│   └── Tennis Point by Point Analysis.pdf     # Final analysis report
```

## Analysis Components

### 1. Data Cleaning Pipeline (`Cleaning.ipynb`)

A comprehensive data cleaning and validation workflow:

- **Data Loading**: Imports raw ATP match data from CSV
- **Score Validation**: Verifies match winners match recorded scores
- **Data Parsing**: Extracts point-by-point play sequences
- **Duplicate Removal**: Eliminates duplicate match records
- **Quality Filtering**:
  - Duration validation (30–500 minutes)
  - Date format standardization
  - Removal of missing critical fields
- **Output**: `Cleaned_dataset.csv` containing validated match data

**Key Transformations:**
- Parses point strings (S=Server, R=Receiver, A=Ace)
- Extracts set winners from compressed format
- Calculates total match duration and point counts
- Standardizes temporal data

### 2. Duration Analysis (`Analysis_1.ipynb`)

**Research Question**: How does match length vary based on the number of sets played?

**Key Findings:**
- Compares average match duration for 2-set vs. 3-set matches
- Identifies impact on tournament scheduling
- Uses duration distribution visualization (histogram with KDE)
- Reveals significant time differences that affect tournament planning


### 3. First Set Advantage (`Analysis_2.ipynb`)

**Research Question**: Does winning the first set guarantee a match victory?

**Analysis Methods:**
- Feature engineering to extract first set winner
- Compares first set winner with match winner
- Calculates win probability for first set advantages
- Statistical testing of hypothesis

---

### 4. Player Resilience (`Analysis_3.ipynb`)

**Research Question**: Who bounces back after losing the first set? Which players show the highest resilience?

**Methodology:**
- Identifies players who lose first set but win matches (comebacks)
- Calculates resilience score: Win% after losing first set
- Ranks players by comeback frequency and success
- Measures overall comeback potential

---

### 5. Match Intensity vs. Duration (`Analysis_4.ipynb`)

**Research Question**: Can match duration be predicted from the number of points played?

**Analysis Approach:**
- Parses point-by-point data to count total points
- Calculates match intensity metrics
- Analyzes correlation between points played and duration
- Identifies outliers and exceptional matches

---


## Key Findings Summary

1. **Match Duration**: 3-set matches take substantially longer than 2-set matches, affecting tournament schedules
2. **First Set Advantage**: Winning the first set is a strong predictor of match victory
3. **Player Resilience**: Certain players excel at comebacks, showing high win rates after losing the first set
4. **Match Intensity**: Strong correlation exists between total points played and match duration

## Technical Details

### Technologies Used
- **Python**: Data analysis and visualization
- **Pandas**: Data manipulation and cleaning
- **NumPy**: Numerical computations
- **Matplotlib & Seaborn**: Statistical visualizations
- **Jupyter Notebooks**: Interactive analysis and documentation

### Data Processing
- Point notation parsing (S, R, A)
- Set winner extraction and aggregation
- Outlier detection and filtering
- Temporal data standardization

## Installation & Setup

1. Ensure Python 3.7+ is installed
2. Install required packages:
   ```bash
   pip install pandas numpy matplotlib seaborn jupyter
   ```
3. Navigate to the Notebook directory
4. Run notebooks in order: Cleaning → Analysis_1 through Analysis_4 → Overall_analysis


