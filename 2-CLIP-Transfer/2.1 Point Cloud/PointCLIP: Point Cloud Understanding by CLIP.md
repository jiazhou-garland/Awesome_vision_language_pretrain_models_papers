# 2022_PointCLIP: Point Cloud Understanding by CLIP

## Research Questions
whether CLIP, pre-trained by large-scale image-text pairs in 2D, can be generalized to 3D recognition ?
## Motivations
1. How to bridge the modal gap? (convert point clouds into CLIP-accessible representations)
2. How to design a modal adapter module for few-shot settings?
## Contributions
1. propose PointCLIP to extend CLIP for handling 3D point cloud data, which achieves cross-modality zero-shot recognition by transferring 2D pre-trained knowledge into 3D.
2. An inter-view adapter is introduced upon PointCLIP via feature interaction among multiple views and largely improves the performance by few-shot finetuning.
3. PointCLIP can be utilized as a multi-knowledge ensemble module to enhance the performance of existing fully-trained 3D networks.
## Method Details
1. generate point-projected images from multiple views to eliminate the modal gap between 3D and 2D.
2. use CLIP to extract visual features from multiple views projected images by the CLIP visual encoder. For the textual branch, place K category names into the class token position of a pre-defined template: “point cloud depth map of a [CLASS].” and encode their textual features by the CLIP text encoder.
3. the classification logits of each view are separately calculated and the final logits of point cloud are acquired by their weighted summation.
4. append a three-layer Multi-layer Perceptron (MLP) on top of PointCLIP, named inter-view adapter, to further enhance its performance under few-shot settings.(freeze both CLIP’s visual and textual encoders and only fine-tune the learnable adapter via cross-entropy loss)
5. To investigate if the two forms of knowledge can be ensembled together for better joint inference, ensemble PointNet++ and Point-CLIP predicted logits by simple addition as the final output.
## Experiments
Zero-shot Classification
Few-shot Classification
Multi-knowledge Ensemble
## Weaknesses
