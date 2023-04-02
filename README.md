# Deep_Learning

# Report on the Neural Network Model


## Project Overview:

This project is aimed at providing the nonprofit foundation Alphabet Soup a tool to help select applicants for funding with the best chance of success in their ventures. Using knowledge of ML and neural networks I will use features provided in the dataset to create a binary classifier that is able to predict whether applicants will be successful if funded by Alphabet Soup.

The dataset for this project is a CSV provided by Alphabet Soup’s business team containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. It also contains numerous columns that capture metadata about each organization, such as:

* **EIN** and **NAME**—Identification columns
* **APPLICATION_TYPE**—Alphabet Soup application type
* **AFFILIATION**—Affiliated sector of industry
* **CLASSIFICATION**—Government organization classification
* **USE_CASE**—Use case for funding
* **ORGANIZATION**—Organization type
* **STATUS**—Active status
* **INCOME_AMT**—Income classification
* **SPECIAL_CONSIDERATIONS**—Special consideration for application
* **ASK_AMT***—Funding amount requested
* **IS_SUCCESSFUL**—Was the money used effectively


# Process

### 1: Preprocessing the data
* I first verified that the dataset has no null or duplicate values 


* I established a cutoff point for values outside of the normal categorical variables and created an ‘Other’ bin to store these. This process was completed for `CLASSIFICATION` and `APPLICATION_TYPE` columns.
<img width="1324" alt="Screenshot 2023-04-02 at 15 32 42" src="https://user-images.githubusercontent.com/115706722/229359440-ec17a610-c031-4dd7-b12f-3f8b5c28e4d0.png">

* **EIN** and **NAME**— Columns that are not targets or features are removed from the data

<img width="689" alt="Screenshot 2023-04-02 at 13 36 32" src="https://user-images.githubusercontent.com/115706722/229359755-df267b45-dd7d-4d55-9758-3d19e8a5c88b.png">

Target Variable for the model: 
* **IS_SUCCESSFUL**

Feature Variables for the model: 

* **APPLICATION_TYPE**
* **AFFILIATION**
* **CLASSIFICATION**
* **USE_CASE**
* **ORGANIZATION**
* **STATUS**
* **INCOME_AMT**
* **SPECIAL_CONSIDERATIONS**
* **ASK_AMT* *
* **IS_SUCCESSFUL**




### 2: Compiling, Training, and Evaluating the Model

The first model I built was with:
2 hidden layers - with and 80, 30 neurone split and the hidden layer activation function as `relu`, with efficiency in mind for the first go

Output layer - node is 1 because it was a binary classifier with one output - whether the funding application was successful or not. The output layer activation was `sigmoid`, because the model produces a binary classification 0-1.

The first model created the following loss and accuracy scores:
<img width="693" alt="Screenshot 2023-04-02 at 15 31 37" src="https://user-images.githubusercontent.com/115706722/229359366-714666d2-b8c7-4153-8020-bc1aabc34d0d.png">


2nd Attempt:
3 hidden layers - 100, 75, 20, I increased the number of hidden layers to 3 and added more neurones to each hidden layer, spreading the nodes proportionately to work towards greater accuracy

This model had a slight increase in accuracy score from 0.7202… to 0.7213…

<img width="780" alt="Screenshot 2023-04-02 at 15 31 01" src="https://user-images.githubusercontent.com/115706722/229359329-6efef9bb-c1f6-415b-a94e-e045ebd805ae.png">

3rd Attempt:
I experimented with using different activation functions for the hidden layers, increasing the number of epochs. This was successful and increased the accuracy score to the highest yet, as seen below.

<img width="960" alt="Screenshot 2023-04-02 at 14 54 09" src="https://user-images.githubusercontent.com/115706722/229359234-8776648c-fe68-4cb5-a9a1-c5fc391a6aed.png">
<img width="727" alt="Screenshot 2023-04-02 at 15 30 13" src="https://user-images.githubusercontent.com/115706722/229359289-30941b59-4ea0-49ed-86cc-01226e166203.png">

# Summary: 
Despite changing the number of hidden layers, the spread of neurones, the activation functions and the epochs, the accuracy scores for these attempts came blow the 75% threshold. The most successful model was the third attempt.  

If I were to make another attempt with a different model I would go back to the preprocessing stage and re-assess the columns I discluded. I would experiment with the impact of including those columns in the model and see how the accuracy score changed on this basis.
