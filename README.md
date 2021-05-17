# EdvancerDlMultilabel-prediction
Data set :  https://www.dropbox.com/s/5721wcs2guuykzl/stacksample.zip?dl=0

Objective : Given text for Questions from StackoverFlow posts, predict tags associated with them.

This is a scaled down version of predecting only top 10 most occurring tags

Programming Language : Python using nltk & Keras

Model Architecture : Deep Learning using Recurrent Neural Network (RNN)

About Data Set

Dataset has text of questions, answers and thier corresponding tags from the Stack Overflow programming Q&A website.

This is organized as three files:

Questions contains the title, body, creation date, closed date (if applicable), score, and owner ID for all non-deleted Stack Overflow questions.

Tags contains the tags on each of these questions.

Data Pre-Processing

Read Questions File
Drop All columns except Id,Title and Body
Now the text in the Body column seem to have many html tags in the text. We use Regular Expressions and Clean the Body column text by removing the html tags

import re 
def rem_html_tags(body):
    regex = re.compile('<.*?>')
    return re.sub(regex, '', body)
ques['Body'] = ques['Body'].apply(rem_html_tags)
