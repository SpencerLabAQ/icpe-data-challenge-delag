# Datasets for the ICPE 2024 Data Challenge track

Information about the track:
[https://icpe2024.spec.org/tracks-and-submissions/data-challenge-track](https://icpe2024.spec.org/tracks-and-submissions/data-challenge-track/)

The dataset is composed by 560 csv files that are pre-processed execution traces from two  microservices systems, namely [E-Shopper](https://github.com/SEALABQualityGroup/E-Shopper) and [Train-Ticket](https://github.com/FudanSELab/train-ticket).

The pre-processed traces are organized as tabular data available in the [data](data) folder. 
Each csv file refers to a specific scenario that involves particular performance anomalies that affect one or multiple Remote Procedure Calls (RPCs).
Each row of the csv file refers to a specific end-to-end request within the microservices system.
Each column reports the cumulative response time (in milliseconds) of particular RPC within the end-to-end request. It is cumulative because if the same RPC is invoked multiple times within a request, the response time of each invocation is summed up.
The `Latency` column reports the end-to-end response time of each request, i.e., the response time of the root RPC.
An additional column (`anomaly`) specifies whether the request is affected by a performance issue or not. `0` indicates no anomalies in the request, while values ≥ `1` indicates the presence of a  performance issue.
Each scenario involves two different types of performance issue (namely, `1` and `2`).
Each type of performance issue affect a distict set of RPCs.
For a detailed exaplanation of the dataset generation process refers to Section X of [(Traini and Cortellessa, 2023)](https://doi.org/10.1109/TSE.2023.3266041).
The csv files reported in the [data](data) folder refers to the data used in the context of RQ1, RQ2, and RQ3.


Questions about the dataset can be asked by opening issues on this repository, or by sending an e-mail to tbd@easychair.org.

## Usage example

The Jupyter notebooks [Example-Supervised.ipynb](Example-Supervised.ipynb) and [Example-Unsupervised.ipynb](Example-Supervised.ipynb) report explanatory examples of dataset usage, involving the adoption of unsupervised and supervised machine learning models, respectively. The notebooks execution requires `pandas`, `scikit-learn`, `seaborn` and `notebook`:
```
python3 -m venv .env
source .env/bin/activate
pip install -r requirements.txt
```

---

The dataset was originally created for the paper:

L. Traini and V. Cortellessa, ***DeLag: Using Multi-Objective Optimization to Enhance the Detection of Latency Degradation Patterns in Service-Based Systems***, in IEEE Transactions on Software Engineering, vol. 49, no. 6, pp. 3554-3580, 1 June 2023, [DOI: 10.1109/TSE.2023.3266041](https://doi.org/10.1109/TSE.2023.3266041).
