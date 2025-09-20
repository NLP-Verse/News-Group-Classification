# 📰 News Group Classification  

A Natural Language Processing (NLP) project that classifies news articles into their respective categories.  
This project applies **text preprocessing, TF–IDF feature extraction, and multiple machine learning algorithms** to automate the categorization of news articles.  

---

## 📖 About  

The **News Group Classification** project demonstrates how NLP and machine learning can be applied to large-scale textual datasets.  
Our goal was to build a pipeline that processes raw news content and predicts its category (e.g., sports, politics, technology).  

We experimented with multiple models, optimized their hyperparameters, and compared their performance to select the best classifier.  

---

## 📂 Dataset Overview  

The dataset consists of news articles with the following columns:  

- **category** → Target label (sports, politics, tech, etc.)  
- **filename** → File name/path for each article  
- **content** → Full article text (used as input for training)  

We trained the models on **80% of the dataset** and evaluated on the remaining **20% test set**.  

---

## 🛠️ Preprocessing Pipeline  

We applied a complete preprocessing pipeline to clean and prepare the text for training:  

- Expand contractions (`don't → do not`, `it's → it is`)  
- Convert text to lowercase  
- Remove metadata, numbers, and punctuation  
- Normalize whitespace  
- **Tokenization** with NLTK  
- Remove **stop words** (e.g., "the", "is", "and")  
- **Lemmatization** → reduce words to their base form (`cars → car`)  
- **TF–IDF Vectorization** → convert text into numerical feature vectors  

---

## 🤖 Models & Results  

We trained and evaluated four classification algorithms:  

### 🔹 Multinomial Naïve Bayes  
- Works naturally with TF–IDF features  
- Best hyperparameters: `alpha = 1`  
- Achieved solid baseline performance  

### 🔹 Random Forest Classifier  
- Handles high-dimensional, sparse TF–IDF vectors  
- Best hyperparameters: `n_estimators = 200`, `max_depth = 10`  
- ✅ **Best-performing model overall**  

### 🔹 Support Vector Machine (SVM)  
- Effective in high-dimensional sparse space  
- Best hyperparameter: `C = 0.1`  
- Strong classification accuracy  

### 🔹 K-Nearest Neighbor (KNN)  
- Non-parametric, similarity-based classifier  
- Best hyperparameters: `n_neighbors = 3`, `p = 1`, `weights = distance`, `n_components = 100`  
- Worked well but less efficient compared to Random Forest  

📌 **Conclusion:**  
Across all experiments, **Random Forest outperformed the other models** and is our recommended choice for news group classification.  

---

## 📊 Evaluation  

We evaluated models using:  
- Accuracy  
- Precision  
- Recall  
- F1-Score  
- Confusion Matrices (for detailed error analysis)  

Detailed results and plots are available in:  
📄 **`News Group Classification Report.docx`**  

---

# Setup

After cloning the repository, run the following commands inside the `project` folder to set up your development environment:

```bash
# Create virtual environment
python -m venv .venv        # On Windows
python3 -m venv .venv       # On Linux/Mac

# Activate virtual environment
.venv\Scripts\activate      # On Windows
source .venv/bin/activate   # On Linux/Mac

# Install dependencies
pip install -r requirements.txt

```
Then you're ready to start coding!
