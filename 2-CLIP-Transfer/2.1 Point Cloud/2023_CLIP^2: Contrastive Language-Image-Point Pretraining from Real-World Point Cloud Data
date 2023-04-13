# 2023_CLIP^2: Contrastive Language-Image-Point Pretraining from Real-World Point Cloud Data

## Research Questions
directly learn the transferable 3D point cloud representation in realistic scenarios
## Motivations
1. Existing works that leverage VLM for 3D understanding generally resort to constructing intermediate 2D representations for the 3D data, but at the cost of losing 3D geometry information.
## Contributions
1. propose a novel CLIP2 framework that aligns 3D space with open-world language representation, facilitating zero-shot transfer in realistic scenarios。
2. present a Triplet Proxies Collection scheme in real world scenes, which alleviates the shortage of text-3D data sources and facilitates the pretraining methods.
3. jointly optimizes the correlation alignment between point cloud, language and image by proposed cross-modal pretraining mechanism, which enhances the transferability of learned 3D representation.
## Method Details
1. Triplet Proxy Collection
1.1 Language Proxy: set the language proxies as a raw text list from the 2D open-world dataset.
1.2 Image Proxy: obtain the image proxies by an open vocabulary detector DetCLIP.
1.3 3D Proxy: for indoor scenes equipped with RGB-D sensors, remove the background pixels by unsupervised segmentation algorithm for each image proxy; 
For outdoor scenes captured by LiDAR sensors, create a 3D frustum for each image proxy by extruding the 2D image proposal into 3D space following.
Then we conduct DBSCAN algorithm within frustum and select the point cloud cluster as the point proxy
2. Semantic-Level Language-3D Alignment + Instance-Level Image-3D Alignment.
## Experiments

## Weaknesses
it can not provide the accurate tight bounding box for open-world 3D objects as a common detector does.
