[https://doi.org/10.1007/s12525-021-00475-2](https://doi.org/10.1007/s12525-021-00475-2)

Machine learning refers to the capability of systems to acquire knowledge from training data that is specific to a problem. This knowledge is then used to automatically construct analytical models and tackle related tasks. Deep learning, on the other hand, is a machine learning approach that relies on artificial neural networks.

#### Machine Learning

-  Learns from examples and observations
- Challenges : The suitable choice from many implementation options, bias and drift in data, the mitigation of black-box properties, and the reuse of preconfigured models (as a service).
- ML means that a computer program’s performance improves with experience with respect to some class of tasks and performance measures

**Knowledge base approach** : An early AI approach in which a computer automatically reasons based on logical inference rules from hard coded statements in formal languages. Couldn't handle complex tasks.

#### Deep Learning
Deep Learning is useful in domains with large and high dimensional data and outperforms shallow algorithms for applications where text, image, audio, video and speech data need to be processed. But in cases of limited training data availability, shallow ML can still produce superior results.
### Artificial Neural Networks
Artificial neural networks have a flexible structure which allows them to be modified for a wide variety of contexts across all types of ML.
- ANNs consist of mathematical representations of connected processing units called artificial neurons.
- Each connection between neurons transmits signals whose strength can be amplified or attenuated by a weight that is continuously adjusted during the learning process.
- Signals are only processed by subsequent neurons if a certain threshold is exceeded as determined by an activation function. 
- Typically, neurons are organized into networks with different layers. An input layer usually receives the data input, and an output layer produces the ultimate result.
- In between, there are zero or more hidden layers that are responsible for learning a non-linear mapping between input and output. 
- The number of layers and neurons, among other property choices, such as learning rate or activation function  constitute a model’s hyperparameters and must be set manually or determined by an optimization routine.

### Deep Neural Networks

- Consist of more than one hidden layer, organized in deeply nested network architectures.
- Usually contain advanced neurons in contrast to simple ANNs. That is, they may use advanced operations like convolutions or multiple activations in one neuron rather than using a simple activation function. 

ANNs are considered to be a part of shallow machine learning and DNNs are a part of deep machine learning.

### Drift
ML models for intelligent systems may not produce satisfactory results when historical
data does not describe the present situation adequately anymore.
Currently, manual checks and periodic model retraining are the 2 options to keep drift in check.

### Transfer Learning
Allows models that are trained on general
datasets to be specialized for specific tasks by using a considerably smaller dataset that is problem-specific.