---
layout: post
title:  "OCMSExplorer Tutorial"
date:   2020-05-07
categories: bioinformatics
permalink: /bioinformatics/OCMSExplorer
toclink: /OCMS-blog/bioinformatics/OCMSExplorer
excerpt_separator: <!--more-->
author: Sandi Yen
contributors: Nick Ilott, Jethro Johnson
updated: 11 May 2020
parent: Bioinformatics Resources
parent_url: /OCMS-blog/bioinformatics
postid: bioin_001
---

## About OCMSExplorer
OCMSExplorer is a visualization tool designed for 16S rRNA gene sequence data. It is a `R Shiny` app that is distributed as a `R` package. Even though this tool was created as an extension of the 16S rRNA gene analysis pipeline within OCMS, 16S data generated from other pipelines may be used, given that the input file formats are compatible.

## Installing OCMSExplorer
The app is still under development, but it can be installed from the github page. To install OCMSExplorer, use the following in your R console:

{% highlight R %}
devtools::install_local("path/to/OCMSExplorer-30-07-2020.tar.gz")
{% endhighlight %}
<!--more-->

## Launching OCMSExplorer
The app is launched from your R console by:

{% highlight R %}
library(OCMSExplorer)
run_app()
{% endhighlight %}

This will open the app in your web browser. If pop-ups have been blocked by your browser, you may have to allow them for the app.

## Using OCMSExplorer
The app is laid out such that all major tasks in the analysis process are shown across the top, where each task is given its own tab. Sub-tasks are shown in the sidebar on the left.

### Import: Uploading your data
There is an example dataset available in the Import tab (toggle the `Example data` switch to enable/disable). When enabled, you can browser through all the entire app using this dataset.

As part of the OCMS 16S analysis pipeline, the count and taxonomy tables are exported as a `SQLite` database file called `csvdb`. This file is uploaded as the `Database file`. The upload may take a few minutes if the dataset contains several hundred samples. If your raw 16S data was not processed by the OCMS pipeline, there is a helper function in the `OCMSExplorer` package that creates a `SQLite` database file from either R dataframes or from csv or tsv files:
{% highlight R %}
OCMSExplorer::create_db(counts, taxonomy, overwrite = FALSE, outdir, fromfile = FALSE)

# for details on function usage
?OCMSExplorer::create_db
{% endhighlight %}

The format of the count table should be: features (ASVs or OTUs) in rows, in a column called `featureID`, and samples in columns.
{% highlight markdown %}
+-----------+---------+---------+-----+
| featureID | sample1 | sample2 | ... |
+-----------+---------+---------+-----+
| ASV1      | ...     | ...     | ... |
+-----------+---------+---------+-----+
| ...       | ...     | ...     | ... |
{% endhighlight %}

The format of the taxonomy table should have the columns as shown below. The column `Taxon` is a concatenation of all taxonomy levels (`k_kingdom;p_phylum;c_class;o_order;f_family;g_genus;s_species`).
{% highlight markdown %}
+-----------+----------+--------+--------+-------+-------+--------+-------+---------+-------+
| featureID | sequence |Kingdom | Phylum | Class | Order | Family | Genus | Species | Taxon |
+-----------+----------+--------+--------+-------+-------+--------+-------+---------+-------+
| ASV1      | ATG...   | ...    | ...    | ...   | ...   | ...    | ...   | ...     | ...   |
+-----------+----------+--------+--------+-------+-------+--------+-------+---------+-------+
{% endhighlight %}

The metedata associated with your data is imported from a csv or tsv file. The only restriction on the format of the metadata file is that samples are in rows, in a column called `sampleID`. Sample identifiers must be unique and must correspond with the sample columns found in your count table. All columns should have a header.

Once the files have been uploaded, click the `Launch Data` button to submit. Preview of the uploaded data is available.