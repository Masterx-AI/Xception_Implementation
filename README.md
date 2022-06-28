# Xception Implementation

onvolutional Neural Networks (CNN) have come a long way, from the LeNet-style, AlexNet, VGG models, which used simple stacks of convolutional layers for feature extraction and max-pooling layers for spatial sub-sampling, stacked one after the other, to Inception and ResNet networks which use skip connections and multiple convolutional and max-pooling blocks in each layer. Since its introduction, one of the best networks in computer vision has been the Inception network. The Inception model uses a stack of modules, each module containing a bunch of feature extractors, which allow them to learn richer representations with fewer parameters.

Xception paper — https://arxiv.org/abs/1610.02357

The Xception module has 3 main parts. The Entry flow, the Middle flow (which is repeated 8 times), and the Exit flow.


Entry flow of the Xception architecture (Source: Image from the original paper)
The entry flow has two blocks of convolutional layer followed by a ReLU activation. The diagram also mentions in detail the number of filters, the filter size (kernel size), and the strides.

There are also various Separable convolutional layers. There are also Max Pooling layers. When the strides are different than one, the strides are also mentioned. There are also Skip connections, where we use ‘ADD’ to merge the two tensors. It also shows the shape of the input tensor in each flow. For example, we begin with an image size of 299x299x3, and after the entry flow, we get an image size of 19x19x728.


Middle and Exit flow of Xception architecture (Source: Image from the original paper)
Similarly, for the Middle flow and the Exit flow, this diagram clearly explains the image size, the various layers, the number of filters, the shape of filters, the type of pooling, the number of repetitions, and the option of adding a fully connected layer in the end.

Also, all Convolutional and Separable Convolutional layers are followed by batch normalization.
