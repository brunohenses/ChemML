
# ChemML - Molecular Property Prediction System

## Overview

ChemML is a comprehensive molecular property prediction system that integrates machine learning techniques with computational chemistry. It enables users to input molecular structures (via SMILES) and receive reliable predictions of key physicochemical properties.

## Project Goals

* **Technical:** Showcase the application of ML to real-world scientific challenges.
* **Professional:** Demonstrate proficiency in Flask, PyTorch, RESTful APIs, and database management.
* **Differentiator:** Leverage chemical expertise for feature engineering and rigorous validation of predictions.

## Key Features

1. **Property Prediction**

   * Water solubility (LogS regression)
   * Acute toxicity (binary classification)
   * Melting point (temperature regression)
   * Environmental biodegradability (classification)

2. **Web Interface**

   * SMILES input or molecular drawing upload
   * 2D/3D structure visualization
   * User-specific prediction history
   * Dashboard with usage statistics and performance metrics

3. **REST API**

   * Endpoints for external integration
   * JWT-based authentication
   * Auto-generated Swagger documentation
   * Rate limiting and caching support

4. **Validation System**

   * Chemical validation of SMILES strings
   * Out-of-domain molecule detection
   * Prediction reliability scoring

## System Architecture

```
chemml/chemml/
├── app/
│   ├── models/           # PyTorch models and SQLAlchemy schemas
│   ├── routes/           # API endpoints, authentication, and web views
│   ├── utils/            # Descriptor calculations, validators, and preprocessing
│   └── templates/        # HTML templates: base, index, predict, history
├── data/
│   ├── raw/              # Raw datasets
│   ├── processed/        # Preprocessed data
│   └── models/           # Trained model artifacts
├── notebooks/            # Exploratory analysis and model development
├── tests/                # Unit and integration tests
├── config.py             # Environment configurations
├── requirements.txt      # Python dependencies
└── README.md             # Project documentation
```

## Technology Stack

* **Backend:** Flask, SQLAlchemy, PyTorch, RDKit, Pandas, NumPy
* **Frontend:** HTML/CSS/JavaScript, Bootstrap, Chart.js
* **Database:** SQLite (development), PostgreSQL (production)
* **Deployment:** Docker, Gunicorn, Nginx, Redis

## Suggested Datasets

* **Solubility:** AqSolDB, ESOL
* **Toxicity:** Tox21, ChEMBL
* **Melting Point:** Bradley Melting Point, NIST WebBook

## Evaluation Metrics

* **Regression:** R², RMSE, MAE
* **Classification:** Accuracy, F1-score, AUC-ROC

## Development Timeline

1. **Phase 1 (Weeks 1-2):**

   * Environment setup and project scaffolding
   * Data collection and preprocessing
   * Molecular descriptor calculation
   * Database schema design

2. **Phase 2 (Weeks 3-4):**

   * Model development and training
   * Hyperparameter tuning and validation pipeline

3. **Phase 3 (Weeks 5-6):**

   * REST API implementation and authentication
   * Model integration into API
   * Automated testing

4. **Phase 4 (Weeks 7-8):**

   * Web interface and dashboard development
   * Molecular visualization and history tracking

5. **Phase 5 (Weeks 9-10):**

   * Final documentation and end-to-end tests
   * Deployment and performance optimization

## Deployment

1. Build the Docker image:

   ```bash
   docker build -t chemml .
   ```
2. Run with Gunicorn and Nginx:

   ```bash
   docker run -d -p 80:80 chemml
   ```
3. Additional services: Redis for caching and session management.

## Usage

1. Clone the repository:

   ```bash
   git clone https://github.com/brunohenses/chemml.git
   cd chemml
   ```
2. Create a virtual environment and install dependencies:

   ```bash
   python -m venv venv
   source venv/bin/activate
   pip install -r requirements.txt
   ```
3. Initialize the database:

   ```bash
   flask db init && flask db migrate && flask db upgrade
   ```
4. Start the development server:

   ```bash
   flask run
   ```

## Contributing

Contributions are welcome! Feel free to open issues and submit pull requests.

## License

This project is licensed under the MIT License.
