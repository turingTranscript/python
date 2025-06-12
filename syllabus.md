---
layout: page
title: Syllabus
nav_order: 2
description: >-
    Principles and Techniques of Data Science
---

# Syllabus

<!-- ## Note: This page is under construction. Everything on this website is subject to change. -->

# Python & Biopython Course Syllabus

## Course Information
**Course Code:** BT 2113  
**Course Name:** Python & Biopython  
**Credits:** 2 (1-0-2)  
**Course Position:** Semester III  
**Department offering the course:** Centre for Life Sciences  
**Level:** Pre-Ph.D./Core for UG 2nd year  
**Any pre-requisite course:** None  
**Overlap with any existing course:** None  
**Frequency of offering:** Every Fall  
**Faculty who will teach the course:** Dr. Balan Ramesh  

## Course Culture

Our classroom is a collaborative and inclusive learning environment. We encourage active participation, respectful dialogue, and a supportive atmosphere where everyone feels comfortable asking questions and sharing ideas. Given the hands-on nature of programming, learning from mistakes and helping peers is highly valued. We believe that diverse perspectives enrich the learning experience, and we are committed to fostering an environment free from harassment and discrimination. Your active engagement, curiosity, and willingness to help others will contribute significantly to the success of this course.

## Academic Dishonesty

Academic integrity is paramount in this course. All work submitted must be your own original effort. While collaboration on concepts and debugging is encouraged in the lab sessions, particularly in a Software Carpentry-style environment, direct copying of code or solutions is strictly prohibited. This includes, but is not limited to:

- Submitting work that is not your own.
- Copying code from another student or any unauthorized online source without proper citation.
- Allowing another student to copy your work.
- Plagiarizing text or code from any source.
- Misrepresenting data or results.
- Using unauthorized materials during quizzes or exams.

Any instance of academic dishonesty will result in serious consequences, as per the university's academic integrity policies, which may include a failing grade for the assignment or the course, and referral to the disciplinary committee. When in doubt about what constitutes acceptable collaboration, please ask the instructors or TAs.

## Course Overview

### Core Modules
The course is structured around four core modules:
**CORE PYTHON FOR BIOLOGISTS: THE BASICS**  
    * Basic syntax, data types, data structures, conditional statements, loops and functions.  
**ORGANIZING DATA AND INTERACTING WITH FILES**  
    * Dictionaries and File I/O operations.  
**BIOPYTHON: THE BIOLOGIST'S TOOLKIT**  
    * Biopython Library, Seq and SeqRecord Object. SeqIO module for sequence files.  
**APPLYING PYTHON & BIOPYTHON TO BIOLOGICAL PROBLEM**  
    * Biopython's pairwise2, accessing online databases like NCBI via Bio.Entrez.  

### Course Objective and Outcome  

**Objective:** 
    - To introduce fundamental programming concepts and their application using Python.  
    - To familiarize students with the principles of computational handling of biological data.  
    - To teach the use of the Biopython library for standard bioinformatics tasks.  
    - To introduce key Python libraries for numerical and tabular data analysis in biology (e.g., NumPy, Pandas).  
**Outcome:** 
    - Write and execute basic Python programs to manipulate biological data.  
    - Read, parse, and write various biological file formats programmatically.  
    - Utilize Biopython for tasks such as sequence analysis, database querying, and simple alignment.  
    - Perform basic data analysis on biological datasets using relevant Python libraries.  
    - Apply learned programming and computational skills to address introductory problems in computational biology.  

### Course Contents (Maximum 100 words)
This course provides a foundation in Python programming for biology (BT/CB) students. It covers fundamental concepts like syntax, data types, control flow, and functions, tailored with biological examples. Key skills include handling biological data using lists and dictionaries, and reading/writing various file formats. The course also focusses on the Biopython library for sequence manipulation, file parsing (FASTA, GenBank), sequence alignment, and database access. Finally, it introduces using libraries like NumPy and Pandas for biological data analysis, enabling students to solve practical computational problems in biology. 

## Lecture Outline

| Module No. | Topic | Number of hours |
| :--------- | :---- | :-------------- |
| 1       | Core Python for Biologists: The Basics | 11  |
| 2       | Organizing Data and Interacting with Files | 11  |
| 3       | Biopython: The Biologist's Toolkit | 10  |
| 4       | Applying Python & Biopython to Biological Problem | 10  |

**Detailed Module Descriptions:**  

