# Predictive Bill Analytics Using Temporal Fusion Transformer (TFT), Model Context Protocol (MCP), and Agent-to-Agent (A2A) Communication

## M.Tech Dissertation Project – Artificial Intelligence & Machine Learning

### Author
Sanjay Kumar

### Academic Program
Master of Technology (M.Tech) – Artificial Intelligence & Machine Learning

---

# 1. Executive Summary

Predictive Bill Analytics is an enterprise-inspired AI platform developed as part of an M.Tech dissertation. The project focuses on forecasting future telecom customer bills using Temporal Fusion Transformer (TFT), integrating Explainable AI (XAI), Model Context Protocol (MCP), and Agent-to-Agent (A2A) communication.

Telecommunication providers generate large volumes of billing, usage, and customer interaction data. Accurate forecasting of future bills helps organizations improve revenue planning, identify anomalies, optimize plans, and enhance customer experience.

This project proposes a unified architecture that combines:

- Deep Learning Forecasting
- Explainable AI
- Multi-Agent Collaboration
- Enterprise Data Integration
- Dashboard-Based Analytics
- API Services

The solution demonstrates how modern AI systems can be applied to real-world telecom billing environments.

---

# 2. Problem Statement

Traditional telecom billing systems primarily focus on historical reporting and invoice generation. They typically do not provide:

- Accurate future bill forecasting
- Explainable predictions
- Intelligent anomaly detection
- Agent-driven decision support
- Enterprise AI integration

As telecom businesses become increasingly data-driven, there is a need for intelligent forecasting systems capable of generating interpretable predictions and actionable recommendations.

---

# 3. Research Objectives

The project aims to:

1. Predict future telecom bills using Temporal Fusion Transformer.
2. Build an enterprise-style telecom billing dataset.
3. Store and manage data using PostgreSQL.
4. Engineer predictive features from historical usage.
5. Integrate Explainable AI using SHAP.
6. Implement Agent-to-Agent communication.
7. Integrate Model Context Protocol.
8. Develop a business-facing Streamlit dashboard.
9. Evaluate model performance using standard forecasting metrics.

---

# 4. Key Contributions

The project contributes the following:

- End-to-end telecom forecasting pipeline.
- Transformer-based forecasting architecture.
- Explainable prediction framework.
- Multi-agent analytical ecosystem.
- MCP integration for AI interoperability.
- PostgreSQL-based enterprise data architecture.
- Interactive analytics dashboard.

---

# 5. System Architecture

Data Sources
↓
PostgreSQL Database
↓
Training Dataset Generation
↓
Feature Engineering
↓
Temporal Fusion Transformer
↓
Future Bill Forecasts
↓
Explainable AI Layer
↓
A2A Agent Collaboration
↓
MCP Server
↓
Dashboard & APIs

---

# 6. Technology Stack

## Programming

- Python 3.11

## Database

- PostgreSQL

## Machine Learning

- PyTorch
- Lightning
- PyTorch Forecasting

## Explainability

- SHAP

## Dashboard

- Streamlit

## APIs

- FastAPI
- Uvicorn

## Agent Framework

- LangGraph
- Custom A2A Architecture

## MCP

- FastMCP

## Data Processing

- Pandas
- NumPy

---

# 7. Repository Structure

```text
predictive-bill-analytics/
├── database/
├── data/
├── training/
├── xai/
├── agents/
├── a2a/
├── mcp/
├── dashboard/
├── api/
├── models/
├── reports/
├── notebooks/
└── tests/
```

---

# 8. Database Design

The platform uses PostgreSQL for persistent storage.

## customer_master

Stores customer demographics.

Columns:

- customer_id
- customer_name
- customer_segment
- plan_type
- customer_tenure
- state
- city
- activation_date

## billing_history

Stores monthly billing information.

Columns:

- customer_id
- billing_month
- bill_amount
- device_payment
- discount_amount
- tax_amount
- total_amount

## usage_history

Stores monthly usage information.

Columns:

- customer_id
- usage_month
- data_usage_gb
- voice_minutes
- sms_count
- roaming_charges
- international_charges

## plan_history

Tracks plan changes.

## customer_interactions

Tracks support and billing interactions.

---

# 9. Dataset Generation

Because access to production Verizon billing data is restricted, a realistic synthetic telecom dataset is generated.

Characteristics:

- 5,000 customers
- 24–48 months history
- Billing seasonality
- Usage fluctuations
- Customer segmentation
- Plan variation
- Roaming charges
- International charges

The synthetic dataset mimics realistic telecom behavior while maintaining privacy.

---

# 10. Feature Engineering

Feature engineering is one of the most important parts of the forecasting pipeline.

## Lag Features

Generated:

- bill_lag_1
- bill_lag_2
- bill_lag_3
- bill_lag_6

## Rolling Statistics

Generated:

- bill_roll_mean_3
- bill_roll_mean_6

## Temporal Features

Generated:

- month
- quarter
- year

## Ratio Features

Generated:

- roaming_ratio
- intl_ratio

## Trend Features

Generated:

- bill_growth_rate
- usage_growth_rate

---

# 11. Temporal Fusion Transformer

Temporal Fusion Transformer is the primary forecasting model.

Reasons for selection:

- State-of-the-art forecasting performance
- Multi-horizon prediction
- Attention mechanisms
- Variable selection networks
- Built-in interpretability

## Model Inputs

