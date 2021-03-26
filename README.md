# Toxicity Inspector

Data Source: Dataset is obtained from Kaggle as a part of the [Toxic Comment Classification Challenge] hosted by Jigsaw/Conversation AI in 2017.

[Toxic Comment Classification Challenge]: https://www.kaggle.com/c/jigsaw-toxic-comment-classification-challenge

## Motivation
The recent global pandemic situation has forced masses to rely on the internet now more than ever, for activities as simple as online shopping to online education. Toxic comments are detrimental to internet users and limit their freedom of expression in diverse perspectives, and such unconstructive remarks are discourteous, disrespectful, and detestable. Such animosity results in users disabling their comments on many online communities, and eventually, they stop expressing their opinions. Hence, there is a pressing need to build a fast, precise, and deployable solution to help organizations weed out such remarks from getting online.

## Objective
At present, there are a plethora of state-of-the-art pre-trained classification models such as BERT are available to us for performing classification. Although these models are very accurate, they are huge and require extensive computational resources for training. Their massive size makes them less useful for deploying them on constricted environments such as mobile devices. Through this project, we aim to learn how to perform multi-label text classification and build a naïve solution that is fast, light-weight, i.e., suitable for deploying in constricted environments, and highly accurate in classifying the comments.

## Methodology
1. Data Analysis: The dataset used here is from wiki corpus dataset which was rated by human raters for toxicity. The corpus contains 63M comments from discussions relating to user pages and articles dating from 2004-2015. Different platforms/sites can have different standards for their toxic screening process. Hence the comments are tagged in the following six categories:\
- Toxic
- Severe_toxic
- Obscene
- Threat
- Insult
- Identity_hate
The tagging is done via crowdsourcing which means that the dataset is rated by different people which in turn implies there is probable cause for low accuracy.

2. Data Modelling: From the individual classification reports, we can see these classifiers are majority classifiers as they are doing a good work of predicting Class 0 (non-toxic) comments but either overpredict or have a low precision when classifying toxic labels. The deep learning model also has a very low F1-score; however, the accuracy is high. Upon analyzing the classification report of the Bi-LSTM model, we can see that it completely misses two toxic subcategories resulting in a low F1-score. We can attribute this low score to the prevalent class imbalance in our dataset. The class labels were not stratified while doing the training/validation split. However, the performance of the model on the other toxic subcategories is high. Hence, we choose Bi-LSTM model is our best model, whose classification performance can further be enhanced by using data augmentation techniques and stratified splitting.

## Conclusion
To summarize, through this project, we learned how multi-label classification works and its available methods. The machine learning concepts and algorithms such as classification, Naïve Bayes, Neural Networks, NLP techniques learned during our class helped us with the execution of the project, and we were able to apply them according to build the models and evaluate their performance. The best model (Bi-LSTM) is a good baseline model that could be employed to classify specific toxic subcategories. However, it requires additional training for the categories which have fewer data points.

Analysis on my [Medium]!

[Medium]:https://sheetalkalburgi.medium.com/
