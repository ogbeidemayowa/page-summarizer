# Page-Summarizer
      Text summarization is the technique for generating a concise and precise summary of voluminous texts while focusing on the sections that convey useful information, and without losing the overall meaning.
 # Machine learning Libraries used
       Python’s NLTK toolkit
# Steps taken
     STEP 1 : Preparing the data
         To enable us to fetch the article’s text, we’ll use the Beautiful Soup library.The BeautifulSoup library is used for parsing the page while the urllib library is used for connecting to the page and retrieving the HTML We’ll use the urlopen function from the urllib.request utility to open the web page. Then, we’ll use the read function to read the scraped data object. For parsing the data, we’ll call the BeautifulSoup object and pass two parameters to it; that is, the article_read and the html.parser.
     The find_all function is used to return all the <p> elements present in the HTML. Furthermore, using .text enables us to select only the texts found within the <p> elements.
     STEP 2 : Processing the data
         To assist us to do the processing, we’ll import a list of stopwords from the nltk library.We’ll also import PorterStemmer, which is an algorithm for reducing words into their root forms. For example, cleaning, cleaned, and cleaner can be reduced to the root clean.
      STEP 3 : Tokenizing the article into sentences
         To split the article_content into a set of sentences, we’ll use the built-in method from the nltk library.
      STEP 4 :  Finding the weighted frequencies of the sentences 
         To evaluate the score for every sentence in the text, we’ll be analyzing the frequency of occurrence of each term. In this case, we’ll be scoring each sentence by its words; that is, adding the frequency of each important word found in the sentence.  
      STEP 5 :  Calculating the threshold of the sentences
          To further tweak the kind of sentences eligible for summarization, we’ll create the average score for the sentences. With this threshold, we can avoid selecting the sentences with a lower score than the average score.
      STEP 6 : Getting the summary
          Lastly, since we have all the required parameters, we can now generate a summary for the article.
          *def _get_article_summary(sentences, sentence_weight, threshold):
    sentence_counter = 0
    article_summary = ''

    for sentence in sentences:
        if sentence[:7] in sentence_weight and sentence_weight[sentence[:7]] >= (threshold):
            article_summary += " " + sentence
            sentence_counter += 1

    return article_summary*
          
      
