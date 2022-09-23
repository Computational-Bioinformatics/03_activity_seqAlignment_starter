# Bioinformatics (CMPSC 300) Activity 3

This repository contains information about the Bioinformatics activity deliverable(s).
This assignment invites students to complete an experiment in sequence alignment by 
following steps and then writing responses to questions.

## Dates

Handed out: 23 Sept 2022

Due: 26 Sept 2022

## Objectives

* To gain experience in using free online tools
* To gain experience in gathering sequence data from public databases
* To gain experience working with sequence alignment and multiple sequence alignments.
* To gain experience in reading and understanding the results of sequence alignment experiments.

### Introduction
In class, we spent a moment to discuss ClustalW which is computer software for the
comparison of genetic sequences, known as __Sequence Alignment__. The
underlining algorithm of the software tool uses dynamic programming
which studies one sequence in light of the other. Any differences between
both sequences are determined logically and a score if given to allow
the researcher to determine the similarity between sequences. In this
activity, we are going to study several alpha-globin gene sequences from
several different organisms, determine similarity between sequences, and
complete critical thinking about the results we find.

This activity will have three parts.

* Part 1. To begin our work, we will be creating a data set of DNA sequences to study. To assemble this genetic material, we will be using National Library of Medicine's online GeneBank available from [https://www.ncbi.nlm.nih.gov/nucleotide](https://www.ncbi.nlm.nih.gov/nucleotide/) to locate the sequences.

