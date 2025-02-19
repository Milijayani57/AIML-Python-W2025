**Histogram of Oriented Gradients (HOG)**

* Histogram of Oriented Gradients (HOG) is a technique for feature extraction, particularly used in computer vision and image processing.
* It basically computes pixel-wise gradients and orientations and plots them on histogram.
* It retains only a small piece of information while discarding the rest and still retains all the crucial information.

Talking about intuition, without diving deep into the technicalities, HOG has the following steps involved:
1. Image pre-processing
In this step, we standardize the image size such that they can then be divided into cells of typically 8x8 or 16x16

2. Calculate gradients and orientations
Calculate total gradient magnitude and orientation for each cell inside the cell:
Total gradient magnitude = √([(G_x )^2+(G_y )^2 ] )

Orientation = tan^(-1)⁡█((G_y/G_x )@)
3. Build histogram
Calculate value per bin of histogram = (magnitude x angle weight)
Similarly, we calculate for each cell and get 1 x n feature matrices
Where ‘n’ is number of bins in the histogram
4. Normalization
Localized gradients of the image are sensitive to overall lighting.
Make blocks by grouping of cells and then reduce variance by normalizing gradients.
This block has a normalized matrix of 1 x [(no. of bins) x (no. of cells per block)]

Finally, we calculate normalized vectors for all blocks and obtain an image feature descriptor.
Normalized vector = (a1/k,a2/k,…an/k)
Where k = √(a_1^2+a_2^2+⋯+ a_n^2 )  

and n = (no. of bins) x (no. of cells per block)


*“The HOG feature descriptor counts the occurrences of gradient orientation in localized portions of an image.” (Singh, 2025)*

References
AI, S. (2022, August 13). Histogram of Oriented Gradients (HOG) — Simplest Intuition. Retrieved from Medium: https://medium.com/@skillcate/histogram-of-oriented-gradients-hog-simplest-intuition-2392995f8010
Singh, A. (2025, February 12). HOG Feature Descriptor: Feature Engineering for Images. Retrieved from Analytics Vidhya: https://www.analyticsvidhya.com/blog/2019/09/feature-engineering-images-introduction-hog-feature-descriptor/