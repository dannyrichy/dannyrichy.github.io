---
layout: default
title: "CV"
---
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
<a href="assets/resume.pdf" download class="download-link">
  <i class="fa-regular fa-circle-down" style="color: #000;"></i> Download
</a>

## Education

#### M.Sc in Machine Learning  
<div style="display: flex; justify-content: space-between; font-size: small; font-style: italic;">
  <span>KTH Royal Institute of Technology, Stockholm, Sweden <a href="https://www.kth.se/en" target="_blank"><i class="fa-solid fa-square-up-right" style="color:#333; margin-left: 3px;"></i></a></span>
  <span>2021 – 2023</span>
</div>

<div style="display: flex; justify-content: space-between; font-size: small; font-style: italic; color:#808080">
  <span><emp>Highlighted coursework</emp>: Advanced Deep Learning, Advanced Machine Learning, Artificial Neural Network, Stochastic Differential Equations for ML</span>
</div>

#### B.Tech in Mechanical Engineering
<div style="display: flex; justify-content: space-between; font-size: small; font-style: italic;">
  <span>Indian Institute of Technology - Madras, Chennai, India <a href="https://www.iitm.ac.in/" target="_blank"><i class="fa-solid fa-square-up-right" style="color:#333; margin-left: 3px;"></i></a></span>
  <span>2014 – 2018</span>
</div>

<div style="display: flex; justify-content: space-between; font-size: small; font-style: italic; color:#808080">
  <span><emp>Highlighted coursework</emp>: Linear Algebra, Machine Learning, Data Structures and Algorithms, Multivariate Data Analysis</span>
</div>

---

## Work Experience

#### Research Visit (Internship)
<div style="display: flex; justify-content: space-between; font-size: small; font-style: italic;">
  <span>Inria Centre at Université Côte d’Azur, Nice, France</span>
  <span>Sep 2024 – Present</span>
</div>

<p style="text-align: justify;">Work on topics related to Green Federated Learning under the supervision of Prof. Dr. Giovanni Neglia</p>

#### Research Engineer
<div style="display: flex; justify-content: space-between; font-size: small; font-style: italic;">
  <span>Division of Geoinformatics, KTH, Stockholm, Sweden</span>
  <span>Jun 2023 – Jul 2023</span>
</div> 

<p style="text-align: justify;">Tweaked and expanded the transformer-based wildfire detection model trained on satellite images (VIIRS) to encompass new geographic regions.</p>

#### Teaching Assistant
<div style="display: flex; justify-content: space-between; font-size: small; font-style: italic;">
  <span>KTH, Stockholm, Sweden</span>
  <span>Nov 2021 – May 2023</span>
</div>

<p style="text-align: justify;">Assisted in tutorials, graded assignments, and prepared course materials for Advanced Machine Learning, Artificial Intelligence, and Search Engines courses</p>

#### Scania Student Intro Program
  <div style="display: flex; justify-content: space-between; font-size: small; font-style: italic;">
  <span>Scania AB, Stockholm, Sweden</span>
  <span>Jun 2022 – Nov 2023</span>
</div>

<p style="text-align: justify;">Selected for the Scania Student Intro Program, gaining insights into Scania’s operations, sustainability initiatives, and innovation strategies<br>
<strong>Thesis Worker</strong> Probed learnt representation of State-of-the-art Deep learning models for Time Series anomaly detection use-cases<br>
<strong>Summer Worker</strong> Developed an *MLP model* during the summer program to identify faulty components by leveraging diagnostic trouble codes (DTC)</p>

#### Data Scientist
<div style="display: flex; justify-content: space-between; font-size: small; font-style: italic;">
  <span>Gyan Data, Chennai, India</span>
  <span>Sep 2019 – Jun 2021</span>
</div>

<p style="text-align: justify;"><strong>Smart Pill Manufacturing - Pfizer</strong>: Utilized KNN to estimate APIs/Excipient properties for pills in development; developed Mean Feed Flow predictor using SVR; Implemented an IPython notebook-based and Tkinter tool<br>
<strong>HVAC Fault Detection system - VOLTAS</strong>: Developed Logistic Regression and Rule-based system; Detected change points using L1-trend filter; Designed and developed web interface using Flask to monitor industrial HVAC systems deployed across India</p>

