# spaceship-titanic-ml
# 🚀 Spaceship Titanic: My First Clean ML Pipeline

## 📖 What is this project?
This project uses the famous **Spaceship Titanic** dataset from Kaggle. The goal is to predict which passengers were mysteriously transported to an alternate dimension during a spaceship collision. 

My main focus for this project wasn't just chasing the highest accuracy. Instead, I wanted to move away from writing messy, step-by-step code and learn how to build a clean, organized Machine Learning pipeline that is easy to reuse and read.

## 🛠️ How I built it
Instead of cleaning the data manually column by column, I used **Python** and **Scikit-Learn** to automate the entire process:

* **Parallel Data Cleaning:** I used a `ColumnTransformer` to split the data into two tracks. It fills in missing numbers and converts text categories (like Home Planet) into numbers at the exact same time, rather than doing it one after the other.
* **Keeping Column Names:** By default, Scikit-Learn strips away column headers and leaves a confusing grid of nameless numbers. I changed the settings to output a Pandas DataFrame so my column names (like `Age` or `RoomService`) stayed intact.
* **The All-in-One Pipeline:** I connected the data cleaning steps and the final ML model (Random Forest) into one single `Pipeline`. This means raw data goes in one end, and predictions come out the other without the risk of accidentally messing up the test data.

## 📊 Results
* **Models Tested:** Random Forest
* **Baseline Accuracy:** ~78.8% (achieved with basic data cleaning and no complex feature engineering)

## 🚀 What's Next?
Now that the code structure is solid, I am going to focus on **Feature Engineering** to push the accuracy higher:
* **Parsing Cabins:** Splitting the `Cabin` text (e.g., `B/0/P`) to see if being on a specific deck or side of the ship affected the passenger's chances.
* **Travel Groups:** Using the passenger IDs to figure out if families or groups traveling together had the same outcome.
* **Total Spending:** Adding up all luxury expenses (Spa, Food Court) to easily identify passengers who were in CryoSleep (who spent $0).
