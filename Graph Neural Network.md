(https://distill.pub/2021/gnn-intro/)
A Graph Neural Network is a type of Neural Network that accepts a [[Graphs|graph]] as an input instead of classical data. It should be noted that many classical datatypes can also be transformed into a graph as described [[Data as Graphs|here]].

Problems for Graph Neural networks can be split into different categories.
## Graph-level Task
In a Graph-level task, the goal is to predict the property of an entire graph. This is analogous to image classification problems, where we want to associate a label to a n entire image.

## Node-level task
Node-level tasks are concerned predicting the identity or role of each node within a graph

A classic example of a node-level prediction problem is Zach's karate club where two rival groups have allegiance towards 'Mr Hi' or 'John H' . The nodes represent practitioners and the edges represent interactions between these members outside of karate. The prediction problem is to classify whether a given member becomes loyal to either Mr. HI or John H.

Following the image analogy, node-level prediction problems are analogous to image segmentation, where we are trying to label the role of each pixel in an image.

## Edge-level task
The remaining prediction problem in graphs is edge prediction.

One example of edge-level inference is in image scene understanding. Beyond identifying objects in an image, deep learning models can be used to predict the relationship between them. 

We can phrase this as an edge-level classification: given nodes that represent the objects in the image, we wish to predict which of these nodes share an edge or what the value of that edge is. If we wish to discover connections between entities, we could consider the graph fully connected and based on their predicted value prune edges to arrive at a sparse graph
![[Pasted image 20230626215044.png]]

describing the 