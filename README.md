
# ChaosNet Seismic Classification

## Overview
This semester project, developed during my Integrated MSc in Computer Science (AI & Data Science) at CUSAT, implements a ChaosNet model for classifying seismic waveform data (quake vs. noise) from the IRIS database. Based on the paper ["A Novel Chaos Theory Inspired Neuronal Architecture"](https://ieeexplore.ieee.org/abstract/document/8978360) by Harikrishnan and Nagaraj (2019), it extends prior experiments on the Iris flower dataset to high-dimensional seismic traces, achieving 80% accuracy on a 10-sample test set.

## Dataset
The dataset comprises 150 samples (75 quake, 75 noise) fetched from IRIS (network IU, stations ANMO, COLA, HRV, KBS, MAJO, TATO, POHA) for 2020, each with 2400 samples at 40 Hz. Quake and noise data were collected from 1-minute windows, normalized, and saved as `iris_subset_150.npz`.

## Implementation
- **Model**: ChaosNet with Topological Transitivity (TT) for feature extraction, using Generalized Luröth Series (GLS) map and Euclidean distance classification.
- **Tech Stack**: Python, NumPy, Pandas, Obspy, Scikit-learn.
- **Key Features**:
  - Fetches and preprocesses seismic waveforms from IRIS.
  - Tunes hyperparameters (`q`, `b`, `epsilon`) to handle 2400D traces.
  - Achieves 80% accuracy on a 10-sample test set (`q=0.5, b=0.4, epsilon=0.05`).

## Results
- Initial Iris flower dataset: 94.81% accuracy (5 samples/class).
- Seismic data: 80% accuracy on a 10-sample test set after tuning, with potential for 100% on smaller subsets (`q=0.7, b=0.5, epsilon=0.1`). High-dimensional seismic data posed challenges compared to 4D Iris data.

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/ssutharya/ChaosNet-Seismic.git
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Run the notebook:
   ```bash
   jupyter notebook Earthquake.ipynb
   ```
   - Alternatively, open `Earthquake.ipynb` in Google Colab.
   - Follow steps to fetch data, train, and evaluate.

## Usage
- **Data**: Load `iris_subset_150.npz` or fetch new IRIS data using the notebook.
- **Training**: Run cells to preprocess, tune ChaosNet parameters, and train.
- **Evaluation**: View accuracy metrics for quake/noise classification.

## Future Work
- Improve accuracy on larger test sets (e.g., 5/140 split).
- Develop anomaly detection for real-time seismic streams.
- Test with extended IRIS datasets or other seismic sources.

## Citation
- Harikrishnan, N. B., & Nagaraj, N. (2019). A Novel Chaos Theory Inspired Neuronal Architecture. *2019 Global Conference for Advancement in Technology (GCAT)*, Bangalore, India, 1–6. DOI:10.1109/GCAT47503.2019.8978360.

## Acknowledgments
- Work on Soft Computing and the ChaosNet paper.
- Thanks to IRIS for providing open seismic data.

Explore or contribute to enhance seismic classification!
