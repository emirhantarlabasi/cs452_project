CS452 Flight Pricing & Dynamic Revenue Optimization
This project implements a comprehensive Machine Learning pipeline designed for an Airline Revenue Management scenario. It predicts ticket price categories (Cheap, Normal, Expensive) and features a Dynamic Pricing Engine that adjusts fares based on real-time factors like demand and user behavior.

Project Highlights
To meet the CS452 course requirements, the following steps were implemented:

Feature Engineering: Derived high-value features such as urgency_score and simulated user interaction metrics.

Target Binning: Transformed continuous price data into discrete categories (0: Low, 1: Mid, 2: High) using statistical quantiles.

Imbalanced Learning: Addressed class imbalance in "Premium" tickets using SMOTE (Synthetic Minority Over-sampling Technique).

Statistical Comparison: Validated model superiority (e.g., XGBoost vs. Random Forest) using the McNemar Test.

Dynamic Pricing Demo: A rule-based simulation showing how the model's output combined with "User Urgency" affects final ticket pricing in real-time.

File Structure
CS452_Flight_Pricing.ipynb: The primary Jupyter Notebook containing the full end-to-end workflow.

data/Data_Train.csv: The core flight booking dataset.

requirements.txt: List of Python dependencies required to run the project.

Setup & Execution (Windows / PowerShell)
Navigate to the project folder (OneDrive example path):

```powershell
cd "$env:USERPROFILE\OneDrive\Masaüstü\CS452_Project"
```

Create and activate a virtual environment:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

Install the Jupyter Kernel:

```powershell
python -m ipykernel install --user --name cs452_project --display-name "Python 3 (CS452 Project)"
```

Launch the Project:

```powershell
jupyter lab
```

Open `CS452_Flight_Pricing.ipynb`, ensure the kernel is set to **Python 3 (CS452 Project)**, then **Run All** to execute the pipeline end-to-end.

Important Note
The original dataset lacks real-time fields (e.g., `days_left`, user revisit counts, live occupancy), so these are **simulated inside the notebook** to illustrate the airline pricing scenario and dynamic pricing demo.