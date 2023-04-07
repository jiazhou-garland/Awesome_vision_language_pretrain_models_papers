# 2022_Event Camera Data Pre-training

## Research Questions
Event camera data pretraining using paired event data and RGB images for training.
## Motivations
1. How to narrow the domain-gap between RGB images and event data?
2. How to do event data augmentation correctly?
3. How to do event masking? (Random masking would generate non-informative patches because an event image is spatially sparse, leading to training instability.)
4. The oberservation that simply performing metric learning in the event embedding space leads to model collapse and embeddings from paired RGB images can be used as a regularizer.
## Contributions
1. An self-supervised framework for event camera data pre-training. The pre-trained model can be transferred to diverse downstream tasks;
2. A family of event data augmentations, generating meaningful event images;
3. A conditional masking strategy, sampling informative event patches for network training;
4. An embedding projection loss, using paired RGB embeddings to regularize event embeddings to avoid model collapse;
5. A probability distribution alignment loss for aligning embeddings from paired event and RGB images.
## Method Details

## Experiments

## Weaknesses
