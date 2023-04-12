# 2023_CLIP goes 3D: Leveraging Prompt Tuning for Language Grounded 3D Recognition
## Research Questions
Apply CLIP to 3D point cloud.
## Motivations
1. How to overcome the distribution shift from RGB images and rendered 2D images from point could? (Attempting to train the visual and text encoder
to account for this shift results in catastrophic forgetting and a notable decrease in performance)
2. How to address the limitations that CLIP is not suitable for extracting 3D geometric features?
## Contributions
1. propose CG3D, a contrastive pre-training framework for training 3D networks using natural language supervision while also leveraging the knowledge of CLIP.
2. utilize prompt tuning to shift the input space of a pretrained visual encoder from rendered images of CAD objects to natural images, allowing for more effective use of CLIP for 3D shapes
## Method Details
1. 3D Encoder: be agnostic with the choice of 3D encoder
2. 2D Visual Encoder takes in the corresponding rendered image of the 3D pointcloud as the input, utilizing CLIP visual encoder(ResNet and ViT)
3. Text Encoder takes in the corresponding text caption of the 3D point cloud as input, trained to correspond text descriptions with images
4. Prompt Tuning for Visual Encoder: introduce learnable prompts as learnable tokens at every layer in the transformer layer in ViT (visual encoder).
5. Triple loss: The contrastive losses (InfoNCE objective) between 3D-image features, text-image features and 3D-text features
## Downstream tasks
zero-shot
open scene understanding
retrieval tasks
## Weaknesses
