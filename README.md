# COD-MW-2019-DNN
This is a Enemy Detection Neural Network for Call of Duty Modern Warfare.

# How it works
### Intent
By looking at a 200x200 pixel block the NN determines if their is an enemy. Realistically, this is a neural network trained on successfully detecting Gamer tags.
![](https://imgur.com/5Fowghj.png) ![Targets](Misc/targets.gif)

### How To Run
1. Clone
2. Download the Model and Training image Data [Model and Data Link](https://drive.google.com/file/d/1_xOPdYpHkda_mh1SWyg9eFJKhAIix0Rq/view?usp=sharing)
3. Set up your venv. (Using Tensorflow 2.0)
4. Run
  * NetworkDataCollection.py for Self Training
  * Overlay.py To show Real Time Detection
  * Run.py This Prints to console
  * Train.py to build a new Model or retain current

If you can run Tensorflow off your GPU, Highly recommend you do so. Good instructions here: https://www.tensorflow.org/install/gpu and here https://docs.nvidia.com/cuda/cuda-installation-guide-microsoft-windows/

### What does 'EnemyDetector/Scripts/Run.py' do?
Grab the center 200x200 pixel block, and run it through the Neural Network. It will print to the console any time it is > 95% confident that it sees an enemy.

### What does 'EnemyDetector/Scripts/Overlay.py' do?
Grab the center 200x200 pixel block, and run it through the Neural Network. It will also render a crude transparent window over COD/Twitch showing you real time values.  
![Sample Gif Here](Misc/SampleOverlay.gif)  
[Sample Video Here](https://youtu.be/Qif8g2Ib5pI)  

### What does 'EnemyDetector/Scripts/NetworkDataCollection.py' do?
This is the "Self Training" Script. You can have it watch Twitch streams of COD in 1080p and store them by % Confidence  
You will need to manually go through the screenshots and sort them (Targets) and (Neutral)
Restart the training with this new data appended to the existing training set.

### What does 'EnemyDetector/Scripts/Train.py' do?
This is where the magic happens
The most simple thing, Pull in a boat load of images from 4 directories (2 train (Neutral and Targets), 2 validation (Neutral and Targets)) and start training!
