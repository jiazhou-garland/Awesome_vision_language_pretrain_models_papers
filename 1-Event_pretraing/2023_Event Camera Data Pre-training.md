# 2022_Event Camera Data Pre-training

## Research Questions
Event camera data pretraining using paired event data and RGB images for training.
## Motivations
1. How to narrow the domain-gap between RGB images and event data?(Simply performing metric learning in the event embedding space leads to model collapse and embeddings from paired RGB images can be used as a regularizer.)
2. How to do event data augmentation correctly?
3. How to do event masking? (Random masking would generate non-informative patches because an event image is spatially sparse, leading to training instability.)
## Contributions
1. An self-supervised framework for event camera data pre-training. The pre-trained model can be transferred to diverse downstream tasks;
2. A family of event data augmentations, generating meaningful event images;
3. A conditional masking strategy, sampling informative event patches for network training;
4. An embedding projection loss, using paired RGB embeddings to regularize event embeddings to avoid model collapse;
5. A probability distribution alignment loss for aligning embeddings from paired event and RGB images.
## Method Details
1. generate an event image by applying the event histogram algorithm;
2. consecutively perform data augmentations(not mentioned in detail???), event image generation, and conditional masking to obtain two patch sets (xq; xk);
3. extract event features and then project event features to latent embedding;
4. designe loss from event discrimination and event and natural RGB image discrimination to train the model.
## Experiments
1. N-ImageNet and ImageNet-1K datasets for pre-training.
2. explore three backbones, i. e., ViT-S/16, ViT-B/16, and ResNet50 and compared with three group of methods: (a) Training from scratch; (b)Transfer learning of supervised pre-training methods; (c)Transfer learning of selfsupervised pre-training methods.
3. transfer learning to object recognition, optical flow estimation and semantic segmentation.
## Weaknesses
Paired RGB and event data are requried for pre-training(N-ImageNet + ImageNet-1K)
