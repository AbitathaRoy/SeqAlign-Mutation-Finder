# SeqAlign-Mutation-Finder

This tool helps you find out the mutations and indels in a target genome sequence with respect to a reference genome sequence and stores the results in a file for further analysis. It is useful for detecting genetic variations, particularly in cases like viral genome mutation tracking or drug resistance studies.

## Features

- **Pairwise sequence alignment** using Biopython’s alignment tools.  
- **Mutation detection** (substitutions) with positional tracking.  
- **Indel detection** (insertions/deletions) with separate categorization.  
- **Structured output storage** in a text file for further study.  
- ~~**Customizable analysis** to interpret mutations based on external datasets.~~

## Installation

Ensure you have Python installed. You can run it in either of the two ways.
1) Download this notebook on your local system and run it using your local software, such as Visual Studio Code or Anaconda.
2) Import this notebook in a cloud environment such as Google Colab and run it directly.

## Usage

### Installing BioPython and importing packages

Run the first two sections of the notebook to achieve this purpose.

### Load Sequences

The **Load Sequences** section handles the input through the following lines.

```python
reference_seq = read_fasta("reference.fna")  # replace with your reference file
target_seq = read_fasta("target.fna")  # Replace with your target file
```

Replace the filenames with the path of the files you want to use and run.

### Visualize the Output

By running the subsequent sections, you get two sets of outputs.
1) You can visualize the sequence alignment under the **Sequence Alignment** section.
2) You get a proper list of the mutations and indels upon running the **Mutations and Insertions/Deletions** section. This output is also stored in a file in your notebook directory.
(Note: You must run (1) to make (2) work!)

## Example Output

### Sequence Alignment

```
target            0 GGTCTCTCTGGTTAGACCAGATCTGAGCCTGGGAGCTCTCTGGCTAACTAGGGAACCCAC
                  0 -----------||-------------|--||.||---||||||-|||||||.||.|||.|
query             0 -----------TT-------------G--TGTGA---CTCTGG-TAACTAGAGATCCCTC

target           60 TGCTTAAGCCTCAATAAAGCTTGCCTTGAGTGCTTCAAGTAGTGTGTGCCCGTCTGTTGT
                 60 .|---|...|||.|.|.||--||--|..|...|-||.||.||||-|.|||||--------
query            30 AG---ACCACTCTAGATAG--TG--TAAAAATC-TCTAGCAGTG-GCGCCCG--------

target          120 GTGACTCTGGTAACTAGAGATCCCTCAGACCCTTTTAGTCAGTGTGGAAAATCTCTAGCA
                120 -----------|||-||-|--------|||----||----------||||---.|.|-.|
query            73 -----------AAC-AG-G--------GAC----TT----------GAAA---GCGA-AA

target          180 GTGGCGCCCGAACAGGGACCTGAAAGCGAAAGGGAAACCAGAGGAGCTCTCTCGACGCAG
                180 ||-------.|||||||||..|||||||||||---..||||||.||.|||||||||||||
query            94 GT-------TAACAGGGACTCGAAAGCGAAAG---TTCCAGAGAAGTTCTCTCGACGCAG
```

### Mutations

```
Position 5880 to 5880: G → A
Position 5882 to 5883: AA → TG
Position 5885 to 5885: A → C
Position 5888 to 5888: G → A
Position 5924 to 5924: G → A
Position 5945 to 5945: T → C
```

### Indels

```
Position 7033 to 7041: TGAAGGAAG → ---------
Position 7193 to 7195: --- → AAT
Position 7202 to 7207: ------ → ACTAAC
Position 7977 to 7978: -- → TT
Position 7987 to 7988: AC → --
Position 8184 to 8204: --------------------- → CAGTCTCAAGGGACTGAGACT
Position 8400 to 8400: - → A
```

## Applications

- Viral genome analysis (e.g., tracking mutations in HIV, SARS-CoV-2).
- Drug resistance studies by comparing known mutation databases.
- Evolutionary biology for detecting sequence variations over time.

## License

This project is licensed under GPL v3, meaning modifications must remain open-source and credit must be given to the original author.


#### For any contributions, bug reports, or feature requests, feel free to open an issue or fork the repository!
