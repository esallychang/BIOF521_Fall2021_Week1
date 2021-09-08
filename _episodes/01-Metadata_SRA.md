---
title: "Examining Metadata and Obtaining Data from the SRA"
teaching: 0
exercises: 0
questions:
- "How do I plan and organize a genome sequencing project?"
- "What information should I collect about my samples?"
- How do I access public sequencing data? 
- What metadata accompanies public sequencing data? 
objectives:
- Understand the data we send to and get back from a sequencing center.
- Make decisions about how (if) data will be stored, archived, shared, etc.
- Understand how to access and download public data.
keypoints:
- KEY POINT! 
---

## Planning an analysis of sequencing data 

There are a variety of ways to work with a large sequencing dataset. In the most important ways, the methods and approaches we need in bioinformatics are the same ones we need at the bench or in the field - *planning, documenting, and organizing* are the key to good reproducible science.  

> ## Brainstorm: What questions you need to consider before you begin analysis of sequencing data? 
>
>  Let's say that you and your collaborator have planned a sequencing project, and have a proposed experimental design and set of samples ready to go. Before we go any further, take a moment to consider: What challenges do you think you'll face (or have already faced) in working with large sequencing data sets?  
>
> > ## Solution
> > Here are just a few possibilities: 
> > 
> > + What is your strategy for saving and sharing your sequence files?  
> > + How can you be sure that your raw data have not been unintentionally corrupted?  
> > + Where will my data be stored? How big do I anticipate the files to be? 
> > + Where/how will you (did you) analyze your data - what software, on what computer(s)?  
> {: .solution}
{: .challenge}

The exact questions you will need to ask yourself and your collaborators is dependent on exactly what kind of sequencing project you are doing, and what resources you might have available at your institution or workplace. The raw data you get back from the sequencing center is the foundation of your sequencing analysis. You need to keep this data, so that you can always come back to it if there are any questions or you need to re-run an analysis, or try a new analysis approach.

> ## Brainstorm: What are some guidelines for storing data? 
>
>  Let's say that you are the principal investigator for a lab that works with sequencing data on a regular basis. You want to create policies to make sure that data you don't lose your valuable data. Take a moment to write down a few potential rules or guidelines. 
>
> > ## Solution
> > Here are just a few possibilities.
> > + Store the data in a place that is accessible by you and other members of your lab - maybe create a shared data storage solution that you (the PI) and your lab manager can also access. 
> > + Store the data in a place that is redundantly backed up. It should be backed up in two locations that are in different physical areas.
Leave the raw data raw. You will be working with this data, but you do not want to modify this stored copy of the original data. 
> > + Leave the raw data raw. You will be working with this data, but you do not want to modify this stored copy of the original data. This means making copies for subsequent analyses. 
> > + What other ideas did you come up with? 
> {: .solution}
{: .challenge}

## Sending samples to the sequencing facility 

When you send your precious samples of DNA or RNA to a sequencing facility, they will require you to submit some information, or **metadata** about each of the samples. This information not only helps you keep track of the samples but also provides the sequencing center staff crucial information they will use to best prepare your samples for sequencing. For example, different input DNA concentrations may require different amounts of reagent and may lead to differing amounts of output sequence data.


As an example, the [Genome Sequencing Core][ku-gsc] of the University of Kansas (where I got my PhD!) requires the following information to be sent with each sample: 

+ Sample Name
+ DNA or RNA? 
+ DNA/RNA concentration in ng/uL 
+ How did you quantify that concentration? 
+ Sample volume (uL)
+ Should they run further quality control? 
+ Submit any relevant gel images 

> ## What other information will you want to have collected about your samples? 
> This will probably depend on the goals of the study, but could include:
> + Sample Collection date
> + Sample location date (if location is important to your study)
> + Sample sex (if important or known)
> + Sample treatment (experimental condition)
> + Probably many other things relevant to your experimental design!
{: .solution}

## Receiving your data from the sequencing facility

When the data come back from the sequencing facility, you will receive some documentation (more metadata) as well as the sequence files themselves. Download and examine the following example file - here provided as a text file and Excel file:

