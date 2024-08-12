*Troll Tweet Analysis Project from Late 2022*
---
**Description**
- Simple application of the spaCy natural language processing pipeline and the spacytextblob additional component
- The base pipeline contains a tokenizer, tagger, parser, entity recognizer, and lemmatizer.
- - The tokenizer segments the text into tokens
  - The tagger handles the assignment of part-of-speech tags to different parts of the text
  - The parser takes care of dependency labels
  - The entity recognizer is what can identity something like the name of a place, or person
  - The lemmatizer turns words into their base forms (running -> run)
  - It is the additional component added by spacytextblob which handles the sentiment analysis, and provides two metrics: polarity and subjectivity.
  - - Polarity determines the overall sentiment of text, with values greater than 0 leaning positive, and values less than 0 leaning negative. A value close to zero is neutral. Think of the number line going from -1 to 1, with 0 obviously in the center.
   

