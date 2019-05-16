# Goldsum
An open-source corpus for testing summarization algorithms, provided and maintained by SumUp Analytics, Inc.

## Background
Summarization research typically relies on reference corpora to measure the quality of proposed summarization algorithms, whether extractive or abstractive methods are chosen. Such reference corpora are comprised of a collection of raw documents alongside gold summaries, human-generated, for each of these raw documents. Gold summaries can themselves be  extractive or abstractive.

Several corpora are commonly used in summarization research, including:
- Newsroom: 1.3 million articles collated from 38 different medias. https://summari.es. Note that there are licensing restrictions on the usage of this corpus
- CNN: 90k articles. https://cs.nyu.edu/~kcho/DMQA/
- Dailymail: 197k articles. https://cs.nyu.edu/~kcho/DMQA/
- DUC: DUC 2004 seems to be used for summarization tests. https://duc.nist.gov/data.html. Note that there is paperwork involved to get access to that dataset.

## Motivation
Through our own summarization research and interactions with users, we noticed limitations, for certain applications, in using the aforementioned datasets for benchmarking algorithms.
- News articles are typically fairly short, while the majority of documents our users deal with tend to be in the tens to hundreds of pages.
- News articles are typically fairly focused on events and related immediate developments, or on a fairly slef-contained subjects. The majority of our users deal with documents that are mentioning multiple topics within a broader subject. Even in the case of a single-topic write-up, the content is commonly more dispersed than what is found in news articles.
- News articles are written in journalistic style, where a summary of the article is provided in the first few sentences, thus creating a bias towards algorithms that weight initial sentences more (the [https://arxiv.org/abs/1804.11283 newsroom paper] clearly shows that a simple such baseline outperforms all the methods).

Here we provide two new corpora that address these limitations for certain applications of summarization.

## Corpora Overview
### - 2019 Financial Outlooks 
This corpus contains 10 "2019 Outlook Reports" produced by financial institutions, in English, and freely available online. Each report ranges from 10 to 144 pages, with a median length of 33 pages; each contains a disclaimer, a table of content in a handful of cases, as well as annotated tables and charts. 

There are no Gold summary per-se. Instead, we define the gold summaries as follows:
- Either the collection of sentences or sections of sentences, which appear in bold in the content;
- Or, any sentences that are highlighted as an insert within the content.

We do not enforce any constraint on the length of the Gold summaries. Sentences in any Gold summary respect the order in which they appear in the raw document.

In cases where both a highlighted insert and bold sentences appear in the content, we retain all of it as part of the Gold summary of the document. In that case, the highlighted insert will come on the first page of the Gold summary, and the bold sentences will be added subsequently, starting on a new page.

In cases where there are two kinds of summary, typically a summary of the whole outlook and then further in the document, a summary of each section, we reatin all of it as part of the Gold summary of the document. In that case, the summary for the whole outllok will come on the first page of the Gold summary, and the summaries for each section of the document will be added subsequently, starting on a new page.

These outlook reports are made available as PDF and DOCX, the latter format allowing users of Goldsum to better control for disclaimers, tables of content, tables, and charts in their summarization tests.

### - Classical Literature
This corpus contains 11 English-language classical books that are available freely online in PDF or TXT formats. They range from 53 to 1139 pages, with a median length of 198 pages. Each classical book typically contains preface, postface and a table of content.

There are Gold summaries, which are retrieved from WikiSummary http://wikisum.com/w/Main_Page and free to use.

Again we do not enforce any constraint on the length of the Gold summaries.

## Evolution
We are happy to expand both corpora with documents of the same kind, alongside their gold summary. If you would like to host additional corpora within the Goldsum repo, we are also happy to incorporate those. All contributions will be acknowledged. 
