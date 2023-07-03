# Deep-Learning-textual-reviews

This report is regarding a Deep Learning project. It involves training a deep neural network to predict the rating of a review starting from its textual contents. The solution is made using the free version of Google Collab, It includes relevant frameworks, particularly TensorFlow with the related Keras interface.

The project is fairly simple to run. I wanted to take advantage of the free TPU-processing from Google to speed up the training, hence the code is written within code blocks using an instance of “tf.distribute.TPUStrategy”. Note that this is only an optional setting which can be set in Settings -> Runtime -> Change runtime type. If the TPU is not enabled, it will fall back on the default setting on the computer running it, which is typically the local GPU. Alternatively you could use one of the GPUs available from Google Collab which will work just fine.

The dataset is imported using the Kaggle API, to avoid downloading the entire data frame to the local computer. Before doing preprocessing, a sample is collected from the dataset using the standard built-in Python libraries. Only one JSON-file in the collection is used for the project, specifically the “yelp_academic_dataset_review.json” file.

Note that the hyperparameter tuning might not run efficiently if you are using the TPU. If some problems arise when trying to run the tuning chunk it is advisable to switch to GPU. This is what worked for me when running the project as the directory in Google Collab may not support TPU in some occasions. 

The model is using some prebuilt models. In particular the word2vec model is used for embedding of our textual data. It consumes a bit of memory but should still be within the limits of a standard computer RAM by a good margin.

Otherwise, the project can be run normally.

Some additional notes:
I had some problems receiving high accuracy on my models. Some of them performed OK, some of them yielded lower accuracy. Even though the models themselves does not deliver high accuracy I still delivered the project as it is because I think it leaves room for discussion.

I was not able to determine the exact reason for the overfitting and somewhat low accuracy. It may be that the model was to complex.  


1.	The considered version of the dataset  (in terms of access date, as the dataset is updated very frequently), and the parts of the latter which have been considered
•	The latest version as of 03/07/2023

2.	how data have been organized
•	The data has been loaded using the Kaggle API, and loaded into batches for preprocessing as it is a very big dataset. 
3.	the applied pre-processing techniques
•	As described in the notebook itself, Word2vec and Keras has been used mainly. The numerical features are simple, the text needed to be processed using embedding.
4.	the considered algorithms and their implementations
•	I have tested different solutions, mostly within the RNN architecture. They are implemented with different layers and techniques to test how the model will perform with the given data.
5.	how the proposed solution scales up with data size
•	As the data is loaded in batches, to scale it up you would simply use more batches to as input to the training model. I have used a relatively small batch as I prioritized efficiency and time, while also trying to stay below the limits of the free TPU/GPU of Google Collab.
6.	a description of the experiments
•	It is further described in the notebook itself, but the experiments consists of different aspects with the models themselves. From simple to more complex RNNs, I tried to use different techniques to see how the model would perform under different structures. 
7.	comments and discussion on the experimental results
•	I spent a lot of time trying to improve the models, but got a relatively low accuracy on my results. But I thought that gaining the highest accuracy was not necessarily the point of the project, so I accepted lower results and rather experimented with different models. If I had more time I would use it to improve my model and find out exactly how to improve it.



Declaration:

I declare that this material, which I now submit for assessment, is entirely my own work and has not been taken from the work of others, save and to the extent that such work has been cited and acknowledged within the text of my work. I understand that plagiarism, collusion, and copying are grave and serious offences in the university and accept the penalties that would be imposed should I engage in plagiarism, collusion or copying. This assignment, or any part of it, has not been previously submitted by me or any other person for assessment on this or any other course of study.
