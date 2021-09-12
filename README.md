# Quora Question Pair Similarity

## Description 

<img align="left" src="https://user-images.githubusercontent.com/20265851/132982880-34ee5dc5-c358-4105-ae02-2eca800acb47.png" height="222px"/>

Quora is a place to gain and share knowledge—about anything. It’s a platform to ask questions and connect with people who contribute unique insights and quality answers. This empowers people to learn from each other and to better understand the world.

Over 100 million people visit Quora every month, so it's no surprise that many people ask similarly worded questions. Multiple questions with the same intent can cause seekers to spend more time finding the best answer to their question, and make writers feel they need to answer multiple versions of the same question. Quora values canonical questions because they provide a better experience to active seekers and writers, and offer more value to both of these groups in the long term.

## Problem statement 

“Given two question are they duplicates of each other”

## Data set 

source : https://www.kaggle.com/c/quora-question-pairs/overview/description

COLUMNS 

    - id : tuple unique id
    - qid1/qid2 : question id of question1/question2 
    - question1/question2 : actual question in string 
    - is_duplicate : is question1 is duplicate of question2? (1:YES/0:NO) 
    
![image](https://user-images.githubusercontent.com/20265851/132982876-67501c08-bd1f-45fe-9fd0-dcd22daf8d1a.png)

## Basic Feature Addition 
 - ____freq_qid1____ = Frequency of qid1's
 - ____freq_qid2____ = Frequency of qid2's 
 - ____q1len____ = Length of q1
 - ____q2len____ = Length of q2
 - ____q1_n_words____ = Number of words in Question 1
 - ____q2_n_words____ = Number of words in Question 2
 - ____word_Common____ = (Number of common unique words in Question 1 and Question 2)
 - ____word_Total____ =(Total num of words in Question 1 + Total num of words in Question 2)
 - ____word_share____ = (word_common)/(word_Total)
 - ____freq_q1+freq_q2____ = sum total of frequency of qid1 and qid2 
 - ____freq_q1-freq_q2____ = absolute difference of frequency of qid1 and qid2 
 - 
![image](https://user-images.githubusercontent.com/20265851/132982873-4d122ae6-1bfc-4743-b725-7c8a7cf87a40.png)

## Advanced Feature Addition 
- __cwc_min__ :  Ratio of common_word_count to min lenghth of word count of Q1 and Q2 
- __cwc_max__ :  Ratio of common_word_count to max lenghth of word count of Q1 and Q2 
- __csc_min__ :  Ratio of common_stop_count to min lenghth of stop count of Q1 and Q2 
- __csc_max__ :  Ratio of common_stop_count to max lenghth of stop count of Q1 and Q2
- __ctc_min__ :  Ratio of common_token_count to min lenghth of token count of Q1 and Q2
- __ctc_max__ :  Ratio of common_token_count to max lenghth of token count of Q1 and Q2
- __last_word_eq__ :  Check if First word of both questions is equal or not
- __first_word_eq__ :  Check if First word of both questions is equal or not
- __abs_len_diff__ :  Abs. length difference
- __mean_len__ :  Average Token Length of both Questions
- __fuzz_ratio__
- __fuzz_partial_ratio__ 
- __token_sort_ratio__ 
- __token_set_ratio__ : 
- __longest_substr_ratio__ :  Ratio of length longest common substring to min lenghth of token count of Q1 and Q2

![image](https://user-images.githubusercontent.com/20265851/132982867-37ab81c6-6532-47fb-9bed-3369df85935c.png)

## Vector representation : idf-GLOVE

## Merging 

    Basic feature extraction 
    +
    Advanced feature extraction 
    +
    Vector representation
    
![image](https://user-images.githubusercontent.com/20265851/132982864-b83cd219-197e-4b8c-ba8e-bdc7c20fb350.png)

## Machine Learning 

Data split : 70/30 (70pc training and 30pc testing)

### Logistic Regression with hyperparameter tuning
 
    For values of alpha =  1e-05 The log loss is: 0.592800211149
    For values of alpha =  0.0001 The log loss is: 0.532351700629
    For values of alpha =  0.001 The log loss is: 0.527562275995
    For values of alpha =  0.01 The log loss is: 0.534535408885
    For values of alpha =  0.1 The log loss is: 0.525117052926
    For values of alpha =  1 The log loss is: 0.520035530431
    For values of alpha =  10 The log loss is: 0.521097925307

![image](https://user-images.githubusercontent.com/20265851/132982817-281d7562-0f5e-4a3f-a953-62c149eed0fe.png)

![image](https://user-images.githubusercontent.com/20265851/132982822-4cf46f72-5585-466d-9d3d-17aaceba519a.png)

### Linear SVM with hyperparameter tuning

    For values of alpha =  1e-05 The log loss is: 0.657611721261
    For values of alpha =  0.0001 The log loss is: 0.489669093534
    For values of alpha =  0.001 The log loss is: 0.521829068562
    For values of alpha =  0.01 The log loss is: 0.566295616914
    For values of alpha =  0.1 The log loss is: 0.599957866217
    For values of alpha =  1 The log loss is: 0.635059427016
    For values of alpha =  10 The log loss is: 0.654159467907

![image](https://user-images.githubusercontent.com/20265851/132982845-d2c0cff6-2916-4658-b90a-75be650372d8.png)

![image](https://user-images.githubusercontent.com/20265851/132982850-1517bb2d-d28c-45c9-bf46-6947f4ad7d60.png)

## This project was done with the help of

![image](https://user-images.githubusercontent.com/20265851/132983986-c575ee89-a790-4ae8-a8df-ef01cc1d1578.png)



