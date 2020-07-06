## CVND---Image-Captioning-Project  
 > In this project I have design a CNN-LSTM architecture to predict a image caption from COCO dataset  
 - Use CNN as Encoder
 - Use LSTM as Decoder
 - For CNN I have used pretrained resnet-50 architecture and made it's embedded layer trainable
 - For LSTM, all the weights were trainable


## Instructions  
1. Clone this project repo: ```https://github.com/Apucs/Image-Captioning.git```

2. Clone this repo: ```git clone https://github.com/cocodataset/cocoapi.git```

3. Setup the coco API (also described in the readme [here](https://github.com/cocodataset/cocoapi)) 
```
cd cocoapi/PythonAPI  
make  
cd ..
```

3. Download some specific data from here: http://cocodataset.org/#download (described below)

* Under **Annotations**, download:
  * **2014 Train/Val annotations [241MB]** (extract captions_train2014.json and captions_val2014.json, and place at locations cocoapi/annotations/captions_train2014.json and cocoapi/annotations/captions_val2014.json, respectively)  
  * **2014 Testing Image info [1MB]** (extract image_info_test2014.json and place at location cocoapi/annotations/image_info_test2014.json)

* Under **Images**, download:
  * **2014 Train images [83K/13GB]** (extract the train2014 folder and place at location cocoapi/images/train2014/)
  * **2014 Val images [41K/6GB]** (extract the val2014 folder and place at location cocoapi/images/val2014/)
  * **2014 Test images [41K/6GB]** (extract the test2014 folder and place at location cocoapi/images/test2014/)


## Network Architecture   
 - Firstly images were passed through the pretrained resnet model to extract the image features
 - Those extracted features were then given input to the lstm layer along with the embdded layer output
 - I have used 1 LSTM layer
 - Embedding layer size = LSTM layer size = 512
 - Batch size = 128
 - Learning rate = 0.001
 - Vocabulary threshold = 5
 - For network architecture, I have used [this paper](https://arxiv.org/pdf/1411.4555.pdf) as a reference
 
## Inference
![][/home/apu/Pictures/Screenshot from 2020-07-06 12-30-19.png]

