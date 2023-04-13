# 2022_PointCLIP V2: Adapting CLIP for Powerful 3D Open-world Learning

## Research Questions
CLIP  transferred capacity on 3D point clouds is still far from satisfactory.
## Motivations
1. How to generate more realistic depth maps for CLIP’s visual encoder to narrow the domain gap between projected point clouds with natural images?
2. How to automatically design a more descriptive 3D-semantic prompt for CLIP抯 textual encoder, instead of the previous hand-crafted one?
## Contributions
1. propose PointCLIP V2, an efficient cross-modal adaption method for CLIP to transfer the pre-trained 2D knowledge into 3D domains.
2. introduce realistic shape projection and LLMassisted 3D prompting to effectively mitigate the 2D-3D domain gap.
3. PointCLIP V2 can be extended for zero-shot 3D part segmentation and object detection without any 3D-domain training.
## Method Details
1. 【Visual Projection】: To generate more realistic depth maps from 3D point clouds and also achieve time efficiency, the projection in our PointCLIP V2 includes four steps: Voxelize, Densify, Smooth, and Squeeze. For few-shot classification, the Smooth step is intergrated with learnable smoothing.
2. 【Textual Prompting】: LLM-assisted 3D Prompting feed four types of language commands into the pre-trained LLMs to generate a 3D-specific prompt for CLIP’s textual encoder.
3. Downstream tasks including Zero-shot Classification, Few-shot Classification, Zero-shot Part Segmentation and Zero-shot 3D Object Detection.
## Experiments

## Weaknesses
Is there any better way to generate a 3D-specific prompt for CLIP’s textual encoder rather than the usage of GPT-3?
The projection of point cloud data into 2d depth image introduces too much hand-crafted design.
