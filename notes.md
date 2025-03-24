Information used: Introduction to information retrieval (2009): Manning, Raghawan, Schhütze

## 1. Boolean retrieval

Definition:
Information retrieval is about finindg unstructured material like text, that satisfies he information need from a large collection.

Information retrieval works with unstructured data.
Structured data: e.g. relational databases
Unstructured data: e.g. text

IR is also used to filtering, processing and classification of documents.
Small example: E-Mails of a person. Classified into groups (entry, spam) and can be searched/filtered

### 1.1 First IR problem, term-document-matrix, inverted index structure

Problem: You have a text/book/document and want to determine which document contain a specific word.
- You can read every document and mark the word, or use regular expression
But the amount of documents ob the web are extermly rising!

You could index the documents in advance.

A matrix is beeing build with every word out of the documents on the rows and the documets as the columns.
A field is 1, if the document contains a word, otherwise its 0 (Boolean)
Example: 110100 AND 110111 AND 101111 = 1001100
Why: When a bit in all vectors are 1, e.g. V1 [0], V2 [0] and V3 [0] == 1, then the 1 will stay
     If the incies are different, then where will be a 0.

Throught this we get vectors for our searches.
The boolean retrieval works with the opearators and, or and not.

Ad Hoc Retrieval: most standard IR task: Provide documents  in relevance to the usersinformation need.

effectiveness of results staticsits:
- Precision: What fraction of thr returned results are relevant to the information need?
- recall: what fraction of the relevant documents in the collection were returned by the system?

If we would use the matrix way for large documents, we would break the memory of an pc.
But the most cells in the matric would be zero, we can only save the occuring words, the 1.

The inverted index (inverted file)
We have a dictionary, wich the terms as the keys and a list of documents, in which the term appears as the value. (The position of the document)
- The lists are called posting lists

### 1.2. building an inverted index

The index have to build in advance to gain speed.
1. Collect documents to be indexed
2. Tokenize the text, turning each document in to a list of tokens
3. linguistic preprocessing (normalization)
4. Creat the inverted index, by indexing each document to the term is appears in

Tokens or normilized tokens == words (For the first understanding)

From the inverted index, we tag the terms with the doicument id.
It is sorted alphabetically.
Then instances of the same word are grouped by word, and then by document id.
We save the frequency of the term in doicument, e.g. a word is in 2 documents, or 1 document, etc.
The terms have a pointer to the docposztings lists, they apear in.

Simple excersises: 
1.1
1.2
1.3