# heart-disease-bayesian-network-analysis
Heart Disease Risk Prediction - Data Detective Project
MediMystery Labs - Bayesian Network Analysis
A comprehensive data science project that uses Bayesian Networks to predict heart disease risk from patient records. This project demonstrates advanced probabilistic modeling, data preprocessing, and medical inference capabilities.
🎯 Project Overview
As a Data Detective at MediMystery Labs, this project tackles the critical challenge of heart disease risk prediction using:

Bayesian Networks: Probabilistic graphical models for uncertainty reasoning
Data Preprocessing: Comprehensive cleaning and normalization pipeline
Medical Inference: Evidence-based diagnostic probability calculations
Visualization: Clear representation of network structure and results

🔬 Key Features

✅ Automated data cleaning (duplicates, missing values)
✅ Min-Max normalization for numeric features
✅ Bayesian Network construction with medical domain structure
✅ Maximum Likelihood Estimation for parameter learning
✅ Probabilistic inference for diagnostic questions
✅ Comprehensive visualizations and reporting

📊 Dataset Information
Source: Heart Disease Dataset (heart_disease.csv)
URL: https://bit.ly/3T1A7Rs
Variables Include:

age: Patient age
chol: Serum cholesterol level
fbs: Fasting blood sugar > 120 mg/dl
thalach: Maximum heart rate achieved
target: Heart disease presence (0/1)

🏗️ Network Structure
The Bayesian Network follows medical domain knowledge:
age → fbs → target → chol
              ↓
           thalach
This structure represents:

Age influences fasting blood sugar levels
Fasting blood sugar affects heart disease risk
Heart disease impacts cholesterol and heart rate patterns

🚀 Setup Instructions
Prerequisites
bashPython 3.8+
pip package manager
Installation

Clone the repository

bashgit clone <repository-url>
cd heart-disease-detective

Install required packages

bashpip install -r requirements.txt
Required packages:
pandas>=1.3.0
numpy>=1.21.0
matplotlib>=3.4.0
seaborn>=0.11.0
scikit-learn>=1.0.0
pgmpy>=0.1.18
networkx>=2.6.0

Download the dataset

bash# Download from https://bit.ly/3T1A7Rs
# Save as heart_disease.csv in the project directory
🎮 Usage
Quick Start
bashpython heart_disease_detective.py
Step-by-Step Analysis
pythonfrom heart_disease_detective import HeartDiseaseDetective

# Initialize detective
detective = HeartDiseaseDetective('heart_disease.csv')

# Run complete analysis
detective.run_complete_analysis()
Custom Analysis
python# Load and clean data
detective.load_data()
detective.clean_data()
detective.normalize_data()

# Build Bayesian Network
detective.discretize_for_bayesian()
detective.build_bayesian_network()

# Perform inference
results = detective.perform_inference()
📈 Sample Outputs
Data Cleaning Results
🧹 CLEANING DATA
==========================================
Duplicates removed: 5
Rows with missing values removed: 12
Final clean dataset shape: (290, 14)
✅ Cleaned data saved as 'cleaned_heart_disease.csv'
Bayesian Network Training
🕸️ BUILDING BAYESIAN NETWORK
==========================================
Network structure: [('age', 'fbs'), ('fbs', 'target'), ('target', 'chol'), ('target', 'thalach')]
Training model using Maximum Likelihood Estimation...
✅ Bayesian Network model is valid!
Probabilistic Inference Results
P(Heart Disease | High Age)
╒═══════════╤═══════════════╕
│ target    │   phi(target) │
╞═══════════╪═══════════════╡
│ target(0) │        0.3524 │
├───────────┼───────────────┤
│ target(1) │        0.6476 │
╘═══════════╧═══════════════╛
Interpretation: Patients with high age have a 64.76% probability of heart disease.
P(Cholesterol | Heart Disease = Yes)
╒═════════╤════════════╕
│ chol    │   phi(chol) │
╞═════════╪════════════╡
│ chol(0) │     0.2847  │
├─────────┼────────────┤
│ chol(1) │     0.4329  │
├─────────┼────────────┤
│ chol(2) │     0.2824  │
╘═════════╧════════════╛
Interpretation: Given heart disease, cholesterol levels show highest probability in medium range (43.29%).
📊 Generated Files
After running the analysis, the following files are created:
FileDescriptioncleaned_heart_disease.csvDataset after removing duplicates and missing valuesnormalized_heart_disease.csvMin-max normalized numeric featuresdiscretized_heart_disease.csvDiscretized variables for Bayesian Networkbayesian_network_structure.pngNetwork topology visualizationinference_results.pngProbability distribution plotsanalysis_report.mdComprehensive analysis summary
🔍 Key Diagnostic Questions Answered

Risk Assessment: What's the probability of heart disease given patient age?
Feature Correlation: How does cholesterol distribute in heart disease patients?
Metabolic Indicators: What's the relationship between age and fasting blood sugar?
Cardiovascular Patterns: How do heart rate patterns relate to disease presence?

📸 Visualizations
Network Structure
Show Image
The network shows the probabilistic dependencies between medical variables, enabling transparent reasoning about diagnostic relationships.
Inference Results
Show Image
Bar plots displaying probability distributions for key diagnostic queries, making medical insights accessible to healthcare professionals.
🎯 Medical Insights
High-Risk Profiles

Age Factor: Older patients show significantly higher heart disease probability
Metabolic Connection: Fasting blood sugar levels serve as intermediate risk indicators
Cardiovascular Markers: Heart rate patterns provide diagnostic value

Clinical Applications

Screening Programs: Identify high-risk patients for preventive care
Resource Allocation: Prioritize diagnostic resources based on probability scores
Treatment Planning: Evidence-based risk stratification for intervention timing

🧠 Technical Approach
Data Preprocessing Pipeline

Quality Control: Remove duplicates and handle missing data
Normalization: Standardize numeric ranges using Min-Max scaling
Discretization: Convert continuous variables to categorical for Bayesian modeling

Bayesian Network Methodology

Structure Learning: Domain-knowledge driven network topology
Parameter Learning: Maximum Likelihood Estimation from data
Inference Engine: Variable Elimination for probabilistic queries

Model Validation

Network topology validation using pgmpy
Conditional probability distribution verification
Inference consistency checks

🚀 Future Enhancements
Model Improvements

Structure Learning: Automated network discovery from data
Feature Engineering: Additional derived medical indicators
Cross-Validation: Robust model performance assessment

Clinical Integration

Real-time Inference: API for live diagnostic support
Uncertainty Quantification: Confidence intervals for predictions
Explainable AI: Detailed reasoning paths for medical decisions

📚 References

pgmpy Documentation: Bayesian Network implementation
Medical Literature: Heart disease risk factor research
Data Science Best Practices: Reproducible analysis workflows

👥 Contributing

Fork the repository
Create feature branch (git checkout -b feature/enhancement)
Commit changes (git commit -am 'Add new feature')
Push to branch (git push origin feature/enhancement)
Create Pull Request
