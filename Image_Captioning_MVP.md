# Image Captioning Using Deep Learning and NLP
## Goal of the Project
This project aims to generate a textual description for images through Neural Networks and NLP, for reducing the time consumed on generated manually. 
## Natrual Langauge Processing
The NLP process included:

- Performed text cleaning
- Removed digits from texts.
- Made all text lowercase.
- Removed all punctuations.
- 'startseq' was added at the beginning of each caption
- 'endseq' was added at the end of each caption

 ## Start building Traditional Neural Network Procedures
 <img src = 'https://github.com/shhdSU/Image_Captioning_DeepLearning/blob/main/Image/model_summary.png' width = '500' />

> As shown in the summary above, seven sequential layers with different activation function (__tanh__, __relu__) was added 
> to traditional NN as baseline, the number of neurons in each layer start from 2<sup>11</sup> to 2<sup>5</sup>, an output layer was neglected since 
> our target is to generate a caption for each image, in other words it's not a classification problem.
## Future Work
- Use pre-trained NN (RNN, CNN) for images and caption separately.
- Build a new NN that takes the output of pre-trained NN as X<sub>i</sub> and y<sub>i</sub>.
