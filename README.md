# Mobile Phone Price Range Prediction

> A machine learning project designed to estimate mobile phone price tiers based on hardware specifications to optimize manufacturing and business strategies.

---

## 📖 Business Problem
Bob has started his own mobile company to compete with industry giants like Apple and Samsung. However, estimating the appropriate price for newly manufactured mobile phones in a highly competitive market requires data-driven decision-making rather than simple assumptions. This project leverages sales data from various companies to identify the relationships between mobile phone features (such as RAM, internal memory, etc.) and their selling price. The objective is to predict a price range—indicating the cost tier of the device—rather than predicting the exact monetary value.

## 📊 Dataset Overview
The dataset contains 2,000 entries with 21 hardware and specification features. 

**Key Features:**
*   **battery_power**: Total energy a battery can store, measured in mAh.
*   **ram**: Random Access Memory, measured in Megabytes.
*   **px_height** & **px_width**: Pixel resolution dimensions.
*   **price_range**: The target variable categorized into 0 (low cost), 1 (medium cost), 2 (high cost), and 3 (very high cost).

---

## 🛠️ Methodology
The project is divided into three main analytical phases:

### 1. Exploratory Data Analysis (EDA)
*   **RAM Distribution**: A boxplot analysis confirmed that RAM size is the most important attribute associated with the price range, showing a step-by-step increase across categories and high predictive power.
*   **Battery Power**: Kernel Density Estimate (KDE) plots revealed overlapping distributions, though premium phones tend to feature a subtle rightward shift indicating larger batteries.
*   **Correlation Heatmap**: Verified that standard connectivity features like WiFi and Bluetooth show near-zero correlation with the price range, meaning their presence alone does not justify a price markup.

### 2. Predictive Modeling
The data was split into an 80% training set and a 20% testing set. Three models were evaluated to find the best fit for production:
*   **Logistic Regression**: Selected as the best model for production, achieving the highest accuracy at 97.50% after standardizing the continuous variables using `StandardScaler`. It is lightweight, fast, and highly interpretable.
*   **Random Forest Classifier**: Achieved 89.25% accuracy and was utilized specifically to extract feature importances to drive business strategy.
*   **K-Nearest Neighbors (KNN)**: Performed the poorest on the testing data due to the "curse of dimensionality" across the 20 unique features.

### 3. Business Expansion Recommendations
Based on the machine learning feature importance analysis, the following strategies are recommended:
*   **Invest Heavily in RAM**: The majority of the hardware budget should be allocated to high-capacity RAM for premium flagship devices.
*   **Prioritize Battery and Screen for Mid-Tier**: Upgrading battery capacity and screen resolution provides the best return on investment for pushing mid-range phones into higher price tiers.
*   **Save Money on Basic Connectivity**: Use cost-effective components for ubiquitous features like 3G/4G, WiFi, and Bluetooth, as consumers do not pay a premium for them.

---

## 🚀 How to Run the Project
1. Clone this repository to your local machine.
2. Ensure the `datasets_11167_15520_train.csv` file is located in the root directory (or your designated data folder).
3. Install the required Python dependencies: `pandas`, `matplotlib`, `seaborn`, and `scikit-learn`.
4. Open and execute `CellphonePrice.ipynb` in a Jupyter Notebook environment.