- [Sequencing results - text](../files/sequencing_results_metadata.txt)
- [Sequencing results - Excel](../files/sequencing_results_metadata.xls)

> ## Exercise
> Open the data file in the analysis program of your choice and see if you can answer the following questions: 
> 1. How are these samples organized?
> 2. What type of sequencing projects did these samples come from? 
> 3. What do you think the \_R1/\_R2 extensions mean in the file names? 
> 4. What does the '.gz' extension on the filenames indicate?
> 5. What is the total file size?
>
> > ## Solution
> >
> > 1. Samples are organized by sample_id (the first column). 
> > 2. These samples are from an RNA-Seq project
> > 3. The \_R1/\_R2 extensions mean "Read 1" and "Read 2" of each sample. We will be learning more about what this means soon!
> > 4. The '.gz' extension means it is a compressed "gzip" type format to save disk space
> > 5. The size of all the files combined is 1113.60 Gb (over a terabyte!). To transfer files this large you should validate the file size following transfer. Absolute file integrity checks following transfers and methods for faster file transfers are possible but beyond the scope of this lesson. 
> >
> {: .solution}
{: .challenge}

## Examining Data on the NCBI SRA Database

In our experiments we usually think about generating our own sequencing data. However, almost all analyses use reference data, and you may want to use it to compare your results or annotate your data with publicly available data. You may also want to do a full project or set of analyses using publicly available data. This data is a great, and essential, resource for genomic data analysis.

When you come to publish a paper including your sequencing data, most journals and funders require that you place your data on a public repository. Sharing your data makes it more likely that your work will be re-used and cited. It helps to prepare for this early!

There are many repositories for public data. Some model organisms or fields have specific databases, and there are ones for particular types of data. Two of the most comprehensive public repositories are provided by the [National Center for Biotechnology Information  (NCBI)](https://www.ncbi.nlm.nih.gov) and the [European Nucleotide Archive (EMBL-EBI)](https://www.ebi.ac.uk/). The NCBI's [Sequence Read Archive (SRA)](https://trace.ncbi.nlm.nih.gov/Traces/sra/) is the database we will be using for this lesson, but the EMBL-EBI's Nucleic Acid Archive (ENA) is also useful. The general processes are similar for any database.

# Accessing the original archived data

The [sequencing dataset (from Tenaillon, *et al.* 2016) adapted for this lesson](http://www.datacarpentry.org/organization-genomics/data/) was obtained from the [NCBI Sequence Read Archive](http://www.ncbi.nlm.nih.gov/sra), which is a large (~27 petabasepairs/2.7 x 10^16 basepairs as of April 2019) repository for next-generation sequence data. Like many NCBI databases, it is complex and mastering its use is greater than the scope of this lesson. Very often there will be a direct link (perhaps in the supplemental information) to where the SRA dataset can be found. We are only using a small part of these data, so a direct link cannot be found. If you have time, go through the following detailed description of finding the data we are using today (otherwise skip to the next section). 

## Locate the Run Selector Table for the Lenski Dataset on the SRA

See the figures below for how information about data access is provided within the original paper. 

<img style='border:1px solid #000000' src="../fig/03_paper_header.png" alt="Screenshot of header from Tenaillon et al. paper (linked in References)" width="800"/>

The **above image** shows the title of the study, as well as the authors.

The excerpt from the paper below includes information on how to locate the sequence data. In this case, the text appears just before the reference section.

> **Author Information** All sequencing data sets are available in the NCBI
> BioProject database under accession number PRJNA294072. The *breseq*
> analysis pipeline is available at GitHub ([http://github.com/barricklab/breseq](https://github.com/barricklab/breseq/)).
> Other analysis scripts are available at the Dryad Digital Repository ([http://dx.doi.org/10.5061/dryad.6226d](https://doi.org/10.5061/dryad.6226d)). R.E.L. will make strains available to qualified
> recipients, subject to a material transfer agreement. Repreints and permissions
> information is available at www.nature.com/reprints. The authors declare no
> competing financial interests. Readers are welcome to comment on the online
> version of the paper. Correspondence and requests for materials should be
> addressed to R.E.L. (lenski *at* msu.edu)


{% include links.md %}
