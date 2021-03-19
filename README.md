# Semantic Segmentation using AWS SageMaker


## AWS SageMaker
- Amazon SageMaker is a fully managed machine learning service. With Amazon SageMaker, data scientists and developers can quickly build and train machine learning models, and then deploy them into a production-ready hosted environment.

- SageMaker removes the heavy lifting from each step of the machine learning process to make it easier to develop high quality models. SageMaker provides all of the components used for machine learning in a single toolset so models get to production faster with much less effort and at lower cost.

## Semantic Segmentation
- The SageMaker semantic segmentation algorithm provides a fine-grained, pixel-level approach to developing computer vision applications.
- It tags every pixel in an image with a class label from a predefined set of classes. Tagging is fundamental for understanding scenes, which is critical to an increasing number of computer vision applications, such as self-driving vehicles, medical imaging diagnostics, and robot sensing.
- For comparison, the SageMaker Image Classification Algorithm is a supervised learning algorithm that analyzes only whole images, classifying them into one of multiple output categories. 
- The algorithm classifies every pixel in an image, it also provides information about the shapes of the objects contained in the image. 
- The segmentation output is represented as a grayscale image, called a segmentation mask. 
- A segmentation mask is a grayscale image with the same shape as the input image.

## Implementation
- I have explored the Oxford IIIT Pet's data with 37 category with 200 images for each class. All images have an associated ground truth annotation of breed, head ROI, and pixel level trimap segmentation. 
- First, I've ingested the data from the source and visualize the data using images and annotations.
- SageMaker setup is equally necessary to get the training image data ready to use.
- Prepared the data by splitting the data into training(75%) and validation(25%) data set.
- Uploaded the data to s3 buckets created while SageMaker setup.
- Defined the SageMaker Estimator to provide role, instance details, input mode, output path, etc.
- Defined the hyperparameters to tune the algorithm with details of built-in algorithms such as Fully-Convolutional Network (FCN), backbone details, etc.
- Configured the data channels for training the model.
- Trained the model using images and annotations.
- Deployed the trained model on EC2 instance.
- Performed inference/predictions using the deployed model.

## Data Source

Image Data: https://www.robots.ox.ac.uk/~vgg/data/pets/data/images.tar.gz

Groubd Truth Data: https://www.robots.ox.ac.uk/~vgg/data/pets/data/annotations.tar.gz

## References

- https://docs.aws.amazon.com/sagemaker/latest/dg/semantic-segmentation.html

- https://www.robots.ox.ac.uk/~vgg/data/pets/
