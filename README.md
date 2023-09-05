# DeepLearningWeightInitializing

**Source** : https://www.geeksforgeeks.org/weight-initialization-techniques-for-deep-neural-networks/

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
## Xavier/Glorot Initialisation
In Xavier/Glorot weight initialization, the weights are assigned from values of a uniform distribution as follows:

<img src="https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-ad8f226636f9e63ba020ec8c9af15d7b_l3.svg" class="ql-img-inline-formula quicklatex-auto-format" alt="w_i \sim U\space[  -\sqrt{  \frac{\sigma }{fan\_in + fan\_out}}, \sqrt{  \frac{\sigma }{fan\_in + fan\_out}}]" title="Rendered by QuickLaTeX.com" height="48" width="491" style="vertical-align:-19px">

Xavier/Glorot Initialization often termed as Xavier Uniform Initialization, is suitable for layers where the activation function used is Sigmoid. Xavier/Gorat initialization can be implemented in Keras layers in Python as follows:

```
from tensorflow.keras import layers
from tensorflow.keras import initializers
 
initializer = tf.keras.initializers.GlorotUniform()
layer = tf.keras.layers.Dense(3, kernel_initializer=initializer)
```

## Normalised Xavier/Glorot Initialisation
In Normalized Xavier/Glorot weight initialization, the weights are assigned from values of a normal distribution as follows:

w  ~  N(0, \sigma )

Here, sigma is given by:

<img src="https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-a536122216fb0573a908d175015995fe_l3.svg" class="ql-img-inline-formula quicklatex-auto-format" alt="\sigma =\space\sqrt{ \frac{6 }{fan\_in + fan\_out}}" title="Rendered by QuickLaTeX.com" height="48" width="234" style="vertical-align:-17px">

Xavier/Glorot Initialization, too, is suitable for layers where the activation function used is Sigmoid. Normalized Xavier/Gorat initialization can be implemented in Keras layers in Python as follows:

```
from tensorflow.keras import layers
from tensorflow.keras import initializers
 
initializer = tf.keras.initializers.GlorotNormal()
layer = tf.keras.layers.Dense(3, kernel_initializer=initializer)
```

## He Uniform Initialization

In He Uniform weight initialization, the weights are assigned from values of a uniform distribution as follows:

<img src="https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-8a3618b316f33bb702cf0a28a1ef7e4a_l3.svg" class="ql-img-inline-formula quicklatex-auto-format" alt="w_i  \sim  U\space[  -\sqrt{  \frac{6 }{fan\_in}}, \sqrt{  \frac{6}{fan\_out}}]" title="Rendered by QuickLaTeX.com" height="48" width="326" style="vertical-align:-17px">

He Uniform Initialization is suitable for layers where ReLU activation function is used. He Uniform Initialization can be implemented in Keras layers in Python as follows:

```
from tensorflow.keras import layers
from tensorflow.keras import initializers
 
initializer = tf.keras.initializers.HeUniform()
layer = tf.keras.layers.Dense(3, kernel_initializer=initializer)
```

## He Normal Initialization

In He Normal weight initialization, the weights are assigned from values of a normal distribution as follows:

w ~ N(0, sigma)

Here, sigma is given by:

 <img src="https://www.geeksforgeeks.org/wp-content/ql-cache/quicklatex.com-6cb4c9f872f46c1cf3a33c334eb39ea1_l3.svg" class="ql-img-inline-formula quicklatex-auto-format" alt=" \sigma =  \sqrt{ \frac{2}{fan\_in} }" title="Rendered by QuickLaTeX.com" height="48" width="146" style="vertical-align:-17px">

He Uniform Initialization, too, is suitable for layers where ReLU activation function is used. He Uniform Initialization can be implemented in Keras layers in Python as follows:

```
from tensorflow.keras import layers
from tensorflow.keras import initializers
 
initializer = tf.keras.initializers.HeNormal()
layer = tf.keras.layers.Dense(3, kernel_initializer=initializer)
```
