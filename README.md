# Student Success Prediction with Machine Learning 📊

This project analyses academic performance in higher education with the aim of identifying factors associated with **student dropout, enrolment and academic success**.

The analysis combines three complementary Machine Learning tasks:

- **Multiclass classification** to predict students' final academic status
- **Regression** to predict second-semester academic performance
- **Unsupervised learning** to identify student profiles through clustering

The project focuses not only on prediction, but also on understanding patterns that could support the early identification of students at risk.

## 🧠 Machine Learning Tasks

### 1. Multiclass Classification

The goal is to predict the final status of each student:

- Dropout
- Enrolled
- Graduate

The following models are compared:

- Logistic Regression
- Support Vector Machine (SVM)
- Random Forest

The analysis considers class imbalance and evaluates the models using:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion matrices
- 5-fold cross-validation

Special attention is given to the **dropout class**, as identifying students at risk is one of the main objectives of the project.

### 2. Academic Performance Regression

The second task predicts students' average grade during the second semester.

The following models are evaluated:

- Linear Regression
- Ridge Regression
- Random Forest Regression

Two different scenarios are compared:

**Scenario A:** Prediction using demographic and contextual information.

**Scenario B:** Prediction incorporating first-semester academic performance.

The models are evaluated using:

- MAE
- RMSE
- R²

### 3. Student Profiling with Unsupervised Learning

The final part explores whether meaningful student profiles can be identified without using the target variable.

The analysis includes:

- K-Means clustering
- Elbow Method for selecting the number of clusters
- Cluster stability analysis using different random seeds
- Interpretation of the resulting student profiles

A solution with **K = 3** is selected and analysed.

## 📊 Results

### Classification

Among the evaluated models, **Random Forest** achieved the best overall performance:

| Model | Accuracy | Dropout Recall | Weighted F1 |
|---|---:|---:|---:|
| Random Forest | **77.7%** | **77.1%** | **75.4%** |
| Logistic Regression | 75.5% | 74.3% | 74.3% |
| SVM | 72.9% | 65.8% | 70.9% |

A class-balanced Random Forest was also evaluated using **5-fold cross-validation**, obtaining a mean macro F1-score of approximately **0.714 ± 0.012**.

The *Enrolled* class proved more difficult to distinguish than *Dropout* and *Graduate*.

### Regression

Including first-semester academic information significantly improved the prediction of second-semester performance.

| Model | RMSE | MAE | R² |
|---|---:|---:|---:|
| Ridge Regression | **2.61** | 1.64 | **0.749** |
| Random Forest | 2.64 | **1.40** | 0.743 |

Without first-semester academic information, the best models achieved an R² of around **0.40**, highlighting the predictive importance of early academic performance.

### Unsupervised Learning

The clustering analysis identified **three differentiated student profiles** with clear differences in academic performance and final outcomes.

Graduation rates ranged from approximately **40% to 77%** across the three groups, showing that meaningful student profiles can be identified even without using the final academic status during training.

## 🛠️ Technologies

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Jupyter Notebook

## 📂 Project Structure

```text
student-success-machine-learning/
│
├── tarea1_clasificacion.ipynb
├── tarea2_regresion.ipynb
├── tarea3_aprendizaje_no_supervisado.ipynb
├── rendimiento_estudiantes.csv
│
├── report/
│   └── project-report.pdf
│
└── README.md
```

## 🔎 Main Findings

- First-semester academic performance is one of the strongest predictors of future academic success.
- Different student profiles can be identified through clustering.
- Non-linear and regularised models improve predictive performance compared with simpler approaches.
- Machine Learning can provide useful information for identifying students who may require additional academic support.

## ⚠️ Limitations

- The results represent statistical associations and should not be interpreted as causal relationships.
- The target variable presents class imbalance.
- K-Means clustering is sensitive to the selected number of clusters.
- Intermediate academic states may overlap and be more difficult to classify.

## 📄 Project Report

A detailed description of the methodology, analysis and conclusions is available in the [project report](report/project-report.pdf).

## 👩‍💻 Author

**Míriam Mingo Revuelta**  
Mathematical Engineering and Artificial Intelligence  
Universidad Pontificia Comillas – ICAI
