=============================================================================================================
                                                                       
                              ======                                   
                              README                                   
                              ======                                   
                                                                       
						  TF-IDF Measure
                          March 04 2013
						Author: Barkin Aygun
				Author: Rushdi Shams, UWO, Canada
						   version: 1.0
                                                                       
		JAR file for measuring TF-IDF of each document in a collection
NOTE: 	THE TERM FREQUENCY AND INVERSE DOCUMENT FREQUENCY ARE MEASURED WITHOUT EXCLUDING THE STOPWORDS
		THIS HAS BEEN FIXED IN version 1.1
		
=============================================================================================================

Contents:
---------

1. Overview
2. Operation example

=============================================================================================================

1. Overview:
-----------------------------------
TF-IDF.jar is a Java Archive file to measure TF-IDF of each document 
in a document collection (corpus).

The jar can be used to 
(a) get all the terms in the corpus
(b) get the document frequency (DF) and inverse document frequency (IDF) of 
all the terms in the corpus
(c) get the TF-IDF of each document in the corpus
(d) get each term with their frequency (no. of presence), term frequency (TF) and TF-IDF in every document

To calculate TF the following formula is used.
TF (term) = frequency of the term in the document / no. of terms in the document

It is possible to use a variant of the formula (like 1 + log (frequency) or sqrt (frequency) by
extracting the frequency of each word.

To calculate IDF the following formula is used.
IDF (term) = log (no. of documents in the corpus / document frequency of the term)

To calculate TF-IDF of each term the following formula is used
TF-IDF (term) = TF (term) X IDF (term)

To calculate TF-IDF of each document, the following formula is used
TF-IDF (document) = sqrt (sum (TF-IDF (term)))

It is possible to use a variant of TF-IDF (document) normalization other than using squared root by
extracting the TF-IDF (term)s.

2. Operation example:
------------------------
A test class is provided as follows:

import java.util.HashMap;
import java.util.Iterator;
import java.util.Map;

public class TestTF_IDF {
	
	public static void main(String[] args){
		//Test code for TfIdf
		TfIdf tf = new TfIdf("directory of your corpus");
		//Contains words in the documents
		String word;
		//Contains file name being processed
		String file;
		//Variable to hold document frequency and IDF of each word
		Double[] dfIDF;
		
		//Print document frequency and IDF of every word in the corpus
		for (Iterator<String> it = tf.allwords.keySet().iterator(); it.hasNext(); ) {
			word = it.next();
			dfIDF = tf.allwords.get(word);
			//dfIDF[0] is the DF of the word and dfIDF[1] is the IDF of the word
			System.out.println("Term " + word + " " + " Document Frequency " + dfIDF[0] + " " + " IDF " + dfIDF[1]);
		}//for (Iterator<String> it = tf.allwords.keySet().iterator(); it.hasNext(); )	
		
		tf.buildAllDocuments();
		
		//Print TF-IDF of each document in the corpus
		for (Iterator<String> it = tf.documents.keySet().iterator(); it.hasNext(); ) {
			file = it.next();
			System.err.println("File Name " + file + "\t" + "TF-IDF " + tf.documents.get(file).vectorlength);
		}//for (Iterator<String> it = tf.documents.keySet().iterator(); it.hasNext(); )
		
		//Prints each term in a document, its frequency, term frequency and tf-idf
		Map<String, Double[]> myMap = new HashMap<String, Double[]>();
		Double[] values;
		for (Iterator<String> it = tf.documents.keySet().iterator(); it.hasNext(); ) {
			file = it.next();
			System.out.println("File \t" + file);
			
			myMap = tf.documents.get(file).getF_TF_TFIDF();
			
			for (String key : myMap.keySet()) {
				
				values = myMap.get(key);
			    System.out.println("Term = " + key + " Frequency = " + values[0] + " Term Frequency " + values[1] + " TF-IDF " + values[2]);
			  
			}//for (String key : myMap.keySet())
		}//for (Iterator<String> it = tf.documents.keySet().iterator(); it.hasNext(); )
		
	}//public static void main(String[] args)
}//public class TestTF_IDF


=============================================================================================================