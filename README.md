# VGSOM---Passenger-Prediction

🚆 Public Transport Ridership Forecasting & Train Dispatch Optimization

Vinod Gupta School of Management, IIT Kharagpur (Sep 2024 – Nov 2024)

This project builds a complete forecasting–simulation pipeline to improve urban rail operations by predicting passenger demand and dynamically regulating train dispatch. Using historical ridership data, time-series modeling, and discrete-event simulation, the system reduces passenger waiting time while maintaining optimal train utilization.

📌 Problem Statement

Public transport systems struggle with demand uncertainty, leading to:

Overcrowded trains during peak hours

Underutilized capacity during off-peak periods

Increased passenger waiting time

The objective of this project is to forecast demand accurately and use it to control train dispatch frequency in a way that minimizes passenger waiting time while keeping train operations efficient.

🧠 Solution Overview

The pipeline consists of three integrated layers:

1. Time-Series Demand Modeling

We model passenger ridership using classical and deep learning methods:

STL Decomposition to separate trend, seasonality, and residuals

ADF Test to verify stationarity

ARIMA for linear temporal patterns

LSTM for non-linear and long-term dependencies

Hybrid ARIMA-LSTM model for robust forecasting

The system was trained on 8500+ hours of ridership data.

2. Demand Structuring & Disaggregation

To make forecasts usable for real-time dispatching:

Data was enriched using 10+ variables (time of day, weekday/weekend, holidays, etc.)

Daily demand was converted into fine-grained time intervals using:

Poisson processes

Zero-Inflated Poisson (ZIP) models

Temporal disaggregation

This produces realistic passenger arrival streams for simulation.

3. Train Dispatch Simulation (SimPy)

A Discrete Event Simulation (DES) was built using SimPy to model:

Passenger arrivals

Queue formation

Train dispatching

Boarding and capacity constraints

The simulation dynamically adjusts train frequency based on predicted demand.

📊 Results

When tested on a real operational day:

Passenger waiting time reduced by 18–22%

Train utilization optimized, avoiding both overcrowding and idle capacity

Dispatch decisions became data-driven rather than fixed-schedule based

🛠 Tech Stack

Python

Statsmodels, pmdarima – ARIMA, ADF tests

TensorFlow / Keras – LSTM

SimPy – Discrete Event Simulation

Pandas, NumPy, Matplotlib – Data processing & visualization

📂 Repository Structure
├── STL Decomposition.ipynb      # Trend, seasonality & stationarity analysis  
├── Prediction Code.ipynb       # ARIMA, LSTM, hybrid forecasting models  
├── Simulation (SimPy)          # Train dispatch & passenger flow modeling  
├── Data                         # Processed ridership datasets  
└── README.md

🎯 Key Takeaways

This project demonstrates how forecasting + simulation can be combined to solve real-world transportation problems. Instead of treating demand prediction and operations separately, the system creates a closed-loop decision engine that continuously aligns train supply with passenger demand.

This framework is directly applicable to:

Metro rail systems

Bus rapid transit

Airline and logistics capacity planning
