# Craigslist Used-Car Price Prediction

CDS4003 – Data Science Final Project

This project uses machine learning to estimate the asking price of a used vehicle in the United States. The model takes details such as the manufacturer, model, year, mileage and condition, then provides an estimated price and an indicative range. The Streamlit app also lets users compare an advertised price with the estimate.

## Team members

| Name | GitHub username | Contribution |
|---|---|---|
| Rashed Ali | RashedMazrooei | Data preprocessing, exploratory data analysis and model development |
| Sultan Alshamsi | SultanAlshamsi | Model evaluation, Streamlit app development and project documentation |

## Dataset

The project uses the [Craigslist Cars and Trucks dataset by Austin Reese](https://www.kaggle.com/datasets/austinreese/craigslist-carstrucks-data). Check the Kaggle page for the dataset's licence and usage terms.

The full `vehicles.csv` file is not included because of its size. To rerun the data preparation notebooks, download it from Kaggle and place it in `data/raw/`. A sample of 5,000 cleaned records is available in `data/sample/`.

## Repository contents

| Path | Contents |
|---|---|
| `notebooks/` | Four notebooks covering data preparation, exploration, modelling and deployment |
| `src/vehicle_features.py` | Feature engineering and prediction functions |
| `app/app.py` | Streamlit price-estimation app |
| `models/model_metadata.json` | Saved model settings and evaluation results |
| `price_model.joblib` | Trained model file, currently in the repository root |
| `outputs/` | Cleaning reports, model results and other CSV outputs |
| `docs/` | Data dictionary |
| Repository root | Analysis charts and `feature_importance.png` |
| `requirements.txt` | Python dependencies |

## Run the application

1. Install the dependencies with `pip install -r requirements.txt`.
2. Move `price_model.joblib` from the repository root into `models/`, where the app expects it.
3. Start the app with `streamlit run app/app.py`.

The original dataset is only needed to rerun the training notebooks. The app loads the saved model and metadata.

## Model results

The cleaned dataset contains **240,186 listings**, after removing repeated advertisements and records with invalid prices. The final model uses histogram-based gradient boosting to predict log-transformed vehicle prices.

| Test metric | Result |
|---|---:|
| R² | 0.676 |
| Median absolute percentage error | 18.7% |
| Predictions within 20% of asking price | 52.7% |
| Mean absolute error | $4,610 |

These are estimates of advertised prices, not final sale prices. The dataset comes from one platform and time period, so market changes and missing vehicle details can affect accuracy.

## Deployment

The Streamlit app has not yet been deployed. Its public URL can be added here after deployment.

## AI-use disclosure

The final CDS4003 submission should accurately identify any AI tools used and explain their role, as required by the course.
