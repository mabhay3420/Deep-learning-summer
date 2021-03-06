# Simple implementation of Principal component analysis

Principal component analysis is a simple yet powerful tool. Machine learning/Deep learning represent information in terms of high-dimensional vectors which are hard to visualize if plotted as such. One of the application of PCA is visualizing multidimensional data by plotting them on 2-D plot. Now this might not seem interesting, one might say, Just plot the data on x-y plane , but it's not just about plotting, rather we want to see the truest picture possible.

As a simple example, consider 2 points in 3-D space A(1,0,0) and B(2,0,0). We want a 2-D picture, so let's project these points into X-Y plane and Y-Z plane and X-Z plane : A_xy(1,0), B_xy(2,0) and A_yz(0,0) , B_yz(0,0) and A_xz(1,0) , B_xz(2,0). The Y-Z representation is useless in the sense that it does not give us the true picture of the data set. Thus, we need to choose an optimal 2-D plane to project our data upon.

If we want to convert n-D data into k-D data we want a k-D optimal plane. PCA says that the k-axes of this optimal k-D plane are ** k-eigen vectors corresponding to largest k eigen values of X<sup>T</sup>X **, where X is the matrix representing the data.[Proof here](https://www.deeplearningbook.org/contents/linear_algebra.html).

The Code first shows toy examples of encodeing 3-D data into 2-D values and then shows how Learned representation of MNIST data form a beautiful pattern in 2-D space.

# Practical Use of PCA : Visualize higher Dimensional representations

Usually in Deep learning, we start with a very high Dimensional data and then by doing many transformation we convert it into some lower Dimensional data which is then used to make decisions. This lower Dimensional data is rarely 2-D or 3-D as it might not contain enough information for decision making. for example consider a simple digit recognition model trained on MNIST dataset which finally converts each of the images into 10-Dimensional data and then uses a final softmax layer to decide the category of image. I have stored the 10-D representation ( and not the probabilities of various classes) of images and their category.The data is saved from this [simple Implementation](https://github.com/mabhay3420/Deep-learning-Projects/blob/master/Introduction_2_ANN/CNN_LeNet_Implementation/MNIST_classification_model_in_pytorch.ipynb).

One other such visualization is helpfull when we convert words to vector ([word_2_vec tutorial](http://mccormickml.com/2016/04/19/word2vec-tutorial-the-skip-gram-model/)). When we viusualize the results in simple 2-D we get to see that the similar words are very near to each other. ([Simple Implementation](https://github.com/mabhay3420/Deep-learning-Projects/blob/master/Introduction_2_ANN/Autoencoders_NLP_basics_seq2seq_skipGram/Skip_Gram_word2vec.ipynb))
