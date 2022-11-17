# Neural-Networks-with-Tensorflow-and-keras - Learning through code in simple language

#### This post is an attemp to explain the uses of Tenserflow for the creation of the ANN model along with some of the important compnent's explanations. 
![image](https://user-images.githubusercontent.com/64850093/202383113-0fc6ecef-3be0-4ebb-840c-78492346be8d.png)

 https://rukshanpramoditha.medium.com/one-hidden-layer-shallow-neural-network-architecture-d45097f649e6
# Introduction

* **Tensflow**  is a free open source software library for machine learning. It's mainly used for the high numerical computation. 
TensorFlow enables the developers to create a sequrntil and graphical structire that describe how data flows in order and each nodes 
in the graphs shows some mathematcal computation.
and each connection or edge between nodes is a multidimensional data array, or tensor.**Keras** is a high-level neural network library that runs on top of TensorFlow. 
Both provide high-level APIs used for easily building and training models,
but Keras is more user-friendly because it's built-in Python.

* **Deep learning** is a sub topic under the machine learning where we utilize various layers of artifical neural network for the training of model.


<h> <h/>



# Steps for Building a model using Tensorflow
( Before going deep I hope you have touched a little of deep learning or neural networ surfacely )
## 1. Creating the model

#### First we initialize the model with proper parameters

``` 
model = Sequential(
      [               
        Dense(25 , activation = 'sigmoid' , name = 'layer1'),
        Dense(15 , activation = 'sigmoid' , name = 'layer2'),
        Dense(1 , activation = 'sigmoid' , name = 'layer3')
      ], name = "my_model" 
)                            
```

Above In the figure at first we have imported all the libraries important. From the picture we can see for Building model for NN, there are three terms which is necessary to understand
There is ***Sequence()*** and **Dense()** function.
 
 * In **sequence()** we have defined three Dense function which builds upon the three layered neuron network.
 
 * Where first parameter of **Dense()** has **25** or **15**, this imply the number of the nurons in the each layer. second parameter defines which activation function
 we want to use there are various eg. Sigmoid , RElu. ** Later in the section we will discuss about the activations **
 
### 1.1 Activations function and choosing the proper activation function.
**Activation function** are the funcitons which determines if the neuron fires or not. The neuron only fires when an activation function pass a certain value. 
we'll study below three type of Activation function:

* 1. RELU
* 2. SIGMOID
* 3. Linear activation fucniton

`sigmoid` activation function takes any real value as input and outputs values in the range of 0 to 1. 


        










## 2. Specifying the Loss and cost function


``` 
model.compile(
    loss=tf.keras.losses.BinaryCrossentropy(),
   
)

 ```
 Let's understand the Loss and the cost function together.
 
 * **Loss function**:  Loss function calculate the losses i,e the error which is made. It's the difference between the target and the actual output in final output layer.
 * **Cost function**: Cost function averages the losses and evaluate the perfomance of an algorith on a certain dataset.** The aim is to minimize cost function**.
 
 ## 3. Minimizing cost using any algorithm preferred is **Gradient Desent** and fitting accordingly.
 
 ```
 
 model.fit(
    X,y,
    epochs=20
)
 
 ```
 Model is fit using `model.fit()` and uses eg Gradient desent for minimizing losses and `back propagation algorithm` is used to computer derivatives and update the model
 in each itearion.
 
 epoch  = 20 means 20 iterations are done.
 
 **Gradient Desent**: It is an iterative first order first order optimization algorithm to find local minima and maxima.
 ![image](https://user-images.githubusercontent.com/64850093/202390052-01607ba3-d71d-4f61-a929-b7c40d9408a4.png)

 
 ![image](https://user-images.githubusercontent.com/64850093/202387618-ad18e6c4-b977-4316-98a2-172d416d8f84.png)
 
 
 
 
 There are Various function for calucation of the loss one is **BinaryCrossentropy(), MeanSquaredError()** and manymore. Best value of W and B are calculated which minimize loss.





















