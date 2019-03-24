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

