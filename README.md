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
```
def main():
  # example dataset
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
main()
```
## 📊 Data sources and AI methods
- **User data:** Questionnaires about skin type, allergies, lifestyle habits.  
- **Product databases:** Open cosmetic ingredient databases (e.g., INCI lists).  
- **Environmental data:** Climate conditions (humidity, temperature, UV index) via weather APIs.  
- **AI methods:**  
  - Classification models to detect skin type.  
  - Recommendation systems to match products with user profiles.  
  - NLP to analyze product reviews and extract sentiment.  
  - Computer vision (future extension) to analyze skin photos.  
  - Integration with external APIs (weather, product data) for richer evaluation.  

---

##  Challenges
- AI can suggest suitable products, but it cannot guarantee how each individual’s skin will react.  
- Skin conditions are influenced by hormones, stress, and lifestyle factors that may not be captured in data.  
- Ingredient databases may be incomplete or inconsistent.  
- Recommendations cannot replace professional dermatological advice.  

---

##  What next?
- **Skin photo analysis:** Add computer vision to detect dryness, acne, or irritation directly from user images.  
- **Dynamic recommendations:** Suggest different routines depending on season, climate, or daily habits.  
- **Trend analysis:** Use NLP to track beauty trends and adapt recommendations accordingly.  
- **Wellness integration:** Expand beyond skincare into nutrition, sleep, and fitness for holistic beauty advice.  
- **Personalized categories:** Logistic regression to classify users into categories (basic care, advanced care, sensitive skin, premium care).  
- **Technical requirements:** Access APIs for weather, product ingredient data, and user health trackers.  

---

##  Acknowledgments
- **Data inspiration:** Open cosmetic ingredient databases, dermatology research papers.  
- **Libraries:** Python (pandas, scikit‑learn).  
- **Sources:** Beauty blogs, skincare forums, product review platforms.  
- **Community:** Building AI course project gallery and GitHub community projects.
##  Additional resources
- [INCI Decoder](https://incidecoder.com/) — база даних косметичних інгредієнтів.  
- [CosDNA](https://www.cosdna.com/) — аналіз складу продуктів та відгуки користувачів.  
- [OpenWeather API](https://openweathermap.org/api) — дані про кліматичні умови для персоналізованих рекомендацій.  
- [PubMed Dermatology](https://pubmed.ncbi.nlm.nih.gov/) — наукові статті про догляд за шкірою.  

---



