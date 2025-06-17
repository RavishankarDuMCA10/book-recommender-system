Great! Based on that, here’s an updated `README.md` tailored specifically for a **Flask-based Book Recommender System**, deployed on **Heroku**, using the **Pickle library** to load the machine learning model.

---

# 📚 Book Recommender System

A **Flask-based web application** that recommends books using a machine learning model trained on the Book-Crossing dataset. Users can:

* View the **Top 50 most popular books**
* Enter a book title to get **Top 5 similar book recommendations**

The app is **deployed on Heroku** and uses **Pickle** to load pre-trained ML models.

---

## 🚀 Features

* 🔝 View Top 50 most popular books with cover images
* 🔍 Get Top 5 book recommendations for any entered book
* 🧠 Cosine similarity-based recommendation system
* 📦 Flask backend with Pickle model loading
* ☁️ Deployed to Heroku for live access

---

## 🧠 How It Works

1. **Data Preprocessing**

   * Loaded `Books.csv`, `Ratings.csv`, `Users.csv`
   * Removed missing values and duplicates
   * Filtered for books with at least 250 ratings and active users

2. **Model Training**

   * Created a pivot table of books and users
   * Applied **cosine similarity** on the matrix
   * Saved the final model and pivot table using `pickle`

3. **Web Interface**

   * Built using **Flask**
   * Home page shows Top 50 books
   * Recommendation page takes input and shows 5 similar books

---

## 🗂️ Project Structure

```
📁 book-recommender/
├── static/
│   └── style.css                  # Styling for the app
├── templates/
│   ├── index.html                 # Home page showing Top 50 books
│   └── recommend.html             # Recommendations page
├── app.py                         # Flask app entry point
├── book-recommender-system.ipynb # Jupyter notebook for model training
├── Books.csv                      # Book metadata
├── Ratings.csv                    # User ratings
├── Users.csv                      # User data
├── similarity.pkl                 # Cosine similarity matrix (pickled)
├── pt.pkl                         # Pivot table (pickled)
├── books.pkl                      # Book info for recommendations (pickled)
└── requirements.txt               # Python dependencies
```

---

## ▶️ Getting Started Locally

### 1. Clone the Repository

```bash
git clone https://github.com/RavishankarDuMCA10/book-recommender-system.git
cd book-recommender-system
```

### 2. Create Virtual Environment & Install Dependencies

```bash
python -m venv venv
source venv/bin/activate  # or venv\Scripts\activate on Windows
pip install -r requirements.txt
```

### 3. Run the Flask App

```bash
python app.py
```

Then visit `http://127.0.0.1:5000/` in your browser.

---

## ☁️ Deployment on Heroku

1. Ensure you have a `Procfile`:

   ```
   web: gunicorn app:app
   ```

2. Install Gunicorn:

   ```bash
   pip install gunicorn
   ```

3. Commit your changes and push to Heroku:

   ```bash
   heroku create your-app-name
   git push heroku main
   ```

4. Open in browser:

   ```bash
   heroku open
   ```

---

## 🧪 Example Usage

### Home Page

Shows 50 most popular books with cover images and ratings.

### Recommendation Page

Input: `The Da Vinci Code`
Output:

* Angels & Demons
* Deception Point
* Digital Fortress
* The Lost Symbol
* Inferno

---

## 📝 License

This project is licensed under the [MIT License](LICENSE).

---