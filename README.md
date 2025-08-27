# ml_portfolio
# Hi there 👋
I work in ML and Data Science. Here are some of my projects:

- [Fraud Detection](https://github.com/AleksandrRodkin/FraudDetection) — detecting  of fraudulent applications with bank accounts
  - Got a realistic Bank Account Fraud Dataset from kaggle;
  - Performed EDA (the target class is imbalanced), Feature Engineering and data preprocessing;
  - Used Recall@5% FPR as the main metric (to balance the model’s accuracy and user experience);
  - Tuned baseline models (LR and SVC), Random Forest and XGB with TimeSeries CV.
  - Applied a paired statistical test on bootstrap subsamples to compare mean metric values for model selection;
  - Calibrated the probabilities of the XGB model with Platt’s method and changed the predict method to limit FPR at 5% level;
  - Developed an API with FastAPI and containerized it using Docker.


