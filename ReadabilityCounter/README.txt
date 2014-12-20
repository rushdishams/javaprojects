=====================================================================
                                                                       
                              ======                                   
                              README                                   
                              ======                                   
                                                                       
						Readability Counter
                          December 19 2012
                                                                       
	JAR file for getting different readability measure of sentences
                                                                       
                                                                      
=====================================================================

Contents:
---------

1. Overview
2. Operation example

====================================================================

1. Overview:
-----------------------------------
ReadabilityCounter is a jar file to provide various readability scores of sentences.

The user needs to create an object of this class and then using the object, s/he can
get the readability score of sentence(s).

2. Operation example:
------------------------
A test class is provided as follows:
import java.util.ArrayList;


public class TestReadability {
	
	public static void main (String[] args){
		
		ArrayList<Double> a = new ArrayList<Double>();
		Readability r = new Readability();
		r.setText("This is a sample sentence");
		r.computeReadability();
		a = r.getReadability();
		System.out.println(a);
		
	}

}

The index of object a will be as follows: [flesh reading ease score, flesch-kincaid readability index, smog index, forcast index, fog index]

===============================================================================================================================================================