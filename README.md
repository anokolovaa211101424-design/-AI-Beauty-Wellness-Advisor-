# -AI-Beauty-Wellness-Advisor-
AI‑система для персоналізованого підбору догляду за шкірою та косметики.
# AI Beauty & Wellness Advisor 

AI‑система для персоналізованого підбору догляду за шкірою та косметики.

---

##  Summary
Find the right skincare and beauty products for your unique skin type and lifestyle.  
The AI analyzes your habits, environment, and product ingredients to recommend affordable and effective options.

---

##  Background
- **Problem:** Choosing the right skincare or makeup products is confusing. Marketing often misleads, and experimenting with new products can be costly and harmful.  
- **Motivation:** Help women and beauty lovers find care that truly works for them.  
- **Importance:** This project combines beauty, health, and AI — making technology practical for everyday life.

---

##  Data sources and AI methods
- **Data sources:**  
  - User questionnaires (skin type, allergies, habits).  
  - Open databases of cosmetic product ingredients.  
  - Climate conditions (humidity, temperature, UV index).  
- **AI methods:**  
  - Classification (skin type detection).  
  - Recommendation systems (product matching).  
  - NLP for analyzing product reviews.  
  - Possible extension: computer vision for analyzing skin photos.  

### Example code (Python + pandas + scikit-learn)
```python
import pandas as pd
from sklearn.neighbors import KNeighborsClassifier

# Example dataset
data = {
    "skin_type": ["dry", "oily", "combination", "dry", "oily"],
    "climate": ["sunny", "humid", "cold", "sunny", "cold"],
    "product": ["moisturizer", "cleanser", "serum", "sunscreen", "oil-control"]
}

df = pd.DataFrame(data)

# Encode categorical features
X = pd.get_dummies(df[["skin_type", "climate"]])
y = df["product"]

# Train model
model = KNeighborsClassifier(n_neighbors=2)
model.fit(X, y)

# New user input
new_user = pd.DataFrame([["dry", "sunny"]], columns=["skin_type", "climate"])
new_user_encoded = pd.get_dummies(new_user).reindex(columns=X.columns, fill_value=0)

prediction = model.predict(new_user_encoded)
print("Recommended product:", prediction[0])
 
##  Data sources and AI methods
