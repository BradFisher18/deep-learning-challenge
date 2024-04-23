# Alphabet Soup Neural Network
## OVERVIEW
The purpose of this is to create a predictive neural network that will assist Alphabet Soup to determine if the applicant will be successful in their ventures if funding is granted. Using a CSV of over 34,000 instances of funding, the data is first pre-processed to clean the data so the model can run smoother. Firstly, the rows not required for the model are removed, application type and classification are sorted into ‘buckets’, converted to categorical data, and then split into test and training sets of data. The preprocessed data is then modelled using a deep neural net to try and achieve 75% accuracy so the model may be implemented in practice by Alphabet Soup.
## RESULTS
Data Preprocessing:
* For this model analysis, the variable ‘is_successful’ is the target for the model as if that is able to be predicted accurately and precisely, then it will assist Alphabet Soup to be more confident in their funding being granted.
* The variables which are used as features in this model include; status, ask amount, venture successful/unsuccessful, application type split into a column for each type, income amount split into grouping, special considerations ‘yes’, totaling 43 features.
* The variables EIN, orginisation name, affiliation, use case and organization, may all be removed from the input data as they don’t contribute to the model. \
![image](https://github.com/BradFisher18/deep-learning-challenge/assets/149662706/157e990f-0a77-45b9-b6be-1b7284b0495f)

Compiling, Training, and Evaluating the Model:
* The initial training and evaluation of the models used two hidden layers both utilizing the ReLU activation model, followed by the output layer using a sigmoid function. The ReLU activation function was selected for the hidden layers as the linear nature of it when greater than zero allows a simpler computing ability, particularly with the dataset size and large number of features inputted. The sigmoid function is then used upon output as this function provides the user a result between zero and one, useful in this case where we require a binary result. Initially two hidden layers were chosen with ten and five nodes respectively, with 30 epochs. These values were selected as a starting point as it is a simple computation to provide feedback as to the scale of optimization, if required. \
![image](https://github.com/BradFisher18/deep-learning-challenge/assets/149662706/e4c39b7c-2e22-45cc-a02c-32ff17f6aca8)

* Unfortunately, the target model accuracy of 75% was not achieved. The first attempt using two hidden layers of ten and five nodes achieved an accuracy 72.96%. Through optimization, (see details of each attempt in the point below) the first attempt of optimization was the most successful, however still only achieving an evaluated accuracy of 73%
* This model was attempted to be optimized three times to try to achieve our target of 75% accuracy. These are as below: \
\
  Attempt One; a third hidden layer with activation function ReLU was added, while the nodes were increased/added to be 25,10, and 10, whilst also increasing epoch to 100. As a result, we achieved an accuracy of 73% and a model loss of 55.35%. \
  ![image](https://github.com/BradFisher18/deep-learning-challenge/assets/149662706/d1ded482-2ab7-4b40-ac83-e17ac993ceb5)
\
![image](https://github.com/BradFisher18/deep-learning-challenge/assets/149662706/50e9d03d-0eac-43dd-92cf-1e8741446822)
\
  Attempt Two; keeping three hideen layers, additional nodes were added to the total of 100, 50 and 50, with epochs increased to 200. It was observed that this did not further improve the models accuracy, achieving only 72.85% \
  ![image](https://github.com/BradFisher18/deep-learning-challenge/assets/149662706/8a8af4c6-5a1a-437f-a7ad-ae83bee7f8d4)
\
![image](https://github.com/BradFisher18/deep-learning-challenge/assets/149662706/b6603bbe-26a5-4b38-aa1e-f29927ec5741)
\
  Attempt Three; due to attempt one outputting a better model than attempt two, the nodes were decreased down to 50 and 25, with the third layer removed. Epochs were also decreased down to 120 as it appeared that the accuracy did not vary much in attempt two as the epochs reached 200. As a result, unfortunately the model still did not achieve our target, only achieving 72.79%.\
  ![image](https://github.com/BradFisher18/deep-learning-challenge/assets/149662706/7fa8456b-6c81-4edd-a863-87420a98b04f)
\
![image](https://github.com/BradFisher18/deep-learning-challenge/assets/149662706/a908a52d-6625-4ca6-8b43-ec96d4226504)

## SUMMARY
In summary, this model was unsuccessful in being able to be implemented into practice by Alphabet Soup. The model achieved an accuracy of 73% when there were three hidden layers using the ReLU function, along with 25, 10 and 10 nodes, iterated over 100 epochs. As we saw that the model performed better in the second attempt, it is recommended that smaller intervals above those nodes are attempted, as well as keeping it at two hidden layers may actually have a positive impact. However, after attempting this the results were not improved and so further optimization techniques such as different activation function, or alternatively hyper-optimisation training may be adopted. \
Each file was outputted as an HDF5 file, which can be found under the directory 'h5_files' for their respective optimisation attempt. 
