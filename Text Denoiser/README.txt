=====================================================================
                                                                       
                              ======                                   
                              README                                   
                              ======                                   
                                                                       
					Text Denoising Tool v2.2
                          JUNE 19 2012
                                                                       
				JAR file for text denoising
                                                                       
                                                                      
=====================================================================

Contents:
---------

1. Overview of Text Denoising Tool

2. Prepare your dataset

3. Run the Tool

4. Other documentations

====================================================================

1. Overview of Text Denoising Tool:
-----------------------------------

Text Denoising Tool removes the insignificant and/or unwanted
sentences of a text according to their reading difficulty score (which in this case
is the Fog Index). 

Changes made since version 2.1:
-------------------------------

- According to [1] and for the task of
biomedical relation mining, the 30% of the most difficult-to-read sentences is called
denoised text and the rest of the text is considered as noise text. According to [2], however,
and for the task of Keyphrase indexing, the 70% of the most difficult-to-read sentences is called
denoised text and the rest of the text is considered as noise text. As the denoising threshold (% of
sentences to keep as important part of the texts) varies for different task and datasets, 
we are facilitating the user to choose his/her desired threshold (between 0% and 100%).

- Second, we are introducing an option to set by the user 
to remove short sentences (sentences of length less than 5)

- Third, the tool is now accessible with command line arguments.

Note:
-----

To get the best result with the tool, pre-process your text files by 
removing various parts of a paper like:

- Title and affiliation
- Headings, subheadings and sub sub headings
- Tables, figures and other graphics and their captions
- Reference citations like [1] [2] or [X et al., 200Z]
- References
- Unwanted symbols inserted during a PDF to text conversion

2. Prepare your dataset:
------------------------

- Your texts should be in ASCII text format in order to get processed
- Put your text files in a directory.

3. Run the Text Denoising Tool:
-------------------------

- Run the Text Denoising JAR file. Run the command java -jar TextDenoisingv2-2.jar option1 option2 option3 option4 option5
- All the options are mandatory.

Legends:
--------
option1: The source directory
option2: The denoised text directory
option3: The noise text directory
option4: Text denoising threshold (from 0 to 100)
option5: Short sentence removal (true for removing sentences of length less than 5, false to run the tool on the full text as it is)

4. Other Documentations:
------------------------

If you want to see how Text Denoising works and/or to user the tool for your research, please refer 
to the work as listed-

[1] Rushdi Shams and Robert E. Mercer, "Extracting Connected Concepts from Biomedical Texts using Fog Index", 
12th Conference of the Pacific Association for Computational Linguistics (PACLING 2011), Kuala Lumpur, 
Malaysia, July 19-21, 2011.
[2] Rushdi Shams and Robert E. Mercer, "Investigating Keyphrase Indexing with Text Denoising", 12th ACM/IEEE-CS Joint Conference on Digital Libraries (JCDL2012), Washington DC, USA, June 10-14, 2012.

===============================================================================================================================================================