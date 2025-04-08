# CSC 448 - Spring 2025



# Project 1. Sequences and Evolutionary Trees

In this first project you will combine what you have learned about aligning sequences, working with substitution matrices, using similarity scores and clustering algorithms to ultimately build an evolutionary tree given orthologous proteins sampled from several strains of bacteria.

0. The protein sequences are in the data/ folder of the github. Each sequences begins on a new line with the masked bacteria ID followed by a white tab and then the actual protein sequence.

1. Align two sequences using the Smith–Waterman algorithm:
- you can borrow an implementation from online, however,
- recall that you need to penalize each substitution and you need to use the BLOSUM62 matrix rather than the simple -1 since you are working with protein sequences and not DNA
- BLOSUM62 substitution matrix is available here: https://anaconda.org/bioconda/blosum
- for gap penalty use -12
- note that the Smith–Waterman algorithm score includes all the penalties for mismatches and gaps as well as positive values for correctly matched amino acids, hence, it reflects how well the two sequences align, or in other words, how similar to each other they are

2. Use your implementation of 1 to align every pair of sequences in the file and:
- convert the alignment scores from (1) into a **uniform** similarity measure that can be used to compare all sequences to one another. That is, given the scores you should be able to say, sequence\_i is more similar to sequence\_j than it is to sequence\_k. This may involve some form of normalization of the raw Smith–Waterman scores. Think carefully and explain how you did this in your report
- given your normalized similarity scores for any pair of sequences, construct the similarity matrix (this is the sequence by sequence matrix that is the input to the clustering in step 3)

3. Use a clustering algorithm of your choice to reconstruct the phylogenic tree:
- plot the tree (the *dendrogram* function of matplotlib may come in handy)
- what do you notice about the tree, how would you interpret it
- compare your tree to that of a classmate (discuss your observations in the report)

4. Think about and suggest a way (a metric) to systematically compare the trees reconstructed by the entire class


5. Write a brief pdf project report including:
- plot of the phylogenic tree with your interpretation and discussion
- concise description of your proposed metric to assess similarity between reconstructed trees
- report of the two closets and farthest away proteins (use bacteria id)

6. Turn in the following two files: 
- FirstName_LastName.pdf containing your report
- FirstName_LastName.gz which is a gzipped of all your code

via canvas by the *deadline: Friday 18th, 11:59pm*





# Project 0. Set Up

During the first lab, let's make sure your environment is set up so that you can work without problems on the projects. 


## 1. Anaconda

Anaconda is extremely popular open-source distribution designed for data science, machine learning, bioinformatics and scientific computing, that simplifies package management, environment creation, and deployment, making it easier to install and manage libraries and dependencies for various projects. I strongly recommend installing the full version of Anaconda and using it to encapsulate and manage all of your project dependencies, not just for this class but in general. There is no need to install software or libraries directly on you machine potentially causing conflicts and littering your system. Anaconda takes care of it, creating virtual environments which isolate software and their dependencies from the rest of the software installed on your machine. This means you can have both Python 2.9 and Python 3.7 installed within Anaconda and use both versions without encountering issues while your laptop carries its vanilla factory distribution of Python 3.X. You are not required to install Anaconda, but having it will probably make your life easier.

Visit the official [Anaconda website](https://anaconda.org/).

Explore their [starting tips](https://www.anaconda.com/docs/getting-started/getting-started). I recommend the full version (not the mini conda) and using the terminal/shell (CLI) rather than the GUI.

Here is a useful [cheat_sheet](https://docs.conda.io/projects/conda/en/4.6.0/_downloads/52a95608c49671267e40c689e0bc00ca/conda-cheatsheet.pdf).


### 1.1 Create an environment
Create a *csc448* environment. In general, do not use the *base* environment and don't install packages there. Create a new one.  

### 1.2 Install packages
Within your *csc448* environment, install the *SciPy*, *NumPy*, and *sklearn* libraries. They contain tons of useful functions for scientific computing, data preprocessing and many other utilities.  

### 1.3 Explore
Play on your own to familiarize how Anaconda works.


## 2. Coding

The focus of this class is on the application of computer science algorithms in the domain of molecular biology, understanding their behavior, pitfalls, analyzing their results, designing modifications, etc and not on coding/debugging. Therefore:

- You are encouraged to use all built in scientific computing libraries available through *SciPy* and *NumPy*. In general, you should never (re-)implement classical computer science algorithms (i.e K-means) but rather simply call the appropriate library.

- You are also allowed to use scripts and code from GitHub repositories of other scientists of their published research. You should properly cite the corresponding paper, see Project report for more details.

- You are **not** allowed to use any code from the internet which is not part of a published (in peer reviewed journal) scientific research.

Your code still needs to adhere to the best python coding practices, be extensively commented and properly organized. Points will be deducted if it is not.

## 3. Writing the report

The project report is very important. It should be neatly organized and clearly:

- detail the computational experiments carried with relevant figures
- justify the specific parametric and algorithmic choices made
- describe the biological interpretation of your results

Don't stress out! I realize you may not be very experienced writing one, I will be fairly lenient in the first half as you learn. Here are some tips:

- every figure should have labels on both axis and a color legend
- if you have a parameter (i.e number of clusters), you have to justify how you selected its value. This typically includes testing several different values and selecting the optimal one according to an evaluation metric
- you should always describe what your metric captures and how it behaves
- don't post code or large data within the text. Add a supplementary table file instead

If you use a code from a GitHub of published research, you should include a full reference to the corresponding paper. The GitHub readme page typically contains a citation section that states exactly the name of the paper, the journal, and the year it was published. If you cannot find one then you cannot use it. If in doubt ask me.

## 4. Submission

For each project, you will upload on canvas two files with the following names: 

- FirstName_LastName.pdf containing your report
- FirstName_LastName.gz which is a gzipped of all your code


## 5. Remember to have fun

![alt text](fun.png)