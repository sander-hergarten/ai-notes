# Overview
Compression Techniques reduce the ammount of trainable parameters. Unfortunately this aproach has two drawbacks:
1. It is hard to determine removable parameters
2. Applications of Compression techniques dont generalize well as they are problem specific


# Quantization
Quantization is the process of converting high precision continuos values into low precision discrete values. 

assuming a floating point is to be transformed to within $2^b$  and the floating point number is within a set range. Quantization would be described by 
$$x_q = min\left(\left \lfloor \frac{x - x_{min}}{s}\right \rfloor ,\ 2^{b-1}\right)$$
$$s = \frac{x_{max}-x_{min}}{2^b}$$
## Dequantization
During Dequantization it is not possible to recover 100% of the original data since the floor operation is not reversable. Excluding that and solving for x we get:
$$x = x_q*s+x_{min}$$

## Quantization in Deep Learning
Most of a models size comes from the weights in its layers and as such, most of the latency comes from calculating the activations. Reducing the precision of the weights can provide two benifits:
1. lower model size 
2. lower inference latency

One Basic neural network operation is:
$$f(X; W, b)=\sigma(XW+b)$$
Here X, W  and b are tensors to denote inputs, weights, and bias respectively. Assuming the shapes to be:
$$X^{batchsize,\ D_1},\ W^{D_1, D_2},\ b^{D_2} $$
The activation operation results in:
$$(XW+b)^{batchsize,\ 1}$$
Since the most expensive operation is $XW$ due to the size of $W$ this is the most logical step to apply Quantization. 

### Weight Quantization 
Quantizing the weights of a model can decrease the model size by a factor of 2-8x. this operation requires the weights to be quantized and then dequantized before being used in standard activations. 

Since this is increases the latency rather than decreasing it a further aproach to avoid such problems is

### Activation Quantization
Quantized activations require all arithmetic to be done with the fixed-point quantized representations in order to save the dequantiztion cost.