#### Business Analytics Consultant
<div style="display: flex; justify-content: space-between; font-size: small; font-style: italic;">
  <span>Crayon Data, Chennai, India</span>
  <span>Jun 2018 – Sep 2019</span>
</div>

<p style="text-align: justify;">Implemented Customer demographic based clustering to extend recommendations increasing customer coverage to 100 % from 30 %; Developed tunable recommender engine for periodic and ad-hoc business opportunities. Utilized a combination of n-gram and Cologne phonetics algorithms for efficient entity resolution. Achieved an impressive reduction ratio of 7000:1. Utilized Apache Spark to improve the scalability of the recommender engine to process 7M customer transaction records, up from 300K</p>

---

## Projects

#### Unmasking Deep Learning for Time Series Anomaly Detection (M.Sc. Thesis)  
  Critically evaluated the need for deep learning models using *VAE* architectures to detect anomalies in time series data; brought out the need for better benchmark datasets. Investigated the effectiveness of the "point-adjusted" metric used by the research community; highlighted the need for a stable metric to help champion deep learning models. <a href="https://kth.diva-portal.org/smash/record.jsf?pid=diva2:1823999" target="_blank" style="color: #333; text-decoration: none;"><i class="fa-regular fa-file" style=" vertical-align: middle;"></i></a>

#### Shenanigans with Learnt Representations of Music Taggers  
  Inspected the quality of the GTZAN dataset (public dataset for music genre recognition) using learned representations from multiple deep-learning-based music taggers. Evaluated the clusterability of the learned representations using KNN and GMM for genre classification; Auditorily inspected the generalisability of these music taggers using out-of-distribution data like non-Western music. <a href="https://github.com/Adhithyan8/musical-embeddings" target="_blank" style="color: #333; text-decoration: none;"><i class="fab fa-github" style=" vertical-align: middle;"></i></a>

#### Git Bi-sect: Dissecting Git Re-basin Paper  
  Reproduced the "Git Re-basin" paper (Ainsworth et al.), verifying low loss barrier between deep learning models after removing permutation symmetries; conducted an in-depth analysis to explore the evolution of Linear Mode Connectivity as training progresses; discovered the importance of hyper-parameters on finding permutations; negated claims of methodology not working on MNIST. <a href="https://github.com/dannyrichy/git-bisect" target="_blank" style="color: #333; text-decoration: none;"><i class="fab fa-github" style=" vertical-align: middle;"></i></a>

#### Deep Learning Model Extraction Attack  
  Assessed model extraction attacks on VGG and ResNet models. Designed and implemented an algorithm to identify a core set; investigated the number of samples needed to extract the model. Executed privacy attacks on the extracted model to assess the vulnerability of the victim model. <a href="https://github.com/dannyrichy/dl-model-extraction" target="_blank" style="color: #333; text-decoration: none;"><i class="fab fa-github" style=" vertical-align: middle;"></i></a>

#### Network Representation Learning  
  Performed a comparative study of unsupervised network representation learning algorithms like [LINE](/notes/line-graph-ml.html), [NetMF](/notes/netmf.html), [Node2vec](/notes/node2vec.html), [Deepwalk](/notes.deepwalk.html), and [GraphSage](/notes/graphsage.html) for node classification and link prediction tasks. <a href="https://github.com/dannyrichy/graph-ml-project" target="_blank" style="color: #333; text-decoration: none;"><i class="fab fa-github" style=" vertical-align: middle;"></i></a>

#### Graphons: Efficient Graph Embeddings  
  Explored the effectiveness of Graphons (Random Graph Model) as graph embedding by comparing against Graph2Vec for graph downstream tasks. <a href="https://github.com/dannyrichy/graphon" target="_blank" style="color: #333; text-decoration: none;"><i class="fab fa-github" style=" vertical-align: middle;"></i></a>

---

## Skills

  Python, Java, Scala, TensorFlow, PyTorch, Keras, Apache Spark, Airflow, OpenMPI, SQL, AWS, GCP, Git, Slurm, OAR
