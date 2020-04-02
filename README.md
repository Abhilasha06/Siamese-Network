# Siamese-Network
This repo aims at ternary classification of images using siamese neural network.

The dataset consists of images of three tpyes of coal-

Class 1 has 30 images. <br />
Class 2 has 23 images. <br />
Class 3 has 35 images. <br />

original data- https://drive.google.com/open?id=15bkqBI1rsjN21Yx6jSk_97PqF4sqinNG

Since the images are very few in number, I used different augmentation techniques and in the final augmented dataset-

Class 1 has 390 images. <br />
Class 2 has 299 images. <br />
Class 3 has 465 images. <br />

augmented data- https://drive.google.com/open?id=1eM4k49cKBuQw3GqmU4q4abSb5iyP4zGP


Thus there are a total of 1154 labelled images.


I tried using CNN and resnet for this classification problem and the results achieved were as follows-

CNN - Train accuracy 98%, Test accuracy 83% <br />
resnet - Train accuracy 98%, Test accuracy 87%


Siamese Network-

![1_aSolByv3zrlRgoYkyXxxSQ](https://user-images.githubusercontent.com/43816262/78264161-732db500-7520-11ea-90a0-b96180a0937c.jpeg)



Training pairs - I paired a single image with 10 different images. If the images were same I labelled the pair as 1 else I labelled it as 0. I did this for a total of 500 images and thus I had a total of 5000 training pairs. This is one of the major advantages of siamese neural network, we can generate a large number of trainig pairs using relatively smaller number of training images.


Base Network - I used CNN as the base network. The last layer used was sigmoid with 64 units. Thus the base network converts an image to embeddings (of size 64).


L1_distance was used to get the difference between the two embeddings. And finally a dense layer with softmax activation was used to get the output as 0 or 1 depending on whether the two images matched or not.


Testing - The remaing 654 images were tested by pairing them with the training images.

Accuracy-

Training accuracy - 98% <br />
Testing accuracy - 90%

Thus, the siamese network gave a much better training accuracy as compared to CNN and resnet.
