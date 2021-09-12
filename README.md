# Quora Question Pair Similarity

## Description 

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

