---
layout: post
title:  "Download data from SRA parallelly"
date:   2019-06-06 11:21:23
categories: [skill]
tags: [Command line]
---

It is very painful to download bulk SRA data. Generally, there are two way to download data from SRA, FTP or SRA toolkit. However, the most recent submissions may not able in FTP sites. Thus, I have to use `fastq-dump` sometimes. 

To make the download more efficient. I execute it parallelly. To start the downloading, all SRR numbers should be gathered into the same file one per line.

```
parallel --verbose fastq-dump --gzip --split-files {} --outdir "~/Download/data" < download_list.txt
```