**Module 1 (Core Python for Biologists: The Basics):** This module introduces the fundamentals in python programming concepts tailored for students with a biology background. This covers the rationale for programming in biological research, setting up python environment, understanding the basic syntax, variables, data types (integers, floats, strings and booleans) and performing string manipulations (indexing and slicing) of biological sequences. The module also introduces data structures (lists and tuples) and teaches control flow using conditional statements (if/elif/else) and loops (for/while) to manage program logic. Finally, it covers the creation and use of functions to write reusable code blocks for simple biological tasks and basic debugging techniques.  
**Module 2 (Organizing Data and Interacting with Files):** Building upon Python fundamentals, this module focuses on effectively structuring data and handling file input/output, which is critical for biological data analysis. Students will learn to use dictionaries for storing and accessing data in key-value pairs, (as in gff/gtf files). The module covers working with file paths and reading from/writing to various file types, including plain text and delimited formats like TSV and CSV. It introduces methods for parsing simple biological file formats using core Python, enabling students to extract and process data from files by combining loops, conditionals, functions, lists, and dictionaries.  
**Module 3 (Biopython: The Biologist's Toolkit):** This module introduces the Biopython library. It covers installing Biopython and utilizing its core objects: the Seq object for representing and manipulating biological sequences (DNA, RNA, and Protein) and the SeqRecord object for bundling sequences with descriptive metadata. A key focus is the SeqIO module for efficient reading and writing of common biological file formats like FASTA, GenBank, and basic FASTQ, enabling students to easily handle and parse biological data.  
**Module 4 (Applying Python & Biopython to Biological Problem):** Building on the previous modules, this module applies integrated Python and Biopython skills to solve practical computational biology problems.  It includes performing sequence alignments using Biopython's `pairwise2`, accessing online databases like NCBI via `Bio.Entrez` to retrieve biological data, and parsing BLAST results. The module introduces essential libraries for handling numerical and tabular biological data: NumPy for array manipulation and Pandas for working with DataFrames, commonly used for data like expression values. It also introduces Regular Expressions (`re` module) for powerful pattern matching in biological text. It introduces the foundational concepts of DNA language models and their role in sequence analysis, exploring their potential applications and limitations. 

**Course Total Lectures:** 42 

**Brief description of tutorials:** NIL 

## Laboratory Component

**Brief description of Laboratory:**
The lab component of this course is designed to provide hands-on practice with the Python programming language and the Biopython library, directly complementing the course lectures.  Students will work through practical exercises and problems using biological datasets, reinforcing fundamental concepts in Python programming, data handling, and file manipulation.  The lab sessions will focus on building essential skills in writing, debugging, and executing code, and applying learned concepts from Biopython for tasks like sequence analysis, file parsing, and database interaction in a guided environment (software carpentry style), ensuring students gain practical experience in computational biology techniques. 

## Week-wise Teaching Plan

| Week | Topic |
| :--- | :---- |
| 1    | Introduction to Programming & Python Fundamentals: Why program in biology, setup, basic syntax, variables, data types (numbers, strings), simple string manipulation, errors.  |
| 2    | More String Manipulation & Collections: String indexing, slicing, methods; Introduction to lists and tuples; Simple for loops.  |
| 3    | Control Flow & Functions: Conditional statements (if/elif/else), comparison/logical operators; while loops; Defining and calling functions.  |
| 4    | Functions Revisited & Dictionaries: Function arguments, return values, scope, writing reusable functions; Introduction to dictionaries (creation, access, iteration).  |
| 5    | File Input/Output (I/O): Opening, reading (read, readline, readlines), and writing text files; File paths and basic OS interaction.  |
| 6    | Parsing Files with Basic Python: Combining file I/O with loops, conditionals, and data structures; Parsing simple delimited files (CSV); Basic FASTA parsing using core Python.  |
| 7    | Introduction to Biopython & Seq Objects: Biopython overview, installation; Seq object (creation, alphabets, basic methods like transcription, translation, reverse complement).  |
| 8    | SeqRecord and Basic Annotation: The SeqRecord object (sequence + metadata); Creating and accessing SeqRecord components; Introduction to basic annotations.  |
| 9    | Biopython File I/O (SeqIO): SeqIO module (parsing and writing standard formats - FASTA, GenBank, basic FASTQ); Iterating over multiple records.  |
| 10   | Database Access & Advanced Parsing: SeqIO continued (extracting detailed info); Bio.Entrez (accessing NCBI databases - searching and fetching records).  |
| 11   | Sequence Comparison & Pattern Matching: Pairwise sequence alignment (Bio.pairwise2); Introduction to Regular Expressions (re module) for biological patterns.  |
| 12   | Data Analysis Libraries & Integration: Introduction to NumPy (arrays for numerical data); Introduction to Pandas (DataFrames for tabular data); Case study or mini-project integrating skills from all modules.  |

## Lab Sessions

| Week | Topic | Lab Activity |
| :--- | :---- | :----------- |
| 1    | Introduction & Python Fundamentals | Getting Started: Install Python (miniconda3) and IDE (jupyter-lab). Write and run simple scripts (print(), variables, basic arithmetic). Practice identifying and fixing syntax errors.  |
| 2    | String Manipulation & Collections | Sequence Basics: Practice string indexing and slicing on DNA/protein sequences. Use string methods (.upper(), .lower(), .count(), .find()) to analyze simple sequences. Create and manipulate lists of sequences or biological items.  |
| 3    | Control Flow & Functions | Decision Making & Reusability: Implement conditional logic (if/elif/else) to filter sequences based on criteria (e.g., seq length, GC content). Use for and while loops to iterate through sequences or lists. Write and test simple functions for biological calculations (e.g., GC content function).  |
| 4    | Functions Revisited & Dictionaries | Organizing Data: Practice writing functions with different types of arguments and return values. Implement biological lookups using dictionaries (e.g., DNA to RNA table, amino acid codon table).  |
| 5    | File Input/Output (I/O) | Working with Files: Write scripts to read data from simple text files (e.g., a list of genes). Practice writing processed data or results to a new output file.  |
| 6    | Parsing Files with Basic Python | Processing File Data: Write scripts to parse simple delimited files (CSV, TSV) and extract relevant data. Develop and use a basic Python function to parse a simplified FASTA file format line by line.  |
| 7    | Introduction to Biopython & Seq Objects | Introducing Biopython: Install Biopython. Create and manipulate Seq objects. Practice using Seq object methods for transcription, translation, and reverse complement on sample sequences.  |
| 8    | SeqRecord and Basic Annotation | Sequence Records: Create SeqRecord objects for sequences, adding ID, description, and basic annotations. Practice accessing and modifying information within SeqRecord objects.  |
| 9    | Biopython File I/O (SeqIO) | Biopython File Handling: Use the SeqIO module to read multiple sequences from a multi-FASTA file. Parse a sample GenBank file and extract sequence and basic annotation information using SeqIO. Practice writing SeqRecord objects to different file formats.  |
| 10   | Database Access & Advanced Parsing | Online Data Retrieval: Use Bio.Entrez to search for sequence records on NCBI (e.g., Nucleotide or Protein database) and fetch sequences. Practice parsing more detailed features from SeqIO objects (e.g., CDS, gene features).  |
| 11   | Sequence Comparison & Pattern Matching | Alignment & Regex: Perform pairwise sequence alignments using Bio.pairwise2. Practice using the re module to find more complex patterns (e.g., restriction sites with ambiguity codes, protein motifs) in sequences using regular expressions.  |
| 12   | Data Analysis Libraries & Integration | Basic Data Analysis & Project Prep: Introduce NumPy arrays and perform basic operations (e.g., simple statistical calculations on a list of measurements). Introduce Pandas DataFrames by loading a small CSV file into a DataFrame and accessing columns/rows. Work on exercises that combine Python, Biopython, and potentially NumPy/Pandas to solve a small integrated problem (e.g., process a small dataset derived from a file or online query).  |

## Suggested Texts and Reference Books

1.  Antao, T. (2022). *Bioinformatics with Python Cookbook: Use modern Python libraries and applications to solve real-world computational biology problems* (3rd ed.). Packt Publishing. 
2.  Biopython Project. *Biopython Tutorial and Cookbook*. (This is the primary documentation for the Biopython library). 
3.  Jones, M. (2013). *Python for Biologists: A complete programming course for beginners*. 
4.  Jones, M. (2014). *Advanced Python for Biologists*. 
5.  Model, M. L. (2009). *Bioinformatics Programming Using Python: Practical Programming for Biological Data*. O'Reilly Media. 
6.  Stevens, T. J., & Boucher, W. (2015). *Python Programming for Biology: Bioinformatics and Beyond*. Cambridge University Press. 

## Suggested Assessment

* (Lab) Minor 1: 25% 
* (Lab) Minor 2: 25% 
* Internal quizzes (Weekly Quiz - 12 Total): 20% 
* End term exam: 30%