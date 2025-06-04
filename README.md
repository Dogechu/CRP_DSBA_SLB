# SLB Corporate Project 

## 1. Project Context

This repository is developed in the context of the corporate Data Science for Business Analytics (DSBA) project with SLB.  
The project's goal is to automate the detection of geological formation change points (markers) from well log data, replacing the traditional manual geological interpretation process. Two modeling approaches are implemented:
- A Graph Neural Network (GNN)-based model for spatio-temporal classification.
- A Transformer-based model integrated with graph learning for direct marker prediction.

This work contributes to improved speed, scalability, and consistency in subsurface reservoir characterization—an essential task in industries like petroleum extraction, geothermal energy, and carbon capture.

---

## 2. Tree (Structure of the Repo)


---

## 3. Dependencies and Environment

Each model folder contains its own environment specification to ensure compatibility and reproducibility.

Before running any model notebooks or scripts, **you must first install the required dependencies**. Navigate to the specific model folder in your terminal and execute:

```bash
pip install -r requirements.txt ```



In addition, each folder also includes a pyproject.toml file configured for use with Poetry. This file defines:

- the build system (poetry)

- project metadata (name, version, authors, etc.)

- all required dependencies

To set up the environment using Poetry instead, run:

```bash
poetry install ```

---

## 4. Explanation of Each Model

### `model_gnn/` – Graph Neural Network Approach
This approach formulates the marker detection as a node classification task:
- Each well is modeled as a node with features derived from log sequences.
- Edges encode spatial proximity or geological similarity between wells.
- GNNs such as GCN, GraphSAGE, or GAT are applied to learn representations capturing both spatial and temporal dependencies.
- Goal: classify whether a formation change (marker) occurs at a given depth in each well.

###  `model_transformer/` – Transformer with Graph Context
This model integrates temporal modeling and graph structure:
- Input: static and dynamic features for each well, including Gamma Ray (GR) sequences near potential markers.
- Architecture: encoder-decoder Transformer enriched with graph-aware embeddings.
- Each graph is constructed per marker type, where wells are nodes.
- Goal: directly predict the marker depth for each well by capturing inter-well relationships and sequential patterns.

---

