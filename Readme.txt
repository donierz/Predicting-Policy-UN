Version 3.0: May 19th, 2021

The following is the document for replication file "Predicting Policy: A Psycholinguistic Artifical Intelligence in the United Nations."
By: Gandall, Chhouk, and Wang. 

To run code, users need to use Juypter Notebook, google colab, or some equivalent. This code was programmed on google colab, with the webscrapper run on juypter notebook. 
Additional programs include Tensorflow 2.4, pdfminer, fuzzywuzzy 3.6, python-levenshtein 3.6, and setuptools 3.6. All additional programs used can be found in the code.

You will also need the Linguistic  

Overview Files: 

Model Replication: a file that contains all of the files needed to replicate results. 
General Assembly: a file containing supplemental information, including PDF documents of each webscrapped meeting. 
Security Council: a file containing supplemental information, including PDF documents of each webscrapped meeting. 

The following summary procedures will result in the replication of results. These files can be found all under the "Model Replication" 
folder.

WARNING: Tensorflow is stochastic - that is, it uses randomization - so the results may be similar, but will rarely be exactly the same. 

----- ----- ----- ----- -----
----- Start Procedure -----
----- ----- ----- ----- -----

Step 1: Parse the data and run the queries (this can take as short as a day or long as a week, depending on your computer). 
1. webscrapper_fuzzy.ipynb: a python script that, if run, will yield the meeting documents from the United Nations in text files.The script will then run queries 
using fuzzywuzzy and produce a csv. This will produce the files you need to also run through LIWC. 
2. GA_Queries.csv: A csv file containing raw data from query results (motions) in the General Assembly (CI: .95). 
3. SC_Queries.csv: A csv file containing raw data from query results (motions) in the Security Council (CI: .95). 
4. GA_LIWC Results.csv: A csv file containing documents you have run through LIWC for the GA.  
5. SC_LIWC Results.csv: A csv file containing documents you have run through LIWC for the SC.

Step 2: Clean the data and sort into classes. 
6. GA_Query_Clean.ipynb: code to clean raw GA data and summarize data.
7. GA_Query_LIWC.csv: csv file of cleaned data, both motions and LIWC combined. 
8. GA_Query_Clean.csv: csv file of cleaned and summarized GA data.
9. SC_Query_Clean.ipynb: code to clean raw SC data and summarize data. 
10. SC_Query_LIWC.csv: csv file of cleaned data, both motions and LIWC combined. 
11. SC_Query_Clean.csv: csv file of cleaned and summarized SC data.

Step 3: Run the code to produce the General Assembly Models.
12. GAPolicy_Psychology.ipynb
13. GAPolicy_Motions.ipynb
14. GAPolicy_Mixed.ipynb

15. GAConflict_Psychology.ipynb
16. GAConflict_Motions.ipynb
17. GAConflict_Mixed.ipynb

Step 4: Run the code to produce the Security Council Models. 
18. SCPolicy_Psychology.ipynb
19. SCPolicy_Motions.ipynb
20. SCPolicy_Mixed.ipynb

----- ----- ----- ----- -----
----- End Procedure -----
----- ----- ----- ----- -----

For a review of the general outline of our architecture, see figure 2. 

The following are supplemental folders you can access that will help see how the algorithm produced specific results. 

General Assembly: 
  GA Cleaned Data: an easily accessible folder of the clean GA data
  Meeting PDFs: a complete folder of every PDF pulled by the webscrapper in the GA. 
  GAPolicy_Mixed: code for mixed policy code. 
  GAConflict_Mixed: code for mixed conflict code. 

Security Council: 
  SC Cleaned Data: an easily accessible folder of the clean SC data
  Meeting PDFs: a complete folder of every PDF pulled by the webscrapper in the SC. 
  SCPolicy_Mixed: code for mixed policy.
  SCConflict_Mixed: code fro mixed conflict code. 

Suggested guidelines: 
1. Beware of the webscrapper. If you seek to replicate the entire study, running the webscrapper will take time. Again, this may take up to a week, depending on your 
computer. Second, because the UN website is constantly changing (new meetings added, new security features, etc.) you will likely not the replicate the exact data. Instead,
we recommend you use the GA_Queries.csv or SC_Queries.csv.
2. If you fail, try try again (for the ParliHeg machine)! Just because your first try fails to reproduce our results doesn't mean the code isn't working. In a stochastic system there always results that differ from the general truth. 
If results seem odd, simply rerun. This study DOES NOT set seeds, because doing so requires a consistently in the operating computer and use of tensorflow in a CPU
instead of GPU format (GPU will always be non-deterministic). 
3. Beware modifying queries. We cannot guarantee the program will work with modified queries. However, we have tested it several times on different programs, and all do work. If you wish modify the queries to check 
other possible results, do not modify any other definitions. 
4. Why Google Colab vs. Juypter Notebook? For experienced programmers the latter is obviously better - but we hope that google colab will open up the world of programs to those 
without formal training. Google colab is easy to use, and will allow various political science students to use these programs to further education. There is also a pedagogical 
purpose: instead of just asking students to accept our methods as listed in the paper, they can more easily test and run programs on their own computers, without having to download 
any additional software (well, at least formally - the code does require some downloads, but those are done automatically). 