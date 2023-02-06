# eigenfaces #humanfacerecognition #facerecognition #facedetection
Haar Feature-based Cascade for Face detection and Eigenfaces for Human face recognition

Face detection vs Face recognition

Face/facial detection is a computer technology used to find and identify human faces in digital images. It is used to locate the face/faces in images.
Face/Facial recognition, on the other hand, is software that identifies or confirms a person's identity using their face. It works by identifying and measuring facial features in an image. Facial recognition can identify human faces in images or videos, determine if the face in two images belongs to the same person, or search for a face among an extensive collection of existing images.

Datasets

Two datasets have been used in this project which were obtained from Kaggle.
1) Labeled Faces in the Wild (LFW) Dataset:
https://www.kaggle.com/datasets/jessicali9530/lfw-dataset
2) The ORL Database of Faces:
https://www.kaggle.com/datasets/tavarez/the-orl-database-for-training-and-testing

Goal

The goal is to perform face detection and recognition on both datasets efficiently. Additionally, the results from both datasets are discussed and compared to draw further conclusions on the algorithm.

Haar Cascade Classification is done in four stages:
1. Calculating Haar Features
2. Creating Integral Images
3. Using Adaboost
4. Implementing Cascading Classifiers

Haar Feature-based Cascade Classification in Python
The model created for this classification is available at the OpenCV GitHub repository:
https://github.com/opencv/opencv/tree/master/data/haarcascades

The repository has the models stored in XML files, and can be read with the OpenCV methods.

Eigenfaces

An Eigenface is the name given to a set of eigenvectors when used in the computer vision problem of human face recognition.
● The eigenvectors are derived from the covariance matrix of the probability distribution over the high-dimensional vector space of face images.
● The eigenfaces themselves form a basis set of all images used to construct the covariance matrix. An example of they look is given in figure given below. This produces dimension reduction by allowing the smaller set of basis images to represent the original training images.
● Classification can be achieved by comparing how faces are represented by the basis set.

2.2.2 Eigenfaces in Python

The algorithm discussed above can be implemented in python using OpenCV. 
The Eigenfaces method in OpenCV performs face recognition by:
1) Projecting all training samples into the PCA subspace.
2) Projecting the query image into the PCA subspace.
3) Finding the nearest neighbor between the projected training images and the projected query image.

Results and Conclusion:

ORL Dataset: 

Correct Predictions:

![image](https://user-images.githubusercontent.com/121651746/217105597-9b1caa2d-6b69-40d9-8d68-314874d1b36f.png)

Incorrect Predictions:

![image](https://user-images.githubusercontent.com/121651746/217105703-0c2868b6-f0fb-4017-bdc0-aa8762f6beb1.png)

Result:
Accuracy Score: 0.9487

Labelled Faces in the wild dataset:

Correct Predictions:

![image](https://user-images.githubusercontent.com/121651746/217106070-e4d49862-d948-4ea2-b0f4-d87707e7e065.png)

Incorrect Predictions:

![image](https://user-images.githubusercontent.com/121651746/217106145-319defc3-9bbc-4539-85b8-8bec6c43b87c.png)

Result:
Accuracy Score: 0.7943

Conclusion:

After Running the EigenFace model on both the datasets the Accuracy Score was approximately 0.7943 for the Labelled faces in the Wild dataset and 0.9487 for the ORL dataset. On examining the results we can conclusively say the following about the model:

1) Easy to implement and computationally less expensive.
2) No knowledge (such as facial features) of the image is required (except id).
3) Proper centered face is required for training/testing.
We can see that when the face is rotated too much or if there are a lot of occlusions it fails to recognize the face in the first dataset. To further prove this I tested it on the ORL dataset in which all the pictures were taken of the people had almost centered face and there were never objects covering portions of the face. Another interesting thing to be noticed is that the algorithm can recognize quite efficiently if the person is wearing glasses(The transparent ones where the eyes are still seen). But if the person is wearing shades that cover the eyes completely then it doesn’t recognize the person.
4) The algorithm is sensitive to lighting, shadows and also the scale of the face in the image.
5) Front view of the face is required for this algorithm to work properly at least to train efficiently











