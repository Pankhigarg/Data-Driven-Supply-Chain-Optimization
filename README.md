# Data-Driven-Supply-Chain-Optimization
Developed a data-driven Supply Chain Optimization Model that minimizes freight costs by optimally assigning sellers to customer orders using Linear Programming (LP) with the Optimizer in Python

Description:
This project optimizes supply chain logistics by selecting the best sellers for fulfilling customer orders.
It uses Linear Programming (LP) with Gurobi Solver in Python to minimize freight costs.

📂 Project Structure
bash
Copy
Edit
📦 Supply-Chain-Optimization/

│── 📂 src/                         # Source code directory

│   ├── 📄 optimization_model.py     # Main optimization script

│   ├── 📂 data2/                    # Folder for cleaned dataset

│   │   ├── 📄 cleaned_supply_chain_data.csv  # Large dataset (Google Drive link)

│   ├── 📂 utils/                     # Helper functions

│   │   ├── 📄 data_preprocessing.py  # Data cleaning script

│   │   ├── 📄 model_helper.py        # Functions for optimization model

│── 📂 results/                      # Stores optimization results

│   ├── 📄 optimized_routes.csv      # Output CSV file

│── 📄 README.md                     # Project documentation

│── 📄 requirements.txt               # Required dependencies

│── 📄 .gitignore                     # Ignores large/unwanted files
📊 Data Collection: Scraping Amazon Data
🔍 1. Getting Raw Data from Amazon
The dataset includes order details, seller IDs, and freight costs from Amazon’s supply chain.
Since Amazon doesn’t provide open access to its logistics data, we used Olist E-Commerce Dataset as a reference.

📥 Download the raw dataset here:
🔗 Olist Dataset on Kaggle

2️⃣ Preprocessing the Data
Before optimization, we clean the dataset to:
✅ Remove missing values
✅ Convert seller IDs & order IDs to numeric format
✅ Extract relevant columns: seller_id, order_id, freight_value

🛠 Running Data Preprocessing
sh
Copy
Edit
python src/utils/data_preprocessing.py
This will create a cleaned dataset inside src/data2/cleaned_supply_chain_data.csv.

🧠 Optimization Model: How It Works
We use Linear Programming (LP) to minimize freight costs while ensuring every order is fulfilled.

⚙️ Objective Function
\text{Minimize} \sum (x_{i,j} \times \text{freight_value})
Where:

𝑥
𝑖
,
𝑗
x 
i,j
​
  is the number of units shipped from seller 
𝑖
i to order 
𝑗
j
freight_value is the shipping cost
📌 Constraints
✔️ Each order is fulfilled by at least one seller
✔️ A seller cannot exceed its shipping capacity

🚀 Running the Optimization Model
🔹 Step 1: Install Dependencies
First, install the required libraries:

sh
Copy
Edit
pip install -r requirements.txt
🔹 Step 2: Run the Optimization Model

sh
Copy
Edit
python src/optimization_model.py
🔹 Step 3: View Results The optimized shipping routes will be saved in:
