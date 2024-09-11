# Image Compression Using K-Means Clustering

This repository contains a Python implementation of **image compression** using the **K-means clustering algorithm**. The algorithm reduces the number of colors in an image by clustering the pixels in the RGB color space.

## Overview

In an RGB image, each pixel is represented by three 8-bit integers (ranging from 0 to 255) that specify the red, green, and blue intensity values. A typical image contains many different colors, which can be compressed by finding a smaller set of representative colors using K-means clustering.

This project demonstrates how to:
- Apply K-means to reduce the number of colors in an image.
- Cluster every pixel in the image into a reduced number of color clusters (K = 10 and K = 20).
- Replace each pixel in the image with its corresponding cluster center.

## K-Means Image Compression

The key steps in K-means image compression are:
1. **Treat each pixel as a 3-dimensional point** in the RGB color space.
2. **Apply K-means clustering** to group the pixels into `K` clusters.
3. **Replace each pixel** in the image with the closest cluster center, resulting in a compressed image with only `K` colors.

## Implementation

The `k-means.ipynb` notebook contains the implementation. The main steps are as follows:

1. **Load the image**: 
   - Read the original image using `matplotlib` or `PIL`.
   - Convert the image into a 2D array where each row represents a pixel, and each column represents the RGB values.
   
2. **Apply K-means clustering**:
   - Use the `KMeans` algorithm from `sklearn` to cluster the pixels into `K` groups.
   - Experiment with `K = 10` and `K = 20`.

3. **Reconstruct the image**:
   - Replace each pixel in the image with its corresponding cluster center (the closest cluster).
   - Save and display the compressed image.

4. **Evaluate the results**:
   - Compare the original image with the compressed images.
   - Report observations about image quality and file size.

## Results

The results of applying K-means with `K = 10` and `K = 20` show the following:
- **K = 10**: The image retains a good level of detail with a reduced color palette.
- **K = 20**: The image preserves even more detail while still achieving compression.
- The tradeoff between compression and image quality becomes apparent as `K` increases.

## How to Run

1. Clone the repository:
    ```bash
    git clone https://github.com/Aliz-f/ImageCompression-with-KMeans.git
    ```

2. Install required libraries (if applicable):
    ```bash
    pip install -r requirements.txt
    ```

3. Run the Jupyter notebook `k-means.ipynb` to see the image compression in action:
    - Change the value of `K` to experiment with different numbers of clusters.

## Conclusion

- **K-means clustering** is an effective method for image compression, allowing the reduction of colors while preserving the overall structure and content of the image.
- Increasing the number of clusters improves image quality but reduces the degree of compression.

