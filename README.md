# Investigating Student Interaction with Competency-Based CS Education - Replication Package

This repository contains the complete replication package for the research paper **"Investigating Student Interaction with Competency-Based CS Education"**. The package includes anonymized data, analysis pipelines, survey instruments, and all code necessary to reproduce the study's findings.

## Repository Structure

```
├── data-processing/
│   ├── data-anonymization-pipeline.ipynb    # Data anonymization process (transparency)
│   ├── data-pipeline-paper.ipynb           # Main analysis pipeline (run this)
│   └── data/
│       ├── 00_in/                          # Input directory for raw survey data
│       ├── 01_anonymized/                  # Anonymized datasets (provided)
│       └── 02_output/                      # Generated analysis outputs
├── survey/
│   ├── pre/                               # Pre-survey UI documentation
│   │   ├── 01_CBE.pdf
│   │   ├── 02_Course.pdf
│   │   └── 03_Demographics.pdf
│   └── post/                              # Post-survey UI documentation
│       ├── 01_CBE.pdf
│       ├── 02_Tool.pdf
│       ├── 03_Course.pdf
│       ├── 04_PreSurveyCheck.pdf
│       └── 05_Demographics.pdf
├── requirements.txt                        # Python dependencies
└── README.md                              # This file
```

## Prerequisites

- **Python 3.13**
- **Jupyter Notebook** or **JupyterLab**

## Installation

1. **Download the repository:**

2. **Create and activate a virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate
   ```

2. **Install required Python packages:**
   ```bash
   pip install -r requirements.txt
   ```

3. **Launch Jupyter:**
   ```bash
   jupyter notebook
   ```
   or
   ```bash
   jupyter lab
   ```
   or use an IDE like Visual Studio Code or JetBrains Dataspell.
  
4. **Select the right Python Interpreter**
    Either select the Python Interpreter in the new virtual environment with the IDE or in the Jupyter Notebook  by opening a new terminal and running
   ```bash
   python -m ipykernel install --user --name cbe-venv --display-name "Python (cbe-venv)"
   ```
   and selecting the Kernel "Python (cbe-venv)" for each Analysis.

## Usage

### Main Analysis (Recommended)

To reproduce the study's results, run the main analysis notebook:

1. Navigate to `data-processing/`
2. Open `data-pipeline-paper.ipynb`
3. Run all cells sequentially (Cell → Run All)

**Expected runtime:** ~5-10 minutes depending on your system.

### Data Pipeline Overview

The main analysis notebook performs the following steps:

1. **Data Import:** Loads anonymized datasets from `data/01_anonymized/`
2. **Data Cleaning:** Filters, renames, and preprocesses the data
3. **User Classification:** Groups users by interaction level (No/Low/High)
4. **Statistical Analysis:** Performs descriptive and inferential statistics
5. **Visualization:** Generates publication-ready figures
6. **Output Generation:** Saves results to `data/02_output/`

### Data Anonymization Pipeline (Optional/Transparency)

The `data-anonymization-pipeline.ipynb` notebook is included for full transparency and reproducibility. It demonstrates how raw survey data was anonymized. **You do not need to run this notebook** unless you are conducting your own experiment with new data.

To use it with your own data:
1. Place raw survey exports in `data/00_in/`
2. Run `data-anonymization-pipeline.ipynb`
3. Anonymized data will be generated in `data/01_anonymized/`

## Expected Outputs

Running the main analysis notebook will generate the following files in `data/02_output/`:

### Data Files
- `science_event_with_comp.csv` - Science events mapped to competencies
- `user_mapping.csv` - User interaction group classifications

### Visualizations
- `mastery.pdf` - Mastery score analysis by interaction group
- `exam.pdf` - Exam performance analysis by interaction group  
- `perception.pdf` - Student perception survey results (Likert scales)

## Data Description

### Anonymized Datasets (`data/01_anonymized/`)

The repository includes the following anonymized datasets:

- **System/LMS Data:**
  - `competency.csv` - Competency definitions and thresholds
  - `competency_exercise.csv` - Competency-exercise mappings
  - `competency_lecture_unit.csv` - Competency-lecture unit mappings
  - `competency_user.csv` - User competency progress and confidence
  - `exercise.csv` - Exercise definitions
  - `learning_path.csv` - Learning path interactions
  - `lecture.csv` - Lecture definitions
  - `lecture_unit.csv` - Lecture unit definitions
  - `participation.csv` - Student participation data
  - `participant_score.csv` - Exercise scores
  - `participant_score_exam.csv` - Exam scores
  - `science_event.csv` - User interaction events
  - `jhi_user.csv` - User information
  - `tutorial_mapping.csv` - Tutorial mappings

- **Survey Data:**
  - `lime_survey_pre.csv` - Pre-course survey responses
  - `lime_survey_post.csv` - Post-course survey responses

### Survey Documentation (`survey/`)

The `survey/` directory contains PDF files showing the exact user interface that participants encountered during the surveys. These serve as documentation of the survey instruments used in the study.

## Research Questions Addressed

The analysis addresses three main research questions:

1. **Performance:** How does the level of interaction with CBETool relate to student performance on assessments?
2. **Engagement:** How does the level of interaction with CBETool relate to student engagement and motivation?
3. **Perception:** How do students perceive CBETool in terms of usability and learning support?

## Key Analyses Performed

- **Descriptive Statistics:** Demographics, mastery scores, exam performance, engagement metrics
- **Statistical Tests:** Kruskal-Wallis tests, Dunn's post-hoc tests, proportion z-tests
- **Visualizations:** Half-violin plots, Likert scale charts, distribution analyses
- **Effect Sizes:** Risk ratios, odds ratios, and effect size calculations

## Reproducibility Notes

- Results should be identical across different runs and systems
- The anonymized data provided ensures consistent results
- All statistical analyses include appropriate multiple comparison corrections

## Technical Notes

- The analysis pipeline handles missing data appropriately
- User interaction groups are determined by median split of competency interactions
- All visualizations are publication-ready PDF format
- Statistical significance testing includes both unadjusted and adjusted p-values

## Support

For questions about reproducing the analyses or understanding the data structure, please refer to the detailed documentation within the Jupyter notebooks. Each notebook contains comprehensive markdown cells explaining every step of the analysis process.

## Data Availability Statement

The anonymized datasets provided in this replication package contain all information necessary to reproduce the study's findings while protecting participant privacy. Raw survey data is not included to maintain anonymity but the anonymization process is fully documented for transparency.