* Part 2. We will analyze our data to determine their differences and common regions. For this, we will using the online Multiple Sequence Alignment tool available from [https://www.ebi.ac.uk/Tools/msa/](https://www.ebi.ac.uk/Tools/msa/) for the task of sequence alignment.

* Part 3. We will translate our DNA sequences to protein sequences to construct a new alignment study. For this, we will be using the EMBOSS Transeq tool available from [https://www.ebi.ac.uk/Tools/st/emboss_transeq/](https://www.ebi.ac.uk/Tools/st/emboss_transeq/) to translate our DNA into protein sequences. Next, we will reverse translate the protein sequences using the tool available at URL [https://www.bioinformatics.org/sms2/rev_trans.html](https://www.bioinformatics.org/sms2/rev_trans.html) for this task. This tool will translate the protein sequences back into to DNA sequences according to CODON usage observed by a selected organism. We note here that this tool is forced to make educated guesses about the exact sequence of the DNA as it moves to DNA from the protein sequence. This new DNA sequence will then be aligned against the other previous DNA sequences to see how close they align, and thus we determine the simplicity of moving from protein sequence to a DNA sequence.

---

### Part 1

The **Data** is the DNA sequences which can be obtained from the following listing of GeneBank IDs. Please note, some of the below GeneBank IDs may have multiple entries and so if this is the case for you, then you can pick the entry from the top of the list of results.

#### GenBank IDs

    + AB001981
    + X01831
    + AH002483
    + J00043
    + J00044
    + X01086
    + X07053
    + AF098919

#### Downloading and formatting sequence data

* Copy and paste all GenBank IDs into the search field (separated by spaces) at [NCBI](https://www.ncbi.nlm.nih.gov/). Be sure to select the *Nucleotide* database.

* After running your search, you should now see eight results. Select each check box of each result. Locate the _Send to_ drop down menu from the upper right of the results page. In the menu, select *Coding Sequences* and FASTA formatting. Then, click on *Create File* to download your sequence data.

* Note: all sequences of each GeneBank ID have been placed into a file using *FASTA* formatting. By this formatting, each gene take-up two lines in the file where the first line, beginning with a `>` character, concerns the title and reference information. The second line concerns only the DNA sequence. An example of FASTA formatting is shown below for the first GeneBank ID `AB001981`.

``` bash
>lcl|AB001981.1_cds_BAA19668.1_1 [gene=alpha-D] [protein=alpha-D globin] [protein_id=BAA19668.1] [location=join(1104..1192,1306..1510,1614..1742)] [gbkey=CDS]
ATGCTGACCGACTCTGACAAGAAGCTGGTCCTGCAGGTGTGGGAGAAGGTGATCCGCCACCCAGACTGTG
GAGCCGAGGCCCTGGAGAGGCTGTTCACCACCTACCCCCAGACCAAGACCTACTTCCCCCACTTCGACTT
GCACCATGGCTCCGACCAGGTCCGCAACCACGGCAAGAAGGTGTTGGCCGCCTTGGGCAACGCTGTCAAG
AGCCTGGGCAACCTCAGCCAAGCCCTGTCTGACCTCAGCGACCTGCATGCCTACAACCTGCGTGTCGACC
CTGTCAACTTCAAGCTGCTGGCGCAGTGCTTCCACGTGGTGCTGGCCACACACCTGGGCAACGACTACAC
CCCGGAGGCACATGCTGCCTTCGACAAGTTCCTGTCGGCTGTGTGCACCGTGCTGGCCGAGAAGTACAGA
TAA
```

Complete your reflections questions at the end of this part.

---

### Part 2

We will now complete a sequence **alignment** experiment.

* Go to EBI's [multiple alignment page](http://www.ebi.ac.uk/Tools/msa/) and choose the program MAFFT. Note, we are using a _Multiple Sequence Alignment_ that has been improved for speed using the Fast Fourier Transform algorithm. Copy the sequence data from the FASTA file that you downloaded into the larger field under the words _ Enter your input sequences_. Leave the setting `AUTOMATIC` as it is by default. Note, you could also upload the `sequence.fasta` that was downloaded earlier to complete this task.
* Submit your job. Note, the completion of this task may take time and so there is an option for you to add your email to be told when your results are ready to view. Otherwise, if you submit your work without giving an email address, you can still check your work thanks to a URL link that you are given by the site.
* Be sure to note your job ID as you might need it in the future. For example, at the top of my results page, I see the line below.

```
Results for job mafft-I20220922-215435-0219-95152536-p2m
```

* Go to the "Results Viewers" tab and find the *MView* link. After clicking on the *View in MView* link, you will find yourself at another page where you can enter sequences. However, you will notice that in the sequence field, your Job ID has been automatically entered. Find the *Submit* button and click on it to process your previously aligned sequences. If all has gone according to plan, you should see a graphical display of your aligned sequences.

Complete your reflections questions at the end of this part.

---

### Part 3

We will now translate the DNA sequence data to proteins and then perform another alignment.

* Go to the EMBOSS [Transeq](https://www.ebi.ac.uk/Tools/st/emboss_transeq/) tool to translate the DNA sequence of the first GeneBank ID `AB001981` sequence. Use the default options in the tool. Note see above; `>lcl|AB001981.1_cds_BAA19668.1_1 [gene=alpha-D] [protein=alpha-D globin] [protein_id=BAA19668.1] [location=join(1104..1192,1306..1510,1614..1742)] [gbkey=CDS]`. Note the protein sequence as you will be using it later.

* Go to the [Reverse Translate](https://www.bioinformatics.org/sms2/rev_trans.html) tool and copy in your protein sequence from the step above. You will be reverse translating the protein back into DNA following the _E. Coli_ DNA codon usage model. Keep the resulting protein for use later. The tools works by translating codons according usage frequency tables (usage signatures) which are observed in different organisms. Select the top _DNA_ sequence in the output.

* Return to the [Multiple Sequence Alignment with FFT](https://www.ebi.ac.uk/Tools/msa/mafft/) that we were using earlier. Paste all DNA sequences from Part 1 along with the new DNA _reverse_ sequence from the previous step. Run a multi-sequence alignment.

Complete your reflections questions at the end of this part.

---

## Reflection

Once you have finished a Part of your work, you are invited to respond to the questions in the File `writing/reflections.md`. Please be sure that you use Markdown where necessary for formatting.

## Assessment
This is a checkmark grade.

## GatorGrade

You can check the baseline writing and commit requirements for this lab assignment by running department's assignment checking `gatorgrade` tool. To use `gatorgrade`, you first need to make sure you have Python3 installed (type `python --version` to check). If you do not have Python installed, please see:

* [Setting Up Python on Windows](https://realpython.com/lessons/python-windows-setup/)

* [Python 3 Installation and Setup Guide](https://realpython.com/installing-python/)

* [How to Install Python 3 and Set Up a Local Programming Environment on Windows 10](https://www.digitalocean.com/community/tutorials/how-to-install-python-3-and-set-up-a-local-programming-environment-on-windows-10)

Then, if you have not done so already, you need to install `gatorgrade`:

* First, [install `pipx`](https://pypa.github.io/pipx/installation/)

* Then, install `gatorgrade` with `pipx install gatorgrade`

Finally, you can run `gatorgrade`:

`gatorgrade --config config/gatorgrade.yml`
