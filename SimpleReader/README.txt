=====================================================================
                                                                       
                              ======                                   
                              README                                   
                              ======                                   
                                                                       
						 Simple File Reader
                          December 19 2012
                                                                       
		JAR file for reading every line in an ASCII text file
                                                                       
                                                                      
=====================================================================

Contents:
---------

1. Overview
2. Operation example

====================================================================

1. Overview:
-----------------------------------
SimpleReader is a jar file to read every line of a text file.

This class is useful to read the sentences in a text file if each sentence is
put in a newline.

2. Operation example:
------------------------
A test class is provided as follows:
import java.util.ArrayList;


import java.util.ArrayList;


public class TestSimpleReader {
	
	public static void main(String[] args){
		ArrayList<String> a = new ArrayList<String>();
		SimpleReader reader = new SimpleReader("file path and file name");
		a = reader.readFile();
		System.err.println(reader.getFileLength());
		for (String line: a){
			System.out.println(line);
		}
		
	}

}

===============================================================================================================================================================