# Resume Classifier Project

This project develops a machine learning model to classify resumes into categories based on the job descriptions. It utilizes several algorithms like Support Vector Machine (SVM), Multinomial Naive Bayes, Random Forest, and DistilBERT to achieve this.

## Table of Contents
- [Installation](#installation)
- [Data](#data)
- [Usage](#usage)
- [Models](#models)
- [Performance](#performance)
- [Contributing](#contributing)
- [License](#license)

## Installation

To set up this project locally, follow these steps:

```bash
git clone https://github.com/yourusername/resume-classifier.git
cd resume-classifier
pip install -r requirements.txt
```

## Data

The dataset for this project is collected by scraping resume data from [LiveCareer.com](https://www.livecareer.com). Approximately 8,350 resumes are collected across 10 job categories including Python Developer, Java Developer, Web Developer, Database Administrator, Security Analyst, Project Manager, Frontend Developer, Network Administrator, and Software Developer.

### Data Collection Process

Resumes are scraped using Selenium with the Chrome WebDriver. The process involves navigating to specific URLs constructed for each job category and extracting links to individual resumes. Here’s a brief outline of the steps involved in the scraping process:

1. **Set up Selenium WebDriver**: Configure Selenium with ChromeDriver to interact with web pages.
2. **Navigate through job categories**: For each category, generate URLs to navigate through pages of listings on LiveCareer.com.
3. **Extract resume links**: Collect the href attribute of each resume link on the listing pages.
4. **Visit each resume link**: For each extracted link, navigate to the corresponding page to access the full resume.
5. **Extract resume text**: Parse the HTML content of each resume page to extract the textual data.
6. **Store data**: Save the collected resume texts and their corresponding categories to a DataFrame, then export to a CSV file named `Resume.csv`.

This scraping process ensures the collection of a diverse and extensive dataset that represents various sectors in the job market, suitable for training our classification models.

### Note on Data Collection Ethics
This data is used strictly for educational purposes in the context of this project. Ensure compliance with LiveCareer.com’s terms of service regarding data scraping and use.

### Data Structure
The resulting dataset comprises columns for `Resume` text and the corresponding `Category`. It's stored in a CSV file to facilitate easy access and manipulation for training machine learning models.


## Usage

To run the classification:

```python
python resume_classifier.py
```

This script will execute the data preprocessing, model training, and output the classification accuracy of each model.

## Models

This project includes several classification models:
- **Support Vector Machine (SVM)**: Used for high accuracy in categorical classification.
- **Multinomial Naive Bayes**: Effective for word counts or frequency data.
- **Random Forest**: Provides a good benchmark for complex classification tasks.
- **DistilBERT**: Not implemented in the project's current scope but recommended for future scaling to handle contextual embeddings from text data.

## Performance

The models are evaluated based on accuracy, precision, recall, and F1-score. Random Forest showed a significant performance with an accuracy of 83%, followed by SVM at 88% and Multinomial Naive Bayes at 79% and DistilBERT at 93%.
