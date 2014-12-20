=====================================================================
                                                                       
                              ======                                   
                              README                                   
                              ======                                   
                                                                       
Text Content (Interface to use Lingpipe sentence boundary detection method)
                          October 30 2012
                                                                       
			JAR file for extracting sentences from an ASCII text file
                                                                       
                                                                      
=====================================================================

Contents:
---------

1. Overview
2. Operation example

====================================================================

1. Overview:
-----------------------------------
TextContent is a jar file to extract sentences from an ASCII text file.
The jar file works as an easy interface to the lingpipe sentence boundary
detection method. 

If the user has an ASCII text file as a string containing one or more sentences and
wants to extract the sentences from it using the lingpipe sentence boundary model,
then this is the interface for that.

2. Operation example:
------------------------
A test class is provided as follows:

public class TestTestContent {
	
	public static void main (String [] args){
		TextContent t = new TextContent(); //creating TextContent object
		t.setText("This is wonderful. This is cold."); //setting the text
		t.setSentenceBoundary(); //detecting the sentence boundaries
		String[] array = t.getSentence();//getting the sentences in an array
		for (String str : array)
			System.out.println(str); //printing each sentence of the text
	}

}

4. Other Documentations:
------------------------

If you use this interface, then please refer to the work as listed. The interface was originally developed for this work-

[2] Rushdi Shams and Robert E. Mercer, "Investigating Keyphrase Indexing with Text Denoising", 12th ACM/IEEE-CS Joint Conference on Digital Libraries (JCDL2012), Washington DC, USA, June 10-14, 2012.

===============================================================================================================================================================