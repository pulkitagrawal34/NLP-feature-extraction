### NLP Feature Extraction
Using Natural Language Processing to extract key features from the employment agreements.

Some information about the employment agreements: 
* Agreements are from different employers and for different positions, though key elements   of the agreement like base salary, termination clause etc. may be common, the structure of the agreement itself will be different 
* There are two different document types – a) employment agreements and b) amendments to employment agreement

A model has been built that classifies the dataset into employment and amendment letter feature extraction has been done on the employment letter.
Now employment letter was used for further extraction of features such as employee name, employer name, salary, role and agreement date.

#### Extraction of Employee name:
A regular expression was run on the entire txt file to find out the first name of the employee beside salutation.
Every employment letter was pre-processed(which involves tokenization, parts of speech tagging) which was further chunked to list all the "PERSON" chunk labels, and then another regex was applied to remove the unwanted names from the list(incase there is more than one).

#### Extraction of Employer name:
A regular expression was run which looks for nouns ending with "corporation or Inc."

#### Extraction of Base Salary:
A regular expression was run which looks for $ sign followed by numbers. Now, as there is a possibility of multiple such cases.  While going through these txt files, it was seen that the base salary was the maximum amount mentioned on the letter and hence was sorted accordingly. 

#### Extraction of agreement date:
A regular expression was run which finds all the dates in the txt file and it was seen that the agreement date was the first date mentioned in the letters, and hence was returned accordingly.

#### Extraction of role:
A list of all common roles was made and again regex waas used to look if the letter contains any of the listed roles. Any column that you find empty might have roles not mentioned in the list and hence empty.