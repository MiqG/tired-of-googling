# Tired Of Googling

## Bioinformatics

### Utils
#### Paired end reads are found in the same fastq file
##### interleaved
One read after the other
```
bbmap/reformat.sh \
      verifyinterleaved=f \
      t={threads} \
      in={params.fastqs_dir}/{params.sample}.fastq.gz \
      out1={params.fastqs_dir}/{params.sample}_1.fastq.gz \
      out2={params.fastqs_dir}/{params.sample}_2.fastq.gz
```
###### not interleaved
forward and reverse reads are concatenated. Usually, the identifiers of each pair are the same except for a "/1" or "/2".
```
# forward
zcat {params.fastqs_dir}/{params.sample}.fastq.gz | \
grep '^@{params.sample}.*/1$' -A 3 --no-group-separator | \
pigz -p {threads} > {params.fastqs_dir}/{params.sample}_1.fastq.gz

# reverse
zcat {params.fastqs_dir}/{params.sample}.fastq.gz | \
grep '^@{params.sample}.*/2$' -A 3 --no-group-separator | \
pigz -p {threads} > {params.fastqs_dir}/{params.sample}_2.fastq.gz
```

### Pipelines

#### RNA-Seq
##### Bulk
###### Gene Expression
###### Splicing

##### Single cell
###### 10X
####### Gene Expression
####### Splicing

###### smartseq2
####### Gene Expression
####### Splicing


### Aligners
#### STAR
##### Installation
##### Build Index
##### Basic Alignment
###### Bulk
###### Single Cell

#### RSEM
##### Installation
##### Build Index
##### Basic Alignment
###### Bulk
###### Single Cell

## Databases

## HPC
#### Sun Grid Engine


## Programming
### Python
### R

## Statistics


