# Datasets for the ICPE 2024 Data Challenge track

Information about the track:
[https://icpe2024.spec.org/tracks-and-submissions/data-challenge-track](https://icpe2024.spec.org/tracks-and-submissions/data-challenge-track/)

The dataset comprises 560 csv files with pre-processed execution traces from two open-source microservices systems, namely [Train-Ticket](https://github.com/FudanSELab/train-ticket) and [E-Shopper](https://github.com/SEALABQualityGroup/E-Shopper).

T All trace data are organized in tabular format within the [data](data) folder. 
Each CSV corresponds to a unique scenario involving specific performance anomalies affecting one or more Remote Procedure Calls (RPCs).
Rows in the CSV represent individual end-to-end requests.
Columns show the cumulative response time (in milliseconds) for specific RPCs within those requests. If an RPC is invoked multiple times within a request, response times from all invocations are summed.
The `Latency`` column provides the response time for the root RPC, reflecting the end-to-end request time.
The anomaly column indicates performance issue presence: `0` means no anomalies, while values ≥ `1` indicate the presence of a performance issue.
Each scenario involves two different types of performance issues (namely, `1` and `2`).
Each type of performance issue affect a distict set of RPCs.
For a detailed exaplanation of the dataset creation process, refer to Section X of [(Traini and Cortellessa, 2023)](https://doi.org/10.1109/TSE.2023.3266041).
The csv files reported in the [data](data) folder are utilized in the context of RQ1, RQ2, and RQ3.

Questions about the dataset can be asked by opening issues on this repository, or by sending an e-mail to icpe2024-data@easychair.org.

## Usage example

The Jupyter notebooks [Example-Supervised.ipynb](Example-Supervised.ipynb) and [Example-Unsupervised.ipynb](Example-Supervised.ipynb) report explanatory examples of dataset usage, involving supervised and unsupervised machine learning models, respectively. The notebooks execution requires `pandas`, `scikit-learn`, `seaborn` and `notebook`:
```
python3 -m venv .env
source .env/bin/activate
pip install -r requirements.txt
```

---

The dataset was originally created for the paper:

L. Traini and V. Cortellessa, ***DeLag: Using Multi-Objective Optimization to Enhance the Detection of Latency Degradation Patterns in Service-Based Systems***, in IEEE Transactions on Software Engineering, vol. 49, no. 6, pp. 3554-3580, 1 June 2023, [DOI: 10.1109/TSE.2023.3266041](https://doi.org/10.1109/TSE.2023.3266041).
