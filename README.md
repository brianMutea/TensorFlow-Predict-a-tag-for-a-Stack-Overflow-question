# Predict a tag for a Stack Overflow question using TensorFlow(Notebook)

In this project, my quest was to learn how to use the TensorFlow  `tf.keras.layers.TextVectorization` for:
  * data standardization,
  * tokenization, 
  * vectorization

I found out that with vectorization we have two modes:
  * `int mode` - Very useful for building models where the word sequence/order is very important like NMT. In short, it maps each          word to its integer index.
  * `binary mode` - Produces a bag of words. Word order is not critical. Actually it returns a binaries for most appearing words.

Snap short of the models Prediction(the `binary mode` model:
  
  ```python
  inputs = [
    "How do I iterate over a Pandas column?",
    "How do I use the arrow functions"
]

predicted_scores = export_binary_model.predict(inputs)
predicted_labels = get_string_labels(predicted_scores)


for input, label in zip(inputs, predicted_labels):
  print("Question: ", input)
  print('Predicted tag/label: ', label.numpy())
  
  ```
  ```
**output**

1/1 [==============================] - 0s 41ms/step
Question:  How do I iterate over a Pandas column?
Predicted tag/label:  b'python'
Question:  How do I use the arrow functions
Predicted tag/label:  b'javascript'
  ```
  
  

--> The porject is overall a demonstration of how to load and preprocess text data.

--> I also experimented on how tune my model to enable for deployment purposes

--> Finally gave myself an assignmet to read more on various topics encoutered in this project
