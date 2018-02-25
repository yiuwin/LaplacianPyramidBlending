# LaplacianPyramidBlending
Seamlessly blend an object or texture from a source image into a target image by implementing Laplacian Pyramid Blending in Python

In all Laplacian Pyramid cases, a function called createPyramid(img, pyramidN) is called for each of "foreImg", "backImg", and "mask", respectively. In my implementation of createPyramid(img, pyramidN), I first downsize original image by resizing height h and width w to h/2 and w/2. I then append this image to my imagePyramid and then generate the proceeding levels of three pyramids (imagePyramid, gaussianPyramid, and laplacePyramid) in a single for-loop detailed as follows:

1. Downsize img once again from h and w to h/2 and w/2
2. Append img as next level of imagePyramid
3. Upsize img by factor of 2
4. Append img to gaussianPyramid
5. Compute laplacianPyramid as the difference of imagePyramid and gaussianPyramid at current level
6. Append img to laplaceianPyramid
7. Set img to the downsized image at the current for-loop iteration
8. Set corresponding h and w of img
