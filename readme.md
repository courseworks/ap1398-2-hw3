<center>
<h1>
In The Name Of ALLAH
</h1>
<h2>
Advanced Programming - Homework 3
</h2>
<h2>
Dr.Amir Jahanshahi
</h2>
<h3>
Deadline: Wednesday, 13 Farvardin - 23:00
</center>

#  Introduction
In this homework, you'll get familiar a little with **neural networks**. Also, you'll estimate some functions using them. Isn't that wonderful?! In this way, you must use the **Matrix** class implemented in the last homework by yourself. You can also change it if you think it's necessary. In the end, you must do all your codes in **Matrix**, **dataset**, **result**, **neuralnet** and **aphw3** header and cpp files.

<img src="https://drive.google.com/uc?id=1fkXeKZZzZBagTWpYo3WCGKOgnLudTHwT" width="400">

#  Dataset Class
In this class, you'll manage whatever we need for storing our data. Each data element or sample in our dataset is composed of an input part and a target part. We give the inputs to our neural net and we expect it to generate an output similar to the targets. That's all. Since we're trying to train a neural net, we need a dataset. We divide our dataset into 2 parts: **Train** and **Test**. We use the *train* data to teach the neural network about the patterns embedded in our data. After that, we must test our neural network to see if it has learned enough or not. So we use the *test* data. 

Dataset class must have the following member variables. No need to mention that all of them *must* be private.

* 
  ```c++
  Matrix inputs;
  ```
Matrix of all input parts of samples of dataset. Each column of this matrix is a sample input.

*
  ```c++
  Matrix targets;
  ```
Matrix of all target parts of samples of dataset. Each column of this matrix is a sample target.

*  
  ```c++
  Matrix train_inputs;
  ```
Matrix of inputs of the *train* part of dataset. Each column of this matrix is a sample input of the *train* part.

*  
  ```c++
  Matrix train_targets;
  ```
Matrix of targets of the *train* part of dataset. Each column of this matrix is a sample target of the *train* part.

*  
  ```c++
  Matrix test_inputs;
  ```
Matrix of inputs of the *test* part of dataset. Each column of this matrix is a sample input of the *test* part.

*  
  ```c++
  Matrix test_targets;
  ```
Matrix of targets of the *test* part of dataset.  Each column of this matrix is a sample target of the *test* part.

*  
  ```c++
  double percentage{70};
  ```
This variable tells the class how to divide data into train and test parts. When it is 70, for example, it takes 70% of data randomly into the train part and the other 30% into the test part of dataset.

*  
  ```c++
  size_t no_of_samples;
  ```
Number of all samples in the dataset.

*
  ```c++
  size_t input_dim;
  ```
Dimension of inputs of dataset.

*  
  ```c++
  size_t target_dim;
  ```
Dimension of targets of dataset.

Dataset class must have the following member functions too.

*  
  ```c++
  Dataset(Matrix inputs, Matrix targets, double percentage=70);
  ```
Note that in this constructor, you must not change the order of samples of dataset in the ```inputs``` and ```targets``` variables.

*  
  ```c++
  size_t getNoOfSamples();
  ```

*  
  ```c++
  size_t getNoOfTrainSamples();
  ```

*  
  ```c++
  size_t getNoOfTestSamples();
  ```

*  
  ```c++
  size_t getInputDim();
  ```
*  
  ```c++
  size_t getTargetDim();
  ```
*  
  ```c++
  Matrix getInputs();
  ```

*  
  ```c++
  Matrix getTargets();
  ```

*  
  ```c++
  Matrix getTrainInputs();
  ```

*  
  ```c++
  Matrix getTrainTargets();
  ```

*  
  ```c++
  Matrix getTestInputs();
  ```

*  
  ```c++
  Matrix getTestTargets();
  ```

*  
  ```c++
  void show();
  ```
This function shows some properties of the dataset, such as number of samples, number of train samples and test samples, input and target dimensions in a beautiful way like the following figure.

  <img src="https://drive.google.com/uc?id=15CbgPc3BtHncGGGBqT04c5E4J5F-hCp0" width="400">


*  ‍‍‍‍‍You must also write the ```[ ]```operator for your class such that, for example, for a dataset object of this class ```dataset[10][0]``` returns the input part of the 11-th sample of dataset (```inputs``` variable) as a Matrix object and ```dataset[10][1]``` returns the target part of the 11-th sample of dataset (```targets``` variable) as a Matrix object. So, the following code must return the value of the first dimension of the input part of the 11-th sample of dataset.
  ```c++
  std::cout<<dataset[10][0][0][0];
  ```

*  
  ```c++
  Dataset operator+(const Dataset& dataset);
  ```
 You must also implement the **+** operator such that we can merge two datasets together. In this case, the result input must be a concatenation of both given datasets inputs. Also, the result target must be a concatenation of both given datasets targets. Seperation of data samples into *train* and *test* parts must also be done randomly again (separation percentage is the default 70).

*  The following code should also do just like the ```show()``` method of your class.
  ```c++
  std::cout<<dataset<<std::endl;  \\ dataset is a Dataset object
  ```
  **Question1**: How do you do this? In order to access private variables of the Dataset object, what would you do without using *getter* functions? Explain it.
  
<img src="https://drive.google.com/uc?id=1kfszEBX0bclfNw0avfD7Q3L52x124UTO" width="400">



