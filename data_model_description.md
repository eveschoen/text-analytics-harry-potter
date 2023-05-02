**CORPUS**: all books combined into a dataframe and indexed by a particular OHCO; enables access to chronological tokens with associated part-of-speech (https://github.com/eveschoen/text-analytics-harry-potter/blob/main/output/CORPUS.csv)
  - `book_id`: first level of the OHCO; identifies the particular book in the Harry Potter series where ids 1-7 correspond to the respective books
  - `chap_num`: second level of the OHCO; identifies the particular chapter in a given book in the Harry Potter series
  - `para_num`: third level of the OHCO; identifies the particular paragraph in a given chapter in a given book in the Harry Potter series
  - `sent_num`: fourth level of the OHCO; identifies the particular sentence in a given paragraph in a given chapter in a given book in the Harry Potter series
  - `token_num`: fifth level of the OHCO; identifies the particular token in a given sentence in a given paragraph in a given chapter in a given book in the Harry Potter series
  - `pos_tuple`: a tuple of a specific token and its associated part-of-speech in the given context
  - `pos`: the extracted part-of-speech for that token
  - `token_str`: the word as it appears in the text
  - `term_str`: the token in its most basic form, completely lower-cased and any extraneous punctuation removed
  
**LDA-PHI**: a table of topics and term concentration in a particular topic (https://github.com/eveschoen/text-analytics-harry-potter/blob/main/output/LDA-PHI.csv)
   - `term_str`: the index of the `PHI` table; a term from the corpus
   - `T00` - `T19`: topics 1-20, used for topic modeling

**LDA-THETA**: a table of documents and their associated topic concentrations (https://github.com/eveschoen/text-analytics-harry-potter/blob/main/output/LDA-THETA.csv)
   - `book_id`: the index of the `THETA` table; the identifier for a book in the Harry Potter series
   - `T00` - `T19`: topics 1-20, used for topic modeling

**LIB**: offers metadata for the source files (https://github.com/eveschoen/text-analytics-harry-potter/blob/main/output/LIB.csv)
   - `book_id`: the index of the `LIB` table; the identifier for a book in the Harry Potter series
   - `title`: the title of a given book in the Harry Potter series
   - `chapter_regex`: the regex used to parse the chapters in a given book in the Harry Potter series
   - `book_len`: the number of tokens the given book
   - `n_chaps`: the number of chapters in a given book
   - `kendall_sum`: the Kendall statistic for rank correlation measurement

**PCA-DCM**: document and principal component matrix merged with the `LIB` table, used in PCA (https://github.com/eveschoen/text-analytics-harry-potter/blob/main/output/PCA-DCM.csv)
   - `book_id`: the index of the `LIB` table; the identifier for a book in the Harry Potter series
   - `chap_num`: the title of a given book in the Harry Potter series
   - `PC0` - `PC9`: identifiers principal components 1-10, discovered during PCA
   - `title`: the title of a given book in the Harry Potter series
   - `chapter_regex`: the regex used to parse the chapters in a given book in the Harry Potter series
   - `book_len`: the number of tokens the given book
   - `n_chaps`: the number of chapters in a given book
   - `kendall_sum`: the Kendall statistic for rank correlation measurement

**PCA-LOADINGS**: term and principal component matrix, used in PCA (https://github.com/eveschoen/text-analytics-harry-potter/blob/main/output/PCA-LOADINGS.csv)
   - `term_str`: the index of the `LOADINGS` table; a term from the corpus
   - `PC0` - `PC9`: identifiers principal components 1-10, discovered during PCA

**SA-DOCEMOTIONS**: books and the scores of their associated sentiments, used for sentiment analysis (https://github.com/eveschoen/text-analytics-harry-potter/blob/main/output/SA-DOCEMOTIONS.csv)
   - `title`: the title of a given book in the Harry Potter series
   - `anger`: measure of anger sentiment in a given book
   - `anticipation`: measure of anticipation sentiment in a given book
   - `disgust`: measure of disgust sentiment in a given book
   - `fear`: measure of fear sentiment in a given book
   - `joy`: measure of joy sentiment in a given book
   - `sadness`: measure of sadness sentiment in a given book
   - `surprise`: measure of surprise sentiment in a given book
   - `trust`: measure of trust sentiment in a given book
   - `polarity`: measure of the overall sentiment of a given book - negative suggests negative sentiment and positive suggests positive sentiment

**SA-VOCAB**: an extension of the `VOCAB` table with dummies identifying the sentiment of a given term (https://github.com/eveschoen/text-analytics-harry-potter/blob/main/output/SA-VOCAB.csv)
   - `term_str`: the index of the `SA_VOCAB` table; a term from the corpus
   - `n`: an integer denoting how many times an associated term appears in the corpus
   - `p`: the probability of term occurrence in the corpus
   - `i`: the information metric for each term in the corpus
   - `n_chars`: the number of characters that make up the associated term
   - `max_pos`: the most frequent part-of-speech associated with a term
   - `n_pos`: the number of unique parts-of-speech associated with a term throughout the corpus
   - `cat_pos`: a set of tags for each unique part-of-speech associated with a term
   - `stop`: a dummy identifier for whether a term is a stopword
   - `stem_porter`: the stem for a term based on the Porter method
   - `stem_snowball`: the stem for a term based on the Snowball method
   - `stem_lancaster`: the stem for a term based on the Lancaster method
   - `dfidf`: global boolean term entropy
   - `mean_tfidf`: the average significance of a term in the Harry Potter series
   - `anger`: dummy identifier for anger mapped to terms
   - `anticipation`: dummy identifier for anticipation mapped to terms
   - `disgust`: dummy identifier for disgust mapped to terms
   - `fear`: dummy identifier for fear mapped to terms
   - `joy`: dummy identifier for joy mapped to terms
   - `sadness`: dummy identifier for sadness mapped to terms
   - `surprise`: dummy identifier for surprise mapped to terms
   - `trust`: dummy identifier for trust mapped to terms
   - `sentiment`: a -1 or 1 to indicate the overall sentiment of a word (negative or positive)
   - `polarity`: measure of the overall sentiment of a given book - negative suggests negative sentiment and positive suggests positive sentiment

**VOCAB**: a table that provides in depth insight into the terms of a corpus (https://github.com/eveschoen/text-analytics-harry-potter/blob/main/output/VOCAB.csv)
   - `term_str`: the index of the `VOCAB` table; a term from the corpus
   - `n`: an integer denoting how many times an associated term appears in the corpus
   - `p`: the probability of term occurrence in the corpus
   - `i`: the information metric for each term in the corpus
   - `n_chars`: the number of characters that make up the associated term
   - `max_pos`: the most frequent part-of-speech associated with a term
   - `n_pos`: the number of unique parts-of-speech associated with a term throughout the corpus
   - `cat_pos`: a set of tags for each unique part-of-speech associated with a term
   - `stop`: a dummy identifier for whether a term is a stopword
   - `stem_porter`: the stem for a term based on the Porter method
   - `stem_snowball`: the stem for a term based on the Snowball method
   - `stem_lancaster`: the stem for a term based on the Lancaster method
   - `dfidf`: global boolean term entropy
   - `mean_tfidf`: the average significance of a term in the Harry Potter series

**W2V-VOCAB**: an extension of the `VOCAB` table with terms and their embeddings (https://github.com/eveschoen/text-analytics-harry-potter/blob/main/output/W2V-VOCAB.csv)
   - `term_str`: the index of the `SA_VOCAB` table; a term from the corpus
   - `n`: an integer denoting how many times an associated term appears in the corpus
   - `p`: the probability of term occurrence in the corpus
   - `i`: the information metric for each term in the corpus
   - `n_chars`: the number of characters that make up the associated term
   - `max_pos`: the most frequent part-of-speech associated with a term
   - `n_pos`: the number of unique parts-of-speech associated with a term throughout the corpus
   - `cat_pos`: a set of tags for each unique part-of-speech associated with a term
   - `stop`: a dummy identifier for whether a term is a stopword
   - `stem_porter`: the stem for a term based on the Porter method
   - `stem_snowball`: the stem for a term based on the Snowball method
   - `stem_lancaster`: the stem for a term based on the Lancaster method
   - `dfidf`: global boolean term entropy
   - `mean_tfidf`: the average significance of a term in the Harry Potter series
   - `vector`: the term vectorized in (x, y) form
   - `x`: the x-coordinate of the term vector
   - `y`: the y-coordinate of the term vector 
