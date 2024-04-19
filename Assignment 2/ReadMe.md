# Assignment 2: Clustering

Due 31 March, 2024

## The Task

- The "Bag of Words" data set from the UCI Machine Learning Repository contains five text collections in the form of bags-of-words. The URL for the UCI repository is <https://archive.ics.uci.edu/ml/datasets/Bag+of+Words.>
- Your task is to cluster the documents in these datasets via $K$-means clustering for different values of $K$ and determine an optimum value of $K$.
- As a similarity measure, use Jaccard index, that measures similarity between two documents based on the overlap of words present in both documents. Note that this changes the underlying model from "bag of words" to "set of words".
- The datasets are of different sizes. Report your results on the three smaller datasets (Enron emails, NIPS blog entries, KOS blog entries).

## The Data Set

- In each of the text collections, each document is summarized as a bag (multiset) of words. The individual documents are identified by document IDs and the words are identified by word IDs.
- After some cleaning up, in each collection the vocabulary of unique words has been truncated to only keep words that occurred more than ten times overall in that collection.

For each collection XYZ:

- `vocab.XYZ.txt` is the vocabulary file, listing all words that appear in the collection XYZ, one word per line. Each word has an implicit `wordID` that is its line number in this file, starting with $1$ (the word on line $1$ has `wordID` 1, the word on line $2$ has `wordID` 2, ...)
- `docword.XYZ.txt` lists out the number of times each word in `vocab.XYZ.txt` occurs in each document (only non-zero counts are recorded).
  The file docword.XYZ.txt begins with 3 header lines

  ```plaintext
  D
  W
  NNZ
  ```

  where `D` is the number of documents in the collection, `W` is the number of words whose frequency is counted (i.e., `W` is the number of words in `vocab.XYZ.txt`) and `NNZ` is the number of non-zero frequency entries for this collection (i.e., `NNZ` is 3 less than the number of lines in `docword.XYZ.txt`).

  This is followed by `NNZ` lines of the form
  
  ```plaintext
  docID wordID count
  ```

  where `count` is the number of time the word with id `wordID` appears in document with id `docID`. Remember that only non-zero counts are recorded.

Information about the datasets in the repository (that you need to analyze)

- Enron Emails:
  orig source: <www.cs.cmu.edu/~enron>

  ```plaintext
  D=39861
  W=28102
  N=6,400,000 (approx)
  ```
  
- NIPS full papers:
  orig source: books.nips.cc
  
  ```plaintext
  D=1500
  W=12419
  N=1,900,000 (approx)
  ```

- KOS blog entries:
  orig source: dailykos.com

  ```plaintext
  D=3430
  W=6906
  N=467714
  ```

## Solving the Task

- You can use any programming language, including Python and R. You can make use of standard packages for analytics and machine learning. Clearly document any external packages used by your code.
- Submit the following via Moodle, as a Jupyter notebook if you are using Python and as a single archive (zip, tar.gz, …) otherwise:
  - The code you used to solve the assignment.
  - If you have voluminous output to report, save it somewhere on the cloud and provide a link.
  A short write up describing how your code ran on the data sets: the parameters used, time taken, space required, and anything else of interest.
- You may work alone or in groups of two. Each group makes a single submission to Moodle. Use either person's Moodle account to submit. The submission should mention the names of the two partners.
- There will be a short oral presentation and question/answer session for each submission.
