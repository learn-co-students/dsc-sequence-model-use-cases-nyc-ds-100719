
# Sequence Model Use Cases

## Introduction

In this lesson, you'll learn about **_Sequence Models_**, and what makes them different from traditional multi-layer perceptrons. You'll also examine some of the common things sequence models can be used for!

## Objectives

You will be able to:

- Define a Sequence Model 
- List some of the use cases for Sequence Models 

## What is a Sequence Model?

A **_Sequence Model_** is a general term for a special class of deep neural networks that work with time series of data as input (or any data where you want the model to consider the data one point at a time, in order). This means that they are great for problems where the order of the data matters - for instance, stock price data or text. In both cases, the data only makes sense in order. For instance, scrambling the words in a sentence destroys the meaning of the sentence, and it's impossible to predict if a stock price is going to go up or down if you don't see the prices in sequential order. In both cases, the sequence of the data matters. 

Consider the following problem: you are given the sentence "you are going to" and asked to complete the sentence by generating at least 5 more words.  The second word that you choose will depend heavily on the first word that you choose. The third word that you choose will depend heavily on the first and second words that you choose, and so on. Because of this, it is crucial that the models _remember_ the previous words that they generated. In computer science, you call this being **_stateful_**. This means that when the model is generating the second word, it needs to know what it generated as the first word! To do this, **_Recurrent Neural Networks_** feed their output for timestep  <img src="https://render.githubusercontent.com/render/math?math=\large x_t"> back into the model as input for timestep  <img src="https://render.githubusercontent.com/render/math?math=\large x_{t %2b 1}"> !

<img src="images/rnn.gif">

There are many different kinds of sequence models, and they are most generally referred to as **_Recurrent Neural Networks_**, or **_RNNs_**. In the next lesson, you'll dig into how they work. Let's examine some of the things that RNNs can do!

## Sequence Model Use Cases

### Text Classification

One of the most common applications of RNNs is for plain old text classification. Recall that all the models that you've used so far for text generation have been incapable of focusing on the order of the words, which means that they're likely to miss out on more advanced pieces of information such as connotation, context, sarcasm, etc. However, since RNNs examine the words one at a time and remember what they've seen at each time step, they're able to capture this information quite effectively in most cases! As the final part of this section, we'll actually build one of these models which will be able to detect toxic comments from real-world Wikipedia comments!

### Sequence Generation

Sequence generation is probably some of the most incredible things you can do with neural networks, because they excel at coming up with wacky, almost-human sounding names for things when fed the right data. For instance, all of the following cookie names were generated by feeding a dataset of actual cookie names from recipes. The model was built to generate it's own cookie names letter by letter, based on what it saw in the recipe names. Since the model is responsible for generating its own output letter by letter, one at a time, this makes it a prime example of **_Sequence Generation_**!  

<img src="images/rnn_cookie_names.png">

### Sequence-to-Sequence Models

If you've ever used Google Translate before, then you've already interacted with a **_Sequence to Sequence Model_**. These models learn to map an input sequence to an output sequence, usually through an **_Encoder-Decoder_** architecture. Note that although going from a sequence of English words to the corresponding sequence of French words is probably the basic example of Sequence to Sequence models, there are many other kinds of problems that are Sequence to Sequence that aren't immediately obvious. For instance, check out this example of a neural network that completes drawings of a mosquito based on how you start drawing the bug!

<img src="images/multi_sketch_mosquito.gif">

Here's another example from [pix2pix](https://phillipi.github.io/pix2pix/). Now, stop what you're doing, follow that link, and take a few minutes to play around with pix2pix -- watching it generate photos from your own drawings is really cool!

<img src="images/pix2pix.gif">

## Summary

In this lesson, you learned about sequence models, and some of their more common use cases. 
