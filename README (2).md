
# 📱 SMS Spam Detector

A machine learning project that detects whether a given SMS message is spam or not. Built using Scikit-learn, TF-IDF vectorization, and Linear Support Vector Classification (LinearSVC). Includes a Gradio-powered web interface for real-time predictions.

## 🚀 Features

- Preprocessing and vectorization using TF-IDF
- Supervised learning with LinearSVC
- Model evaluation and accuracy scoring
- Interactive web app via Gradio
- Easy-to-read predictions: "Spam" or "Not Spam"

## 📂 Project Structure

```
sms_spam_detector/
│
├── Resources/
│   └── SMSSpamCollection.csv       # Dataset file
│
├── gradio_sms_text_classification.ipynb   # Notebook with Gradio interface
├── sms_text_classification_solution.ipynb # Model training and evaluation notebook
├── README.md                              # Project documentation
```

## 📊 Dataset

- **Name:** SMSSpamCollection.csv  
- **Source:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/sms+spam+collection)
- **Content:** 5,574 SMS messages labeled as "ham" or "spam"

## 🛠️ Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/tonyd1002/sms_spam_detector.git
   cd sms_spam_detector
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## 🧠 Model Training

Use the provided Jupyter notebook:
```bash
sms_text_classification_solution.ipynb
```

It includes:
- Data cleaning
- Train-test split
- Pipeline creation using `TfidfVectorizer` and `LinearSVC`
- Accuracy evaluation

## 🌐 Launch Web App

Run the Gradio notebook:
```bash
gradio_sms_text_classification.ipynb
```

Or use the Python snippet:
```python
import gradio as gr

def sms_prediction(text):
    prediction = text_clf.predict([text])[0]
    return f"The text message: \"{text}\" is {'not spam' if prediction == 'ham' else 'spam'}."

gr.Interface(
    fn=sms_prediction,
    inputs=gr.Textbox(label="Enter SMS Text"),
    outputs=gr.Textbox(label="Prediction"),
    title="SMS Spam Detector"
).launch()
```

## 📈 Model Accuracy

- **Training Accuracy:** ~99%
- **Testing Accuracy:** ~97–98%

## 🧪 Example Predictions

```python
text_clf.predict(["You have won a free prize worth $1000!"])
# Output: ['spam']

text_clf.predict(["Are we still on for lunch at noon?"])
# Output: ['ham']
```

## 📬 Contact

Made with ❤️ by Tony D.  
Feel free to contribute or fork this repo!
