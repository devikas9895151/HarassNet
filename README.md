# HarassNet
—Harassment detection on online platforms remains
 a critical role, especially across diverse languages. In this paper,
 We have introduced HarassNet. This multilingual harassment
 detection system can identify Harassment and Non Harassment
 in Hindi, English, Punjabi, Tamil, Malayalam, Odia, Bengali,
 Telugu, Kannada, Rajasthani, Gujarati, Marathi, Haryanvi, and
 Bhojpuri texts. Collected the dataset from the Kaggle resource.
 To model this diverse language, we fine-tune a multilingual
 BERT model (mBERT) because it has been trained on different
 languages together and also build an LSTM deep learning model
 to compare the accuracy between the models. After we built this
 model, we designed a RESTful API to facilitate the integration
 of HarassNet into real-world applications. The experimental
 f
 indings show that LSTM (0.83) works better than the MBert
 model (0.64) in F1 score.

  Class imbalance
 Class imbalance is when one class in a dataset significantly
 outweighs the other. This can lead the model to perform
 poorly on the minority class, even if it achieves high overall
 accuracy. This technique assigns higher importance to the
 minority classes during training to ensure that the model does
 not become biased toward the majority class. In our model, we
 computed the class weight for the harassment class as 1.58,
 and for non-harassment, we assigned a weight of 0.731.
 C. BERT tokenization
 To process the multilingual language input, we pre-trained a
 BERT base multilingual case tokenizer, which was trained in
 104 languages using a WordPiece vocabulary. Tokenization is
 the first step in transforming raw textual data into a structured
 format.
 Each input text is segmented into subwords using Wordpiece
 tokenization to effectively capture rare words and morpholog
ically rich structures. Special tokens such as [CLS] and [SEP]
 are added to mark the beginning and to separate each sequence.
 All tokenized texts are padded to fix the maximum length.
 attention masks are generated to distinguish between tokens
 and padded elements.
 D. Model Architecture and Fine-tuning
 To classify the multilingual text data for harassment detec
tion, we used the Multilingual BERT (mBERT) model and
 f
 ine-tuned it with the harassment classifier. We extract the
 Fig. 1. Work Flow
 [CLS] token from BERT’s output, representing an understand
ing of the entire input sequence. This pooled output is passed
 through a feedforward neural network to get a probability
 distribution that predicts the output and labels the sequence
 of text. The fine-tuned multilingual BERT model is compiled
 using the Adam optimizer. The loss function we have used
 is categorical cross-entropy because the labels are one-hot
 encoded to represent the binary classification.
