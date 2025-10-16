📘 Blockchain Network Topology Prediction using Graph Neural Networks (GNN)

🔹 Project Overview

This project demonstrates how Graph Neural Networks (GNNs) can be used to analyze and predict the evolution of blockchain network topology — that is, how nodes and connections (edges) in a blockchain network may change over time.

In a blockchain system, participants (miners, wallets, or smart contracts) interact through transactions forming a graph network.
Using GNNs, we can learn these interaction patterns and predict future links or structural changes (for example, which new nodes will likely connect or which existing edges may strengthen).

This web-based demo simulates such behavior visually using Graph Convolutional Network (GCN)-inspired link prediction logic.


---

🧠 Aim

To employ Graph Neural Networks for predicting and analyzing blockchain network topology evolution, i.e., how nodes and edges evolve over time.


---

📂 Dataset

Input: Blockchain transaction/network graph datasets
(Nodes = participants, Edges = transactions).

In this demo, the dataset can be uploaded as a JSON file or generated randomly.
Example JSON:

{
  "nodes": [{"id": "N1"}, {"id": "N2"}, {"id": "N3"}],
  "edges": [{"from": "N1", "to": "N2"}, {"from": "N2", "to": "N3"}]
}



---

⚙️ Methodology

1️⃣ Data Collection

Gather blockchain transaction data.

Each participant (address or node) is a node.

Each transaction between participants is an edge.


2️⃣ Graph Construction

Build an Adjacency Matrix (A) representing node connections.

Build a Feature Matrix (X) representing node properties (degree, role, transaction count, etc.).


3️⃣ Preprocessing

Normalize the adjacency matrix.

Split data into training, validation, and testing subsets.


4️⃣ Model Design (Graph Convolutional Network)

Use Graph Convolutional Layers:

Input Layer → Hidden Layer(s) → Output Layer


Learn graph embeddings from node features and connectivity.


5️⃣ Training

Train using loss functions like cross-entropy.

Use optimizers such as Adam or SGD.


6️⃣ Prediction

Predict future edges (link prediction) or node roles.

The demo uses a probabilistic + heuristic simulation to show likely new connections.


7️⃣ Evaluation

Measure results using metrics like:

Accuracy

Precision, Recall, F1-Score

AUC (Area Under ROC Curve)




---

💡 Algorithm Used

Graph Convolutional Network (GCN)
A GCN extends neural networks to operate directly on graph-structured data.

Simplified Forward Pass:

H^{(l+1)} = \sigma(\hat{A}H^{(l)}W^{(l)})

 = Node embeddings at layer l

 = Normalized adjacency matrix

 = Learnable weights

 = Activation function (ReLU)


This process aggregates information from each node’s neighbors to learn network patterns.


---

🧩 Technologies Used

Component	Technology

Frontend	HTML5, CSS3, JavaScript
Visualization	HTML Canvas API
Model Logic	Simulated GCN computation in JavaScript
Dataset Format	JSON (Graph nodes and edges)
Exports	CSV / JSON (Predicted topology)



---

🚀 How It Works (Demo Explanation)

1. Open index.html in any browser.


2. Generate a random graph using buttons (Small / Medium / Large).


3. Click Run Prediction to simulate GNN-based link prediction.


4. The canvas shows:

Orange circles: existing nodes.

Blue lines: current blockchain connections.

Green dashed lines: predicted future links.



5. The right-hand table lists top predicted edges with scores.


6. You can export predictions as .json or .csv.




---

📊 Output Example

Before Prediction

A simple blockchain graph with nodes N1, N2, N3.

After Prediction

The system may predict a new link N1 → N3 with high probability.

#	From	To	Score

1	N1	N3	0.86
2	N2	N4	0.79
3	N5	N7	0.73


Simulated metrics:

New edges: 6  
Estimated accuracy: 0.72  
Estimated AUC: 0.77


---

📤 Export Options

Download JSON – predicted graph structure

Download CSV – node-edge list with prediction flags



---

🧩 Future Enhancements

1. Replace simulated predictions with a real GCN model (e.g., using PyTorch Geometric).


2. Integrate real blockchain datasets (Ethereum or Bitcoin transaction graphs).


3. Add dynamic time-evolution analysis for network growth.


4. Deploy a Flask/FastAPI backend for actual inference.




---

🧠 Key Learning Outcomes

How GNNs process graph-structured blockchain data.

How to visualize graph networks dynamically using JavaScript.

Basic principles of link prediction and graph embeddings.

Application of machine learning in decentralized network analysis.
