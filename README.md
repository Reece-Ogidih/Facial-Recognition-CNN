# Facial Recognition CNN

### Inspiration

I was inspired into creating this project shortly after I completed my Machine Learning 2 coursework assignment, which was centered around creating an image search engine using supervised learning methods. Naturally, this resulted in me spending a lot of time contemplating methods to assess similarity between images. During my work, I thought about the practical uses of image similarity outside of a search engine, and one of the first applications that came to mind for me was facial recognition. Due to how completely captivated I am by CNN's and NN's in general, I decided to apply my own knowledge as well as further it by beginning this project.

### Approach

NOTE: This area of the README is subject to change as I undergo the building and testing of my NN

My approach to developing this project can be broken down into a few stages, Data Handling, Model Development, Training and Testing. 

Firstly, I am woring with LFW a huge dataset of images of people that are labelled by the individual's name, I will first build a face detection algorithm that will allow me to detect the persons face and then align and resize the faces so that they're of equal dimensions. I will then normalise to help improve the conditioning of the optimisation problem. Due to dataset size, images will be fed into the model in batches. I will also use additional techniques such as batch normalisation and principle component analysis. Upon completing the first version of the model in its entirety, I will directly update with a full list of data handling techniques used.

The model itself is going to assess similarity using the cosine similarity score. The reason behind this decision is due to the cosine similarity score being impervious to the magnitudes of the vectors, which in this case can help my model be more robust to brightness disparencies. My CNN will follow a Resnet architecture due to it utilising skip connections, which help to address the vanishing/exploding gradient problem that can occur when training very deep neural networks. The feature map of the ResNet CNN will then be passed through some fully connected layers in order to optain the feature vector for each image which will then be handled as explained previously in order to assess similarity. If this resulting similarity score is within a boundary (which will be adjusted during training) the model will accept them as the same person, else they will be dclassified as a different person. 

Regarding specifics for hyperparameters, I will again update the README with the full list when the version has been fully built but I am expecting to use ReLu activation functions, Adam optimisation and minibatch GD. I am also expecting to do "same" oadding and a stride length of one since the information contained at the border of the images may be of use. 

I will use the Binary Cross-Entropy loss function . It is during this stage that I would use the validation loss to constantly adjust my algorithm.  If I am concerned with overfitting, then methods such as early-stopping, weight decay and dropout regularisation, however many of htese techniques I plan to implement directly in my first version already. 

For testing, I will split the LFW dataset into a training, validation and testing set, with a split of approximately 70:15:15. I will  maintain consistent preprocessing (resizing and normalization) across all sets. 

### Versions

V1 - Face Detection and Face Alignment algorithms introduced.
