# Project-cs512


## Objective

Understand and model graph data to enable high-level applications like recommender systems, predict properties of novel drugs etc. This certainly involves learning. Explore the area of `Geometric Deep Learning` and produce a practical application.

## Abstract

Many real world scenarios can be modeled as `Graphs`. We aim to explore the use of `Deep Learning` over `Graphs`. These ideas are still in their nascent phase but have already been successfully employed at scale for various realworld applicatios like - [Google Maps](https://deepmind.com/blog/article/traffic-prediction-with-advanced-graph-neural-networks) and [Discovery of novel drugs](https://pubmed.ncbi.nlm.nih.gov/32084340/). We aim to use these techniques commonly referred as `Graph Neural Networks` for recommenter systems. Matrix Factorization based techniques are commonly used for recommender systems. As a concrete example consider the dataset of `user-item` ratings. Here user corresponsds to the users of the platform say `NetFlix` and the `items` corresponds to the movies on their platform. Here, we aim to formulate this as a Graph structure learning problem, under the `bipartite graph` connecting the users to the corresponding items. To enable learning - `predict the rating from the users for the unseen items`, We will want to use `Graph Neural Networks`. We will take popular datasets for recommender systems  and benchmark against conventional techniques. 


