# Pneumonia-Detection Web-App Project Overview:

**Final Product Hosted On Heroku:** https://pneumonia-detection-appli.herokuapp.com/

I created a tool that classifies pediatric chest X-rays to detect pneumonia. One way to depict Penumonia is by using chest X-ray images. They are obtain easily but the problem is in radiologic interpretation of images which are not always available. Therefore, such a tool could be use to predict fast and automatically whether or not someone have pneumonia. 

*   Project done using the Fast.ai Library.
*   I created a tool that classifies pediatric chest X-rays to detect pneumonia.
*   Used transfer learning (pretrained resnet34). 
*   Used the learning rate finder to find the best learning rate to update the weights. 
*   Fine-tuned the model.
*   Built a client facing API using Flask.
*   Deployed the model on Heroku.


![alt text](https://github.com/gaetanlop/Pneumonia-Detection/blob/master/results%20unfreeze%20pneu.PNG)

## About the Data
Link of the dataset: https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia

**What is Pneumonia:** It is an infection in the lungs tissues caused by microbes. The result is an inflammation which brings water into the lung tissue which can result in breathing problems. "The WHO reports that nearly all cases (95%) of new-onset childhood clinical pneumonia occur in developing countries, particularly in Southeast Asia and Africa. Bacterial and viral pathogens are the two leading causes of pneumonia (Mcluckie, 2009) but require very different forms of management. Bacterial pneumonia requires urgent referral for immediate antibiotic treatment, while viral pneumonia is treated with supportive care. Therefore, accurate and timely diagnosis is imperative." (Quoted from an interesting paper: https://www.cell.com/cell/fulltext/S0092-8674(18)30154-5)

**Medical treatment:** "One key element of diagnosis is radiographic data, since chest X-rays are routinely obtained as standard of care and can help differentiate between different types of pneumonia. However, rapid radiologic interpretation of images is not always available, particularly in the low-resource settings where childhood pneumonia has the highest incidence and highest rates of mortality."(https://www.cell.com/cell/fulltext/S0092-8674(18)30154-5)

**About the Dataset:** The dataset contains 5,863 chest X-Ray images divided into two categories: Pneumonia and Normal.

## Code and Resources Used

**Python Version:** 3.7

**For Web Framework Requirements:** ```pip install -r requirements.txt```

**Fastai Course:** https://github.com/fastai/fastbook


## Chest X-Ray Images Examples

![alt text](https://github.com/gaetanlop/Pneumonia-Detection/blob/master/pneumonia%20data.PNG)


## Data Augmentation Strategy


![alt text](https://github.com/gaetanlop/Pneumonia-Detection/blob/master/data%20aug%20pneumonia.PNG)

## Model Building
* Used transfer learning (pretrained resnet34). 

![alt text](https://github.com/gaetanlop/Pneumonia-Detection/blob/master/An-example-of-CNN-architecture.png)
https://www.researchgate.net/figure/An-example-of-CNN-architecture_fig1_320748406

* One of the most important hyperparameter to tune in order to train a model efficiently is the learning rate. If the learning rate is too low, it will take many epochs to train our model, thus the model will be prone to overfitting. If the learning rate is too high,it can cause undesirable divergent behavior. In order to set the appropriate learning rate, I used the learning rate finder from fastai to find the best learning rate to update the weights. 

![alt text](https://github.com/gaetanlop/Pneumonia-Detection/blob/master/lr%20finder%20pneu.PNG)

## Model performance
As we are using transfer learning, I trained the randomly added layers for 6 epochs, with all other layers frozen and then I unfreezed all of the layers, and trains them all for 4 epochs.

![alt text](https://github.com/gaetanlop/Pneumonia-Detection/blob/master/results%20pneu.PNG)
![alt_text](https://github.com/gaetanlop/Pneumonia-Detection/blob/master/results%20unfreeze%20pneu.PNG)
![alt text](https://github.com/gaetanlop/Pneumonia-Detection/blob/master/conf%20matrix%20pneu.PNG)

## Productionization and Deployment
I built a client facing API using Voila and deployed it using Heroku.
* **Final Product Hosted On Heroku:** https://pneumonia-detection-appli.herokuapp.com/
