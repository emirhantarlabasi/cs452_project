CS452 – Flight Pricing & Dynamic Revenue Optimization

In this project, I modeled an airline revenue management scenario using Machine Learning techniques.
Instead of directly predicting ticket prices, the main objective is to classify flight tickets into three price categories: Cheap, Normal, and Expensive, and then demonstrate how this output can be used in a dynamic pricing setting.

The entire workflow is implemented in a single Jupyter Notebook, following an end-to-end Machine Learning pipeline that meets the requirements of the CS452 course.

Project Overview

The following steps were implemented as part of the project:

Feature Engineering:
New informative features were derived from the raw dataset, including:

An urgency score based on the remaining time to departure

Simulated user interaction features representing how many times a user revisits the flight page

Target Binning:
The continuous ticket price variable was transformed into three discrete classes using statistical quantiles:

0 → Cheap

1 → Normal

2 → Expensive
This converts the problem into a multi-class classification task.

Handling Class Imbalance:
Since “Expensive” tickets appear less frequently in the dataset, SMOTE (Synthetic Minority Over-sampling Technique) was applied during training to balance the class distribution.

Model Comparison:
Decision Tree, Random Forest, and XGBoost models were trained using the same data split and evaluated using classification metrics.

Statistical Validation:
To determine whether the performance difference between the best-performing models was statistically significant, the McNemar Test was applied.

Dynamic Pricing Demonstration:
A rule-based dynamic pricing simulation was created by combining the model’s predicted price category with user urgency indicators.
This section demonstrates how Machine Learning predictions could be integrated into a real-time airline pricing system.

File Structure

CS452_Flight_Pricing.ipynb
The main Jupyter Notebook containing the full workflow, including EDA, feature engineering, model training, evaluation, and the dynamic pricing demo.

data/Data_Train.csv
The primary flight booking dataset used in the project.

requirements.txt
A list of Python dependencies required to run the project.

Setup & Execution (Windows / PowerShell)

Navigate to the project directory (example OneDrive path):

cd "$env:USERPROFILE\OneDrive\Masaüstü\CS452_Project"


Create and activate a virtual environment:

python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt


Install the Jupyter kernel:

python -m ipykernel install --user --name cs452_project --display-name "Python 3 (CS452 Project)"


Launch the notebook environment:

jupyter lab


Open CS452_Flight_Pricing.ipynb, select the kernel
Python 3 (CS452 Project), and run Run All to execute the full pipeline.

Important Note

The original dataset does not include real-time operational variables such as:

days remaining until departure

user revisit counts

live seat occupancy information

Therefore, these features are simulated within the notebook to demonstrate the logic of an airline dynamic pricing system in an academic setting.
