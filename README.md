# Goldsum
An open-source corpus for testing summarization algorithms, provided and maintained by SumUp Analytics

## Background
Summarization research typically relies on reference corpuses to measure the quality of proposed summarization algorithms, whether extractive or abstractive methods are chosen. Such reference corpuses are comprised of a collection of raw documents alongside gold summaries, human-generated, for each of these raw documents. Gold summaries can themselves be extractive or abstractive.

A few corpuses are commonly used in summarization research:
- Newsroom. 1.3 million articles collated from 38 different medias. https://summari.es. Note that there are licensing restrictions on the usage of this corpus
- CNN. 90k articles. https://cs.nyu.edu/~kcho/DMQA/
- Dailymail. 197k articles. https://cs.nyu.edu/~kcho/DMQA/
- DUC. DUC 2004 seems to be used for summarization tests. https://duc.nist.gov/data.html. Note that there is paperwork involved to get access to that dataset.

## Motivation
Through our own summarization research and interactions with users, we noticed certain limitations, for certain applications, from using the aforementioned datasets for benchmarking of algorithms.
- News articles typically are fairly short, while the majority of documents our users deal with tend to be in the tens to hundreds of pages
- News articles typically are fairly focused on an events and its immediate developments, or on a fairly contained subjects. The majority of our users deal with documents that are addressing multiple topics within a broader subject. Even in the case of a single-topic write-up, the content commonly is more dispersed than what is found in news articles
- News articles regularly have highlights at their beginning

We decided to expand the references corpuses with an additional two, which would address these limitations for certain applications of summarization.

## Corpuses Overview
### - Financial Outlooks 
10 outlooks for 2019 produced by financial institutions, in English, and made freely available online. They range from 15 to 144 pages, with a median length of 40 pages. Each outlook contains a disclaimer, a table of content in a handful of cases, as well as annotated tables and charts. 

There is no Gold summary per-se. Instead, we define the gold summaries as follows:
- Either the collection of sentences or sections of sentences, which are bolded in the content
- Or the outlook highlights made available in an insert within the content

We do not enforce any constraint on the length of the Gold summaries.

These outlooks are made available as PDF and DOCX, the latter allowing users of Goldsum to control for disclaimers, tables of content, tables, and charts in the conduct of their summarization tests.

### - Classical Literature
11 books, in English, whose PDF or TXT is made freely available online. They range from 250 to 800 pages, with a median length of 350 pages. Each classical book contains preface, postface and a table of content.

There are Gold summaries, which are retrieved from WikiSummary http://wikisum.com/w/Main_Page and free to use.

We do not enforce any constraint on the length of the Gold summaries.

## Evolution
We are happy to expand both corpuses with documents of the same kind, alongside their gold summary. If you would like to host additional corpuses within the Goldsum repo, we are also happy to incorporate those. All contributions are acknowledged. 