Static Features:

- Customer Segment
- Plan Type
- Customer Tenure

Known Features:

- Month
- Quarter
- Time Index

Unknown Features:

- Bill Amount
- Data Usage
- Voice Minutes
- Roaming Charges

## Forecast Horizon

- 3 months

## Encoder Length

- 12 months

---

# 12. Training Pipeline

The training pipeline consists of:

1. Data Extraction
2. Feature Engineering
3. Dataset Preparation
4. TFT Training
5. Model Validation
6. Checkpoint Saving

Outputs:

- best_tft.ckpt
- final_tft.ckpt

---

# 13. Prediction Pipeline

The prediction module:

- Loads trained TFT model
- Creates inference dataset
- Generates future forecasts
- Saves predictions

Output:

```text
predictions.csv
```

---

# 14. Evaluation Metrics

The model is evaluated using:

## MAE

Mean Absolute Error

## RMSE

Root Mean Squared Error

## MAPE

Mean Absolute Percentage Error

## R² Score

Coefficient of Determination

Generated artifacts:

- evaluation_metrics.csv
- actual_vs_forecast.png
- error_distribution.png
- scatter_actual_vs_forecast.png

---

# 15. Explainable AI (XAI)

Business users require interpretable predictions.

The project integrates SHAP.

Benefits:

- Feature importance
- Global interpretation
- Local interpretation
- Forecast transparency

Generated outputs:

- shap_summary.png
- feature_importance.png

---

# 16. Multi-Agent Architecture

The platform implements four primary agents.

## Billing Agent

Responsibilities:

- Bill analysis
- Customer bill monitoring

## Forecasting Agent

Responsibilities:

- Forecast generation
- Trend analysis

## Anomaly Agent

Responsibilities:

- Abnormal bill detection
- Alert generation

## Recommendation Agent

Responsibilities:

- Plan recommendations
- Cost optimization suggestions

---

# 17. Agent-to-Agent Communication

A2A communication allows autonomous collaboration.

Example workflow:

Forecasting Agent
→ sends forecast

Anomaly Agent
→ checks abnormal behavior

Recommendation Agent
→ generates recommendation

Billing Agent
→ prepares customer summary

This architecture improves scalability and modularity.

---

# 18. Model Context Protocol (MCP)

MCP provides standardized communication between AI systems and enterprise resources.

The MCP server exposes tools such as:

- forecast_bill()
- explain_prediction()
- detect_anomaly()
- get_customer_history()

Benefits:

- Reusable tools
- Enterprise integration
- Context sharing
- Standardized interfaces

---

# 19. Dashboard

A Streamlit dashboard is implemented for visualization.

Modules:

## Forecast Dashboard

Displays:

- Actual Bills
- Forecast Bills
- Trends

## Anomaly Dashboard

Displays:

- Outliers
- Billing anomalies

## XAI Dashboard

Displays:

- SHAP explanations
- Feature importance

## Agent Dashboard

Displays:

- Agent decisions
- Recommendations

---

# 20. API Services

FastAPI is used to expose services.

Endpoints:

- /health
- /forecast
- /anomaly
- /explain

Swagger UI:

http://localhost:8000/docs

---

# 21. Installation Guide

## Create Environment

```bash
python -m venv bill_env
```

## Activate

Windows:

```bash
bill_env\Scripts\activate
```

## Install Packages

```bash
pip install -r requirements.txt
```

---

# 22. Execution Workflow

## Generate Dataset

```bash
python database/generate_telecom_dataset.py
```

## Create Training Dataset

```bash
python database/create_training_dataset.py
```

## Feature Engineering

```bash
python training/feature_engineering.py
```

## Train Model

```bash
python training/train_tft.py
```

## Predict

```bash
python training/predict_tft.py
```

## Evaluate

```bash
python training/evaluate_model.py
```

## Run Agents

```bash
python agents/orchestrator.py
```

## Run MCP

```bash
python mcp/server.py
```

## Launch Dashboard

```bash
streamlit run dashboard/app.py
```

---

# 23. Expected Outcomes

The completed system should provide:

- Accurate bill forecasting
- Revenue prediction
- Explainable decisions
- Autonomous agent collaboration
- Business recommendations
- Interactive dashboards

---

# 24. Dissertation Mapping

Chapter 1 – Introduction

Chapter 2 – Literature Review

Chapter 3 – Proposed Framework

Chapter 4 – Dataset Design

Chapter 5 – Methodology

Chapter 6 – Implementation

Chapter 7 – Results

Chapter 8 – Future Work

Chapter 9 – Conclusion

---

# 25. Future Enhancements

Potential future improvements:

- Real Verizon integration
- Real-time forecasting
- LLM-powered assistant
- Cloud deployment
- Reinforcement learning optimization
- Vector databases
- RAG integration

---

# 26. Academic Significance

This work demonstrates how forecasting, explainability, agent systems, and enterprise AI integration can be combined within a single intelligent analytics platform.

The project provides practical exposure to:

- Time Series Forecasting
- Transformer Models
- Explainable AI
- Multi-Agent Systems
- MCP Integration
- Dashboard Engineering
- Enterprise Data Architecture

---

# 27. License

This repository is intended for academic research and educational purposes as part of an M.Tech dissertation.

---

# 28. Acknowledgement

The author expresses gratitude to the dissertation supervisor, faculty members, institution, and research community for their support and guidance throughout this project.
