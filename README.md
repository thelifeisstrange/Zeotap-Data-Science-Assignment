# Lookalike Model: Customer Recommender System
**Identify similar customers to optimize marketing and outreach.**
*A vector-based recommendation engine that identifies the top three "lookalike" customers for any given user based on their purchase history and demographic profile.*

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)
![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white)

---

## 📖 Overview

The **Lookalike Model** is a data science solution designed to find high-value potential customers by identifying existing users with similar behavioral and profile traits. By analyzing transaction values, purchase frequency, product category preferences, and regional data, the model computes a similarity score to rank the most relevant "lookalikes" for the business.

## ✨ Core Features

*   **📊 Multi-Source Data Integration:** Merges raw datasets (Customers, Products, and Transactions) to build a unified 360-degree view of the customer.
*   **🛠️ Feature Engineering:** Aggregates granular transaction data into high-level metrics including:
    *   Total and Average Spending.
    *   Purchase Frequency (Transaction Count).
    *   Preferred Product Category (Mode of purchase).
    *   Sign-up Recency (To-Ordinal date conversion).
*   **🔍 Cosine Similarity Engine:** Utilizes Scikit-Learn to build a pairwise similarity matrix, treating each customer as a vector in a high-dimensional space.
*   **📜 Automated Recommendations:** Generates a mapped list of the top 3 lookalikes for the first 20 customers, including precise similarity scores.

## 🗂️ Project Structure

The project follows a linear Vector Space Model architecture, transforming raw business data into a numerical matrix for distance calculation.

```text
thelifeisstrange-lookalike/
├── Customers.csv               # Input: Customer profile information (Region, SignupDate)
├── Products.csv                # Input: Product details (Category, Price)
├── Transactions.csv            # Input: Logs of all customer purchases
├── Lookalike.csv               # Output: Top 3 recommendations for C0001 - C0020
└── LookAlike_Model.ipynb       # Core Logic: Data prep, similarity modeling, & execution
```

## 🚀 Installation & Setup

### Prerequisites
* Python 3.8+
* Jupyter Notebook or Google Colab

### Step-by-Step Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/lookalike-model.git
   cd lookalike-model
   ```

2. **Install required libraries**
   ```bash
   pip install pandas scikit-learn numpy
   ```

3. **Run the model**
   Open the Jupyter Notebook and execute all cells:
   ```bash
   jupyter notebook Yogesh_Kulkarni_LookAlike.ipynb
   ```

## 💻 Usage

The model identifies similarity based on numerical and encoded categorical values. To use the model for a specific customer:

1.  **Feature Vector:** The system converts a customer's behavior (e.g., spending \$3354, top category 'Electronics') into a vector.
2.  **Comparison:** It compares that vector against all other customers in the database.
3.  **Result:** It outputs the `CustomerID` and the `Similarity Score` (ranging from 0 to 1).

**Example Output (Lookalike.csv):**
| CustomerID | Cust1_Score | Cust2_Score | Cust3_Score |
| :--- | :--- | :--- | :--- |
| **C0001** | ('C0137', 0.9999) | ('C0152', 0.9999) | ('C0181', 0.9998) |

## 🛣️ Future Roadmap

1.  **⚖️ Weighted Features:** Currently, all features (spending vs. region) contribute equally to the score. Future iterations will allow weighting "Total Spending" more heavily than "Region."
2.  **🕒 RFM Integration:** Implement Recency, Frequency, and Monetary (RFM) analysis to better distinguish between loyal long-term customers and one-time high spenders.
3.  **🧠 Embedding-based Similarity:** Move beyond simple Cosine Similarity by using Deep Learning (Autoencoders) to create more nuanced customer embeddings.
