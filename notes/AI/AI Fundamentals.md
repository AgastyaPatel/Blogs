---
title: "AI Fundamentals"
author: "Agastya Patel"
categories: [Notes, AI, Brief]
draft: false
---
[Resource]
Elements of ai : https://course.elementsofai.com/ [LearnWithGoogle](https://learndigital.withgoogle.com/digitalgarage/course/elements-artificial-intelligence )
Assistance : ChatGPT, Bard AI
By - Agastya

> [!Example]- Different AI Techniques 
> - Computer vision
> - Search and planning for finding optimal routes\
> - Decision Making under complex/dynamic enviroment
> -  Content recommendation


[Additional Resource]
AI Terminologies : https://atozofai.withgoogle.com

> [!check] Key Terminology #Key-Terminology
> ### Autonomy
> The ability to perform tasks in complex environments without constant guidance by a user.
> ### Adaptivity
The ability to improve performance by learning from experience.

When defining and talking about AI we have to be cautious as many of the words that we use can be quite misleading. Common examples are learning, understanding, and intelligence.

[Marvin Minsky](https://en.wikipedia.org/wiki/Marvin_Minsky), a cognitive scientist and one of the greatest pioneers in AI, coined the term **suitcase word** for terms that carry a whole bunch of different meanings that come along even if we intend only one of them. Using such terms increases the risk of misinterpretations such as the ones above.

in the context of AI, it is obvious that different AI systems cannot be compared on a single axis or dimension in terms of their intelligence. Is a chess-playing algorithm more intelligent than a spam filter, or is a music recommendation system more intelligent than a self-driving car? These questions make no sense. This is because artificial intelligence is narrow; being able to solve one problem tells us nothing about the ability to solve another, different problem.

> When discussing AI, we would like to discourage the use of AI as a countable noun: one AI, two AIs, and so on. AI is a scientific discipline, like mathematics or biology. This means that AI is a collection of concepts, problems, and methods for solving them.
> 
> The use of AI as a countable noun is of course not a big deal if what is being said otherwise makes sense, but if you’d like to talk like a pro, avoid saying "an AI", and instead say "an AI method".


![](../_MediaSource/AI/AI%20Fundamentals/IMG-1.png)

Fields related to AI

-------
## Machine learning
Systems that improve their performance in a given task with more and more experience or data.

## Deep learning
Complexity of mathematical model.

## Robotics
Robotics is the ultimate challenge of AI since it requires a combination of all areas of AI. programming robots to navigate complex real-world situations, integrating AI components like computer vision, speech recognition, natural language processing, reasoning, and machine learning to enable interaction and collaboration with humans.
# Defining AI
>[!Info] Turing Test #CaseStudy 
>- Alan Turing 1912 - 1954 - English mathematician and Logician
>- contribution to AI is his imitation game, which later became known as the [Turing test](https://en.wikipedia.org/wiki/Turing_test)
>- If the interrogator cannot determine which player, A or B, is a computer and which is a human, the computer is said to pass the test. The argument is that if a computer is indistinguishable from a human in a general natural language conversation, then it must have reached human-level intelligence.

>[!example] Counter Argument - Chinese Room  argument
>The best known counter-argument is John Searle’s [Chinese Room](http://www.iep.utm.edu/chineser/) thought experiment.
Searle argued that even if the person outside the room gets the impression that he is in a conversation with another Chinese-speaking person, the person inside the room does not understand Chinese.

> [!Check] Key Terminology
> ## General AI VS Narrow AI
>   General AI refers to a machine capable of handling any intellectual task, while narrow AI refers to AI that focuses on a specific task. Narrow AI is what we currently use, while general AI remains mostly a concept in science fiction. 
>   ## Weak AI Vs Strong AI
>   Weak AI refers to systems that exhibit intelligent behavior despite being computers, whereas strong AI would represent a genuinely intelligent and self-conscious mind.
# Search and Problem Solving

First stage of problem solving is defining the choices and their consequences, which is often far from trivial and can require careful thinking

two kinds of problems:
- Search and planning in static environments with only one “agent”
- Games with two-players (“agents”) competing against each other

>[!Check] Key terminology #Key-Terminology 
>### The state space
>State space refers to the set of possible situations or locations in a problem.
>### Transition
>Transitions are the direct moves between states. 
>### Cost
>Costs are associated with transitions, indicating differences in preference or expense. Costs can represent factors like distance or time. If transitions are equal, costs can be ignored.

### John McCarthy’s key statement about AI
“The study is to proceed on the basis of the conjecture that every aspect of learning or any other feature of intelligence can in principle be so precisely described that a machine can be made to simulate it.”


## MinMax Problem 
#Algorithm https://course.elementsofai.com/2/3
Actual Algorithm : https://en.wikipedia.org/wiki/Minimax#Minimax_algorithm_with_alternate_moves

>[!example] Game Tree
In AI, game trees are used to solve games. Nodes in the game tree represent different states of the game, arranged in levels corresponding to each player's turn. The root node is the starting position, and its children are the possible states resulting from the first player's moves. Each child node further has children representing states resulting from the opposing player's moves. This continues until reaching end states, such as a win or a tie in tic-tac-toe.

> [!info] Finding the optimal moves
> Having determined the values of all the nodes in the game tree, the optimal moves can be deduced: 
> - at any Min node (where it is Min’s turn), the optimal choice is given by the child node whose value is minimal, and conversely, 
> - at any Max node (where it is Max’s turn), the optimal choice is given by the child node whose value is maximal. 
> - Sometimes there are many equally good choices that are, well, equally good, and the outcome will be the same no matter which one of them is picked.

Player whose chance is next is mentioned on the side
![](../_MediaSource/AI/AI%20Fundamentals/IMG-2.png)

When applying AI to real-world problems, plain search methods become limited. The number of states in complex scenarios grows exponentially, making exhaustive search or clever heuristics impractical. Additionally, transitions between states are often non-deterministic, meaning the outcome of an action is not completely determined due to factors beyond our control. To handle these challenges, we need to introduce concepts of uncertainty and probability, moving towards real-world AI applications.

# Odds and probability
> [!quote] History of Dealing with uncertainty 
> In the history of AI, different approaches emerged for handling uncertain and imprecise information. One contender was fuzzy logic, which dealt with degrees of uncertainty and found applications in areas like washing machines. However, probability has proven to be the most effective approach for reasoning under uncertainty. Currently, the majority of AI applications rely on probability to some extent.

> [!example] How probability is used to deal with uncertainty
>   The main lesson about probability is to view uncertainty as something that can be quantified, even if it's challenging. This means we can compare and measure uncertainty using numbers. By collecting data and evaluating probabilistic statements, we can rationally discuss and think about uncertainty. Probability provides a systematic approach to address uncertainty.

## The Bayes rule/Formula
Bayes' rule can be expressed in terms of odds, specifically the *prior odds and posterior odds*. 
Prior odds represent our assessment of the likelihood before obtaining new information. The formula allows us to update the prior odds based on new information, resulting in the posterior odds. Posterior odds reflect the updated odds after incorporating the new information.

>[!check] Key Terminology #Key-Terminology 
>## Likelihood Ratio
>The likelihood ratio is a ratio that compares the probability of an observation given the event of interest (e.g., rain) to the probability of the observation given the absence of the event (e.g., no rain). It helps quantify the relative chances of the event occurring.

## Bayes classifier
The Bayes classifier is a machine learning technique that can be used to classify objects such as text documents into two or more classes. The classifier is trained by analyzing a set of training data, for which the correct classes are given.

# Machine Learning
#MachineLearning 
Art of extracting knowledge from data.
Computer programs that uses algorithms to <u>analyze data</u> and <u>make intelligent predictions</u> based on the data without being explicitly programmed.
- In most common  ML problems, exactly one class value is correct at a time.
## Division of Machine Learning
1. **Supervised Learning**: ==(Classification task)== We feed the data to algorithms, in which that data are labeled and we know what our output should like having the relationship between the input values "X" and Output values "Y" 
   Where the correct answers are available, and the task of the machine learning algorithm is to find a model that predicts them based on the input data.  
> [!Tip]- Supervised Learning / Regression
> In supervised machine learning, instead of manually creating rules for classification, we use examples with correct labels to train an AI model. The AI learns from these labeled examples and can then recognize labels for new, unseen data. This process is supervised because a supervisor provides the correct labels for the training data, guiding the learning algorithm to produce accurate answers independently.
> In supervised learning, we can use it not only for classification (predicting labels), but also for regression tasks where the goal is to predict numerical outcomes. For example, predicting the number of ad clicks, traffic accidents, or real estate prices based on relevant data.


2. **Unsupervised Learning**: In this data is not labelled instead pattern recognition is being relied on to generate algorithms. 
   Patterns like grouping similar items ie. clusters  or reducing the data to small number of important "dimensions"
   >[!Tip]- Unsupervised Learning
   >In unsupervised learning, the correct answers are not provided. This makes the situation quite different since we can’t build the model by making it fit the correct answers on training data. It also makes the evaluation of performance more complicated since we can’t check whether the learned model is doing well or not.
   >
   >Typical unsupervised learning methods attempt to learn some kind of “structure” underlying the data. This can mean, for example, visualization where similar items are placed near each other and dissimilar items further away from each other. It can also mean clustering where we use the data to identify groups or “clusters” of items that are similar to each other but dissimilar from data in other clusters.
<br>
3.  **Reinforcement Learning**: Type of machine learning where an agent learns how to make decisions by interacting with its environment. Agent receives feedback in the form of reward and punishments. The goal of agent is to learn the best action to take in different situations to maximize its rewards.
   It does this by trying out different actions, observing the results, and adjusting its strategy based on the feedback it receives.

## What is overfitting?

> [!Danger] Overfitting
> Overfitting is a problem that can occur in machine learning when a model learns the training data too well. This means that the model becomes too specific to the training data and does not generalize well to new data. As a result, the model may perform poorly on new data that it has not seen before.

There are a few things that can cause overfitting, including:

- Using a model that is too complex for the data.
- Training the model for too long.
- Having too little training data.

There are a few things that can be done to prevent overfitting, including:

- Using a regularization technique.
- Cross-validation.
- Data augmentation.


> [!example] :*Cross-Validation method* : Used to avoid overfitting
> Training Data / Test Data/ Model  
> The first thing to keep in mind in order to avoid big mistakes, is to split your data set into two parts: the **training data** and the **test data**. We first train the algorithm using only the training data. This gives us a model or a rule that predicts the output based on the input variables.
> *Regularisation* and *Data Augmentation* methods are also used to avoid overfitting

## Types of Supervised Learning

> [!quote] Nearest Neighbour

### Linear Regression (Subset of Supervised Learning)
> [!Info] Linear Regression:
> Linear regression is a statistical method that is used to model the relationship between two variables. One variable is called the dependent variable, and the other variable is called the independent variable. The goal of linear regression is to find the best-fitting line that describes the relationship between the two variables.
> ```
> y = a + bx where:
> y is the dependent variable
x is the independent variable
a is the y-intercept
b is the slope of the line
> ```

> [!Check] Key Terminology
> - Intercept : "The starting figure through which model begins"
> -  Weight or coefficient : The constant through which the value changes in one unit

Here are some of the advantages of linear regression:

- It is a simple and easy-to-understand algorithm.
- It is relatively easy to implement and interpret.
- It can be used to solve a wide variety of problems.

Here are some of the disadvantages of linear regression:

- It assumes that the relationship between the variables is linear.
- It can be sensitive to outliers.
- It is not always possible to find a good-fitting line.

> [!quote] Logistic regression

# Neural Network
Neural network can mean either a “real” biological neural network such as the one in your brain, or an artificial neural network simulated in a computer.

> [!Check] Key Terminology
> - **Deep learning** is a machine learning technique that uses multiple layers of simple processing units to learn more complex structures.
> - **Neural networks**, both biological and artificial, consist of simple units called **neurons** that receive and transmit signals to each other.
> - The wires that provide the input to neurons are called **dendrites**, and the wires that transmit the outgoing signal are called **axons**.

> [!quote]  Neural networks are different from traditional computers in two key ways:
> - **Data storage and processing are not separated.** In neural networks, the neurons both store and process information, so there is no need to retrieve data from memory for processing.
> - **Neural networks can process vast amounts of information simultaneously.** This is because they consist of a large number of neurons, each of which can process information on its own.
> >[!Example]  Usage
> > - Because of these two differences, neural networks are suited for different tasks than traditional computers. Neural networks are particularly well-suited for tasks that require parallel processing, such as image recognition and natural language processing.
> > - Graphics processing units (GPUs) are a type of hardware that is well-suited for parallel processing. This is why GPUs have become a cost-effective solution for running massive deep learning methods.

**Linear Combination** : The sum of the weights times the inputs is called the linear combination of the inputs.

## Perceptron
- Simple neuron model with step activation function
- fundamental role in the history of neural network
- perceptron algorithm

> [!Check] Key Terminology 
> Layers
Neural networks are composed of layers. The input layer receives data directly, like pixel values in image recognition. Hidden layers process outputs from previous layers and pass their results to subsequent layers. The output layer produces the final network output. Neurons in each layer receive inputs from the previous layer and feed their output to the next layer. This layer-by-layer structure enables the network to learn and make predictions effectively.

## Convolutional Neural Network
- Convolutional neural networks (CNNs) are a type of neural network that are specifically designed for image processing.
- CNNs can detect image features such as bright or dark spots, edges, and patterns.
- This makes CNNs well-suited for tasks such as object detection and classification.
- CNNs can recognize objects in different positions, orientations, and sizes in an image.
- This is because CNNs learn to detect features, not specific pixel values.
- As a result, CNNs can be trained on relatively small datasets and still achieve high accuracy.

### CNN Structure
- Convolutional neural networks (CNNs) are typically composed of two parts: a bottom layer of convolutional neurons and a top layer of basic neurons.
- The bottom layer of convolutional neurons is responsible for detecting features in the input image.
- The top layer of basic neurons is responsible for classifying the image based on the features detected by the bottom layer.
- The bottom layer of convolutional neurons can be trained using unsupervised learning, while the top layer of basic neurons is always trained using supervised learning.
- This means that pre-trained convolutional layers can be reused in many different image processing tasks, as long as the top layer is trained on a dataset specific to the task.

Here are some additional points that are mentioned in the text but not explicitly summarized above:

- The bottom layer of convolutional neurons is typically trained on a large dataset of unlabeled images.
- The top layer of basic neurons is typically trained on a smaller dataset of labeled images.
- The features detected by the bottom layer of convolutional neurons are typically low-level features, such as edges and corners.
- The features detected by the top layer of basic neurons are typically high-level features, such as objects and scenes.

###  Generative adversarial networks (GANs)
To write


