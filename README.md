# Explorer documentation
The project is part of NNLP-IL. NNLP-IL is a national initiative for the creation of infrastructure, research and development of advanced capabilities for the advancement of the field of NLP in Hebrew and Arabic. More about that [here](https://nnlp-il.mafat.ai/)

[Explorer](https://dataset-explorer.nnlp-il.mafat.ai/)
Lemmatization was performed using [Trankit](https://github.com/nlp-uoregon/trankit).  
By using our extended list, we can remove [stopwords](https://github.com/NNLP-IL/Stop-Words-Hebrew).

## Comparative analysis:
Choosing two datasets will allow you to compare them.  

In the first panel, you'll find a summary of the datasets basic statistics:  
**Unique words** - Calculate the sum of all unique words in the two datasets (not to be mistaken with the sum of all word frequencies), this can give you an idea of how complex the text is.  
**Words appear ones** -  Count of unique words appearing only once. This number is inflated due to the Hebrew language's structure. This problem can be partially fixed using lemmatization.  
**Number of words** - Sum of all word frequencies.  
**Type-Token ratio (TTR)** -  Total number of unique words (types) divided by total number of words (tokens). Higher is more complex in terms of complexity.  
**Gini index** -  We measure based on the frequency of words. It measures how evenly words appear. The more evenly words appear in the text, the more difficult it is to predict which word will follow and therefore, the more complex the text becomes. A higher number indicates that the text is less even and therefore less complex. It is worthwhile to note that there are exceptions to this rule: for example, recipes are simply texts with evenly distributed words.  
**Average len words** - The average number of characters in a word. Technical texts have longer words.
Number line - Counting the number of lines in a dataset. 
**Mean line** - Words per line on average. This can provide insight into the basic structure of the text. Depending on the dataset, a line may contain an article, or a sentence.  
**Median line** - The median number of words per line.  
**Language recognition in corpus** - non-Hebrew language that appears in the text (percentage). we used the [langdetect](https://pypi.org/project/langdetect/) package  
**Lexical Density** - The ratio of stop words to the sum of all word frequencies. It is easier to understand a text with more stop words. Children's books, for example, contain a large number of stopwords  


Below you can find the following graphs:  
**Ngram** - The top ten most frequently used N words in the text. The slider lets you adjust the number of N to get a unigram, bigram, trigram, etc.  
**Word frequency** - In order to provide an efficient response, you can obtain the frequency of each word in the text, except for words that appear less than 10 times.  
**Topics** - We modeled the topic using the NMF which gets tf-idf and fine-tuned the number hyperparameter using the Coherence Model. If the improvement is less than 10%, we prefer fewer topics. We don't change the hyper-parameters for each text individually, but we think the result can give a good understanding of the text  
**Character distribution** - For every word in the selected dataset.  
**Non-Alphabetic characters** -  Non-Alphabetic characters are counted. Besides numbers and punctuation, it also contains emojis and Chinese signs and such, which are easily considered noise.  
**Zipf law** - [The Zipf's Law](https://en.wikipedia.org/wiki/Zipf%27s_law) is an empirical formula that describes the frequency distribution of words in natural language texts. The empirical formula is compared with the one calculated based on the dataset.  
**Distance between datasets** - A comparison of the distribution of 5000 words across all datasets using [KL divergence](https://en.wikipedia.org/wiki/Kullback%E2%80%93Leibler_divergence). Higher the number, the greater the distance between the word distributions in the datasets.  



