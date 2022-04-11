---
title: LREC 2022 Investigating User Radicalization - A Novel Dataset for Identifying Fine-Grained Temporal Shifts in Opinion
tags: 
  - LREC
  - Opinion Dynamics
  - Stance Detection Dataset
  - Sociopolitical Language
  - Dataset with Temporal  
---

We are very excited to present our all-female-author paper "Investigating User Radicalization - A Novel Dataset for Identifying Fine-Grained Temporal Shifts in Opinion" from Flora Sakketou, Allison Lahnala, Liane Vogel and Lucie Flek at LREC 2022.  

In this work, we present a dataset called SPINOS (<ins>S</ins>ubtle <ins>P</ins>olarity and <ins>IN</ins>tensity <ins>O</ins>pinion <ins>S</ins>hifts), which contains 3.5k Reddit entries from 600 users for modeling opinion dynamics and detecting fine-grained stances. 

# TLDR; #

The dataset includes a sufficient amount of stance polarity and intensity labels per user **over time** and **within entire conversational threads**, enabling the detection of subtle opinion fluctuations both in long term and in short term. All posts are manually annotated by non-experts and a significant portion of the data is also annotated by experts. In our paper, we provide a strategy for recruiting suitable non-experts and show that by following this strategy, the resulting annotations obtained from the majority vote of the non-experts are of comparable quality to the annotations of the experts.

We analyzed the stance evolution in long term and short term levels. When analyzing the stance evolution on a *long term level*, we observed that users change the polarity of their stance rather frequently, however most users express strong intensities for only one of the two poles (in favor or against). On a *short term level*, when analyzing the opinion fluctuations within conversational threads, we observe that there is usually only a change in intensity and rarely in the polarity, leading us to the conclusion that opinion change is expressed over time. In addition, we provide a comparison of language usage between users who tend to change their opinion frequently and users who are more stubborn, and also employ fine-grained stance detection baselines.

# On to the long version then... #

## Why is this work important? ##

- Temporal data about user opinions is necessary in order to study the dynamics of radicalization and polarization.
- There is a significant lack of NLP data resources that enable such studies.
- Due to the lack of resources, the is also a lack of efficient, data-driven models that investigate the relationships between social media behaviors and opinion formation and fluctuation.
- By introducing this dataset, we attempt to bridge the gap between the theoretical sociopolitical approaches and NLP methodologies

## Why is this dataset novel? ##

This is the first dataset, to the best of our knowledge, that provides:
- a sufficient amount of annotated user history which enables the investigation of opinion shifts both **in the long-term** but also **within a conversation**,
- both stance **polarity** and **intensity** annotations regarding a large range of sociopolitical issues.

## Annotation ##

### Annotation Labels and Guidelines ###

You can find <a href="https://raw.githack.com/caisa-lab/SPINOS-dataset/main/annotation_template/annotation_template_example_abortion.html" target="_blank"> here</a> an example of the annotation template. The template contains the detailed annotation guidelines, the options given to the annotators and the survey they were asked to fill. Namely, the labels that could be assigned are: **strongly against, somewhat against, somewhat in favor, strongly in favor** and **stance not inferrable**.

In addition to the stance polarity and intensity labels, we also provide the following labels for each post:
- **Contextual information requirement.** For every annotation, the annotators could optionally view the top-level post in the thread and/or the previous posts in the thread. This label indicates whether such information was needed for the annotation.

- **Stance explicitness.** A label that indicates whether the stance of the author was explicitly stated or implied within the text. 

- **Expression of sarcasm.** A label that indicates that the content is sarcastic (only for the cases where a stance is assigned).

- **Uncertainty of assigned label.** A label that indicates whether the annotators feel uncertain of their annotation (only for the cases where a stance is assigned). 

### Annotation Phases ###

The dataset was manually annotated by expert annotators and non-experts (NE) with Mechanical Turk. 

- **First phase:** In the first phase, three expert annotators annotated a small subset of posts. The expert annotators were trained on a small subset of posts, where they were able to ask questions and discuss opinions in case of disagreement. 

- **Second phase:** In the second phase, we introduce a two-step process in order to recruit the suitable annotators: 

    1. We introduce a relatively demanding qualification test to ensure that the NE annotators have a comprehensive understanding of the guidelines.

    2. We compute the pairwise inter-annotator agreement between the experts (who passed the qualification test) and the non-experts, and select the NE annotators with the highest scores.  


## The Dataset ##

### Dataset statistics ###

For each user, we collected statements that were posted on average over the course of 6 months and at most within 15 months. The posts were collected from April 2019 to July 2020. 

Our dataset includes the following topics: (1) abortion, (2) feminism, (3) brexit, (4) veganism/animal rights, (5) guns, (6) nuclear energy, (7) capitalism, and (8) climate change. This is the topic distribution in our dataset:

![topic_distribution](../../../images/topic_distr.png)


Here are some basic dataset statistics:
Attribute | Statistic
:------------- | :-------------:
Total number of annotated posts |      3526 
Total number of annotated posts by experts |       673 
Total number of annotated authors |       638 
Average number of posts per author |      5.53  
Number of annotated threads trees |       113 
Number of annotated thread branches |       547 
Number of posts in annotated thread trees |      1752 


The final annotation labels are decided by the majority vote between at least three annotators. The *undecided label* was assigned in cases the cases where the votes were equally distributed to each polarity and the non inferrable category. The stance distribution per topic can be looked at:

![stance_distr](../../../images/stance_distr.png)

### Annotator statistics ###

