---
title: "Getting Data into Galaxy and Performing Quality Control"
teaching: 0
exercises: 0
questions:
- How do I get data from the NCBI SRA into Galaxy?
- How can I describe the quality of my data?
- How can I get rid of data that doesn't meet my quality standards? 
objectives:
- Interpret a FastQC plot summarizing per-base quality across all reads.
- Select and set multiple options for command-line bioinformatic tools.
- Clean sequencing reads using a industry-standard bioinformatics workflow. 
keypoints:
- KEY POINT! 
---

> ## Prerequisites
> **This tutorial assumes the following:**
> + You have created a Galaxy account and can log in to it.
> + You have created a fresh, empty Galaxy history for this tutorial
> + You are familiar with the general format of a FASTQ file and Phread quality scores (watch the lecture if you haven't already!)
> + You have completed the previous tutorial on "Metadata and the NCBI SRA"
{: .prereq}

# Bioinformatic workflows

When working with high-throughput sequencing data, the raw reads you get off of the sequencer will need to pass
through a number of  different tools in order to generate your final desired output. The execution of this set of
tools in a specified order is commonly referred to as a *workflow* or a *pipeline*. 

This week, we are going to be learning about a two-step workflow that is common to almost all sequencing projects: 

1. Quality control - Assessing quality using FastQC
2. Quality control - Trimming and/or filtering reads (if necessary)

![workflow_qc](../img/var_calling_workflow_qc.png)

**We will be building onto this workflow in subsequent weeks!** 

# Getting the data into Galaxy

Often times, the first step in a bioinformatic workflow is getting the data you want to work with onto a computer (or server, in our case) where you can work with it. If you have outsourced sequencing of your data, the sequencing center will usually provide you with a link that you can use to download your data. Today we will be working with publicly available sequencing data. Luckily, as you saw in the **Galaxy 101** Tutorial, it is quite easy to get data onto the Galaxy server. 

> ## Hands-On: Importing using an SRA accession
> 1. In the **Get Data** section of the Tools panel, locate the <button type="button" class="btn btn-outline-tool" style="pointer-events: none"> Faster Download and Extract Reads in FASTQ </button> tool. 
> 2. 
> 
{: .challenge}

{% include links.md %}