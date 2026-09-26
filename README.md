# 📊 TrendPulse — Hacker News Trend Analysis

TrendPulse is a Python-based data analysis project that collects top stories from the **Hacker News API**, categorizes them by topic, cleans and analyzes the collected data, and creates visualizations to identify trends and engagement patterns.

The project demonstrates a complete data workflow:

Collect → Clean → Analyze → Visualize

---

## 🚀 Project Overview

Hacker News contains a large number of technology, science, business, sports, and other news-related stories.

TrendPulse automatically collects top Hacker News stories and categorizes them into five topic areas:

* 💻 Technology
* 🌍 World News
* 🏅 Sports
* 🔬 Science
* 🎬 Entertainment

The collected data is then cleaned, analyzed using **Pandas and NumPy**, and visualized using **Matplotlib**.

---

## 🛠️ Technologies Used

* Python
* Requests — API data collection
* Pandas — data cleaning and analysis
* NumPy — numerical/statistical analysis
* Matplotlib — data visualization
* JSON / CSV — data storage
* Google Colab / Jupyter Notebook
* Git & GitHub

---

## 🔄 Project Workflow


Hacker News API
       ↓
Data Collection
       ↓
Raw JSON Data
       ↓
Data Cleaning
       ↓
Clean CSV
       ↓
Data Analysis
       ↓
Analyzed CSV
       ↓
Visualization
       ↓
Charts + TrendPulse Dashboard


---

# 📥 Task 1 — Data Collection

The project uses the Hacker News Firebase API to retrieve:

1. Top story IDs
2. Individual story details

The collected information includes fields such as:

* Post ID
* Story title
* Score
* Number of comments
* Author
* Category

Stories are categorized using predefined keywords in their titles.

### Example

A story containing keywords such as:


AI, software, code, cloud, GPU, LLM

can be categorized under **Technology**.

The collected raw data is stored as:

data/trends_20260926.json

---

# 🧹 Task 2 — Data Cleaning

The raw JSON data is loaded into a Pandas DataFrame and cleaned before analysis.

The cleaning process includes:

* Removing duplicate posts
* Removing rows with missing `post_id`, `title`, or `score`
* Removing leading/trailing spaces from titles
* Converting `score` and `num_comments` to integers
* Removing stories with scores below 5

Additional analysis columns were created:

* `engagement`
* `engagement_rate`
* `score_category`

The cleaned dataset is saved as:

data/trends_clean.csv

---

# 📈 Task 3 — Data Analysis

The cleaned data is analyzed using **Pandas and NumPy**.

The analysis includes:

* Average story score
* Average number of comments
* Mean score
* Median score
* Standard deviation
* Highest score
* Lowest score
* Number of stories per category
* Most-commented story

Two additional columns are created:

### Engagement

engagement = num_comments / (score + 1)

The `+1` prevents division by zero when a story has a score of zero.

### Popularity


is_popular = score > average_score

A story is considered popular when its score is greater than the average score of the dataset.

The analyzed dataset is saved as:

data/trends_analysed.csv

---

# 📊 Task 4 — Data Visualization

Matplotlib is used to create three charts.

## 1. Top 10 Stories by Score

A horizontal bar chart showing the ten stories with the highest scores.

outputs/chart1_top_stories.png

## 2. Stories per Category

A bar chart showing the number of collected stories in each category.

outputs/chart2_categories.png

## 3. Score vs Comments

A scatter plot comparing:

* X-axis: Story score
* Y-axis: Number of comments

Stories are separated into:

* Popular Stories
* Non-Popular Stories


outputs/chart3_scatter.png

---

# 📋 TrendPulse Dashboard

The three visualizations are combined into a single dashboard for easier comparison.

outputs/dashboard.png

The dashboard provides a quick overview of:

* Highest-scoring stories
* Category distribution
* Relationship between score and comments

---

# 📁 Project Structure


TrendPulse/
│
├── data/
│   ├── trends_20260926.json
│   ├── trends_clean.csv
│   └── trends_analysed.csv
│
├── outputs/
│   ├── chart1_top_stories.png
│   ├── chart2_categories.png
│   ├── chart3_scatter.png
│   └── dashboard.png
│
├── TrendPulse.ipynb
│
└── README.md

---

# ▶️ How to Run

### 1. Clone the repository

git clone https://github.com/poompavai-muni/TrendPulse.git

### 2. Install the required libraries

pip install requests pandas numpy matplotlib

### 3. Open the notebook

Open:

TrendPulse.ipynb

using Google Colab or Jupyter Notebook.

### 4. Run the cells

Run the notebook from the data collection stage through the visualization stage.

---

# 💡 Key Skills Demonstrated

This project demonstrates practical experience with:

* Python programming
* REST API data collection
* JSON handling
* Pandas DataFrames
* Data cleaning
* Handling missing values
* Removing duplicates
* Data type conversion
* Filtering and sorting
* NumPy statistical calculations
* Feature/column creation
* Data categorization
* Matplotlib visualization
* Dashboard creation
* File and folder management
* GitHub project organization

---

# 📌 Future Improvements

Possible improvements for TrendPulse include:

* Collecting data continuously over multiple days
* Comparing trends across different dates
* Adding more categories
* Using NLP for automatic topic classification
* Creating interactive visualizations with Plotly
* Building an interactive dashboard using Power BI or Streamlit
* Applying machine learning to predict story engagement

---

## 👩‍💻 Author

**Poompavai V**

This project was created as part of my learning journey in **Python, Data Analytics, and AI/ML**.
