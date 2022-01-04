# Automatic Number Plate Recognition with standard VS squared plate classification
<p>This set of Notebooks heavily relies on Nicholas Renotte's <a href="https://www.youtube.com/watch?v=0-4p_QgrdbE&t=2972sprovides">tutorial</a> showing how to build a Number Plate Recognition model, train it and run it on several test images. The main difference betewen my code and his are :
  
  - Minors changes in the folders' paths (TF API was already installed on my machine)
  
  - Added a class (suqared_licence) and finetuned the detection model to be able to differentiate between squared and standard plates.
  
  - Tried another OCR (Keras_OCR) to compare with EasyOCR used by Nicholas.
  
  - Ran the OCR on different region of the plate if it is recognized as a squared plate.
  

<img src="https://ibb.co/yhshSwT">

## Steps
<br />
<b>Step 1.</b> Clone this repository: https://github.com/jafarpenot/ANPR
<br/><br/>
<b>Step 2.</b> Create a new virtual environment 
<pre>
conda create ANPR
</pre> 
<br/>
<b>Step 3.</b> Activate your virtual environment
<pre>
conda activate ANPR
</pre>
<br/>
<b>Step 4.</b> Install dependencies
<pre>
pip install requirements.txt
or
</pre>
<pre>
python -m pip install requirements.txt
</pre>
<br/>
<b>Step 5.</b> Open Jupyter Notebook
<pre>
jupyter notebook
</pre>
You can also open and run in colab. In this case, you might want to install the dependencies (requirements.txt) in colab.

In the curent version of the Notebook, the model is pretrained and loaded as it is (checkpoint-11) for detection. You can skip the training process and simply use the pretrained model, or you can train it from scratch with the provided dataset (locatel in Tensorflow/. 

Collect images using the Notebook <a href="https://github.com/nicknochnack/TFODCourse/blob/main/1.%20Image%20Collection.ipynb">1. Image Collection.ipynb</a> - ensure you change the kernel to the virtual environment as shown below
<img src="https://i.imgur.com/8yac6Xl.png"> 
<br/>
<b>Step 6.</b> Manually divide collected images into two folders train and test. So now all folders and annotations should be split between the following two folders. <br/>
\TFODCourse\Tensorflow\workspace\images\train<br />
\TFODCourse\Tensorflow\workspace\images\test
<br/><br/>
<b>Step 7.</b> Begin training process by opening <a href="https://github.com/nicknochnack/TFODCourse/blob/main/2.%20Training%20and%20Detection.ipynb">2. Training and Detection.ipynb</a>, this notebook will walk you through installing Tensorflow Object Detection, making detections, saving and exporting your model. 
<br /><br/>
<b>Step 8.</b> During this process the Notebook will install Tensorflow Object Detection. You should ideally receive a notification indicating that the API has installed successfully at Step 8 with the last line stating OK.  
<img src="https://i.imgur.com/FSQFo16.png">
If not, resolve installation errors by referring to the <a href="https://github.com/nicknochnack/TFODCourse/blob/main/README.md">Error Guide.md</a> in this folder.
<br /> <br/>
<b>Step 9.</b> Once you get to step 6. Train the model, inside of the notebook, you may choose to train the model from within the notebook. I have noticed however that training inside of a separate terminal on a Windows machine you're able to display live loss metrics. 
<img src="https://i.imgur.com/K0wLO57.png"> 
<br />
<b>Step 10.</b> You can optionally evaluate your model inside of Tensorboard. Once the model has been trained and you have run the evaluation command under Step 7. Navigate to the evaluation folder for your trained model e.g. 
<pre> cd Tensorlfow/workspace/models/my_ssd_mobnet/eval</pre> 
and open Tensorboard with the following command
<pre>tensorboard --logdir=. </pre>
Tensorboard will be accessible through your browser and you will be able to see metrics including mAP - mean Average Precision, and Recall.
<br />
