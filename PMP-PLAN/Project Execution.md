##PROJECT OVERVIEW
This chatbot was built in TensorFlow using the new sequence to sequence (NMT) model, with certain rules integrated seamlessly.

Cleverbot's core was built on the NMT model, which has been adapted to meet the needs of a chatbot. Because of changes to the tf.data API in TensorFlow 1.4, as well as numerous other changes since TensorFlow 1.12, this ChatLearner version only supports TensorFlow versions 1.4 through 1.11. If you need to support TensorFlow 1.12, simple updates can be made to the tokenizeddata.py file.

###Conversational Data Set
1.The data is divided into two sets: the first was handcrafted, and the samples were created in order to maintain a consistent role of the chatbot, who can thus be trained to be polite, patient, humorous, philosophical, and aware that he is a robot, but pretending to be a 9-year-old boy named Papaya; the second set was cleaned from some online resources, including scenario conversations designed for training robots, Cornell movie dialogues, and cleaned Reddit datum.
2.The training data set is divided into three categories: two will be augmented/repeated during training at different levels or times, while the third will not. The augmented subsets are used to train the model with rules to follow as well as some knowledge and common sense, while the third subset is simply used to assist in training the language model.
3.This repository contains a cleaned subset of Reddit data (about 110K pairs). Based on all of the included data files, the vocab file and model parameters are created and adjusted. If you require a larger set, scripts to parse and clean Reddit comments can be found in the Corpus/RedditData folder. To use those scripts, you must first download a torrent of Reddit comments from this torrent link. Normally, a single month's worth of comments suffices (can generated 3M pairs of training samples roughly).
4.The data files in this data set have already been preprocessed with the NLTK tokenizer and are ready to feed into the model using TensorFlow's new tf.data API.

###Training
During the training, I really suggest you to try playing with a parameter (colocate_gradients_with_ops) in function tf.gradients. You can find a line like this in modelcreator.py: gradients = tf.gradients(self.train_loss, params). Set colocate_gradients_with_ops=True (adding it) and run the training for at least one epoch, note down the time, and then set it to False (or just remove it) and run the training for at least one epoch and see if the times required for one epoch are significantly different. 

Other than those, training is straightforward. Remember to create a folder named Result under the Data folder first. Then just run the following commands: 
cd chatbot
python bottrainer.py

Good GPUs are highly recommended for the training as it can be very time-consuming. If you have multiple GPUs, the memory from all GPUs will be utilized by TensorFlow, and you can adjust the batch_size parameter in hparams.json file accordingly to make full use of the memory. You will be able to see the training results under Data/Result/ folder. Make sure the following 2 files exist as all these will be required for testing and prediction.

1.basic.data-00000-of-0000
2.basic.index

###Testing
We provide a simple command interface as well as a web-based interface for testing and prediction. It should be noted that the vocab.txt file (as well as files in the KnowledgeBase for this chatbot) is required for inference. Use the following command interface to quickly see how the trained model performs:

cd chatbot
python botui.py

##Project Design and coding






