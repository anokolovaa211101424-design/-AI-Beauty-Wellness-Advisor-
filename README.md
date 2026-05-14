# -AI-Beauty-Wellness-Advisor-
AI‑система для персоналізованого підбору догляду за шкірою та косметики.
# AI Beauty & Wellness Advisor 

AI‑система для персоналізованого підбору догляду за шкірою та косметики.

---

## 📖 Summary
Find the right skincare and beauty products for your unique skin type and lifestyle.  
The AI analyzes your habits, environment, and product ingredients to recommend affordable and effective options.

---

## 📚 Background
- **Problem:** Choosing the right skincare or makeup products is confusing. Marketing often misleads, and experimenting with new products can be costly and harmful.  
- **Motivation:** Help women and beauty lovers find care that truly works for them.  
- **Importance:** This project combines beauty, health, and AI — making technology practical for everyday life.

---

## 🧠 Data sources and AI methods
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
## 📊 Data sources and AI methods
- **Player statistics:** Relevant player data can be gathered from [Rotowire Soccer Stats](https://www.rotowire.com/soccer/stats.php?UCL=1).  
- **Market values:** Current market value data can be obtained from [Transfermarkt](https://www.transfermarkt.com/).  
- **AI methods:**  
  - Linear regression to estimate predicted market price.  
  - Logistic regression for player qualification categories (prospect, value player, star, sale potential).  
  - Neural networks for mapping players to categories and predicting performance trends.  
  - Integration with external APIs (weather, player load, market data) for richer evaluation.  ```

---

###  Challenges
- The AI can predict which player is undervalued compared to market price, but it cannot guarantee future performance.  
- Injuries are unpredictable: even fit players can suffer season‑ending injuries.  
- While injury proneness can be included in evaluation, randomness and external factors remain outside the model’s control.  

---

##  What next?
- **Injury prediction:** Estimate likelihood of injury in each game based on player load, weather, field quality, and average distance per match.  
- **Substitution strategy:** Suggest best substitutes depending on score, recent player performance trends, and weather conditions.  
- **Climate factor:** Add climate sensitivity to evaluation — some players perform better in cold/wet weather, others in extreme heat.  
- **Youth investment analysis:** Predict whether investing in youth players is worth the cost, based on progress vs. money spent.  
- **Player qualification system:** Use logistic regression to categorize players (prospect, value player, star, sale potential).  
- **Technical requirements:** Access APIs for weather, player data, and market data; develop neural networks for advanced classification.  

---

## Acknowledgments
- **Data inspiration:** [Fantasy Premier League](https://fantasy.premierleague.com/my-team#).  
- **Libraries:** Python (NumPy, scikit‑learn).  
- **Sources:** Open football statistics portals and transfer market databases.  
- **Community:** Building AI course project gallery and GitHub community projects.  
