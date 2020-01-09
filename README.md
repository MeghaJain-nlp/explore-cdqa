# Explore-cdqa
Exploring cdqa suite built for closed domain question answering system
Article Reference : https://towardsdatascience.com/how-to-create-your-own-question-answering-system-easily-with-python-2ef8abc8eb5

THEORY : 

CDQA suite has been built over the Pytorch version of BERT by HuggingFace
The suite contains 3 blocks :
  1. cdqa : easy to use python package to implement a Question Answering Pipeline
  2. CDQA annotator : To help you annotate your existing text with question and answer, use that to train your QA pipeline
  3. cdqa UI : to add the question answering ui as a rest api 
  
 CDQA : The architecture works mainly on retriever and READER blocks
 1. The corpus of documents gets converted to a tf idf matrix 
 2. The query is sent as a tf idf vector to the retriever
 3. The retriever uses scoring system to find the most relevant documents
 4. The documents searches through all the paragraphs and sends them to the READER along with the query
 5. The Reader uses BERT to find the most suitable paragraph and the answer of the question
 
 1. Once the query is sent to the retriever, it looks for the most probable docuemnts in the database on the basis of TF IDF based on unigrams and bigrams and computes the cosine similarity between the documents and the question. 
 2. The most probable documents are then divided into paragraphs
 3. The praragraphs and the question is sent to the Reader
 4. The Reader is built upon the pytorch implementation of BERT by huggingFace. The Reader provides the most probable answer in ech paragraph
 5. A final layer uses a ranking system to output the highest probbale answer
 
 
 USE MODEL :
 
