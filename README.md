# Job Salary Prediction: A Text Analytics Approach

## 📋 Overview

This project addresses the salary information asymmetry in the job market by developing an advanced machine learning solution that predicts job salaries based on unstructured text from job descriptions. Using sophisticated NLP techniques and neural networks, we achieved an R² of 0.829, providing job seekers with accurate salary benchmarks for negotiation.

## 🔍 Problem Statement

Job seekers often face disadvantages during compensation negotiations due to limited access to accurate salary benchmarks. This project aims to:
- Predict job salaries from unstructured job description text
- Identify key factors that influence compensation
- Create a practical tool for salary expectation guidance

## 📊 Dataset

- **Size**: 27,900 LinkedIn job postings
- **Structured fields**: Company, industry, work type, experience level
- **Unstructured text**: Job titles and descriptions
- **Target variable**: Annual salary (normalized using US minimum wage as lower bound)

## 🛠️ Methodology

### Data Processing

We implemented an enhanced text preprocessing pipeline:
- Context-aware lemmatization with POS tagging
- Domain-specific stopword customization
- Abbreviation standardization for industry terms
- Outlier handling and salary normalization

### Feature Engineering

Our innovative approach to feature extraction included:
- Creation of 10 distinct professional skill categories
- Skill-specific keyword mapping and extraction
- Category-based feature representation
- Customized TF-IDF vectorization for domain-specific terms

### Model Development

We systematically evaluated multiple text analytics approaches:

| **Model** | **R²** | **RMSE** | **Runtime** |
|------------|--------|----------|-------------|
| Baseline + RF (structured data only) | 0.515 | 29,620.21 | 40.7s |
| TF-IDF (General) + RF | 0.592 | 27,138.60 | 4m 51s |
| BoW + TF-IDF (General & Skill-Specific) + RF | 0.623 | 26,126.36 | 44m 42s |
| BoW + TF-IDF + Neural Network | 0.732 | 21,797.11 | 9m 50s |
| BoW + TF-IDF + NN (Enhanced Cleaning) | 0.829 | 17,502.23 | 5m 28s |
| BERT + Deep Learning | 0.868 | 15,510.12 | 540m |

## 🔑 Key Findings

- Experience level, industry expertise, and education consistently ranked as the strongest salary predictors
- Certain technical skills in software development and data analysis commanded premium compensation regardless of industry
- Our optimized neural network with enhanced preprocessing strikes an excellent balance between accuracy (R² = 0.829) and computational efficiency (5m 28s runtime)

## 💡 Innovations

1. **Enhanced Text Cleaning Pipeline**: Preserved important salary-predictive terms while eliminating noise
2. **Skill-Specific TF-IDF Vectorization**: Separately processed general text and domain-specific terms with optimized parameters
3. **Cross-Validation Strategy**: Implemented stratification based on salary bands for reliable performance estimates across all position levels

## 📈 Applications

This model can be deployed in:
- Recruitment platforms
- Career services
- Compensation planning tools
- Personal career development guidance

## 🚀 Future Work

- Integration with real-time job listing data
- Extension to international job markets with currency and cost-of-living adjustments
- Development of a user-friendly interface for public use
- Incorporation of additional data sources (company reviews, economic indicators)

## 👥 Contributors

- Xinyi Wang
- JaeYoon Lee
