
SMS Spam Classification Using SVM
Project Overview
This project classifies SMS messages as Spam or Ham (not spam)
using a machine learning model. It is implemented in a Jupyter Notebook
and uses text preprocessing, TF-IDF feature extraction, and a Linear
Support Vector Machine (SVM) classifier.
Objectives
- Clean and prepare SMS text messages for machine learning.
- Explore the dataset using basic visualizations.
- Train and evaluate an SVM-based text classification model.
- Tune the model's hyperparameter and evaluate it using
  cross-validation.
- Predict whether a new SMS message is spam or ham.
Technologies and Libraries
- Python
- Pandas and NumPy
- Matplotlib and Seaborn
- NLTK
- WordCloud
- Scikit-learn
- Google Colab or Jupyter Notebook
Dataset
The notebook expects an SMS dataset file named SMS.csv in CSV
format. It reads the file using Latin-1 encoding and expects these
columns: - v1: message label (ham or spam) - v2: SMS message
text
The notebook renames these columns to label and message. Ensure that
your dataset has this structure before running the notebook.
Workflow
1. Load the data: Read the CSV dataset and inspect its shape,
   information, missing values, duplicates, and label distribution.
2. Exploratory Data Analysis: Compare spam and ham counts, examine
   message word counts, and create word clouds for both categories.
3. Preprocessing: Convert text to lowercase, remove URLs, email
   addresses, digits, and punctuation, remove English stopwords, and
   lemmatize words. Duplicate messages are removed.
4. Train/test split: Split the data into training and testing sets
   using an 80/20 ratio, with stratification to preserve the class
   distribution.
5. Feature extraction and classification: Convert messages to
   TF-IDF features using up to 5,000 features and unigram/bigram
   combinations. Train a LinearSVC classifier.
6. Evaluation: Report accuracy, precision, recall, F1-score, and
   the classification report.
7. Hyperparameter tuning: Use GridSearchCV with five-fold
   cross-validation to test SVM C values of 0.1, 1, and 10.
8. Cross-validation: Calculate cross-validation scores and their
   mean.
9. Prediction: Use the selected model to classify new SMS messages.
Installation
Install the required libraries in a Python environment:
pip install pandas numpy matplotlib seaborn wordcloud nltk scikit-learn
In Google Colab, the notebook also includes an installation cell for
some required packages.
How to Run
Option 1: Google Colab
1. Upload SMS_Spam_SVM_updated(1).ipynb to Google Colab.
2. Run the notebook cells from top to bottom.
3. When prompted, upload the dataset file expected by the notebook,
   named SMS.csv.
4. Review the visualizations, evaluation metrics, cross-validation
   results, and example predictions.
Option 2: Jupyter Notebook
1. Install Python and the required libraries.
2. Open the notebook in Jupyter.
3. Make sure SMS.csv is in the notebook's working directory.
4. Run all cells from top to bottom.
Example Predictions
The notebook includes these example messages: -
Congratulations! You have won a free iPhone. Click here now. -
Hi, are we meeting tomorrow at 3 PM?
The prediction function returns either Spam or Ham. Actual
predictions depend on the dataset and the trained model.
Project Structure
.
├── SMS_Spam_SVM_updated(1).ipynb
├── SMS.csv
└── README.md
Notes and Limitations
- The dataset must contain the expected v1 and v2 columns.
- The notebook's prediction function expects the trained model to have
  been created by running the training and tuning cells first.
- Text cleaning removes numbers and punctuation, which may remove
  useful clues from some spam messages.
- Model performance depends on the dataset and the train/test split.
  Use the metrics printed by the notebook rather than assuming a
  particular accuracy.
- The notebook uses a simple train/test split and cross-validation; it
  is intended as an educational machine-learning project, not a
  production spam-filtering service.
