# max_nn
Mac Max 64-bit neural network external sources

In order to create a neural network you only need the an external.
But if you want to train it using backpropagation you also need anntrainingset for storing the training set examples to train the neural network, and delta2error (one for each layer except the first one) to receive the delta and weights of a given layer and output the errors to correct the weights of the previous layer by.

To build the externals, the directories are to be placed in one of the source directory in which the sources of Max externals are to be stored, e.g. ~/Documents/Max 7/Packages/max-sdk-7.0.3/source/basics/ (as I use it). Then, when opening the project in XCode the external can be built, and should be placed in the externals directory (typically ~/Documents/Max 7/Packages/max-sdk-7.0.3/externals/) with the mxo extension ready to be used. The __LP64__ constant tells ext.h to use double precision. If you remove it it compiles for 32-bit Max/MSP.

For an working example, see mattmazur.maxpat. Note that in this example the bias used is not adjusted during training. Therefore a flag blocking changing the bias weight (which is the third 'weight' in the neurons) has to be set. This is done by passing the weight flags integer into each neuron (this is the integer in the patcher with value 4 (binary 100)). 

Marc de Hoogh
5 June 2017
