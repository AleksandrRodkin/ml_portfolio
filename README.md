# Portfolio | Aleksandr Rodkin
# Hi there 👋
I work in ML and Data Science. Here are some of my projects:

## [Bank Account Fraud Detection API](https://github.com/AleksandrRodkin/FraudDetection)

 *Built an end-to-end ML system for fraud detection using realistic data, combining advanced ML with production-ready API deployment*

 - Exploratory Data Analysis & Feature Engineering:
   - Conducted detailed EDA and identified that fraud cases account for approximately 1% of all records;
   - Removed irrelevant features, merged rare categories to improve data stability;
   - Selected informative features using correlation analysis, mutual information, and model-based importance scores to improve generalization.

 - Modeling:
   - Used Recall@5% FPR as the main metric to optimize fraud detection while maintaining low false positives, balancing business impact and user experience;
   - Built a reproducible end-to-end ML pipeline for data preprocessing, feature engineering, and model training;
   - Trained and compared multiple models: Logistic Regression, LinearSVC, Random Forest, and XGBoost;
   - Applied time series cross-validation to prevent data leakage and ensure realistic performance estimation;
   - Used SMOTE and NearMiss to handle imbalanced training data and boost model sensitivity;
   - Tuned hyperparameters with Optuna;
   - Conducted paired statistical tests for model selection;
   - Calibrated XGBoost probabilities with Platt scaling and optimized the classification threshold to ensure the FPR does not exceed 5%;
   - Achieved competitive results on the test set with Recall@5% FPR = 0.55, while avoiding data leakage.

 - API Development & Deployment:
   - Built a high-performance asynchronous API with FastAPI to serve model predictions in real time;
   - Implemented two data access modes: via JSON input (with Pydantic validation) or via PostgreSQL data base connection, managed through SQLAlchemy;
   - Supported batch processing - multiple applications can be checked at once;
   - Validated responses using Pydantic schemas to ensure consistent and safe data exchange;
   - Integrated logging with loguru;
   - Containerized the service with Docker for reproducible deployment and easy scaling across environments.

## [Analysis of Ratio Metrics in A/B Tests](https://github.com/AleksandrRodkin/Statistics_and_AB_tests)

 *This project explored reliable methods for analyzing ratio metrics (on the example of mean session duration) in A/B tests, where standard mean comparisons often produced biased results*
 
 - Demonstrated, using synthetic user-level data, how session-level analysis could inflate false positive rates;
 - Compared several statistical approaches for ratio metrics: Bootstrap, Bucket Method, Linearization, and Linearization with CUPED;
 - Showed that Bootstrap provided a distribution-free estimate but was computationally expensive;
 - Showed that the Bucket Method aggregated users into random groups, offering scalability for large and on-the-fly calculations;
 - Applied Linearization to transform ratio metrics into a linear form, allowing standard statistical tests and variance reduction;
 - Used CUPED (Controlled Experiment Using Pre-Experiment Data) to leverage historical data for further variance reduction and improved sensitivity;
 - Found that CUPED reduced p-values by 2–3× compared to baseline methods, confirming a significant improvement in test precision.

## [Segmentation_MVTec_AD](https://github.com/AleksandrRodkin/Segmentation_MVTec_AD)
 *In this project, a model was developed for defect segmentation on the MVTec_AD dataset*
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
