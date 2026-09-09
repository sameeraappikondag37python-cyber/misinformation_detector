<div align="center" style="border: 2px solid #ccc; padding: 20px; border-radius: 12px; width: 80%; margin: auto; box-shadow: 0 0 10px rgba(0,0,0,0.15);">
    <img
        width="180"
        height="220"
        alt="Logo - SURE ProEd"
        src="https://github.com/user-attachments/assets/88fa5098-24b1-4ece-87df-95eb920ea721"
        style="border-radius: 10px;"
    />

  <h1 align="center" style="font-family: Arial; font-weight: 600; margin-top: 15px;">SURE ProEd (formerly SURE Trust)</h1>
  <h2 style="color: #2b6cb0; font-family: Arial;">Skill Upgradation for Rural youth Empowerment Trust</h2>
</div>

<hr style="border: 0; border-top: 1px solid #ccc; width: 80%;" />

<div style="padding: 20px; border: 2px solid #ddd; border-radius: 12px; width: 90%; margin: auto; background: #fafafa; font-family: Arial;">

<h2 style="color:#333;"> Student Details </h2>
<div align="left" style="margin: 20px; font-size: 16px;">
    <p><strong>Name:</strong> Sameera Appikonda</p>
    <p><strong>Email ID:</strong> sameeraappikondag37python@gmail.com</p>
    <p><strong>College Name:</strong> Vignan's Institute of Engineering for Women</p>
    <p><strong>Branch/Specialization:</strong> B.Tech in Computer Science and Engineering (AI & ML)</p>
    <p><strong>College ID / Roll No:</strong> 23NM1A4202</p>
</div>

<hr style="border: 0; border-top: 1px solid #ccc; width: 80%;" />

<h2 style="color:#333;"> Course Details </h2>
<div align="left" style="margin: 20px; font-size: 16px;">
    <p><strong>Course Opted:</strong> 6-Month Project-Based Internship in Artificial Intelligence & Machine Learning</p>
    <p><strong>Instructor Name:</strong> Gaurav Sir</p>
    <p><strong>Duration:</strong> 6 Months</p>
</div>

<hr style="border: 0; border-top: 1px solid #ccc; width: 80%;" />

<h2 style="color:#333;"> Trainer Details </h2>
<div align="left" style="margin: 20px; font-size: 16px;">
    <p><strong>Trainer Name:</strong> Gaurav Patel</p>
    <p><strong>Trainer Email ID:</strong> gaurav.patel.gpp@gmail.com</p>
    <p><strong>Trainer Designation:</strong> Data Science Instructor</p>
</div>

<hr style="border: 0; border-top: 1px solid #ccc; width: 80%;" />

<h2 style="color:#333;"> Projects Completed </h2>

# MisInfo Shield — Misinformation Detection System

## Project Overview

**MisInfo Shield** is an AI-powered misinformation and fake-news detection system developed using Natural Language Processing (NLP) and Machine Learning. The system analyzes a news headline or text and predicts whether the content is **fake** or **real**. It also displays prediction confidence and provides a simulated view of how misinformation could spread.

The project uses the **ISOT Fake News Dataset** and applies text preprocessing, TF-IDF feature extraction, and Logistic Regression for classification. A Streamlit dashboard provides an interactive interface for users to enter news content and view the prediction.

---

## Table of Contents

