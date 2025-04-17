# Model_Explainability_CoLocalization_with_Most_Important_Feature_Map
A Repository of code and associated information for an assessment of model explainability through co-localization with the most important feature map.

Most modern image and video classification methods seek to achieve high accuracy by overloading models with more training data, layers and features, or some combination of the two. But these methods that utilize automatic feature selection (and especially so for those heavily reliant on a Convolutional Front End that can lead to somewhat random feature maps) are often not explainable. 

For instances of model utility in the medical space, this lack of explainability is often one of the largest reasons healthcare providers ultimately either don't trust or don't use the model selections. 

This simple method seeks to rectify this problem by evaluating the feature maps (or most important feature map to simplify the problem) and investigating if the feature of interest for an external party (like a physician looking for a cancer lesion) is also considered important to the model. To do this the steps are very simple:


(1) Identify the feature maps from the model for a test image

(2) Identify the coordinates of the important feature 

(3) Test if the feature co-localizes with the feature map. 

Interestingly enough, a study and evaluation of a model through this method found that the most important feature map for a predictive model DID NOT co-localize with the most important feature for a clinician (the cancer lesion) for a model trained to identify prostate cancer. Even worse, the feature map didn't look to the organ the cancer was located within (the prostate) at all. I would argue there is a need for a better model front-end that includes relevance of model input features, or a better model-backend that removes unimportant features, to rectify this problem. 

Models built using large amounts of data or built on outside datasets and re-trained (think Transfer Learning) often seek to overcome the inability for a model to identify important features by overwhelming the model with data and features and can frequently select every region of the image and weight it in some format. Although this then leads to the presence of an important feature within the feature maps, the model (in this case an image classification algorithm built using a convolutional layer and as such, one that utilizes an automatic feature selection process) is still ultimately unable to distinguish what features are important. Do we need better models? Or can we modify existing models? I find these questions particularly interesting for the future of machine learning research. 

Please see relevant papers here: 
https://www.medrxiv.org/content/10.1101/2024.10.12.24315347v1
And here:
https://www.medrxiv.org/content/10.1101/2025.03.04.25323311v1

