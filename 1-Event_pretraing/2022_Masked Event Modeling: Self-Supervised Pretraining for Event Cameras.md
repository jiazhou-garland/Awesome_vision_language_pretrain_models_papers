# 2022_Masked Event Modeling: Self-Supervised Pretraining for Event Cameras

## Research Questions
The development of event-based vision has been hampered by the small amount of labeled event data compared to the vast majority of labeled RGB imagery.
## Motivations
Reduce the dependency on labeled event data
## Contributions
1. Masked Event Modeling (MEM) is introduced as a selfsupervised pretraining framework for events that pretrains a neural network on unlabeled events, making it applicable to any event recording.
2. Set a new state-of-the-art accuracy for image classification. N-Imagenet +7.96%, N-Cars +1.49%, and N-Caltech101 +9.5%.
3. It is not always standard protocol to transfer RGB pretrained weights to the event domain.
## Method Details
1. The raw event data is preprocessed to an event histogram, and 50% of the patches are masked and replaced by a learnable mask embedding.
2. a discrete variational autoencoder (dVAE) was employed to predict visual tokens which summarize high-level semantic information in a single vector per patch.
3. transferring the weights of the pretrained network to initialize the ViT. Only the final MEM layer is replaced by a task-specific layer. The dVAE is no longer
used. Requires labeled data when finetuning on a specific task.
## Experiments
1. compare each dataset to multiple baselines from the literature and multiple of our baselines.
2. compare MEM to training the same model with random weight initialization (ViT-from-scratch).
3. compare MEM to supervisedly pretrained RGB-networks on ImageNet-1k and ImageNet-21k (ViT-1k, ViT-21k).
## Weaknesses
Event data labels are still required when finetuning to downstream tasks.
