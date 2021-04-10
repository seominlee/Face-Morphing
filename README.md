# Face Morphing 

![alt text](https://github.com/seominlee/Face-Morphing/blob/master/gogh.png?raw=true)

## Delete lines from  https://github.com/Azmarie/Face-Morphing
===================

Create a morphing sequences betwen two faces. 

Input: Two images containing faces  
Output: A video showing the fluid transformation from one face to the other  

Requirements
-------------
```
pip install imutils

pip install opencv-python
 
python -m pip install -U scikit-image

conda install -c conda-forge dlib  
```

Getting Started
-------------

#### Test with demo images
```

python3 code/__init__.py --img1 2.png --img2 3.png --output output.mp4


ffmpeg -i g7.mp4 -filter:v "setpts=0.6*PTS" 6XX.mp4

2x video  //  ffmpeg -i gogh.mp4 -filter:v "setpts=0.5*PTS" 2X.mp4

extract images from video

ffmpeg -i 2X.mp4 -r 6 s/output_%04d.png

```




Generate a morphing animation video sequence

```
python3 code/__init__.py --img1 images/aligned_images/jennie.png --img2 images/aligned_images/rih.png --output output.mp4
```



#### Test with your own images

1. Put your images in `Images` folder

2. Auto align faces with `python code/utils/align_images.py images/ images/aligned_images --output_size=1024`
This will look for faces in the images - crop out, align (center the nose and make the eyes horizontal), and then rescale the resulting images and save them in "aligned_images" folder.
3. Run `code/__init__.py` above on your aligned face images with arg `--img1` and `--img2`.



Key Features
-------------
1. Detect and **auto align faces** in images (Optional for face morphing) 
2. Generate **corresponding features points** between the two images using Dlib's Facial Landmark Detection
3. Calculate the **triangular mesh** with Delaunay Triangulation for each intermediate shape
4. Warp the two input images towards the intermediate shape, perform **cross-dissolve** and obtain intermediate images each frame






