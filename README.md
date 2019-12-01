# COD-MW-2019-DNN
Deep Neural Networks for Call Of Duty Modern Warfare 2019

Contained are the scripts and validation data as well as the .h5 files for various Call of Duty Modern Warfare Neural Networks

Only limited validation will be provided in this repo. The base training dataset is > 2GB.

# Enimy Detector/Gamertag Detector
### Intent
Look at a 200x200 pixel block at the center of the uers screen, determine if there is an enemy somewhere in that block. If you have ever played COD, then there is a high chance that by just looking at the below, you would agree if there is an enemy in these images.

![](https://imgur.com/d4gYHWW.png)
There are some cases in COD, where just loooking at a 200x200 block, its impossible to tell if its friend or foe. Take the scenerio that the user has been flashbanged. The user doesent see the colord indicator above the player.

![](https://imgur.com/IwZMovH.png)

So realisticly, this is a neural network trained on successfully detecting Gamertags in a 200x200 block

### Ho To Run
1. Clone
2. Large File Download the latest model (https://github.com/darkmatter2222/COD-MW-2019-DNN/tree/master/EnemyDetector/Models)
3. Set up your venv. (Using Tensorflow 2.0)
4. Run https://github.com/darkmatter2222/COD-MW-2019-DNN/blob/master/EnemyDetector/Scripts/Run.py
5. Run COD at full screen (1080p)

If you can run Tensorflow off your GPU, Highly recomend you do so. Its the difference of 2 FPS (i7 3770K) and 12 FPS (GTX 1080 TI). Good instructions here: https://www.tensorflow.org/install/gpu and here https://docs.nvidia.com/cuda/cuda-installation-guide-microsoft-windows/

### What does 'EnemyDetector/Scripts/Run.py' do?
Grab the center 200x200 pixel block, and run it through the Neural Network. It will print to the console any time it is > 95% confident that it sees an enemy. 

### What does 'EnemyDetector/Scripts/Overlay.py' do?
Grab the center 200x200 pixel block, and run it through the Neural Network.It will also render a crude transparrent window over COD/Twitch showing you real time values.
![](https://imgur.com/lNZntCc.png)




