# BASH_snippets
For useful snippets of bash code that I have found useful for various , will add as I find more. 

# number of files in directory
```bash
ls -1 | wc -l
```
# subset lines
```bash
### useful for getting a random(ish) subset of your files (basically take every second file and output to a new file)
####### DO NOT USE TO SUBSET FASTA OR FASTQ FILES!!!! ONLY FILES WHERE EACH LINE IS A NEW ENTRY #########
awk 'NR % 2 == 0' <file> > subset2.txt
```
# file path and file into .tsv
```bash
### to get files paths from a directory into the text file format required for AGENT ANNOTATIONS
### go through all files in directory (could also use * wildcard) 
for file in */*.accessory_loci.txt; do
### set directory variable to output of pwd
directory=$(pwd)
filename=${file%.gbk/*RR*}
###if the file has the correct extension then print the results to file in tab separated format.
echo -e ${directory}/${file}'\t'${filename} >> emm4-agent-annot-list.txt 
done
```
