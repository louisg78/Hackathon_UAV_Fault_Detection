# 🛠️ Track UAV: Fault Detection and Preventive Maintenance of Drones

## 📖 Project Overview
Drones are increasingly used in logistics, surveillance, infrastructure inspection, and rescue operations — raising critical concerns about reliability and safety.  
**Drone failures** can lead to **loss of equipment**, **service interruptions**, or even **risks to human life**.  

This project focuses on developing a **predictive maintenance and early fault detection** system using UAV sensor data to:
- Detect the presence of faults during drone operations.
- Identify the probable origin of detected faults.
- Assess the severity of each fault to guide maintenance decisions.

The ultimate goal is to **enhance availability, safety, and lifespan** of drones by implementing a data-driven **anomaly detection** approach.

---

## 🎯 Objectives
1. **Fault Detection:** Identify whether a drone is operating under normal or faulty conditions.  
2. **Fault Origin Identification:** Determine which subsystem or component (e.g., propeller, motor) is responsible for the detected fault.  
3. **Severity Assessment:** Evaluate the criticality of the detected anomaly to prioritize maintenance actions.

---

## 📊 Dataset
**Source:** [DronePropA: Motion Trajectories Dataset for Commercial Drones with Defective Propellers](https://zenodo.org/record/7708214)

**Format:** `.mat` (MATLAB files) – easily readable in Python using `scipy.io.loadmat`.

**Description:**  
This dataset contains real operational data recorded under **controlled indoor conditions** from drones in both **healthy** and **faulty** states.  
Each file includes sensor readings from the drone and its controller over several trajectories.

**Dataset Volume:**  
- 130 files across 4 main categories (sufficient to use a subset).  
- States include:  
  - `F0` → No fault  
  - `F1–F4` → Fault types (defective propellers, etc.)  

---

## 🧠 Methodology
1. **Data Preprocessing**
   - Convert MATLAB `.mat` files to DataFrames  
   - Handle missing data and normalization  
   - Label drone states (normal/faulty)

2. **Feature Extraction**
   - Sensor fusion and feature computation (e.g., acceleration, angular velocity, controller inputs)  
   - Dimensionality reduction (PCA or autoencoders)

3. **Fault Detection & Classification**
   - Machine Learning: Random Forest, SVM, Gradient Boosting  
   - Deep Learning: LSTM or CNN for time-series patterns  
   - Unsupervised models: Isolation Forest, Autoencoder-based anomaly detection

4. **Evaluation**
   - Metrics: Accuracy, Precision, Recall, F1-score, ROC-AUC  
   - Visualization: Fault occurrence timeline, confusion matrix, sensor signal plots

5. **Predictive Maintenance Insights**
   - Severity mapping  
   - Fault trend analysis  
   - Maintenance action recommendations  

---