1. [Project Overview](#project-overview)
2. [Dataset](#dataset)
3. [Data Preprocessing](#data-preprocessing)
4. [Feature Engineering](#feature-engineering)
5. [Modeling Approach](#modeling-approach)
6. [Exploratory Data Analysis](#exploratory-data-analysis)
7. [Web Dashboard](#web-dashboard)
8. [Model Performance](#model-performance)
9. [How the System Works](#how-the-system-works)
10. [How to Run](#how-to-run)
11. [Model Limitation](#model-limitation)
12. [Future Improvements](#future-improvements)
13. [Conclusion](#conclusion)

---

## Dataset

The project uses the **ISOT Fake News Dataset**.

- **Fake.csv:** 23,502 fake news articles
- **True.csv:** 21,417 real news articles
- **Total:** 44,919 articles
- **Source:** ISOT Dataset, University of Victoria

The dataset contains news articles labelled as fake or real and is used to train and evaluate the classification model.

---

## Data Preprocessing

The preprocessing pipeline prepares the news content before model training.

The project performs:

- Conversion of text to lowercase
- Removal of URLs
- Removal of non-alphabetic characters
- Stopword removal using NLTK
- Combination of news title and article text
- Removal of missing records

The cleaned text is then passed to the feature extraction stage.

---

## Feature Engineering

The project uses **TF-IDF (Term Frequency–Inverse Document Frequency)** to convert cleaned text into numerical features.

- **Feature extraction:** TF-IDF Vectorization
- **Maximum features:** 5,000

TF-IDF helps represent important words and phrases numerically so that the machine learning model can identify patterns associated with fake and real news.

---

## Modeling Approach

The classification model is implemented using a Scikit-learn pipeline containing:

- **TF-IDF Vectorizer**
- **Logistic Regression**

The dataset is divided into training and testing sets using an **80:20 split** with `random_state=42`.

The trained model is saved as:

`models/model.pkl`

---

## Exploratory Data Analysis

The project includes an EDA script that generates six visualizations:

1. Label Distribution
2. Word Count Distribution
3. Category Distribution
4. Confusion Matrix
5. ROC Curve
6. Top 15 Words in Fake News

These visualizations help understand the dataset and evaluate model behaviour.

---

## Web Dashboard

The project provides an interactive **Streamlit** web dashboard called **MisInfo Shield**.

The dashboard allows a user to:

- Enter a news headline or text
- Analyze the submitted content
- View whether it is predicted as fake or real
- View fake and real probability scores
- View a confidence breakdown
- View a simulated misinformation spread graph
- See dataset and model information

---

## Model Performance

According to the project implementation:

- **Accuracy:** 98.88%
- **AUC Score:** 0.99

These values are based on the evaluation performed on the project's test data.

---

## How the System Works

1. The user enters a news headline or text.
2. The text is cleaned using NLP preprocessing.
3. TF-IDF converts the cleaned text into numerical features.
4. Logistic Regression predicts whether the content is fake or real.
5. The dashboard displays the prediction and confidence scores.
6. A spread simulation provides an illustrative view of potential misinformation propagation.

---

## How to Run

### Step 1 — Activate the virtual environment

```text
venv\Scripts\activate
```

### Step 2 — Train the model

```text
python src/train.py
```

### Step 3 — Generate EDA plots

```text
python eda.py
```

### Step 4 — Check the evaluation report

```text
python src/evaluate.py
```

### Step 5 — Run the web dashboard

```text
streamlit run app/app.py
```

---

## Model Limitation

The model was trained on **2016–17 US political news** and therefore works best with political-news headlines similar to the training data.

It should not be treated as a universal fact-checking system for every type of news or current event.

---

## Future Improvements

Possible improvements include:

- BERT or other transformer-based models
- Real-time social media/API integration
- Multilingual misinformation detection
- Browser extension support
- Training on more recent and diverse news sources

---

## Conclusion

The **MisInfo Shield** project demonstrates how NLP and Machine Learning can be combined to identify potentially misleading or fake news content. The system uses text preprocessing, TF-IDF feature extraction, and Logistic Regression, together with an interactive Streamlit dashboard.

The project also demonstrates the complete workflow from dataset preparation and model training to evaluation, visualization, and interactive deployment.

---

<hr style="height:1px; border-top:1px solid #ccc; width:80%;" />

<h2 id="project-report" style="color:#333;"> Project Report </h2>

<p>
  <a href="https://github.com/sameeraappikondag37python-cyber/SAMEERA-APPIKONDA-Community-Service/blob/main/misinformation_detector_Project_Report.pdf" target="_blank">
    <strong>→ View Full Project Report</strong>
  </a>
</p>

<p><em>Note: Upload your project report to the Community-Service repository using the exact filename <strong>misinformation_detector_Project_Report.pdf</strong>, or update the link above to match the actual PDF filename.</em></p>

<hr style="height:1px; border-top:1px solid #ccc; width:80%;" />

## **References**

[![Python](https://img.shields.io/badge/Python-3.x-orange)](https://www.python.org/)
[![NumPy](https://img.shields.io/badge/NumPy-blue)](https://numpy.org/)
[![Pandas](https://img.shields.io/badge/Pandas-blue)](https://pandas.pydata.org/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-yellow)](https://scikit-learn.org/)
[![Streamlit](https://img.shields.io/badge/Streamlit-red)](https://streamlit.io/)
[![Plotly](https://img.shields.io/badge/Plotly-blue)](https://plotly.com/)
[![NLTK](https://img.shields.io/badge/NLTK-green)](https://www.nltk.org/)

## **Learnings from LST and SST**

LST and SST sessions played an important role in improving my technical understanding and professional development throughout the internship period. These sessions provided exposure to industry-oriented practices, communication techniques, and structured learning methodologies.

Through these sessions, I improved my communication skills, presentation abilities, interpersonal interaction, and confidence while expressing ideas and explaining technical concepts.

The sessions also helped me understand the importance of problem-solving, analytical thinking, time management, teamwork, and proper documentation practices in real-world project development.

In addition, the sessions provided guidance regarding professional ethics, workplace expectations, collaborative learning, and continuous self-improvement. These learnings supported my work during the development of the **MisInfo Shield — Misinformation Detection System**.

Overall, the LST and SST sessions contributed to my personal growth, professional readiness, and understanding of real-world project environments.

---

## **Community Services**

During my internship period, I actively participated in community-oriented activities focused on social responsibility and public welfare in **Visakhapatnam, Andhra Pradesh**.

### **Activities Involved**

- **Tree Plantation Drive** – Participated in tree plantation activities in Visakhapatnam and contributed towards environmental awareness and greener surroundings.
- **Food Distribution Activity** – Participated in food distribution activities in Visakhapatnam as part of social service and community support initiatives.

### **Impact / Contribution**

- Contributed towards environmental improvement through plantation activities.
- Supported community welfare through food distribution.
- Improved communication, coordination, teamwork, and social responsibility skills.
- Gained practical exposure to community service and collaborative volunteering.

### **Photos**

<div align="center">

<img src="https://github.com/sameeraappikondag37python-cyber/SAMEERA-APPIKONDA-Community-Service/blob/main/food_image.jpeg?raw=true" alt="Community Service Photo 1" width="41%">

<img src="https://github.com/sameeraappikondag37python-cyber/SAMEERA-APPIKONDA-Community-Service/blob/main/plantting.jpeg?raw=true" alt="Community Service Photo 2" width="41%">

</div>

---

## **Certificate**

The internship certificate section can be updated with the certificate image or document when it is available.

<!-- Add your certificate image URL below when available -->

---

## **Acknowledgments**

- [Prof. Radhakumari Challa](https://www.linkedin.com/in/prof-radhakumari-challa-a3850219b), Executive Director and Founder - [SURE Trust](https://www.suretrustforruralyouth.com/)
