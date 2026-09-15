# Solar Power Plant Output Prediction

## AI4003 Applied Machine Learning

This project predicts the AC power output of a solar power plant using weather data.

## Dataset

The project uses **Plant 1** from the Solar Power Generation dataset.

The dataset contains:

* Plant 1 Generation Data
* Plant 1 Weather Sensor Data
* Plant 2 Generation Data
* Plant 2 Weather Sensor Data

For this project, only **Plant 1** is used.

## Data Preprocessing

The generation data contains power readings from different inverters.

The AC Power and DC Power values were summed for each timestamp.

The generation data was then combined with the Plant 1 weather sensor data.

The 15-minute data was converted into **hourly data**.

The final data contains:

* Date and Time
* AC Power
* DC Power
* Ambient Temperature
* Module Temperature
* Irradiation

## Public Weather Data

Public weather data was collected from **Open-Meteo**.

The following weather variables were used:

* Shortwave Radiation
* Temperature at 2 meters
* Cloud Cover

The public weather data was compared with the on-site sensor data.

## Machine Learning

Two feature sets were used.

### Set A — On-Site Weather Sensors

* Irradiation
* Module Temperature
* Ambient Temperature
* Sin Hour
* Cos Hour

### Set B — Public Weather

* Shortwave Radiation
* Temperature at 2 meters
* Cloud Cover
* Sin Hour
* Cos Hour

## Train and Test Data

The data was divided according to time.

**Training:**
15 May 2020 – 10 June 2020

**Testing:**
11 June 2020 – 17 June 2020

The data was not shuffled.

Feature scaling was performed using the training data.

## Models

Three linear regression methods were implemented:

1. Normal Equation
2. Batch Gradient Descent
3. Stochastic Gradient Descent

The models were implemented using basic Python, NumPy and Pandas without using Scikit-learn.

## Evaluation

The models were evaluated using **RMSE (Root Mean Squared Error)**.

Two RMSE values were calculated:

* All test hours
* Daytime hours only

Negative predictions were changed to zero.

## Web Interface

A simple web interface was created using **Gradio**.

The user enters:

* Hour
* Shortwave Radiation
* Temperature
* Cloud Cover

The interface then predicts the solar plant's **AC Power in kW**.

## Project Files

```text
data/
model/
results/
figures/
README.md
```

### Model Files

```text
theta_setB.npy
setB_mean.npy
setB_std.npy
model_info.txt
```

### Results

The `results` folder contains:

* RMSE results
* Model weights
* Worst residuals

## How to Run

1. Open the notebook in Google Colab.
2. Upload the required CSV files.
3. Run the notebook cells in order.
4. Run the model training cells.
5. Run the web interface cell.
6. Enter weather information.
7. Click **Submit**.
8. The predicted AC power will be displayed.

## Conclusion

This project uses weather information to predict solar power plant AC output. It compares on-site sensor data with public weather data and evaluates different linear regression methods.
