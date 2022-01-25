# Automated Fact-Checking under Fact Extraction and VERification (FEVER) Shared Task

## Task Definition
The first Fact Extraction and VERification (FEVER) shared task was proposed by [FEVER: a Large-scale Dataset for Fact Extraction and VERification (Thorne et al., 2018)](https://aclanthology.org/N18-1074/), which consists of three stages: 1) Document Retrieval; 2) Sentence Selection; 3) Recognizing Textual Entailment.

## Dataset Statistics

![Statistics of FEVER](figs/fever_statistics.png)

## Evaluation
TODO
## Keys
### Claim Generation
1. June 2017 Wikipedia dump, processed it with Stanford CoreNLP.->
2. Sampled sentences from the **introductory** sections of approximately 50,000 popular pages and  5,000 from a Wikipedia **most accessed pages** list and **the pages hyperlinked from them**(for multi-hop cases).->
3. Given a sentence from the sample (i.e. step 2) chosen at random,-> generating *a set of claims*  -> introducing a dictionary as additional information to increase the complexity of the generated claims in a controlled manner: a list of terms that were (hyper-)linked in the original sentence, along with the first sentence from their corresponding Wikipedia pages.
4. Six types of mutation: paraphrasing, negation, substitution of an entity/relation with a similar/dissimilar one, and making the claim more general/specific.
5. A mean length of 9.4 tokens
### Claim Labeling
1. Label each individual claim generated during Claim Generation(#Claim Generation) as **SUPPORTED**, **REFUTED** or **NOTENOUGHINFO**.
2. What sentences can be selected as evidences (which means no IR process for annotators): \
	2.1.  all sentences from the introductory section *of the page* for the main entity and *of every linked entity* in those sentences\
	2.2. all sentences from the introductory section *of any arbitrary pages* added by annotators\
	2.3. the title of the page(not explicitly recorded)\
### Dataset split
1. Each Wikipedia page used to generate claims occurs in exactly one set.
2. Extra 19,998 examples for use as a test set for a shared task(i.e., reserved).

