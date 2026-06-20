# House Price Prediction — Project Summary

**Author:** Maviya Mustahsin  
**Date:** June 2026  
**Course:** Internship — Week 1 Assignment

---

## Objective

To build a regression model that predicts house prices based on property features (area, bedrooms, bathrooms, amenities, etc.) and identify which features most strongly influence property value.

## Dataset

The analysis uses the **Housing Prices Dataset** from Kaggle (545 properties, 13 features). The dataset includes numerical features (area, bedrooms, bathrooms, stories, parking) and categorical features (mainroad, guestroom, basement, hotwaterheating, airconditioning, prefarea, furnishingstatus). No missing values were found.

## Methodology

1. **Data Cleaning**: Converted binary categorical columns (yes/no → 1/0), applied one-hot encoding to furnishing status, and verified no missing values or duplicates.
2. **Feature Engineering**: Created three new features — `price_per_sqft` (price efficiency), `total_amenities` (count of premium features), and `luxury_score` (composite quality indicator).
3. **Model Training**: Trained three regression models on an 80/20 train-test split:
   - **Linear Regression** — Baseline model capturing linear relationships
   - **Random Forest Regressor** — Ensemble model capturing non-linear patterns
   - **Gradient Boosting Regressor** — Sequential ensemble for optimal accuracy
4. **Evaluation**: Used MAE, RMSE, R² Score, and 5-fold cross-validation.

## Key Results

| Model | MAE | RMSE | R² Score |
|-------|-----|------|----------|
| Linear Regression | $970,043 | $1,324,507 | 0.6529 |
| Random Forest | $918,425 | $1,333,773 | 0.6481 |
| Gradient Boosting | $953,398 | $1,352,140 | 0.6383 |

**Best Model**: Linear Regression with R² = 0.6529, meaning it explains ~65% of the variation in house prices.

## Key Insights

1. **Luxury score is the #1 predictor** — Our engineered composite feature (combining bathrooms, stories, parking, and amenities) dominates feature importance at 0.555, proving that feature engineering adds real value.
2. **Area is the #2 predictor** — Square footage (importance: 0.227) is the strongest individual original feature, confirming size drives price.
3. **Bathrooms > Bedrooms** — The number of bathrooms is a stronger price predictor than bedrooms, suggesting buyers value luxury amenities.
4. **Furnishing boosts value** — Unfurnished homes have a -0.28 correlation with price, meaning furnished homes command notably higher prices.
5. **Hot water heating is irrelevant** — Despite being an amenity, it shows only 0.09 correlation with price.

## Business Recommendation

For real estate businesses looking to maximize property value:
- **Prioritize area and bathrooms** when evaluating or developing properties
- **Stage/furnish homes before listing** — the price premium justifies the cost
- **Install air conditioning** as a cost-effective value-add (0.45 correlation with price)
- **Don't over-invest in hot water heating** — it doesn't meaningfully impact selling price

## Tools Used

- **Python 3.x** with Pandas, Scikit-learn, Matplotlib, Seaborn
- **Jupyter Notebook** for interactive analysis
- **3 Regression Models** with 5-fold cross-validation
- **6 Professional Visualizations** saved as high-resolution PNGs

---

*This project demonstrates data loading, cleaning, feature engineering, model comparison, and business insight generation — core skills for a data science workflow.*
