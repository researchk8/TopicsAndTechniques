# Mixture of experts (MoE)



Mixture of experts (MoE) is a machine learning approach that divides an artificial intelligence (AI) model into separate sub-networks (or “experts”), each specializing in a subset of the input data, to jointly perform a task.

Mixture of Experts architectures enable large-scale models, even those comprising many billions of parameters, to greatly reduce computation costs during pre-training and achieve faster performance during inference time. Broadly speaking, it achieves this efficiency through selectively activating only the specific experts needed for a given task, rather than activating the entire neural network for every task.



Sparsity

Key to the concept (and efficiency) of MoEs is that only some of the experts (and therefore parameters) in a sparse layer will be activated at any given time, thereby reducing active computational requirements.



Routing

A number of gating mechanisms can be used to select which experts are utilized in a given situation. The right gating function is critical to model performance, as a poor routing strategy can result in some experts being under-trained or overly specialized and reduce the efficacy of the entire network.



Load balancing

Despite their many benefits, MoEs add significant complexity to the training process. An important downside to the “vanilla” top-k routing strategy is the potential for the gating network to converge to activating just a few experts. This is a self-reinforcing problem: if a handful of experts are disproportionately selected early on, those experts will be trained more quickly, and then continue to be selected more as they now output more reliable predictions than the other, less-trained experts. This imbalanced load means other experts ultimately end up, figuratively and literally, as dead weight(s).


# Resources
https://www.ibm.com/think/topics/mixture-of-experts