# Bias Detection and Mitigation - Titanic Dataset

## 🔍 Project Overview

This project focuses on detecting and mitigating bias in the Titanic dataset to promote ethical and fair machine learning practices. Using statistical and machine learning techniques, we explore and address disparities in survival predictions based on sensitive attributes such as gender, passenger class, and age.

---
## 📁 Dataset
- **Source:** [Titanic Dataset](https://github.com/datasciencedojo/datasets/blob/master/titanic.csv)
- **Target Variable:** `Survived` (1 = Yes, 0 = No)
- **Sensitive Features Considered:**
  - `Sex`
  - `Pclass` (Passenger Class)
  - `Age` (especially children under 10)

## ⚙️ Preprocessing Steps
- Dropped irrelevant features: `PassengerId`, `Name`, `Cabin`, `Ticket`
- Imputed missing values in:
  - `Age` (using median grouped by `Sex` and `Pclass`)
  - `Embarked` (using mode)
- Scaled continuous variables: `Age`, `SibSp`, `Parch`, `Fare`
- One-hot encoded categorical variables: `Sex`, `Pclass`, `Embarked`
- Split the data into training and test sets

## 🛠️ Bias Mitigation Techniques
Applied several mitigation methods from the **AIF360 Toolkit**:

### ✅ Preprocessing:
- **Reweighing**
- **Disparate Impact Remover**
- **Learning Fair Representations (LFR)**

### 🔁 In-processing:
- **Prejudice Remover**

### 📊 Post-processing:
- **Equalized Odds Post-processing**

---

## 🔍 Results

| Method                | Disparate Impact | Accuracy |
|-----------------------|------------------|----------|
| Original              | 0.2546 (Sex)     | 0.809    |
| Reweighing            | 1.2699           | 0.708    |
| LFR                   | 0.5521           | –        |
| Prejudice Remover     | 0.4233           | –        |
| Equalized Odds        | Bias still detected | –    |

- **Trade-off observed**: Bias mitigation may reduce model accuracy.
- Important to evaluate **both fairness and performance** for ethical AI.

---

## 📚 Key Takeaways
- Bias can significantly influence model decisions and outcomes.
- Mitigation techniques may reduce bias but affect model accuracy.
- Representation bias (e.g., missing groups in data) cannot be fixed by algorithms.
- Ethical AI requires balancing fairness, accuracy, and transparency.

---
