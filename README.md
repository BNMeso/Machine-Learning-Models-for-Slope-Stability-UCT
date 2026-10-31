
# Machine Learning Models for Slope Stability: UCT Parking Areas 7 and 8

Code supporting the dissertation *Development of a Simple AI-Based Classification Model for
Slope Stability Assessment Using Case Data from UCT Parking Areas 7 and 8* 
(B. Meso, University of Cape Town, 2026; supervisor: Prof D. Kalumba).

Two tree-based classifiers, XGBoost and a Random Forest (bagged trees), are trained on a
compiled external case-history dataset to classify slopes as Stable or Unstable from six
inputs: unit weight, cohesion, friction angle, slope angle, slope height and pore pressure
ratio. They are then tested on the two sections of the UCT slope and compared with the
conventional limit equilibrium analysis of Kantey and Templer (2025).

## Files

| File | Purpose |
|---|---|
| `XGBoost Model_Code.ipynb` | XGBoost model: cross-validated tuning, final fit and test results (Python notebook) |
| `UCT_RF_Model_.m` | Random Forest model in MATLAB [describe: training and/or evaluation] |
| `ClassificationLearnerSession002.mat` | MATLAB Classification Learner session containing the Random Forest configurations compared and their validation results |

## Random Forest settings

Bagged decision trees: 100 learners, maximum number of splits 442 (tree depth not
restricted), number of predictors per split left at the MATLAB default (square root of the
number of predictors). This configuration was selected from four Random Forest configurations
by 5-fold cross-validation accuracy; no systematic hyperparameter search was carried out.
The session file also contains other models that were trained and compared during
development.

## Requirements

- Python [3.13.5] with xgboost, scikit-learn, pandas and numpy
- MATLAB R2026a with the Statistics and Machine Learning Toolbox


## Data sources

External dataset: Ma et al. (2022), *Sensors* 22, 9166, compiled from earlier studies.
UCT slope inputs: derived from the Kantey and Templer Consulting Engineers geotechnical
report, Project 17327S (2025).
