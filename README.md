Download Link: https://assignmentchef.com/product/solved-ct5133-ct5145-assignment-11
<br>



<strong>Real-time Object Detection and</strong>

<strong>Classification</strong>

<h1>Submission via Blackboard</h1>

Design and implement a computer vision model pipeline and perform matching to identify events from a given video stream. Figure 1 shows the high-level block diagram architecture of the pipeline. The pipeline consists of a video reader and a model cascade. The task is to detect object events (car) with a specific attribute (car type). The pipeline can be developed in Python (highly recommended) or Java <a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a>.

<strong>Video: </strong>The given <a href="https://nuigalwayie-my.sharepoint.com/:v:/g/personal/m_khan12_nuigalway_ie/Ef58UTqhjlxEgEUZ3ZVuNvQBn_ucduz8NiBwZn87GqqEFQ?e=SxJbKd">video clip</a> (duration 30 seconds) is of a road cross-section.

<strong>Pipeline Design: </strong>Implement a pipeline that processes the video frames using a DNN model(s).

<strong>Pipeline Input: </strong>Stream the video stream into the system by using a video reader (fig. 1) at a rate of 30 frames per second. This requires reading the video file and simulating a stream of image frames as individual data items.

<strong>Model Cascade: </strong>The model cascade will be a 2-stage computer vision pipeline. The following steps need to be performed to build the model cascade:

<strong>Stage 1: Object Detector: </strong>Deploy a state-of-the-art object detector model (TinyYolo), pre-trained on PASCAL VOC or MSCOCO dataset. Tiny YOLO model and weights can be downloaded here: <a href="https://github.com/qqwweee/keras-yolo3">https://github.com/qqwweee/keras-yolo3</a><a href="https://github.com/qqwweee/keras-yolo3"><strong>/ </strong></a><a href="https://pjreddie.com/darknet/yolo/">https://pjreddie.com/darknet/yolo/</a>

<ul>

 <li><strong>Stage2- Attribute Classifier (Car Type): </strong>Train an existing pretrained object classifier (Mobilenet from Keras library: <a href="https://keras.io/applications/">https://keras.io/applications/</a> or DeepLearning 4j for Java) using a transfer learning approach for two car classes:</li>

</ul>

○    SUV

○    Sedan

The input to this attribute classifier will be the Region of Interest obtained from Stage-1.

<ul>

 <li><strong>Dataset Preparation for Stage 2: </strong>Students need to create a small dataset of images to train the classifier. The more images, the better the classifier will be trained. It’s recommended to download at least 400 images (SUV and Sedan) (scrape it from google using any image downloading api) for each class and divide the dataset into 80:20 ratio] for training and testing. Split the training set into 80:20 ratio for training and validation set.</li>

</ul>

<strong>Queries: </strong>Two queries need to execute after deploying the model pipeline. The queries are lined with their increasing complexities.

<ul>

 <li><strong>Q1 [Object Detection Task]: </strong>Identify and count the number of cars in each frame.</li>

 <li><strong>Q2 [2-Stage Model Cascade- (Object Detection Attribute Classifier (Car Type))]:</strong></li>

</ul>

Identify and count the cars and their types in each frame.

<strong>Optimisation: </strong>Implement a processing flow optimization of the pipeline and the model cascade for Q1 and Q2. One option is to use a producer consumer, where the producer thread continuously streams video frames and sends it to an internal queue from where the consumer (DNN models) read the frames from the queue and process them.

<strong>Output and Results Evaluation: </strong>Record your results in the format given below and compare your results to the <a href="https://nuigalwayie-my.sharepoint.com/:x:/g/personal/m_khan12_nuigalway_ie/EZlUHkoMjNNBlHr0CuxW3HQBb5bMyEI58CJj8DQ9I0m14g?e=SjBN3B">ground truth</a>.

For Q1 and Q2 do the following:

<ul>

 <li>Compare the count with ground truth and report the accuracy (F1 Score).</li>

 <li>Report the training accuracy of the car type classifier.</li>

 <li>Report the throughput of Q1 and Q2.For the evaluation, the experiment section of <a href="https://www.researchgate.net/publication/337339754_VidCEP_Complex_Event_Processing_Framework_to_Detect_Spatiotemporal_Patterns_in_Video_Streams">VidCEP</a> paper can be useful to consult.</li>

 <li>Report on the effects of your flow optimisation for Q1 and Q2.</li>

</ul>

<h1>Code (50 Marks)</h1>

<ul>

 <li>Pipeline Design</li>

 <li>Dataset Preparation (download 500 images of each class)</li>

 <li>Preprocessing</li>

 <li>Deploying the pre-trained SOTA Object Detector [TinyYolo]</li>

 <li>Car Type Classifiers</li>

</ul>

Model Cascade Deployment

<ul>

 <li>Pipeline Optimisation</li>

 <li>Comments to explain your source code. Insufficient comments will lead to mark deductions.</li>

</ul>

<h1>Report (50 Marks)</h1>

You are required to submit a short report (approximately 4-5 pages including references) specifying:

<ul>

 <li><strong>Pipeline Design: </strong>A description of your approach and design decisions. This should include details on the flow of the pipeline, details of video reader, object detector and classifier. Justify your design decisions.  Where appropriate include appropriate diagrams and references to research papers to support your arguments.</li>

 <li><strong>Pipeline Output: </strong>Detail the output of your pipeline with all the graph results (event extraction, throughput etc).</li>

 <li><strong>Model Training Evaluation: </strong>Description about how the classifier model is trained which includes dataset preparation to transfer learning approach and training process. Report the accuracy of the trained model.</li>

 <li><strong>Pipeline Optimisation: </strong>A description of how you have optimized the execution of the pipeline and the Model Cascade. Report the improvement of the optimised pipeline. Justify your design decisions.</li>

 <li><strong>Design Strengths and Weaknesses: </strong>Detail the Strengthens and Weaknesses of your approach Justify your design decisions. Where appropriate include references to research papers to support your arguments. (minimum 1 Page)</li>

 <li><strong>Download Link for Submission Files: </strong>Provide a download link for the ZIP archive containing your demo video, code and the CSV file with complete results.</li>

</ul>

<h1>Groups and Individual</h1>

The assignment may be completed as a group. Each group can have a maximum of 2 students. Groups are self-selected. Please email your group ( students name) at <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="d0bab1bcb5b5b4febbb8b1be90b9bea3b9b7b8a4fdb3b5bea4a2b5febfa2b7">[email protected]</a> by the end of day Friday 19<sup>th </sup>Feb.  If you cannot form a group or have any other doubt, please connect with Jaleed at the above mail.

There is also the option to complete the assignment as an individual. Please email <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="5f353e333a3a3b7134373e311f36312c3638372b723c3a312b2d3a71302d38">[email protected]</a> to confirm you will complete it as an individual by the end of day Friday 19<sup>th </sup>Feb. For students who have not contacted Jaleed, we assume you will complete it as an individual.

Grading will be appropriate for individual and group submissions.

<ul>

 <li>s. Mistakes cannot be corrected once the deadline has passed.</li>

</ul>

[1]

For java users: <a href="https://deeplearning4j.org/">https://deeplearning4j.org/</a> library consists of TinyYolo and Mobilenet model.

<a href="#_ftnref1" name="_ftn1">[1]</a> For java users: <a href="https://deeplearning4j.org/">https://deeplearning4j.org/</a> library consists of TinyYolo and Mobilenet model.