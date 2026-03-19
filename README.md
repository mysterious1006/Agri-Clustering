🌾 Agricultural Region Clustering & Water-Use Analysis

Unsupervised machine learning to cluster agricultural regions by rainfall, irrigation, and crop yield — surfacing actionable insights on water dependency and irrigation patterns.


📌 Overview
Water scarcity and inefficient irrigation are critical challenges in modern agriculture. This project applies unsupervised machine learning to group agricultural regions with similar rainfall, irrigation usage, and crop yield characteristics. By identifying natural clusters in the data, the analysis reveals which regions are heavily dependent on irrigation, which are rain-fed, and how water resources correlate with productivity.

🧠 Key Features

K-Means Clustering on multi-dimensional agricultural dataset
PCA (Principal Component Analysis) for dimensionality reduction and 2D/3D cluster visualisation
Feature Engineering — normalization, derived ratios, and outlier handling
StandardScaler for data standardisation before modeling
Visualization of clusters using Matplotlib and Seaborn
Actionable insights on irrigation dependency and rainfall patterns per cluster


🛠️ Tech Stack
CategoryLibrariesLanguagePython 3.xML / ClusteringScikit-learn (KMeans, PCA, StandardScaler)Data HandlingPandas, NumPyVisualizationMatplotlib, Seaborn

📁 Project Structure
agricultural-clustering/
│
├── data/
│   └── agricultural_data.csv       # Raw dataset
│
├── notebooks/
│   └── analysis.ipynb              # Full EDA + modeling notebook
│
├── src/
│   ├── preprocessing.py            # Data cleaning & feature engineering
│   ├── clustering.py               # K-Means model training & evaluation
│   ├── pca.py                      # Dimensionality reduction
│   └── visualize.py                # Cluster plots & analysis charts
│
├── outputs/
│   └── cluster_plots/              # Generated visualizations
│
├── requirements.txt
└── README.md

⚙️ Setup & Installation
1. Clone the repository
bashgit clone https://github.com/mysterious1006/Agri-Clustering.git
cd agricultural-clustering
2. Create a virtual environment (recommended)
bashpython -m venv venv
source venv/bin/activate        # macOS/Linux
venv\Scripts\activate           # Windows
3. Install dependencies
bashpip install -r requirements.txt
4. Run the notebook
bashjupyter notebook notebooks/analysis.ipynb

🔄 Workflow
Raw Data
   │
   ▼
Data Cleaning & Feature Engineering
(Pandas · StandardScaler)
   │
   ▼
Dimensionality Reduction
(PCA → 2 components)
   │
   ▼
K-Means Clustering
(Optimal k via Elbow Method)
   │
   ▼
Cluster Analysis & Visualisation
(Matplotlib · Seaborn)
   │
   ▼
Insights on Water Dependency

📊 Results & Insights
The model identified distinct agricultural clusters, each with a characteristic water-use profile:
ClusterProfileIrrigation DependencyRainfall0High-yield, irrigatedVery HighLow1Rain-fed, moderate yieldLowHigh2Transitional regionsMediumMedium3Low-yield, water-scarceHighVery Low

Exact cluster counts and labels may vary depending on dataset and chosen k.

Key findings:

Regions in Cluster 0 are highly productive but critically dependent on artificial irrigation — vulnerable to water shortages.
Cluster 1 regions are sustainably rain-fed and represent low-risk agricultural zones.
PCA explained ~85% of variance using 2 principal components, confirming strong underlying structure.


📈 Sample Visualizations
PCA Cluster PlotIrrigation vs RainfallElbow CurveCluster separation in 2D PCA spaceScatter showing water-use patternsOptimal k selection

🧪 Model Details
Preprocessing

Handled missing values via median imputation
Removed outliers using IQR-based filtering
Standardised all features using StandardScaler to ensure equal weight in distance calculations

Dimensionality Reduction

Applied PCA to reduce high-dimensional feature space to 2 components for visualisation
Retained components explaining cumulative variance ≥ 85%

Clustering

Used the Elbow Method (inertia vs. k) to determine optimal number of clusters
Final model: KMeans(n_clusters=4, init='k-means++', random_state=42)
Evaluated cluster quality using Silhouette Score


📦 Requirements
pandas>=1.5.0
numpy>=1.23.0
scikit-learn>=1.2.0
matplotlib>=3.6.0
seaborn>=0.12.0
jupyter>=1.0.0
Install all at once:
bashpip install -r requirements.txt

🚀 Future Improvements

 Incorporate temporal data to track year-over-year irrigation trends
 Test alternative clustering algorithms (DBSCAN, Agglomerative)
 Add a Streamlit dashboard for interactive cluster exploration
 Integrate geospatial mapping with GeoPandas / Folium
 Expand dataset to include soil type and temperature features


👨‍💻 Author
Shorya Pratap Singh
B.Tech Computer Science & Engineering 
