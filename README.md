# 🧠 IBM HR Analytics Employee Attrition & Performance

## 📘 Project Overview

Employee attrition is one of the most critical challenges faced by organizations. It impacts productivity, stability, and overall business performance.
This project analyzes the factors influencing employee attrition using **data analytics** and **machine learning**, providing insights that can help HR teams take proactive actions to retain valuable employees.

The goal is to answer key business questions such as:

* Which employee characteristics are most associated with attrition?
* What factors contribute most to employee turnover?
* How can predictive modeling help HR prevent future attrition?

---

## 📊 Dataset Description

**Dataset Source:** [IBM HR Analytics Employee Attrition & Performance](https://drive.google.com/file/d/1tv2dfgghMKzN_mKmdn0ymCUrkwVvBk3w/view)
**Records:** 1,470 employees
**Features:** 35 columns (demographics, job satisfaction, compensation, etc.)
**Target Variable:** `Attrition` (Yes / No)

This dataset was developed by **IBM data scientists** for workforce analytics research.

---

## 🎯 Objectives of the Analysis

1. **Understand Current Turnover Rates** – Analyze overall attrition trends and demographic distribution by age, gender, education, and department.
2. **Identify Key Factors Influencing Turnover** – Explore job satisfaction, work-life balance, compensation, and performance metrics.
3. **Build Predictive Models** – Use ML algorithms to predict employee attrition.
4. **Generate Business Insights** – Recommend strategies to improve employee retention and engagement.

---

## 🧹 Data Preprocessing

| Step             | Description                                                                 |
| ---------------- | --------------------------------------------------------------------------- |
| Missing Values   | No missing data found                                                       |
| Duplicates       | None detected                                                               |
| Encoding         | Label Encoding for categorical variables                                    |
| Scaling          | Applied on numerical features like `MonthlyIncome`, `Age`, `YearsAtCompany` |
| Target Balancing | Used **SMOTE** to balance classes (Attrition = Yes/No)                      |

After preprocessing, total features used: **30**

---

## 🔍 Exploratory Data Analysis (EDA)

Key insights discovered during EDA:

* **Overall Attrition Rate:** 16.12%
* **Tenure:** Average tenure ≈ 7 years
* **Age Factor:** Younger employees (25–35 years) show higher attrition
* **Gender:** Slightly higher attrition among males
* **Overtime:** Employees working overtime show the highest attrition
* **Income:** Lower salary ranges correlate with higher attrition
* **Job Role:** Sales Executives and Lab Technicians show higher turnover
* **Satisfaction Levels:** Low Job, Environment, or Relationship Satisfaction → High attrition
* **Work-Life Balance:** Poor balance strongly linked to attrition

**Summary:** Attrition is notably higher among younger, single, frequently traveling employees who work overtime and report low satisfaction.

<img width="2913" height="1637" alt="image" src="https://github.com/user-attachments/assets/ca9000d9-87d3-4ed6-a85a-1596d08595ae" />
<img width="2925" height="1688" alt="image" src="https://github.com/user-attachments/assets/cbd28262-1869-44cd-8f4f-596497453dec" />
<img width="3000" height="1550" alt="image" src="https://github.com/user-attachments/assets/68ffa4c0-0a84-43c7-85bd-0a34a598899f" />
<img width="2962" height="1688" alt="image" src="https://github.com/user-attachments/assets/b4310067-7afa-4a13-9533-3e980adaa48a" />
---

## 📈 Correlation Analysis

Top positive correlations with attrition:

* OverTime → 0.25
* MaritalStatus → 0.16
* DistanceFromHome → 0.07

Top negative correlations:

* MonthlyIncome → -0.16
* JobSatisfaction → -0.10
* YearsAtCompany → -0.13
* TotalWorkingYears → -0.17

**Interpretation:** Employees with higher satisfaction, longer tenure, and higher income are less likely to leave.
<img width="1825" height="1588" alt="image" src="https://github.com/user-attachments/assets/40f4e485-083b-4e48-8aec-1f3b7e476920" />
---

## 🤖 Model Development

### Algorithms Used

* Random Forest Classifier
* Logistic Regression (with StandardScaler)
* K-Nearest Neighbors (K=7)
* Support Vector Machine (SVM)
* Naive Bayes
* XGBoost Classifier

**Train-Test Split:** 80% training, 20% testing (Stratified)
**Class Balancing:** Applied SMOTE

---

## 🧪 Model Evaluation

| Model                   | Accuracy  | Comments                             |
| ----------------------- | --------- | ------------------------------------ |
| **SVM**                 | **84.0%** | Best performer with balanced results |
| **XGBoost**             | 82.7%     | Strong for complex relationships     |
| **Random Forest**       | 80%       | Slight overfitting observed          |
| **Logistic Regression** | 80%       | Stable baseline performance          |
| **KNN / Naive Bayes**   | Lower     | Struggled with complex relationships |

---

## 🏆 Best Model: Support Vector Machine (SVM)

**Test Accuracy:** 84.01%
**Recall (Stay):** 91%
**Recall (Leave):** 47%

**Top Influential Features:**

1. OverTime
2. JobSatisfaction
3. StockOptionLevel
4. MaritalStatus
5. HourlyRate
6. Age
7. EnvironmentSatisfaction
8. TrainingTimesLastYear
9. RelationshipSatisfaction
10. JobRole

📊 **Interpretation:** Employees who work overtime, have lower satisfaction, or receive fewer stock options are more likely to leave.
Improving work-life balance, reward systems, and employee engagement can reduce attrition.

<img width="1672" height="1350" alt="image" src="https://github.com/user-attachments/assets/7a04a139-bc11-4fdf-9c1e-a5059bfbdf4e" />
---

## 🧰 Tools & Technologies Used

| Tool                         | Purpose                                     |
| ---------------------------- | ------------------------------------------- |
| 🐍 **Python**                | Data preprocessing, visualization, modeling |
| 📊 **Pandas, NumPy**         | Data manipulation                           |
| 📈 **Matplotlib, Seaborn**   | EDA & visualization                         |
| 🤖 **Scikit-learn, XGBoost** | Machine learning                            |
| 🧮 **SMOTE**                 | Class balancing                             |
| 💾 **SQL, Excel**            | Data exploration & validation               |

---

## ⚙️ How to Run

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/yourusername/IBM-HR-Analytics-Attrition.git
cd IBM-HR-Analytics-Attrition
```

### 2️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

### 3️⃣ Run the Notebook or Script

```bash
jupyter notebook HR.ipynb
```
---

## 📚 Results Summary

* Attrition Rate: 16.1%
* Best Model: **SVM (84.0% accuracy)**
* Key Drivers of Attrition:

  * Overtime
  * Low Job Satisfaction
  * Low Stock Options
  * Poor Work-Life Balance
  * Short Tenure

---

## 🔮 Conclusion & Future Scope

The analysis concludes that **workload, satisfaction, and compensation** are major factors driving employee attrition.
By addressing these areas, organizations can **increase retention** and **improve employee engagement**.

**Future Enhancements:**

* Implement SHAP for model explainability
* Use ensemble or deep learning models for improved recall on attrition cases
* Integrate dashboard visualization (e.g., Power BI / Streamlit)

---

## 👨‍💻 Author

**M.Umesh Chandra**
📧 *[[metlaumeshchandra2005.email@example.com](mailto:metlaumeshchandra2005.email@example.com)]*
💼 *Data Analyst & Machine Learning Enthusiast*

---

⭐ **If you like this project, don’t forget to star the repo!**
