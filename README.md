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

- [A/B Test Analysis with Ratio Metrics](https://github.com/AleksandrRodkin/Statistics_and_AB_tests)
  - This project explores reliable methods for analyzing ratio metrics (mean session duration) in A/B tests, where standard mean comparisons often produce biased results;
  - Demonstrates, using synthetic user-level data, how session-level analysis can inflate false positive rates;
  - Compares several statistical approaches for ratio metrics: Bootstrap, Bucket Method, Linearization, and Linearization with CUPED;
  - Bootstrap provides a distribution-free estimate but is computationally expensive;
  - Bucket Method aggregates users into random groups, offering scalability for large and on the fly calculations;
  - Linearization transforms ratio metrics into linear form, allowing standard statistical tests and variance reduction;
  - CUPED (Controlled Experiment Using Pre-Experiment Data) leverages historical data to further reduce variance and improve sensitivity;
  - Results show that CUPED reduces p-values by 2–3× compared to baseline methods, confirming a significant improvement in test precision.

- [Segmentation_MVTec_AD](https://github.com/AleksandrRodkin/Segmentation_MVTec_AD)
  - Task: Detect and segment defects on metal nuts at the pixel level using data from MVTec AD;
  - Dataset: The metal_nut subset from MVTec AD is used: training contains only normal, defect-free samples,
    while testing includes a mix of normal and defective samples. Binary masks indicate the exact locations of anomalies;
  - Architecture: ResNet50 is used for feature extraction, with MemoryNet (PatchCore-based) or UpMemoryNet (with refined masks,
    where outputs from the first ResNet layers are added during upsampling) for segmentation.
    These memory-based models help separate normal patterns from anomalous ones;
  - Training: The model is trained using a combined BCE + Dice loss, with AdamW optimizer and MultiStepLR scheduler.
    The pipeline includes image preprocessing, memory bank construction for embeddings, and segmentation evaluation using the Dice coefficient;
  - Results: The model successfully localizes scratches, cracks, and other defects.
    Visualizations include predicted vs. ground truth masks, anomaly heatmaps, and bounding boxes around defective regions.
