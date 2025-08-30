# 🌊 Polynomial Logistic Regression on U-Shape Dataset  

This project demonstrates how **Polynomial Logistic Regression** can be used to correctly classify a **non-linear dataset**.  
We experimented with different polynomial degrees and visualized how decision boundaries evolve as the degree increases.  

---

## 📚 Libraries Used  
- 🐼 pandas  
- 🔢 numpy  
- 📊 matplotlib  
- 🎨 seaborn  
- 📂 kagglehub  
- 💻 os  

---

## 📂 Dataset  
- **File**: `ushape.csv`  
- **Source**: [U-Shape Dataset - Kaggle]() *(replace with actual link)*  
- **Shape**: `(100, 3)` → 2 features + 1 target  
- ✅ No null values  
- ✅ No duplicate rows  

---

## 🛠️ Project Steps  

### 🔹 1. Data Preparation  
- Extracted `X` (features) and `y` (target).  
- Used `.values` to convert into array form (needed for polynomial feature transformation).  

📷 <img width="559" height="413" alt="p16-1" src="https://github.com/user-attachments/assets/7c0dff1a-435f-429d-8201-73207d239d9c" />
  

Observation:  
- Data is clearly **wave/U-shaped**.  
- A straight line will not separate classes properly.  

---

### 🔹 2. Logistic Regression (Simple)  
- Trained a simple **Logistic Regression** model.  
- Plotted decision boundary.  

📷 <img width="546" height="413" alt="p-16-2" src="https://github.com/user-attachments/assets/b7705154-9099-4f6c-982b-6ea18e0d9094" />


- Result: Model gave accuracy **0.83** using `cross_val_score`.  
- Problem: Straight line → **not able to capture wave pattern**.  

---

### 🔹 3. Polynomial Logistic Regression  
- Imported **PolynomialFeatures** with:  
  - `degree = 3`  
  - `include_bias = False` (removed x⁰ column)  
- Transformed dataset into polynomial form.  
- Re-trained Logistic Regression.  

📷 *[Insert Polynomial Decision Boundary Plot]*  

- Result: Cross-validation score improved to **0.90** 🎉  

---

### 🔹 4. Effect of Different Polynomial Degrees  

We compared how **degree of polynomial** changes the decision boundary:  

📷 <img width="546" height="435" alt="p16-3" src="https://github.com/user-attachments/assets/7176f4cd-0a1a-4498-a8fb-26061ea5d904" />

📷 <img width="546" height="435" alt="p16-4" src="https://github.com/user-attachments/assets/5becbf0f-40a4-40ed-9296-bcaf6ff20776" />
 
📷 *<img width="546" height="435" alt="p17-5" src="https://github.com/user-attachments/assets/7b9d77cc-7a16-4ac6-9e1b-96153efe22b3" />
*  
📷 *<img width="546" height="435" alt="p16-6" src="https://github.com/user-attachments/assets/4e1d2574-fa20-47f9-b14f-c5cef21e35a0" />
*  

---

## 📊 Results  

| Degree | Accuracy | Observation |
|--------|-----------|-------------|
| 1      | 0.83      | Straight line → poor fit |
| 2      | ~0.83     | Curve forms, better classification |
| 3      | 0.90      | Matches wave pattern, best fit |
| 4      | ~0.90+    | Very accurate, almost perfect separation |
| 5      | ~0.90+    | Overfitting starts |

---

## 🎯 Purpose  

The purpose of this project was to **visualize the need for polynomial features** in Logistic Regression.  
- Simple Logistic Regression → fails on non-linear datasets.  
- Polynomial Logistic Regression → adds flexibility to capture curves and waves.  

---

## 📝 Learning Outcome  
- Logistic Regression works best on linearly separable data.  
- Polynomial Features allow models to adapt to **non-linear boundaries**.  
- Increasing degree improves fit, but too high → **overfitting risk**.  

---

## 🚀 Future Work  
- Test with different datasets (e.g., moons, circles).  
- Compare Logistic Regression with **SVM** and **Neural Networks** for U-shaped datasets.  
- Automate degree selection using **GridSearchCV**.  

---
