# Image Captioning Using Deep Learning and NLP
## Introduction
Image captioning is an important and routine task for documenters, and take a time to be reckoned with since it requires a semantic understanding of images and the ability to generate description sentences with the proper and correct structure.
For that, we decide to use the magic of deep learning and NLP for building a Neural Networks and Text Analysis to generate suitable textual description for given images.
## Data Description
The used dataset come from Kaggle, which got from merging [Flickr30k](https://www.kaggle.com/hsankesara/flickr-image-dataset) and [Flickr8k](https://www.kaggle.com/adityajn105/flickr8k) datasets.
Flickr30k contains __158,915__ rows and __3__ columns, which are __image_name__, __comment_number__ and __comment__,
while Flickr8k contains __40,455__ rows with the same number of columns.
The total number of unique images for Flickr30k are __31,783__ while Flickr8k has __8091__ each paired with five different captions.
 ## Tools
Here the tools that will be initially uses in this project: <br/>
- Jupyter Notebook  
- python libraries:
    - General:
      - Numpy
      - Seaborn
      - Matplotlib
      - Pickle
    - For Natrual Language Processing:
      - scikit-learn
      - NLTK
      - Regular Expression
      - Gensim
    - For Deep Learning:
      - TensorFlow
      - Keras

## Conclusion
This project aims to generate a textual description for images through Neural Networks and NLP, for reducing the time consumed on generated manually. 
