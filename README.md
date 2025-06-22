# 🥡 Packaged Food Ingredients Classifier

A lightweight machine‑learning + OCR tool that helps Indian consumers instantly see whether a packaged snack is **✅ Healthy**, **⚠️ Moderate**, or **🚫 Unhealthy**—just by scanning the ingredient list with a phone‑camera.

---

## 📌 Why I Built This

With India’s growing appetite for ready-to-eat chips, namkeens, and other packaged foods, many shoppers struggle to decode complicated ingredient lists.

Most publicly available food classification datasets are built around Western ingredients — and don’t include many commonly used Indian ones.  
There’s a visible gap when it comes to Indian packaged food classifiers.

My goal is to bridge that gap and make transparent, data-backed food decisions easier for Indian consumers.

---

## 📂 Dataset

* **Self‑curated** from real product labels of

  * Potato‑chip brands
  * Corn‑based snacks
  * Popular Indian namkeens
* Ingredient health tags assigned with help from biology‑student friends and reputable nutrition sources.
* Three labels:

  * ✅ Healthy
  * ⚠️ Moderate
  * 🚫 Unhealthy

---

## 🧠 ML Model Summary

| Step             | Details                                            |
| ---------------- | -------------------------------------------------- |
| Text prep        | tokenisation • stop‑word removal                   |
| Algorithms tried | Logistic Regression • Random Forest • SVM          |
| Final pick       | Logistic Regression (best F1 on custom test split) |
| Accuracy         | **81.25 %** (on 16-test sample size)               |

### 📋 Classification Report:

```
               precision    recall  f1-score   support

           0       1.00      0.33      0.50         3
           1       0.67      1.00      0.80         2
           2       0.83      0.91      0.87        11

    accuracy                           0.81        16
   macro avg       0.83      0.75      0.72        16
weighted avg       0.84      0.81      0.79        16
```

> 🔎 Model stored as: `ingredient_classifier_model.pkl`

---

## 🖼️ OCR + Streamlit Web App

```bash
pip install -r requirements.txt  # streamlit, easyocr, pandas, scikit‑learn, pillow, joblib
streamlit run app.py             # launches local web interface
```

Features:

1. **Image Upload** – Snap or upload a label photo; EasyOCR extracts text.
2. **Instant Classification** – Each detected ingredient is run through the trained model.
3. **Manual Entry** – Enter comma‑separated ingredients if no picture is available.
4. **Stylish UI** – Custom CSS for a clean 700‑px centred card.

---

## 📊 Key Features

* End‑to‑end pipeline: OCR → text clean‑up → ML prediction → result.
* Dataset built from **Indian** products (market‑specific relevance).
* Completely client‑side—no data leaves your machine.
* Easily extendable: just add more labelled rows to `data/ingredients.csv` and retrain.

---

## 📌 Real‑World Use Cases

* Parents quickly vet snacks for kids.
* Health start‑ups integrate the model via API / Streamlit sharing link.
* Retailers display health traffic‑light next to shelf labels.

---

## 🚀 Roadmap

* [ ] Expand dataset with more regional brands
* [ ] Add quantity-based classification
* [ ] Deploy public Streamlit demo version
* [ ] Add confidence score to predictions

---

## 🙌 Acknowledgements

Thanks to my biology‑student friends for ingredient insights and to open nutrition communities that inspire mindful eating.

---

**Maintained by**: snowflakelogic  
**Last Updated**: June 2025  
**Developed in 2024 - Uploaded here in June 2025**
