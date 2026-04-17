# **User Segmentation for Rewards Program**

## **Overview**

This project focuses on identifying users most likely to respond to a rewards program invitation by segmenting them based on behavioral patterns and aligning targeted incentives (perks) to each group.

The goal is not to increase general activity, but to improve rewards program adoption through data-driven personalization.

---

## **Project Structure**

.  
├── notebooks/  
│   ├── 1\_iteration-TravelTide\_MasteryProject\_AdrianMRizo.ipynb (first attempt)  
│   └── 2\_iteration-TravelTide\_MasteryProject\_AdrianMRizo.ipynb (final segmentation)  
│   └── Adrian Travel\_Tide \- Mastery\_Project.ipynb (entire project)  
│  
├── sql/  
│   └── booking\_rate.sql  
│   └── cumulative-revenue-per-sessions.sql  
│   └── sessions\_per\_user.sql  
│   └── summary-cut-off-criteria.sql  
│   └── user\_features\_v02.sql (used for the final segmentation)  
│   └── user\_features.sql  
│  
├── csv-src/  
│   └── raw datasets (sessions, flights, hotels, users)  
│  
├── csv-result/  
│   ├── user\_segments.csv  
│   ├── high\_value.csv  
│   ├── no\_purchase.csv  
│   ├── trips\_no\_revenue.csv  
│   ├── premium\_long\_haul.csv  
│   ├── high\_friction\_family.csv  
│   └── low\_activity\_leisure.csv  
│  
├── summary/  
│   ├── TravelTide-Executive Summary.pdf  
│   └── TravelTide-Detailed-Report.pdf  
│  
└── README.md

## **Methodology**

### **1\. Data Preparation**

* Built a trip-level dataset combining sessions, flights, hotels, and users  
* Removed inconsistent records (e.g., negative durations, invalid timestamps)  
* Aggregated data into a user-level dataset

---

### **2\. Cohort Definition**

* Applied a cutoff at **sessions ≥ 5**  
* Captures \~25% of users and \~25% of cumulative revenue  
* Focuses analysis on the most relevant users

---

### **3\. Rule-Based Segmentation**

* **No Purchase Users** → sessions but no bookings  
* **Trips Without Revenue** → bookings with no revenue (cancellations)  
* **High Value Users** → top 5% by revenue

---

### **4\. Machine Learning Segmentation**

* Remaining users clustered using **KMeans \+ PCA**  
* Identified three behavioral segments:  
  * Premium Long-Haul Travelers  
  * High-Friction Family Travelers  
  * Low-Activity Leisure Travelers

---

## **Key Insights**

* User activity alone does not drive value  
* Conversion behavior and cancellation patterns are key differentiators  
* Different user groups respond to different types of incentives

---

## **Rewards Strategy (Per Segment)**

| Segment | Recommended Perk |
| ----- | ----- |
| No Purchase | Exclusive Discounts |
| Trips Without Revenue | No Cancellation Fees |
| High Value | Cashback / Rewards |
| Premium Long-Haul | Free Hotel Night (bundled) |
| High-Friction Family | Free Checked Bag |
| Low-Activity Leisure | Free Hotel Meal |

---

## **Notebooks**

* **eda\_segmentation\_v1.ipynb**  
  Initial exploration and segmentation approach (later refined)  
* **segmentation\_final.ipynb**  
  Final pipeline including data preparation, feature engineering, clustering, and export

---

## **Technologies Used**

* Python (Pandas, NumPy)  
* Scikit-learn (KMeans, PCA)  
* Matplotlib  
* SQL  
* Tableau (for visualization)

---

## **Outputs**

* Final user segmentation dataset (`user_segments.csv`)  
* Individual CSV files per segment  
* Executive summary and detailed report  
* Visualizations for presentation

## **Author**

Adrián Marroquín Rizo

