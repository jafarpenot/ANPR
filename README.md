# Automatic Number Plate Recognition with squared VS standard plate classification
<p>This set of Notebooks heavily relies on Nicholas Renotte's <a href="https://www.youtube.com/watch?v=0-4p_QgrdbE&t=2972sprovides">tutorial</a> showing how to build a Number Plate Recognition model, train it and run it on several test images. The main difference betewen my code and his are :
  
  - Minors changes in the folders' paths (TF API was already installed on my machine)
  
  - Added a class (suqared_licence) and finetuned the detection model to be able to differentiate between squared and standard plates.
  
  - Tried another OCR (Keras_OCR) to compare with EasyOCR used by Nicholas.
  
  - Ran the OCR on different region of the plate if it is recognized as a squared plate.
  

<img src="https://i.ibb.co/q0105tG/plates.png">

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
</pre>
or
<pre>
python -m pip install requirements.txt
</pre>
<br/>


<b>Step 5.</b>
You can collect images using Nicholas' Notebook <a href="https://github.com/nicknochnack/TFODCourse/blob/main/1.%20Image%20Collection.ipynb">1. Image Collection.ipynb</a> - or use my dataset (included in the repo) which is actually the same with some more licence plates. 


<br/>
If you downloaded the images with Nichola's notebook, then you should manually divide collected images into two folders train and test. So now all folders and annotations should be split between the following two folders. <br/>
\TFODCourse\Tensorflow\workspace\images\train<br />
\TFODCourse\Tensorflow\workspace\images\test
<br/><br/>

<b>Step 5.</b> Open Jupyter Notebook
<pre>
jupyter notebook
</pre>
You can also open and run in colab. In this case, you might need to install the dependencies (requirements.txt) in colab.

Select the notebook <a href="https://github.com/jafarpenot/ANPR/blob/main/Training%20and%20Detection.ipynb">2. Training and Detection.ipynb</a>. This notebook will walk you through installing Tensorflow Object Detection (if you don't have it), training your model, making detections, and printing te results. You can skip the training process and simply use the pretrained model (saved with with checkpoint file ckpt-11) on images from the test set, or you can train it from scratch on the train set (see below).


 
<br /><br/>
<b>Results </b> The results are shown on the image below. The model can recognize and differentiate quite accurately between squared and standard licence plates. Then the OCR run on different regions of the squared plate, effectively recognize and put into order the text in the plate.


<img src="https://i.ibb.co/q0105tG/plates.png">

NOTE that the model does not perform as good as this with any suqared plate. The reason is that I trained it only adding a few images to the training set for finetuning. The features it could learn from those few images are not enough to make it very efficient. We would need a bigger dataset to train our model on.

Thank you for reading !

