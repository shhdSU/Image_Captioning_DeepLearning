# Image Captioning Using Deep Learning and NLP
## Introduction
Image captioning is an important and routine task for documenters, and take a time to be reckoned with since it requires a semantic understanding of images and the ability to generate description sentences with the proper and correct structure.
For that, we decide to use the magic of deep learning and NLP for building a Neural Networks and Text Analysis to generate suitable textual description for given images.
## Data Description
The used dataset come from Kaggle, which got from merging [Flickr30k](https://www.kaggle.com/hsankesara/flickr-image-dataset) and [Flickr8k](https://www.kaggle.com/adityajn105/flickr8k) datasets.
Flickr30k contains __158,915__ rows and __3__ columns, which are __image_name__, __comment_number__ and __comment__,
while Flickr8k contains __40,455__ rows with the same number of columns.
The total number of unique images for Flickr30k are __31,783__ while Flickr8k has __8,091__ each paired with five different captions.
## Algorithms
1. Exploratory Data Analysis 
  - Reading the data
  - Cleaning the data
  - Merging the two datasets
  - Reshape the dataset and make image name as index and __Caption_1__, __Caption_2__, __Caption_3__, __Caption_4__ and __Caption_5__ as columns
2. Natural Langauge Processing
  - Performed text cleaning
  - Removed digits from texts.
  - Made all text lowercase.
  - Removed all punctuations.
  - 'startseq' was added at the beginning of each caption
  - 'endseq' was added at the end of each caption
 3. Deep Learning 
   - Transfer Learning
     - [InceptionV3](https://cloud.google.com/tpu/docs/inception-v3-advanced)<br/>
       using pre-trained InceptionV3 model, images was converted into (2048,1) vectors using the bottleneck features.
   - Word Embeddings
     - [GloVe](https://nlp.stanford.edu/projects/glove/) <br/> using pre-trained GloVe model, common word vocabulary of captions was mapped to 200D long word vectos.
   - Final Model Architecture <br/>
     Since the input consists of two parts, an **image vector** and a **captions**, we cannot use the Sequential API provided by the Keras 
     library. For this reason, we use the **Functional API** which allows us to create Merge Models (the model visualized in appendix **A**). <br/> The model implemented as following: 
     - The images and words vectors was used as an input
     - Embedding and LSTM layers was applied on words vectors (RNN)
     - **256D** was result from the previous layers
     - Feed Forward Network ending with **2732** softmax layer to predict the next word 
   - Greedy Search <br/>  <br/> 
     <img src = 'https://github.com/shhdSU/Image_Captioning_DeepLearning/blob/main/Image/result%20Example.png' width = '300' />
     <br/> <br/> 
     | iteration | Input 1 (as vector)| input 2 (as vector)                |yhat       |
     |-----------|--------------------|------------------------------------|-----------|
     | 1         | image              | startseq                           | two       |
     | 2         | image              | startseq two                       | dogs      | 
     | 3         | image              | startseq two dogs                  | play      | 
     | 4         | image              | startseq two dogs play             | in        | 
     | 5         | image              | startseq two dogs play in          | the       | 
     | 6         | image              | startseq two dogs play in the      | grass     | 
     | 7         | image              | startseq two dogs play in the grass| endseq    | 
     > The above example shows how the final model works, in each iteration the input2 will be updated with the new yhat and try to predict the next word until reach the maximum length **(71)** or 'endseq' word occur 
   - The Final Results <br/>
     - English Caption
     - Arabic Caption
     - Spoken caption in Arabic
     - Spoken caption in English
     
 ## Tools
- Jupyter Notebook  
- Python Libraries:
    - Pandas
    - NumPy
    - Keras
    - TensorFlow
    - Sklearn
    - Matplot
    - PIL
    - Pickle
      

## Conclusion
The project successfully achieve it's goal using **Deep Learning** and **NLP** with **50,95%** accuracy and **1.8** loss.

## Appendix 
**A.** Model Architecture  <br/> <br/>
     <img src = 'https://github.com/shhdSU/Image_Captioning_DeepLearning/blob/main/Image/model_Architecture.png' width = '500' />
