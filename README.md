# Predicting Power System Dynamics and Transients: A Frequency Domain Approach
This repository contains source code necessary to reproduce the results presented in the following paper:
[Predicting Power System Dynamics and Transients: A Frequency Domain Approach](https://arxiv.org/abs/2009.05654)  

Authors: Wenqi Cui, Weiwei Yang and Baosen Zhang  

University of Washington, Microsoft Research 


# Motivation
The dynamics of a power grid are governed by a large number of nonlinear ordinary differential equations (ODEs). To safely operate the system, operators need to check that the states described by this set of ODEs stay within prescribed limits after various faults. Limited by the size and stiffness of the ODEs, current numerical integration techniques are often too slow to be useful for real-time or large-scale resource allocation problems. In addition, the detailed system parameters are often not exactly known. Machine learning approaches have been proposed to reduce the computational efforts, but current methods generally suffer from overfitting and failures to predict unstable behaviors. 

This paper proposes a novel framework for power system dynamic predictions by learning in the frequency domain. Using the intuition that although the system behavior are complex in the time domain, there are relatively few dominate modes in the frequency domain. Therefore, we learn to predict by constructing neural networks with Fourier transform and filtering layers. System topology and fault information are encoded by taking a multi-dimensional Fourier transform, allowing us to leverage the fact that the trajectories are sparse both in time and spatial (across different buses) frequencies. We show that the proposed approach does not need detailed system parameters, speeds up prediction computations by orders of magnitude and is highly accurate for different fault types.  


# Flexible non-linear controller learnt from the proposed framework
Here we show the action of neural network controller compared with linear droop control
<img src="/Action_Mono.png" height="450px" width="700px" >

# Language and Dependencies
All code are implemented in Python. Data for the power system is imported from MATLAB as 'IEEE_39bus_Kron.mat'. The dataset of trajectories for power system dynamics is generated by power system toolbox from MATLAB as 'Sol_linear.mat'. We used the open-source Python package Tensorflow 2.0 to implement RNN and train the neural network models.


# Code References
We thank https://github.com/zongyi-li/fourier_neural_operator for developping open-sorce code for Fourier Neural Operator
