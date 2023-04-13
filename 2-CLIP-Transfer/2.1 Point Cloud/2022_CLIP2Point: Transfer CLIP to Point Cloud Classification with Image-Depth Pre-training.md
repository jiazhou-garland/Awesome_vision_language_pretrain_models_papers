# 2022_CLIP2Point: Transfer CLIP to Point Cloud Classification with Image-Depth Pre-training

## Research Questions
Transfer CLIP to Point Cloud Classification
## Motivations
1. the domain gap between 3D and images is unsolved, so that V-L pre-trained models are restricted in 3D downstream tasks.
## Contributions
1. CLIP2Point combines cross-modality learning to enforce the depth features for capturing expressive visual and textual features and intra-modality learning to enhance the invariance of depth aggregation.
2. introduce a new depth rendering setting that forms a better visual effect, and then render 52,460 pairs of images and depth maps from ShapeNet for pre-training.
3. propose a novel Dual-Path Adapter (DPA) module, a dual-path structure with a global-view adapter to efficiently extend CLIP2Point to downstream representation learning.
## Method Details
1. Pretraining scheme for zero-shot learning
1.1 randomly choose a camera view for each 3D model and modify the distances of the view to construct pairs of rendered RGB images and corresponding depth maps by ShapeNet.
1.2 adopt one NT-Xent loss between pairs of depth features extracted from the depth encoder and the other between image features and average depth features. Then freeze the image encoder during training, enforcing the depth features by depth encoder to be aligned with the image features by CLIP visual encoder.
2. Lightweight fine-tuning for Downstream Representation Learning
design a Dual-Path Adapter (DPA) module, combining our pre-trained depth encoder with CLIP visual encoder. Then propose a global-view adapter and attach it to each encoder,
## Experiments

## Weaknesses
synthetic pre-training data has a limited improvement on real-world downstream data that contains noise and complicated background information.
