## PROJECT OVERVIEW

This chatbot was built in TensorFlow using the new sequence to sequence (NMT) model, with certain rules integrated seamlessly.

Cleverbot's core was built on the NMT model, which has been adapted to meet the needs of a chatbot. Because of changes to the tf.data API in TensorFlow 1.4, as well as numerous other changes since TensorFlow 1.12, this ChatLearner version only supports TensorFlow versions 1.4 through 1.11. If you need to support TensorFlow 1.12, simple updates can be made to the tokenizeddata.py file.



## Project Design and coding

![image](https://user-images.githubusercontent.com/118036772/209660742-ed023f6d-e1c0-419d-90af-ac39b4062aff.png)

Project Execution
       During the project execution phase, our team performs the actual work. As a project manager, it is your responsibility to design effective workflows and closely monitor the team's progress. Execution of project are necessary actions to be taken that ensures activities in the project plan meet their goal. This includes procuring any new hardware, software and introduce procedures during the allocated operations. This is where most resources are allocated among all project phases. Many project sponsors and customers focus on the reliability of the product of the project. Hence, it is important to keep track of change requests and prepare to update project plan in documents as each step taken will affect the total outcome.

   Potential Risk
This lists the potential risk that most likely be overlooked during execution. As such, the allocated team must keep these in mind.
1.	Lack of encryption during customer-chatbot communication (-, n.d.)
2.	Insufficient protocols
3.	Security vulnerabilities of hosting platform used by chatbot 
4.	Lack of employee education
5.	Lack of answers from chatbot
6.	Overlooking a plan to scale may cause short-lived product  (How to Overcome the Top Seven Risks of Your First Chatbot Project, 2022)
7.	The server traffic must be optimum
8.	Failing to fulfil end user’s requirement
For this small project, Abu would monitor closely all team members to ensure the project does not stray from objectives and produce the desired outcome. Abu would make use of his excellent communication and networking skill to inquire input from other people in the firm free of charge. He would make sure that everyone understands what we are developing and how it would help them in their endeavour. 

Training model
Training model is a dataset that is used to train the machine learning algorithm. Currently, the team has yet figured out the most suitable training model for the chatbot project. Thus, a team is formed to try-and-run several recommended already made chatbot model and is given a week. At the same time, our expert communicator, Abu, knows a few of his friends has experiences on this and will attempt to make contact.

### Training

During the training, I really suggest you to try playing with a parameter (colocate_gradients_with_ops) in function tf.gradients. You can find a line like this in modelcreator.py: gradients = tf.gradients(self.train_loss, params). Set colocate_gradients_with_ops=True (adding it) and run the training for at least one epoch, note down the time, and then set it to False (or just remove it) and run the training for at least one epoch and see if the times required for one epoch are significantly different. <br>

Other than those, training is straightforward. Remember to create a folder named Result under the Data folder first. Then just run the following commands: <br>
cd chatbot
python bottrainer.py

<br>Good GPUs are highly recommended for the training as it can be very time-consuming. If you have multiple GPUs, the memory from all GPUs will be utilized by TensorFlow, and you can adjust the batch_size parameter in hparams.json file accordingly to make full use of the memory. You will be able to see the training results under Data/Result/ folder. Make sure the following 2 files exist as all these will be required for testing and prediction.<br>

1.basic.data-00000-of-0000
2.basic.index

![image](https://user-images.githubusercontent.com/118036772/209769828-88f60bd9-6406-4948-9dd9-886d7777b874.png)



User Interface (UI) Design
Our expert graphic designer, Lee, and expert web designer, Yun Jin, will collab to create the UI for the chatbot for the visitor to see and a dashboard for the admins. Currently, there are no clear picture as to what functionality the UI need to have apart from the customer point of view: “clean and green” is what the client’s quote. This team will attempt to realize the client’s vision and an array of recommendations will be presented during the next meeting.
![image](https://user-images.githubusercontent.com/118036772/209770286-4b48a5bb-5a51-487f-978f-a6cce68a8fe1.png)



Finding Dataset
The challenge of developing an AI-powered chatbot is that a requires a huge amount of data (Industry Knowledge How to Collect Chatbot Training Data for Better CX, 2022). The goal is to create the most accurate response according to what the client’s need. To do so, the CEO and Abu will have to attend the board meeting and relay the company’s policy and business understanding. A team of three will be responsible for finding dataset for the machine learning algorithm for natural speech and business-related Q&A. The dataset must be compatible with the model, however. That is why during the try-and-run model, this team will be responsible for natural speech for the time being. The data will be collected from various social media and mostly the company’s recorded customer services. Abu will attempt to acquire the recordings during the board meeting.

Dataset used in this project :

### Conversational Data Set

1.The data is divided into two sets: the first was handcrafted, and the samples were created in order to maintain a consistent role of the chatbot, who can thus be trained to be polite, patient, humorous, philosophical, and aware that he is a robot, but pretending to be a 9-year-old boy named Papaya; the second set was cleaned from some online resources, including scenario conversations designed for training robots, Cornell movie dialogues, and cleaned Reddit datum.<br>
2.The training data set is divided into three categories: two will be augmented/repeated during training at different levels or times, while the third will not. The augmented subsets are used to train the model with rules to follow as well as some knowledge and common sense, while the third subset is simply used to assist in training the language model.<br>
3.This repository contains a cleaned subset of Reddit data (about 110K pairs). Based on all of the included data files, the vocab file and model parameters are created and adjusted. If you require a larger set, scripts to parse and clean Reddit comments can be found in the Corpus/RedditData folder. To use those scripts, you must first download a torrent of Reddit comments from this torrent link. Normally, a single month's worth of comments suffices (can generated 3M pairs of training samples roughly).<br>
4.The data files in this data set have already been preprocessed with the NLTK tokenizer and are ready to feed into the model using TensorFlow's new tf.data API.<br>
![image](https://user-images.githubusercontent.com/118036772/209769543-9d77976a-cdd1-41b4-83c8-0c5350d05ab2.png)


Test the Model
Finally, testing the model is a crucial moment-of-truth. Naturally, the team that develops the coding and integrating does a lot of testing. However, Erica and her team will be in charged in testing the model in the real world. She will find volunteers to try the model and conduct a survey of how “clean and green” it feels to the users. Any important pointers will be noted down and if there is anything to improve the team will resend back to the coding team and apply any changes. 
 
 ### Testing

We provide a simple command interface as well as a web-based interface for testing and prediction. It should be noted that the vocab.txt file (as well as files in the KnowledgeBase for this chatbot) is required for inference. Use the following command interface to quickly see how the trained model performs:<br>

cd chatbot
python botui.py

![image](https://user-images.githubusercontent.com/118036772/209769650-a864342a-cd3f-443d-8946-94edd7bf6bf0.png)







![image](https://user-images.githubusercontent.com/118036772/209682749-ec65a7fb-5266-448b-b4ef-329c3a1f237c.png)

Monitoring and Controlling 

The fourth phases of the project management process are not consecutive. The project monitoring and control phase runs concurrently with project execution, ensuring that project objectives and deliverables are achieved. Project monitoring and control seamless execution of tasks, and helps improve efficiency and productivity of the project. Monitoring allows you to control the project including completing the project on time. The process of monitoring and controlling a project permits managers to establish effective project timelines, including scope, budget, and schedule. This data can then be utilised throughout the project's lifecycle to track its progress.

Monitor Key Performance Indicators (KPIs)
Monitoring KPIs keeps project deliverables on track and performance up to date. Project managers use data on timelines, budgets, and quality to enable better decisions, make changes to avoid problems, and capitalize on opportunities. The process of development can be supervised through analysis coding lines.

Monitor Change Requests
Measuring project performance data aids in determining whether the project is on track or whether adjustments are required. If the project is veering off course, a change request will be submitted and implemented to bring it back on track. For example, the training dataset may need to change if it can’t meet the target performance. So the change requests need to be sent immediately to avoid delays to another process. 

Monitor Project Scope
This stage ensures that any modifications to the project's scope are confirmed and recorded. You must update all pertinent papers, including the project scope statement and work breakdown structure. Additionally, you will need to assess any time and cost adjustments that may result from a change in approach due to a scope expansion. In this project it will be the boundaries of the ability of chatbot.

Identify Risks
Ideally, risk identification should occur throughout the duration of a project, so that when risks arise, you have the necessary information to make the correct decision. For example, the risk of hiring senior or junior IT chatbot engineers is analysed.

Maintenance
Maintaining consistent communication keeps projects on track and helps avoid costly misunderstandings. It is essential that stakeholders and team members receive all pertinent information promptly. Inform the update of the development chatbot process to them currently.



 


![image](https://user-images.githubusercontent.com/118036772/209770767-5343cf5c-333c-4abb-80a8-30f6975a1a3f.png)






