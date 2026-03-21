# Fetal Health AI: Helping Doctors Prioritize Patient Safety

Can an algorithm help a doctor make a life-saving decision in seconds? This project explores that question by using Machine Learning to analyze Cardiotocography (CTG) data and classify fetal health.

### The "Why" Behind the Project
In a busy labor ward, identifying a baby in distress is a high-stakes race against time. I built this classifier to see if a **Random Forest** model could accurately sort patients into three categories: **Normal**, **Suspect**, and **Pathological**.

The goal wasn't just to get a high accuracy score—it was to build a tool that actually understands medical risk, prioritizing the "catch" of high-risk cases over everything else.

---

### he Results (Clinical Audit)
After training the model on over 2,000 patient records, here is how the AI performed on its "Final Exam" (the test set):

* **Overall Accuracy:** **93%** (Technically 92.72%, but rounded for the big picture).
* **The "Safety" Score (Recall):** I achieved an **86% Recall for Pathological cases**. This means the AI is highly sensitive to the most dangerous situations.
* **False Alarm Control:** For healthy babies, the model is **98% accurate**, meaning it won't cause unnecessary panic for parents or staff.

---

### How I Built It (My Process)
I followed a 6-stage clinical pipeline to ensure the results were reliable:

1.  **The Investigation (EDA):** I dug into the data and found that 'Prolonged Decelerations' and 'Abnormal Short Term Variability' were the two biggest "red flags" for fetal distress.
2.  **Data Preprocessing:** I used `StandardScaler` to level the playing field. In medical data, a heart rate of 140 shouldn't "outvote" a small movement count just because the number is bigger.
3.  **The "Board of Experts":** I chose a **Random Forest Classifier**. Instead of one AI making a guess, I used 100 "digital doctors" (decision trees) to vote. This makes the final prediction much more stable.
4.  **Clinical Evaluation:** I ignored simple accuracy and looked at the **Confusion Matrix**. In medicine, a "missed danger" is a disaster, so I audited the model to ensure it was catching as many high-risk cases as possible.

---

### Tech Stack & Tools
* **Python:** The core language.
* **Pandas & NumPy:** For data wrangling.
* **Scikit-Learn:** For the machine learning brain.
* **Seaborn & Matplotlib:** For creating the medical visualizations.

---

### What I Learned
This project taught me that Data Science in healthcare isn't just about math it's about **context**. A 93% accuracy is great, but understanding where the model fails is what makes it a tool a doctor might actually trust. I focused on making the model "safe," not just "smart."

---

### Getting Started
1. Clone this repository.
2. Open the `.ipynb` notebook in Kaggle or Jupyter.
3. Make sure you have the `fetal_health.csv` dataset in the same folder.
4. Run the cells and see the "Safety Audit" for yourself!

---
*Note: This project was built as part of my data science portfolio to demonstrate clinical classification and model interpretability.*
