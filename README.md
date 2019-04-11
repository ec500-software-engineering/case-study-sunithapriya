# case-study-sunithapriya
Case Study Topic - TensorFlow

# What is TensorFlow?
* Created by the Google Brain team, TensorFlow is an open source library for numerical computation and large-scale machine learning.  It helps in developing and training ML models. It has a comprehensive, flexible ecosystem of tools, libraries and community resources.
* It was released under the Apache 2.0 open-source license on November 9, 2015. 
* TensorFlow can run on multiple CPUS and GPUs. 
* It is available on 64-bit Linux, macOS, Windows, and mobile computing platforms including Android and iOS.
* Its flexible architecture allows for the easy deployment of computation across a variety of platforms (CPUs, GPUs, TPUs), and from desktops to clusters of servers to mobile and edge device

# Why TensorFlow?
* Easy model building - Build and train ML models easily using intuitive high-level APIs like Keras
* Robust ML production anywhere - Easily train and deploy models in the cloud, on-prem, in the browser, or on-device no matter what language you use.
*	Powerful experimentation for research - A simple and flexible architecture to take new ideas from concept to code, to state-of-the-art models, and to publication faster.

# How does TensorFlow work?
TensorFlow allows developers to create dataflow graphs—structures that describe how data moves through a graph, or a series of processing nodes. Each node in the graph represents a mathematical operation, and each connection or edge between nodes is a multidimensional data array, or tensor.

## 1. Technology and Platform used for development
### a. Coding Languages Used: 
TensorFlow is written in Python and C++

It uses Python to provide a convenient front-end API for building applications with the framework, while executing those applications in high-performance C++.

#### Why Python?
* Python was the first well-supported language for expressing and controlling the training of models. 
* Python is probably the most comfortable language for a large range of data scientists and machine learning experts that's also that easy to integrate and have control a C++ backend
* Open source and general.
* Libraries like NumPy makes it easy to do pre-processing in Python

#### Why C++?
* The algorithmic engine is built over C++.
* C++ is highly-optimized for computation.
* Used to get best optimization and high performance in underlying algorithms.

TensorFlow provides stable Python and C APIs as well as non-guaranteed backwards compatible API's for C++, Go, Java, JavaScript and Swift.

I believe the same languages would be used if the project was started today for the reasons mentioned above. 

If the project was starting today, I would use Python for the sole reason of ease of coding. However, having read about the reason behind using a C++ backend, I feel the technologies used in developing TensorFlow are the best choice.

### b. Build System Used
TensorFlow uses  bazel to build TF for all platforms. CMAKE build, used earlier is deprecated. Bazel is the only build tool that is provided by TensorFlow

Additional pre-requisites for Microsoft Windows:
* Visual Studio 
*	Python 3.5

Additional prerequisites for Linux:
* Python 2.7 or later
*	Docker (for automated testing)


## 2. Testing
### a. Meaningful Tests?
Tests are maintained with TensorFlow, in files next to the code. The tests are invocable in the standard way for the build system (bazel or cmake). Since TensorFlow is written in at least two languages (not counting the language bindings), language level testing doesn't make as much sense. The website Coveralls (https://coveralls.io/github/tensorflow/lucid?branch=master) provides the code coverage for tensorflow builds. However, the website is not mentioned in there github. Code Coverage is above 90% for non-contrib TensorFlow.

### b. Continuous Integration
To verify that new changes don’t break TensorFlow,  builds and tests are run, on either Jenkins or a CI system internal to Google.
The builds and tests are triggered on updates to master or on each pull request. Repository maintainers need to be contacted in order to trigger builds on pull requests.
There are two options when running TensorFlow tests locally on machine. 
First, using docker, one can run the Continuous Integration (CI) scripts on tensorflow devel images. 
The other option is to install all TensorFlow dependencies on the machine and run the scripts natively on the system.

### c. Computing platforms
Linux, macOS, windows Raspberry pi, Android

## 3. Software Architecture
Tensorflow can be used as a standalone program to build models. It allows developers to create large-scale neural networks with many layers. It is mainly used for: Classification, Perception, Understanding, Discovering, Prediction and Creation. Tensorflow can also be used with other projects. For example a project on object recognition can use OpenCV and tensorflow.

![layers](https://user-images.githubusercontent.com/43215312/55850985-c8f59a00-5b24-11e9-8e87-374d4c0ed788.png)  
Fig. General Architecture of TensorFlow  

Tensorflow code can be modified and extended for scaling and flexibility.  
To contribute to tensorflow, one must follow the contribution guidelines (https://github.com/tensorflow/tensorflow/blob/master/CONTRIBUTING.md)


Asynchronous kernels provide a way for a callback to be called when computation is complete, instead of waiting for the computation to finish. Queuing constructs are available in TensorFlow for asynchronous computation. When one graph node is done producing its output, it can queue that data and the consumer node can dequeue it later when it is ready. Similarly, some data can be prefetched to the queues so that the device an begin working on it as soon as it is done with previous computation. 


Tensorflow is an object oriented library.

## 2. Defects
I analyzed the following two issues and suggsted a solution for one of them:

* Issue #27720 (https://github.com/tensorflow/tensorflow/issues/27720):
  The issue does not require an architecture changing or adding a function to TensorFlow. I first tried to replicate and upgrade the tensorflow package in my system using ```conda install tensorflow ``` to install the latest package. However, the version was still 1.13.1. I then tried to find what is the latest version of TensorFlow available for conda and found that the highest version available is 1.13.1. 
  
<img width="631" alt="Screen Shot 2019-04-11 at 6 10 26 PM" src="https://user-images.githubusercontent.com/43215312/55996355-24d73480-5c85-11e9-8ffe-573c48fed10c.png">

I therefore suggested the user to build the higher version for TensorFlow from build  
<img width="652" alt="Screen Shot 2019-04-11 at 5 52 29 PM" src="https://user-images.githubusercontent.com/43215312/55996390-43d5c680-5c85-11e9-9ade-d6d5afed81b3.png">

* Issue #27697 (https://github.com/tensorflow/models/issues/2577)
  Analyzed a closed issue to determine if there was any architecture or function change. The issue states that custom plugins failed to build. The problem was identified that .inc header was missed while creating the pip package. The solution is a code change to include the .inc headers
  <img width="730" alt="Screen Shot 2019-04-11 at 6 16 37 PM" src="https://user-images.githubusercontent.com/43215312/55996644-0291e680-5c86-11e9-8652-65a5e6475998.png">



