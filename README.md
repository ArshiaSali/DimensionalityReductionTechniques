# Dimensionality Reduction Techniques - Analysis and Comparison


## **Dimenionality Reduction in Image Dataset**

**Sign Language MNIST Dataset from Kaggle**
The MNIST database (Modified National Institute of Standards and Technology database) is a large database of handwritten digits that is commonly used for training various image processing systems.The database is also widely used for training and testing in the field of machine learning. To stimulate the community to develop more drop-in replacements, the Sign Language MNIST is presented here and follows the same CSV format with labels and pixel values in single rows. The American Sign Language letter database of hand gestures represent a multi-class problem with 24 classes of letters.

The dataset format is patterned to match closely with the classic MNIST. Each training and test case represents a label (0-25) as a one-to-one map for each alphabetic letter A-Z (and no cases for 9=J or 25=Z because of gesture motions). The training data (27,455 cases) and test data (7172 cases) are approximately half the size of the standard MNIST but otherwise similar with a header row of label, pixel1,pixel2….pixel784 which represent a single 28x28 pixel image with grayscale values between 0-255. 

![raw_img](https://user-images.githubusercontent.com/37695314/139573397-52ac489b-9a4f-429b-b6d9-a145d8aff435.PNG)

Dataset Link - <a href="https://drive.google.com/drive/folders/1ltE0BqT06XJgABDglR2raM0jcRLfJZjG?usp=sharing">Click Here</a>


![pca_reduced](https://user-images.githubusercontent.com/37695314/139573422-310958b5-71e4-4a70-aa90-0ac55d1c4b4f.PNG)


![svd_reduced](https://user-images.githubusercontent.com/37695314/139573442-fd011b7f-4a8b-4897-8d0b-98909d51468f.PNG)

ISOMAP Visualization of the dataset

![iso](https://user-images.githubusercontent.com/37695314/139573452-60977be8-d390-4794-948c-a2a21119eacc.PNG)

## **Dimenionality Reduction in Tabular Dataset**
### **Wine Recognition Dataset from Scikit Learn**

The data in this dataset the result of a chemical analysis of wines grown in the same region in Italy by three different cultivators. There are thirteen different measurements taken for different constituents found in the three types of wine.

The 13 predictive attributes in this dataset are:-
- Alcohol
- Malic acid
- Ash
- Alcalinity of ash
- Magnesium
- Total phenols
- Flavanoids
- Nonflavanoid phenols
- Proanthocyanins
- Color intensity
- Hue
- OD280/OD315 of diluted wines
- Proline

Comparison between the Dimension Reduction Techniques: PCA vs t-SNE vs UMAP vs LLE vs ISOMAP vs SVD for Image Dataset

![comp_2d](https://user-images.githubusercontent.com/37695314/139573185-1d71ce02-bd17-4f71-814f-9497d34e5a81.PNG)

Comparison between the Dimension Reduction Techniques: PCA vs t-SNE vs UMAP vs LLE vs ISOMAP vs SVD for Tabular Dataset

![tab_res](https://user-images.githubusercontent.com/37695314/139573522-5851d595-5fd6-45ef-a145-bdb12ad8fbf4.PNG)

![comp_time](https://user-images.githubusercontent.com/37695314/139573190-bd87d928-d1cb-4459-ae9d-c5e842d40137.PNG)

- PCA was not able to do such a good job in differentiating the signs. The main drawback of PCA is that it is highly influenced by outliers present in the data. PCA is a linear projection, which means it can’t capture non-linear dependencies, its goal is to find the directions (the so-called principal components) that maximize the variance in a dataset.

- t-SNE does a better job(it tries to preserve topology neighbourhood structure) as compared to PCA when it comes to visualising the different patterns of the clusters. Similar labels are clustered together, even though there are big agglomerates of data points on top of each other, certainly not good enough to expect a clustering algorithm to perform well.

- UMAP outperformed t-SNE and PCA, if we look at the 2d and 3d plot, we can see mini-clusters that are being separated well. It is very effective for visualizing clusters or groups of data points and their relative proximities. However, for this use case certainly not good enough to expect a clustering algorithm to distinguish the patterns.UMAP is much faster than t-SNE, another problem faced by the latter is the need for another dimensionality reduction method prior, otherwise, it would take a longer time to compute.

### **Summary**
Analysis of six  dimensionality reduction techniques for data visualization : (PCA, t-SNE, UMAP, LLE, ISOMAP, SVD)and tried to use them to visualize a high-dimensional dataset in 2d and 3d plots.
At the end of the day there is no way to map a high-dimensional data into low dimensions and preserving the whole structure at the same time, there is always a trade-off of qualities one technique will have compared to the other.
