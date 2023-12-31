# Definition of Efficiency

Both Training and inference efficiency are counted as model latency

**Training efficiency** 
- How long does the model take to train?
- How many devices are needed for the training? 
- Can the model fit in memory?
- How much data would the model need to achieve the desired performance on the given task that the model is solving

**Inference efficiency**
- How big is the model
- How large is prediction latency 
- What is the Peak Ram consumption


Two equally performing Models could be seperated by the latency.

## Pareto Optimality
When working within constraints often a goal is to minimize, for example latency while maximizing accuracy. While these to metrics opose each other, some models will still be able to achieve higher accuracy without trading latency. If we cannot get a better quality while holding the latency constant, or we cannot get better latency while holding quality constant this is called a **pareto optimal model**. The set off all pareto optimal solutions is called the **pareto frontier**

# Increasing Efficiency
Work in Efficient Deep Learning can rufly be categorized into 4 categories

## [[Compression Techniques]]
Compression Techniques attempt to optimize Network architecture. This is typically done by compressing layers, while trading off some performance.

### Quantization
One Popular technique for instance is Quantization. This is the Practice of reducing weight precision, for Example from a 32-bit float to a 8 bit int. This reduces model size by 2-8x and speeds up inference

### Pruning
During Pruning weights that are not important to the networks quality are removed. This involves many criteria that have to be met in order to safely conclude during training without majorly impacting training time.

## [[Learning Techniques]]
Learning techniques are techniques to improve quality metrics and is applied during training. This is done without changing model size.

### Distillation 
During Distillation a smaller model, also called the student, learns from a larger model, the teacher. The larger model is used to generate soft labels on the training data, and the student model learns to copy both the ground-truth labels as well as the soft labels generated by the teacher model. This makes the regression simpler since the labels are not as hard.

### Data Augmentation
This Method increases the amount of trainable data by augmenting it. For example during image classification an image of a dog stays an image of a dog even when the dog image has been rotated. This forces a Model to create a more general encoding of the data.

## [[Automation]]
Automation techniques automate tedious tuning but also require significant amounts of compute.

### Hyper Param Optimization
When Hyper Parameters are selected by the sweeper, multiple techniques can be used to avoid large amounts of wasted compute. An example would be the Bayesian Optimization. 

### Neural Architecture Search
Neural Architecture Search is an extension of HPO as it optimizes model structure and can find efficient architectures for a given Problem.

## [[Efficient Model Architecture]]
Efficient Model architectures form the crux of Efficient Deep Learning. These are fundamental Blocks that where designed from scratch for example Convolutional Layers. 
