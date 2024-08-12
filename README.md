*Troll Tweet Analysis Project from Late 2022*
---
**Description**
- The goal of this project was to see if sentiment analysis could be leveraged in order to automate the detection of "troll/fake" tweets, but would have been applicable to text content from any social media site.
- - Twitter is much more convenient from an analysis point of view though, due to the (at the time) limited message length only ~280 characters.
  - It's worth nothing that today (8/12/2024), the messages in Twitter are not limited in that way.
---
**Methodology**
Applied the spaCy natural language processing pipeline and the spacytextblob additional component.
- The base pipeline contains a tokenizer, tagger, parser, and entity recognizer.
- - The tokenizer segments the text into tokens.
  - The tagger handles the assignment of part-of-speech tags to different parts of the text.
  - The parser takes care of dependency labels.
  - The entity recognizer is what can identity something like the name of a place, or person.
  - It is the additional component added by spacytextblob which handles the sentiment analysis, and provides two metrics: polarity and subjectivity.
  - - Polarity determines the overall sentiment of text, with values greater than 0 leaning positive, and values less than 0 leaning negative. A value close to zero is neutral. Think of the number line going from -1 to 1, with 0 obviously in the center.

An existing data set of ~200,000 tweets was sourced from this link: https://github.com/fivethirtyeight/russian-troll-tweets
- This data was conveniently placed onto Google BigQuery by GitHub user 'elithrar': https://github.com/elithrar
- Many tweets contained URLs and other impertinent information, so they were all processed via regex prior to the sentiment analysis process
- - This ensured that only relevant data was passed through
---
**Dependencies**
- spaCy
- spacytextblob
- pandas
- numpy
---
**Results**
7 out of the 21 total .csv files were processed in the manner described in the 'Methodology' section
- 70,000 tweets
- Average polarity: 0.167783005
- Average subjectivity: 0.527843928
![image](https://github.com/user-attachments/assets/35e219f6-fdd9-409c-9bd9-6c19bcc4898a)
- It was found that ultimately, sentiment analysis does not provide enough information if the goal is to automate the detection of 'fake/troll/misinformation' content on the web.
- - Location data helps, but can be spoofed
  - - ex: A foreign national sending a tweet about a US election can easily spoof their location to be from Missouri, for example
    - The inclusion of VPN services and other similar mechanisms further complicate matters
