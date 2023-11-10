# Artificial Neural Networks and Deep Learning 2023 - First Homework
Image Classification
IMPORTANT COMMUNICATION: PHASE 2 POSTPONED! SEE THE RELATED THREAD IN THE FORUM.
Welcome to the first Homework of the Artificial Neural Networks and Deep Learning course! You have the opportunity to test what you learned during the course and to compete with your classmates! 😎

In this homework you are asked to classify plants (like the ones in the example image below) that are divided into two categories according to their state of health. It is a binary classification problem, so the goal is to predict the correct class label in {0, 1}.

### Important link:
to the folder wiht data + tips 
https://drive.google.com/drive/folders/152B-_69uFDqnDyBIbS0gEhjlwHmqEKeB?usp=drive_link

For the moment we tried simple data augmentation (zoom, flip, contrast...), and use of transfer learning that gives the best results for the moment. 
Our best upload on codalab gave those results :
set1_score_accuracy: 0.780000000000
set1_score_precision: 0.785714285714
set1_score_recall: 0.578947368421
set1_score_f1: 0.666666666667

we still need to combine data augmentation with transfer learning, and adjust our parameters, it is only the beginning.

Also we found some outliers in the database, still need to take care of that.


# Data
Dataset Details:
Image size: 96x96
Color space: RGB
File Format: npz
Number of classes: 2
Classes:
0: "healthy"
1: "unhealthy"
Dataset Structure
Single folder:
training: containing the 'public_data.npz' file. The file contains the following items:
'data': numpy array of shape 5100x96x96x3, containing the RGB images.
'data': 3-dimensional numpy array of shape 5200x96x96x3, containing the RGB images.
'labels': 1-dimensional numpy array of shape 5200 with values in {'healthy', 'unhealthy'}
Data Download
You can access and download the zipped dataset on the 'Homework1' folder shared with you on the Google Drive course folder.

The data is located within the document 'training_dataset_homework1.zip', which contains the file 'public_data.npz'.

Data Loading
The provided dataset is in zip format. 

After the unzip, we suggest using the numpy.load('public_data.npz', allow_pickle=True) function to read it.

Please notice that no automatic validation set is provided.

External Data
The use of external data is strictly forbidden.

In detail, what is allowed to be used:

Libraries not seen during lectures and labs (bearing in mind that you will be limited to those selected by us during submission)
Models pre-trained on imagenet by keras.applications (for transfer learning and/or fine tuning)
And what is NOT allowed to be used:

Any source of data that has not been provided by us, especially if to be used for training purposes
Any pre-trained model not belonging to keras.applications and/or not pre-trained on imagenet 


# Evaluation
Homework Evaluation
The problem is a binary classification problem. Thus, you must provide for each image in the test set the corresponding predicted class in {0, 1}. In the following the guidelines you must follow:

Only the training set is given. The test set is not provided. You must submit directly your code for evaluation. See the details in Submission Format in this page.
The metric used to evaluate models and place the Teams in Leadeboard is the Accuracy. The score is computed as
Accuracy = Σ1≤i≤N(predictionsi == targetsi) / N , where N is the total number of images in the test set

Two-Phases Competition
We organized the homework as a two-phases competition:

Phase 1: development phase. We provide you with labeled training data. Your submissions will be evaluated on an hidden test set. The score obtained by your models will be displayed on the leaderboard.
Phase 2: final phase. Your submissions will be evaluated on an final hidden test set (different from the one of Phase 1), to compute the final Leaderboard. During this phase you have the possibility of performing maximum 2 submissions. Choose the model you think is the best based on the results on Phase 1.
IMPORTANT: To complete the Homework you must participate in both the phases, and each team member must have succesfully submitted at least one model in at least one phase. Please notice that the duration of Phase 2 is very short, you will have only 2 days. This is because you must only re-submit your best model. 

Submission Format
You are required to submit your code instead of directly providing the predictions. To do so, you must follow the following submission format:

submission must be a zip file (e.g., submission.zip) containing two files: model.py and metadata. The names of these two files must not be changed. 
the metadata file is just an empty file that is required by CodaLab to mark the submission as a "code" submission. Please add it in the zip file as shown in the starting kit.
the model.py file will contain the code you submit for the evaluation. To be compatible with the evaluation backend, it must have the structure reported in the example below. The script must contain the class model's definition, which must have at least two functions: __init__ and predict. In the __init__ function you are required to create and load the model (or the model components), while in the predict function the model is used for predicting the class corresponding to the input X. Please notice that the given definition of these two functions must be respected, i.e., the argument path in the init function must be always provided, as well as the argument X of the predict function. If one of the argument is missing from the class functions you submit, the overall evaluation procedure will raise an error. You can find a submission example in the provided Starting Kit.
