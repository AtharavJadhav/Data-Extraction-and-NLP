# Data-Extraction-and-NLP

Extract textual data articles and perform text analysis to compute variables that are explained below.


## Objective

The objective of this project is to extract textual data articles from the given URL and perform text analysis to compute variables that are explained below.

## Data Extraction

For each of the articles, given in the input.xlsx file, extract the article text and save the extracted article in a text file with URL_ID as its file name.
While extracting text, the program extracts only the article title and the article text. It does not extract the website header, footer, or anything other than the article text. 

This has been done with the help of PYTHON and various other Libraries such as 'polar', Beautiful Soup, requests, openpyxl, os.path, NLTK, re, string, and csv.

## Data Analysis

For each of the extracted texts from the article, perform textual analysis and compute variables, given in the output structure excel file. The output is saved in the exact order as given in the output structure file, “Output.xlsx”

### Sentiment Analysis

Sentimental analysis is the process of determining whether a piece of writing is positive, negative, or neutral. The below Algorithm is designed for use in Financial Texts. It consists of steps:

#### Cleaning using Stop Words Lists

The Stop Words Lists (found in the folder StopWords) are used to clean the text so that Sentiment Analysis can be performed by excluding the words found in Stop Words List. 

#### Creating a dictionary of Positive and Negative words

The Master Dictionary (found in the folder MasterDictionary) is used for creating a dictionary of Positive and Negative words. We add only those words in the dictionary if they are not found in the Stop Words Lists. 

#### Extracting Derived variables

We convert the text into a list of tokens using the nltk tokenise module and use these tokens to calculate the 4 variables described below:

Positive Score: This score is calculated by assigning the value of +1 for each word if found in the Positive Dictionary and then adding up all the values.

Negative Score: This score is calculated by assigning the value of -1 for each word if found in the Negative Dictionary and then adding up all the values. We multiply the score with -1 to be a positive number.

Polarity Score: This is the score that determines if a given text is positive or negative in nature. It is calculated by using the formula: 
Polarity Score = (Positive Score – Negative Score)/ ((Positive Score + Negative Score) + 0.000001)
The range is from -1 to +1

Subjectivity Score: This is the score determining whether a given text is objective or subjective. It is calculated by using the formula: 
Subjectivity Score = (Positive Score + Negative Score)/ ((Total Words after cleaning) + 0.000001)
The range is from 0 to +1

### Analysis of Readability

Analysis of Readability is calculated using the Gunning Fox index formula described below.

Average Sentence Length = the number of words / the number of sentences

Percentage of Complex words = the number of complex words / the number of words 

Fog Index = 0.4 * (Average Sentence Length + Percentage of Complex words)

### Average Number of Words Per Sentence

The formula for calculating is:
Average Number of Words Per Sentence = the total number of words / the total number of sentences

### Complex Word Count

Complex words are words in the text that contain more than two syllables

### Word Count

We count the total cleaned words present in the text by 
-[x] removing the stop words (using the stopwords class of the nltk package).
-[x]removing any punctuations like ? ! , . from the word before counting.

## Output Data Structure

Output Variables: 
1) All input variables in “Input.xlsx”

2) POSITIVE SCORE

3) NEGATIVE SCORE

4) POLARITY SCORE

5) SUBJECTIVITY SCORE

6) AVG SENTENCE LENGTH

7) PERCENTAGE OF COMPLEX WORDS

8) FOG INDEX

9) AVG NUMBER OF WORDS PER SENTENCE

10) COMPLEX WORD COUNT

11) WORD COUNT

This assignment was provided by www.blackcoffers.com
