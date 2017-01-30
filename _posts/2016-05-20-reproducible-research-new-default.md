---
title: Reproducible Research As Our New Default
author: Bret Beheim
date: 2016-05-20
layout: single
---

The last decade has been a sobering one for science, marked by increasingly frank conversations about 'the idea that something has gone fundamentally wrong with one of our greatest human creations', to quote Richard Horton, editor-in-chief of The Lancet. He continues,

>'Afflicted by studies with small sample sizes, tiny effects, invalid exploratory analyses, and flagrant conflicts of interest, together with an obsession for pursuing fashionable trends of dubious importance, science has taken a turn towards darkness.'[^1]

Multiple studies in the social and life sciences have identified widespread use of 'questionable research practices'[^2][^3], and many important results have failed to replicate in follow-up work [^4]. The recent re-analysis of 100 psychology studies by the [Open Science Collaboration](https://osf.io/ezcuj/wiki/home/) has attracted a good deal of attention for finding nonreplication in at least 30%, but possibly as much as 60%, of re-run studies. [^5]

What does the 'reproducibility crisis' mean for scientific anthropology, especially for those of us doing statistical analyses of field data?

From talking to colleagues, most first reactions – mine as well – is that reproducibility is a nonstarter in anthropology. Fieldwork is messy, and our data is observational rather than experimental. Moreover, it was collected in circumstances so unique in time and in location that it's usually impossible to revisit that same data source again.

Yet there remains another kind of replication, one that can be applied to anthropology as it can to any other scientific endeavor. In fact, it's among the most basic and fundamental components of all of science: if someone else looked at the same data you did, will they be able to reproduce your analysis and achieve the same results?

Seems too simple, right? Last year two economists put this most humble of demands to a collection of recent studies, all peer-reviewed in high-impact economics journals. [^6] Alarmingly, of 67 papers, the essential results of only 29 could actually be reproduced in this way. For the majority, the data was either unavailable (even in journals that required data be available), or upon analysis gave fundamentally different results. This was true even when running the original analysis script, and in a few cases, even with the direct help of the original authors.

Similar efforts in biology have been equally dismal. Vines, et al. (2014) attempted to assemble the datasets from 526 morphometry studies published between 1991 and 2011 [^7]. For a shocking 80% of cases they were unsuccessful; half of contacted authors did not respond or were unwilling to share data, and another quarter had no working email. Moreover, in about a fifth of the oldest studies in the sample, published before 1996, Vines, et al. received positive confirmation that the original data was not merely unavailable but actually lost. Much anthropological data was collected before 1996.

At this point, you might expect a 'but'. There is no 'but'. It is really that bad. If the above is any guide, we must confront the possibility that many (most?) quantitative results in anthropology cannot be reproduced, because the original dataset is lost to time, or upon reanalysis does not yield the same results.

If you have an existing analysis in print, consider the following as a personal challenge: delete all the intermediate steps, and also the final tables and figures. With only the original data, and the analysis script, can you recover everything else? Footnote: This challenge was inspired by the excellent [Code and Data for the Social Sciences: A Practitioner’s Guide](http://web.stanford.edu/~gentzkow/research/CodeAndData.pdf), by Matthew Gentzkow and Jesse M. Shapiro.

I recently tried this on [a project](http://biorxiv.org/content/early/2014/05/19/005223.short) I thought was properly archived, and was alarmed to find the answer was 'no'. I had left behind multiple, cryptically-named versions of my files, none complete, and none by themselves producing the actual publication results. With much effort, I was able to properly reconstruct my original sequence of analysis steps, and (to my eternal relief) the published tables and figures re-appeared.

Yet the experience was a sobering one. If you cannot reproduce your own results, surely no one else will either, and our basic premise of scientific knowledge accumulation breaks down.

How is this phenomenon non-reproducibility even possible, let alone apparently at pandemic levels? There's charlantism, no doubt. And widespread reticence to make available the dataset upon which published claims rest. But often, I would guess, the explanation is simply sloppy documentation.

A statistical analysis in anthropology involves literally thousands of individual steps: table joins, cleaning, outlier removal, subsetting, transforming variables, constructing design matricies, fitting multiple model specifications, running tests, and visualizing results, all to be summarized in a brief Methods section. And that's not even including the actual fieldwork!

Herein lies the real value of scripting your work in a statistical computing language like R or Stata; the code is self-documenting. With everything in timeless, universal plaintext (think .csv, .txt, .r, .dta, or .dat), an analysis can be re-run automatically, and becomes available for review and cumulative improvement. And it becomes that much harder to practice charlatanry.

The ethic of reproducible work is part of the larger movement towards open source science, including practices such as pre-registering hypotheses, reporting null results, ensuring author availability through the Open Researcher and Contributor ID (ORCID), and using online repositories like GitHub to publicly enshrine code and data. The parallels with open-source software development are striking, and some very good resources are available for academics eager to develop these skills, such as software-carpentry.com.

There are several commendable recent examples of this philosophy of open-source science. The authors of the recent work on Homo naledi[^b] made almost the entire project available at publication, including downloadable 3D scans of the specimens. Venkataraman and colleagues included a link to their data repository[^a] as part of a recent PNAS submission, allowing reviewers to comment on and even modify the submitted analysis in their reviews. As Richard McElreath says in his Statistical Rethinking, 'The data and its analysis are the scientific product. The paper is just an advertisement.' [^8]

Open-source, reproducible science is now the default approach[^10] for many scientists; let it be so in anthropology as well.

[^10]:http://www.carlboettiger.info/2012/09/28/Welcome-to-my-lab-notebook.html

[^b]: http://www.anthropology-news.org/index.php/2016/03/01/a-game-changer-in-the-study-of-human-origins/

[^1]: Horton, Richard (2015) 'Offline: What is medicine’s 5 sigma?' The Lancet 385, pp.1380

[^2]: Fanelli, Daniele (2009) How Many Scientists Fabricate and Falsify Research? A Systematic Review and Meta-Analysis of Survey Data.

[^3]: Leslie, John K., Loewenstein, George, and Prelec, Drazen (2012) Measuring the Prevalence of Questionable Research Practices With Incentives for Truth Telling.
http://pss.sagepub.com/content/early/2012/04/16/0956797611430953.abstract

[^4]: Begley, C. Glenn, and Ellis, Lee M. (2012) Drug development: Raise standards for preclinical cancer research.
http://www.nature.com/nature/journal/v483/n7391/full/483531a.html

[^5]: Open Science Collaboration (2015) 'Estimating the reproducibility of psychological science.'
Science 349, DOI: 10.1126/science.aac4716

[^6]: Chang, Andrew C., and Phillip Li (2015) 'Is Economics Research Replicable? Sixty Pub-
lished Papers from Thirteen Journals Say “Usually Not”,' Finance and Economics Dis-
cussion Series 2015-083. Washington: Board of Governors of the Federal Reserve System,
http://dx.doi.org/10.17016/FEDS.2015.083.

[^7]: Vines, Timothy H., et al. (2014) 'The Availability of Research Data Declines Rapidly with Article Age', Current Biology 24, pp. 94–97

[^8]: McElreath, Richard (2016) Statistical Rethinking, A Bayesian Course with Examples in R and Stan. CRC Press., pp. 443

[^a]:https://github.com/ThomasKraft/HunterGathererMarginalValueTheorem
