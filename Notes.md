## Step 1 : Get comfortable with basics.

To get started,We need some basics. Below I share quick resources to get upto speed. But feel free to learn these from anywhere.

1. Basic idea of Neural networks
2. [Attention Mechanism](http://peterbloem.nl/blog/transformers)
3. [Modeling graphs with neural networks.](https://www.youtube.com/watch?v=zCEYiCxrL_0)
4. Read this [GAN Paper](https://arxiv.org/abs/1710.10903). This accompanying [video](https://www.youtube.com/watch?v=uFLeKkXWq2c&list=PLBoQnSflObckArGNhOcNg7lQG_f0ZlHF5)  might be helpful.
5. MF(matrix factorization) based techniques for Recommender systems.

Above ideas form the basis for the application of GNN'S to recommender systems. It is almost obvious how to adapt MF based techniques to make use of graph structure for a typical `user-rating` type dataset.
If you want more(not needed) and decided to go down the rabbit hole, here's an informal survey of the [field](https://gordicaleksa.medium.com/how-to-get-started-with-graph-machine-learning-afa53f6f963a).


## Step 2: Additional Study.(Not mandatory)

Resources:
- [For a Code first approach](https://github.com/gordicaleksa/pytorch-GAT)
- [A 150 page book on Graph representation learning.](https://www.cs.mcgill.ca/~wlh/grl_book/)

Since the area of Graph Neural Networks is relatively new for us, here I'm adding my notes on the same as I'm learning the subject.

Source 1: Petar Veličković's talk on [`Theoretical Foundations of Graph Neural Networks`](https://www.youtube.com/watch?v=uF53xsT7mjc)
And here's the [full-slide-deck](https://petar-v.com/talks/GNN-Wednesday.pdf)


Some Notable applications in the wild:

a. New compounds were discovered to treat symptoms.(Stokes et al,cell'20)
![g1](https://user-images.githubusercontent.com/21222766/142782896-fd219bd2-bf54-46e7-a0f2-fbba011bda62.png)

![g2](https://user-images.githubusercontent.com/21222766/142782905-38c2b8dd-1f52-4b6a-a3d1-b39c4a2571e3.png)

![g3](https://user-images.githubusercontent.com/21222766/142782926-7697553e-ca1c-4857-aa25-2239d03416d2.png)

b. Transportation networks : Recently google maps incorporated this to predict ETA.
![g4](https://user-images.githubusercontent.com/21222766/142783003-36e06c76-4aff-4b4e-9622-fb8dc54ae4f5.png)


GNN'S From First Principles:

Basics:
- Graphs are nothing but collection of sets G(V,E).
- All the connection structure is encoded in how we segregate given`v` nodes into `sets`- Adjacency list representation. And yes,we can have edge weights to too.

What are symmetries and invariances should GNN preserve ? For example CNN'S encode - `locality`(pixels close to each other are more important) and `translational invariance`(patterns are interesting no matter where they occur).

Some thoughts:
a. Nodes of a graph are not assumed to be in any order.(or there are multiple ways to draw the same graph or isomorphisms.) - How to enforce this ?

Permutation Invariance
![g6](https://user-images.githubusercontent.com/21222766/142783381-f1b3f434-f969-4c6f-9451-1f3a864be215.png)

![g7](https://user-images.githubusercontent.com/21222766/142783404-64e6370d-a1b1-4d1a-b816-18c141668098.png)

Note: Simple functions like sum,average,max are permutation invariant.
![g9](https://user-images.githubusercontent.com/21222766/142783734-7d91a2e6-ef1e-4eed-95ae-f0d530751069.png)

Learning on graphs
![g10](https://user-images.githubusercontent.com/21222766/142783861-c082ebda-753e-4407-9631-1ed079734c30.png)

![g12](https://user-images.githubusercontent.com/21222766/142783874-affd3f0f-96ff-4e49-b7cb-9556fc446f80.png)

So here's the recipe:

![g13](https://user-images.githubusercontent.com/21222766/142783960-7352deda-3254-4ea8-91f7-7846ad39febf.png)

 ![g14](https://user-images.githubusercontent.com/21222766/142784005-a821ad5f-fe09-45d1-802d-16dfa21bd710.png)

Layers
![g15](https://user-images.githubusercontent.com/21222766/142784071-2455142f-a484-412a-a9c3-008cbdf6ee8e.png)

For full details refer the [slide-deck.](https://petar-v.com/talks/GNN-Wednesday.pdf).

I stopped understading the detour section where he talks about lapacian matrices. Understanding after first 30/40 min mark is hard. Largely he talks about symmeries(specifically studied in abstract mathematics) and it's relation to GNN'S.

Some exciting applications:

Algorithmic reasoning, Combinatorial optimization, particle physics(yes,they study symmetries), Computational chemistry.

For dynamic graphs

Temporal graph ATTENTION network AND Temporal graph network - from twitter.

Can we pretrain in GNN'S ?
Yes,already used in industry. Example use GNN to bootstrap using unsupervised/self-supervised losses. Amazon put out [P-companion paper recently](https://assets.amazon.science/d5/16/3f7809974a899a11bacdadefdf24/p-companion-a-principled-framework-for-diversified-complementary-product-recommendation.pdf)
to bootsrap and then use an MLP in production. Another paper - `Bootstrap representation learning`

