# Final-Project-Face-Enhancement
Final Project for image processing 1/2023 <br>
Member:
- Werapat Wangrungroj
- Nattapong Anansomsin

## Project Overview

เนื่องจากว่าใน social media มักจะมีการลงรูปของตัวเองและหลายๆคนมักจะใช้ filter หรือการ enhance รูปใบหน้าของตัวเองก่อนลง social media จึงเป็นแรงบันดาลใจให้เราอยากทำ face enhancement 

## Architecture

กลุ่มของเราใช้เป็น Unet Architecture สำหรับการ segmentation ในส่วนใบหน้า และใช้ face detection จาก library dlib 

Encoder | Weights | Params,M
--- | --- | ---
resnext101_32x48d | instagram | 826M

## Process in Our Method
![](https://github.com/hellp002/Final-Project-Face-Enhancement/assets/94524977/bd943348-f759-46e2-8852-09b0260ee3d3) ![](https://github.com/hellp002/Final-Project-Face-Enhancement/assets/94524977/29ed89a1-7aa0-44d0-bc5d-0652709778e9)
## How to use our method

การ enhancement ใบหน้าเราจำเป็นต้องรัน code ใน [file](eval_model.ipynb) ที่สามารถ run ได้ใน google colab โดยต้อง run code cell จนถึงบรรทัดสุดท้าย และเราจึงจะสามารถเรียกใช้

```python
enhancer(image)
```

ที่รับ input เป็น BGR image โดยมี output เป็น RGB image นอกจากนี้ก่อนเรียก function enhance จำเป็นต้องใช้คำสั่งนี้ครอบก่อน

```python
model.eval()
with torch.no_grad():
 ....
 result = enhancer(image)
```

เพื่อเปลี่ยน model เป็น mode evaluation จะเป็นการเพิ่ม accuracy ให้ model

## Data set for training reference:

Dataset: [Dataset github](https://github.com/JDAI-CV/lapa-dataset)
Dataset paper: @inproceedings{liu2020new,  
  title={A New Dataset and Boundary-Attention Semantic Segmentation for Face Parsing.},  
  author={Liu, Yinglu and Shi, Hailin and Shen, Hao and Si, Yue and Wang, Xiaobo and Mei, Tao},  
  booktitle={AAAI},  
  pages={11637--11644},  
  year={2020}  
}

## Link and Assets
[train/dev/test set for unet](https://drive.google.com/uc?export=download&id=1XOBoRGSraP50_pS1YPB8_i8Wmw_5L-NG) <br>
[data set that we used](https://www.kaggle.com/datasets/ashwingupta3012/human-faces) <br>
[data set for testing our model](https://drive.google.com/uc?export=download&id=1WeP0mTjUDBt2Zx4JWO0U0xf15jwpsr6V) <br>
[data set for testing (facial mask)](https://drive.google.com/uc?export=download&id=1-sr6XByGYKRdIDuS3MjAWCBnhX1_OnGG) <br>
[data set for testing (face mask)](https://drive.google.com/uc?export=download&id=1K0QTK_GSyai5vNwMgaO3Kh54n5w4Sjtx) <br>
[Model](https://drive.google.com/uc?export=download&id=1_fdYp8trR7mMDWeqjHOhTASp4SQv7RSk) <br>
[dlib model](http://dlib.net/files/shape_predictor_68_face_landmarks.dat.bz2) <br>
[Medium](https://medium.com/@werapatwangrungroj/face-enhancement-ด้วย-semantic-segmentation-model-และ-facial-landmark-detection-model-2a8c1381b1a8) <br>
[Data Label App](https://imagej.net/ij/download.html) <br>
[Slide Presentation](Face%20Enhancement.pdf) <br>


 
