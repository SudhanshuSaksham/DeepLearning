# DeepLearningWeightInitializing

## Zero Initialization

As the name suggests, all the weights are assigned zero as the initial value is zero initialization. This kind of initialization is highly ineffective as neurons learn the same feature during each iteration. Rather, during any kind of constant initialization, the same issue happens to occur. Thus, constant initializations are not preferred.
```
from tensorflow.keras import layers
from tensorflow.keras import initializers
 
initializer = tf.keras.initializers.Zeros()
layer = tf.keras.layers.Dense(
  3, kernel_initializer=initializer)
```

## Random Initialization

In an attempt to overcome the shortcomings of Zero or Constant Initialization, random initialization assigns random values except for zeros as weights to neuron paths. However, assigning values randomly to the weights, problems such as Overfitting, Vanishing Gradient Problem, Exploding Gradient Problem might occur. 

Random Initialization can be of two kinds:

1. Random Normal
2. Random Uniform

Random Normal: The weights are initialized from values in a normal distribution.

w  ~  N(0,1)

Random Normal initialization can be implemented in Keras layers in Python as follows:
```
from tensorflow.keras import layers
from tensorflow.keras import initializers
 
initializer = tf.keras.initializers.RandomNormal(
  mean=0., stddev=1.)
layer = tf.keras.layers.Dense(3, kernel_initializer=initializer)
```
Random Uniform: The weights are initialized from values in a uniform distribution.

w ~  N(0,1)

Random Uniform initialization can be implemented in Keras layers in Python as follows:
Random Uniform Initialization
```
from tensorflow.keras import layers
from tensorflow.keras import initializers
 
initializer = tf.keras.initializers.RandomUniform(
  minval=0.,maxval=1.)
layer = tf.keras.layers.Dense(3, kernel_initializer=initializer)
```
