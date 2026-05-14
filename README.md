<H3>Name: MUKESH KUMAR S</H3>
<H3>Register No: 212223240099</H3>
<H3>Experiment: 6</H3>
<H3>Date: </H3>
<H1 ALIGN = CENTER>Implementation of Semantic Analysis</H1>

## Aim:
To perform Parts of Speech Identification and Synonym using Natural Language Processing (NLP) techniques

## Algorithm:
<b>Step 1:</b> Import the nltk library

<b>Step 2:</b> Download the 'punkt', 'wordnet', and 'averaged_perceptron_tagger' resources

<b>Step 3:</b> Accept user input for the text

<b>Step 4:</b> Tokenize the input text into words using the word_tokenize function

<b>Step 5:</b> Iterate through each word in the tokenized text</br>
•	Perform part-of-speech tagging on the tokenized words using nltk.pos_tag</br>
•	Print each word along with its corresponding part-of-speech tag</br>
•	For each verb , iterate through its synsets (sets of synonyms) using wordnet.synsets(word)</br>
•	Extract synonyms and antonyms using lemma.name() and lemma.antonyms()[0].name() respectively</br>
•	Print the unique sets of synonyms and antonyms</br>

## Program:
```python
import nltk
from nltk.corpus import wordnet

# Downloads
nltk.download('wordnet')
nltk.download('averaged_perceptron_tagger')
nltk.download('averaged_perceptron_tagger_eng')

sentence = input("Enter a sentence: ")

# Simple tokenization
words = sentence.split()

# POS tagging
pos_tags = nltk.pos_tag(words)

synonyms = []
antonyms = []

for word in words:
    for syn in wordnet.synsets(word):
        for lemma in syn.lemmas():
            synonyms.append(lemma.name())

            if lemma.antonyms():
                antonyms.append(lemma.antonyms()[0].name())

print("POS Tags:", pos_tags)
print("Synonyms:", set(synonyms))
print("Antonyms:", set(antonyms))
```

## Output:
<img width="1616" height="297" alt="image" src="https://github.com/user-attachments/assets/09657ee2-ab13-486c-a20b-51a8e8948b3f" />

## Result:
Thus, the program to perform the Parts of Speech Identification and Synonym is executed sucessfully
