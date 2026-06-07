# ML Prediction Service - Problem Statement

## Project

ML Prediction Service

## Dataset

Telco Customer Churn

## Problem Type

Binary classification

## Business Problem

Customer churn is a common business problem where a company wants to identify customers who are likely to stop using its services.

For a telecom company, losing customers can reduce recurring revenue and increase the cost of acquiring replacement customers. If likely churners can be identified early, the business can take retention actions such as targeted offers, customer support follow-ups, or service improvement campaigns.

## ML Problem

Given customer demographic, account, service, contract, and billing-related features, predict whether a customer is likely to churn.

The model will output a churn prediction for a customer. In later versions, the system may also output a churn probability or risk score.

## Target Variable

`Churn`

Expected classes:

- `Yes`: Customer churned
- `No`: Customer did not churn

## Input Features

The model may use customer-related features such as:

- Gender
- Senior citizen status
- Partner status
- Dependent status
- Tenure
- Phone service
- Multiple lines
- Internet service
- Online security
- Online backup
- Device protection
- Tech support
- Streaming TV
- Streaming movies
- Contract type
- Paperless billing
- Payment method
- Monthly charges
- Total charges

## Expected API User

The prediction API may be used by:

- An internal business dashboard
- A customer retention team
- A CRM system
- A batch scoring pipeline
- A backend service that needs churn-risk predictions

The first version of the API will focus on serving predictions reliably rather than supporting a complete business workflow.

## Success Metric

The primary metric will be:

```text
F1-score
```

### Why F-1 score?

F1-score is selected because churn prediction can involve class imbalance. Accuracy alone may be misleading if the model performs well on the majority class but fails to identify customers who are likely to churn.

F1-score balances:

- Precision: how many predicted churners actually churn
- Recall: how many actual churners are identified by the model

## Secondary Metrics

The following secondary metrics will also be tracked:

- Accuracy
- Precision
- Recall
- ROC-AUC
- Confusion matrix

## Initial Success Criteria

The first version of the project will be considered successful if:

- The dataset can be loaded reproducibly.
- Preprocessing is handled through a reusable pipeline.
- A baseline model can be trained and evaluated.
- Evaluation metrics are saved and documented.
- A trained model artifact can be saved.
- The model can later be served through a FastAPI endpoint.

The goal of version 1 is not maximum model accuracy. The goal is to build a clean, maintainable, production-style ML workflow.

## Assumptions

- Historical customer data is representative enough for initial model development.
- The target label `Churn` is correctly recorded.
- Features used during training will also be available during inference.
- The dataset is suitable for demonstrating ML engineering concepts.
- No unnecessary personally sensitive features will be used beyond what is required for this learning project.
- The first version will prioritize reproducibility, structure, and documentation over advanced modeling.

## Limitations

- The model will not fully explain why a customer churns.
- Dataset quality directly affects prediction quality.
- The dataset is a sample dataset, so conclusions should not be treated as real telecom business claims.
- The first version may not include advanced explainability.
- The first version may not include live monitoring.
- The prediction API will provide model output, but business teams would still need to decide what action to take.

## Out of Scope for Version 1

The following are not included in the first version:

- Real-time production deployment
- Advanced model explainability dashboard
- Automated retraining
- Live data drift monitoring
- Customer intervention recommendation engine
- Cost-benefit analysis of retention campaigns

## Version 1 Scope

Version 1 will include:

- Dataset loading
- Exploratory data analysis
- Preprocessing pipeline
- Baseline model training
- Model evaluation
- Model artifact saving
- FastAPI prediction endpoint
- Basic tests
- Docker setup
- Documentation
