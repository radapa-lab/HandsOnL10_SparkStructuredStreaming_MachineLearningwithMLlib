# Handson-L10-Spark-Streaming-MachineLearning-MLlib

## Overview

This project demonstrates real-time data processing using Apache Spark Structured Streaming along with Machine Learning using MLlib. The implementation focuses on processing streaming data, applying a trained model, and performing window-based aggregations.

---

## Technologies Used

Python 3.x
Apache Spark (PySpark)
Spark MLlib
Faker library for data generation

---

## Task 4: Real-Time Fare Prediction

### Approach

In Task 4, a machine learning model is trained using the provided training dataset. The distance feature is converted into a feature vector using VectorAssembler, and a Linear Regression model is trained.

The trained model is saved in the models directory and reused for real-time predictions. Streaming data is read from a socket source, and each incoming record is passed through the model to generate predictions.

The output includes:
trip_id, driver_id, distance_km, fare_amount, predicted_fare, and deviation.

The results are displayed in the console for each micro-batch.

### Output Screenshot

<img width="975" height="687" alt="image" src="https://github.com/user-attachments/assets/0ae6ed55-148e-4469-a87a-4e0c67489f84" />
<img width="975" height="687" alt="image" src="https://github.com/user-attachments/assets/0ae6ed55-148e-4469-a87a-4e0c67489f84" />

---

## Task 5: Window-Based Aggregation and Prediction

### Approach

In Task 5, streaming data is processed using time-based window aggregation. The timestamp column is converted into the appropriate format, and data is grouped using a sliding window.

For each window, the average fare is calculated. The trained model is then used to predict the next average fare based on the computed value.

Since this task uses window aggregation, results are only displayed when sufficient data is available within a window. Therefore, not every batch produces output.

The output includes:
window_start, window_end, avg_fare, and predicted_next_avg_fare.

### Output Screenshot

<img width="981" height="239" alt="image" src="https://github.com/user-attachments/assets/2d38e3bd-5e51-4aa8-9e71-c8d10ba02830" />
<img width="981" height="239" alt="image" src="https://github.com/user-attachments/assets/2d38e3bd-5e51-4aa8-9e71-c8d10ba02830" />

---

## Key Concepts

Structured Streaming
Micro-batch processing
Machine Learning with Spark MLlib
Window-based aggregation
Real-time data simulation

---

## Project Structure

Handson_L10/
task4.py
task5.py
data_generator.py
training-dataset.csv
models/
   fare_model/ (used in Task 4 for fare prediction)
   fare_trend_model_v2/ (used in Task 5 for trend prediction)
README.md

---

## How to Run

### Step 1: Setup environment

python3 -m venv venv
source venv/bin/activate
pip install pyspark numpy faker

### Step 2: Run Task 4

Open two terminals.

Terminal 1:
python3 task4.py

Terminal 2:
python3 data_generator.py

### Step 3: Run Task 5

Open two terminals.

Terminal 1:
python3 task5.py

Terminal 2:
python3 data_generator.py

---

## Conclusion

This project demonstrates how real-time streaming data can be processed using Apache Spark and how machine learning models can be applied in a streaming pipeline. It also highlights the difference between direct prediction and window-based aggregation in streaming systems.
