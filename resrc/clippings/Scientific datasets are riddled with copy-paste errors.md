---
title: "Scientific datasets are riddled with copy-paste errors"
source: "https://www.sciencedetective.org/scientific-datasets-are-riddled-with-copy-paste-errors/"
author:
  - "[[Markus Englund]]"
published: 2026-03-06
created: 2026-04-20
description: "Initial results from scanning through Excel files belonging to 600 published scientific papers."
tags:
  - "clippings"
---
The above data comes from a landmark paper in Parkinson's Disease research, which provided the first-ever evidence that the disease originates in the gut rather than the brain. The paper received [media coverage from major outlets](https://www.bbc.com/news/health-38173287?ref=sciencedetective.org) and has amassed over 3000 citations from other scientific papers. But the underlying data contains sequences of duplicated values that should belong to completely different individual mice. The dataset has been [publicly available on Dryad](https://datadryad.org/dataset/doi:10.5061/dryad.4mp6h?ref=sciencedetective.org) - an open-access repository where scientists upload their raw data - for more than 8 years. Why didn't anyone notice the blatant copy-paste errors until now?

Before going into more detail about this case, let me give some background on how we detected the issue: It was flagged by [a piece of software](https://github.com/markusenglund/copy-paste-detective?ref=sciencedetective.org) I started building last year, which was inspired by two cases of data fabrication that made the news in recent years. One by [Nobel laureate Thomas Südhof's lab](https://forbetterscience.com/2023/10/04/thomas-sudhof-and-the-standards-of-scientific-rigor/?ref=sciencedetective.org) and one by [spider ecologist Jonathan Pruitt](https://laskowskilab.faculty.ucdavis.edu/2020/01/29/retractions/?ref=sciencedetective.org). Both cases had publicly available datasets with entire blocks of copy-pasted data that seemed quite trivial to detect. I was curious what I could dig up by creating a program that would correctly flag those cases, and then unleash it on all datasets available in open-access repositories.

Together with a few volunteer contributors, we've finished reporting all cases from the first 600 datasets we've scanned. There were 18 cases we felt were serious enough to raise concerns. Here are 3 of the most exciting ones:

## Case 1: A seminal Parkinson's paper

- Article: [Gut Microbiota Regulate Motor Deficits and Neuroinflammation in a Model of Parkinson’s Disease](https://doi.org/https://doi.org/10.1016/j.cell.2016.11.018?ref=sciencedetective.org) *Cell* (2016)
- [Dryad dataset](https://doi.org/doi:10.5061/dryad.4mp6h?ref=sciencedetective.org) | [Pubpeer comment](https://pubpeer.com/publications/765CBDC8E738AC8FD5CF0B1A2F6A2E?ref=sciencedetective.org#15) (by contributor Ben Woden)

> We took mice that were genetically predisposed to developing symptoms of Parkinson's and we just cleared out their microbiome - all their symptoms went away.

That's how the paper's senior author Sarkis Mazmanian summarized the findings of the study when he went on the Rich Roll Youtube channel:

![](https://www.youtube.com/watch?v=J6gfH9Q4NWY)

These are the results he is referring to:

![](https://science-detective.ghost.io/content/images/2026/03/Screenshot-from-2026-02-24-10-41-42-1.png)

Source: Figure 4

Graphs B, C, and D contain measurements of the motor function of different groups of mice. They tell a clean story where the ASO mice (genetically predisposed to developing the mouse model Parkinson's disease) take longer to complete the tasks than regular wild-type (WT) mice *only* when they have retained a normal gut microbiome (*SPF,* *Ex-GF*) - not in mice stripped of their microbiome (*GF*, *Abx*).

![](https://science-detective.ghost.io/content/images/2026/03/Untitled-design--1-.png)

Diagram showing which results are affected by each block of duplicate values.

There are two issues with the data:

1. There are two sets of 5 identical sequential numbers in the "Adhesive removal times" column, shared between the SPF mice (brought up with a normal, healthy microbiome) and the ExGF mice (raised with a stripped microbiome, but then had their gut re-colonized).
2. There's a pair of sequences of 3 identical numbers within "Pole-descent time" data for the germ-free wild-type mice.

**Verdict**

It could be either a fat-finger mistake when editing the Excel file or deliberate tampering to cover up real data that didn't tell the right story.

The study has low sample size, so the impact on the conclusions of the paper is serious, even if we trust the rest of the data. The duplicated rows make up 50% of the SPF samples and 42% of the ExGF samples. While the motor function values are not the only data the authors rely on for their conclusions, they're necessary for showing that the gut bacteria actually caused Parkinson's-like symptoms.

The issue was reported in January, and the authors have so far not responded.

## Case 2: Ostrich-snake mixup

- Article: [Constraints on the evolution of toxin-resistant Na,K-ATPases have limited dependence on sequence divergence](https://doi.org/https://doi.org/10.1371/journal.pgen.1010323?ref=sciencedetective.org) *PLOS Genetics* (2022)
- [Dryad dataset](https://doi.org/doi:10.5061/dryad.sqv9s4n68?ref=sciencedetective.org) | [Pubpeer comment](https://pubpeer.com/publications/5088E45EA0034E051FB767BD3A346F?ref=sciencedetective.org)

In this paper, the authors investigated how different animals have evolved resistance to a family of toxins called cardiotonic steroids (CTS). There's an arms race in nature where prey species produce CTS to protect themselves against animals such as birds and snakes, who in turn have developed mutations to help protect themselves against the toxin.

The authors created a blend of Ouabain (a CTS) and Na,K-ATPase (the protein that the poison targets) to get a dose-response curve showing how well different versions of the protein survived the poison at various doses.

**Issues**

![](https://science-detective.ghost.io/content/images/2026/02/image-5.png)

Source: NKA\_Enzyme\_Assays\_Raw\_Data.xlsx, sheet: "IC50"

The yellow cells are precise duplicates between the Ostrich/Sandgrouse data and the Xenodon data (a species of snake). More concerning are the orange cells, which are near-duplicates that differ by one or two digits, always ending with the same digit. For example, 0.538 on row 39 becomes 0.518 on row 71. There are six such pairs out of eight total non-duplicate pairs.

[In her response](https://pubpeer.com/publications/5088E45EA0034E051FB767BD3A346F?ref=sciencedetective.org#2), the lead author Shabnam Mohammadi concedes that this probably is a copy-paste error. For the suspicious orange cells she gives the following explanation:

> We suspect that they \[the cells with one-digit tweaks marked in orange\] stem from measurement variation among multiple reads of the same plate, and that the Ostrich and Xenodon results were copied from different readings of the same plate. However, since the original reader outputs are not available, we cannot confirm that this is the source of the variation.

**Verdict**

Could the one-digit tweaks be caused by multiple readings of the same plate as the author theorizes? My best guess is no, but there is enough uncertainty to give me pause.

When doing multiple readings of the same plate we would generally expect many of the values to jump around a tiny bit. Instead we see almost all of the values staying the exact same except 8 that change by a lot. In email correspondence, the author provides a potential explanation for this: before taking the readings they add a chemical to stop the reaction, which should stabilize the values. But some wells will stabilize faster than others, which could explain why those 8 values still varied by so much.

That still leaves the issue of the 6 pairs of values that each happen to end with the same digit. It would be supremely unlikely for this to happen purely by chance.

The BioRad model 680 is a basic machine that records raw light measurements as it sees them without any post-processing, but perhaps it's still possible that it introduces some bias that makes it more likely for readings to end on the same digit.

The alternative explanation is that the authors either accidentally or deliberately copy-pasted the Ostrich/Sandgrouse data on top of the Xenodon data. Then they might have manually tampered with the data to make it better suit their hypothesis or make it look less suspicious, not realizing that the copy-and-paste would leave behind this signature. However, the fraud theory suffers from there not being any obvious reason for why the authors would tamper with these specific values.

The authors state that they will try to replicate the process and report what they find on Pubpeer.

*See author's response* [*here*](#update-response-to-the-author-of-case-2)*.*

## Case 3: Scrambled fish sizes

- Article: [Behavioural individuality in clonal fish arises despite near-identical rearing conditions](https://doi.org/https://doi.org/10.1038/ncomms15361?ref=sciencedetective.org) *Nature communications* (2017)
- [Dryad dataset](https://doi.org/doi:10.5061/dryad.td3sj?ref=sciencedetective.org) | [Pubpeer comment](https://pubpeer.com/publications/D1769F3E32035DFA98B422B27F8C86?ref=sciencedetective.org) (by contributor Ben Woden)

**Background**

This is a paper from 2017 about fish personalities. They took a bunch of genetically identical fish, then checked how much their swimming behavior varied in terms of distance traveled. The idea was to see how much their behavior differed while keeping genetics and environment identical. Besides movement, they also took the size of each fish into account to check that any difference in movement was not just a result of bigger fish moving differently from smaller fish.

**Issues**

The SL column is the length of the individual fish measured in millimeters. Can you spot anything that looks out of place?

![Spot the issue](https://science-detective.ghost.io/content/images/2026/02/image-7.png)

Source: [Bierbach et al clonal molly behav development\_data for deposit.xlsx](https://datadryad.org/dataset/doi:10.5061/dryad.td3sj?ref=sciencedetective.org) (2018)

It looks quite strange that 3 different individual fish (ID 5, 8 and 10) all have the exact same sequential size measurements. But wait, can an individual fish really get >10% shorter over the course of a few days? Did they actually measure the length of every individual fish 4 times? No.

**Verdict**

The real explanation becomes obvious if we order the sheet by the SL column. It reveals that every unique SL value reoccurs exactly four times. 4 also happens to be the number of observations that were done per individual fish.

![](https://science-detective.ghost.io/content/images/2026/02/image-9.png)

The same spreadsheet sorted by SL (fish length in mm)

The reason for that is that the authors only measured the length of a fish once. So all 4 rows with observations of the same fish are supposed to have the same exact fish length, but they have been scrambled so that the length of one fish has been given to 4 other fish.

In [his response](https://pubpeer.com/publications/D1769F3E32035DFA98B422B27F8C86?ref=sciencedetective.org#5), the first author admits to the error and gives the following explanation:

> \[I\]n short, we stored measured body size and behavior in two separate data files and when we joined these files, we accidentally misaligned the ID values resulting in a phase shift where all body size values were shifted and assigned to the wrong rows

And I don't see any reason to doubt him.

In the paper they unsurprisingly concluded that body size didn't have any effect on distance traveled, while in [their corrected analysis](https://datadryad.org/downloads/file_stream/4591033?ref=sciencedetective.org) they do find a small effect:

> Body size now is a significant predictor of behavior but its effects are quite small (i.e. a 1mm increase in body leads to a 0.8cm decrease in total distance swam over the whole trial) and in fact roughly 3x smaller than the effect of observation. More importantly though, body size still does not explain the among-individual variation in behavior.

It looks like the authors did a solid job of owning up to their mistake and correcting the dataset. Luckily, body size turned out to only explain a small part of the behavioral differences between the fish. "The conclusions remain unaffected" is one thing you should never take at face value coming from a researcher, but in this case it appears to be right.

## Overall results so far

The software detected 18 cases in the first 600 datasets that were serious enough to raise concerns. So far, we have posted 15 of these to PubPeer (see the full list [here](https://www.sciencedetective.org/about)). Most of them probably innocent mistakes, some may be deliberate fabrication. [One of them](https://www.science.org/doi/10.1126/science.aag2792?ref=sciencedetective.org) had already been retracted. So based on that limited sample, around 3% of papers contain these types of errors.

However, the true error rate must surely be a lot higher than 3%. There are myriad other ways of accidentally screwing up your data that this software could never detect. And if you want to commit fraud, there are plenty of less lazy ways to do it than to copy-paste values from a different part of the same Excel sheet.

It might come as a surprise to some that nobody else has cared to check for these errors. Isn't there some peer review thing that is supposed to prevent stuff like this from making it into the scientific record? The conclusion I've come to is that there just isn't anybody whose job it is to actively look for it. Journals, universities and funding organizations won't hire anyone to do it because they generally care a lot more about rankings and metrics. And if you report a serious error to them you've just introduced an annoying inconvenience that might make those numbers go in the wrong direction.

The only bright spot has been [Dryad](https://datadryad.org/?ref=sciencedetective.org) - the research data repository. They have taken an active role in supporting the project by helping push journals and authors to correct the record.

## What's next

I started working on the project last year, and after some good initial results, I was able to raise a [50,000$ grant from Astral Codex Ten](https://www.astralcodexten.com/p/acx-grants-results-2025?ref=sciencedetective.org#:~:text=and%20other%20pests.-,Markus%20Englund,-%2C%20%2450K%2C%20for%20software) (a popular science blog), which allowed me to quit my job and start working on it full-time this year. Next up is to scan through the rest of the ~24,000 datasets with Excel files available on Dryad. It will be interesting to see what other treasures we can dig up there! If the 3% error rate holds, we'd expect to see ~700 more cases in that sample alone. Feel free to subscribe to the email newsletter to stay up to date on what we find.

*Updated on March 8: Removed unwarranted confidence in the verdict of case 2 and added some additional detail.*

*Updated on March 23*: *Clarified that 15 of the 18 cases had been publicly posted on Pubpeer.*

## Update: Response to the author of case 2

*Added on April 11th.*

Shabnam Mohammadi - the first author of the paper, responded in the comments section. I'm adding it here together with my response.

### Mohammadi's response

> As an author of the study featured as the second case and the one who performed the experiments in question, I'd like to provide some additional context.

> As noted, the Model 680 plate reader is a 30-year-old legacy plate reader that requires manual translation or copy-pasting of results. Englund's claim that the Model 680 "records raw light measurements as it sees them without any post-processing" is incorrect. The instrument has a resolution of 0.001 OD and a specified reproducibility of 1.0% or 0.005 OD across the 0.000-2.000 OD range (and 1.5% from 2.000-3.000 OD). It converts analog intensity signals to absorbance values using Beer's law, rounding results to the nearest 0.001 OD. Consequently, values fluctuating within a narrow range may round in ways that produce apparent digit-level patterns with some digits varying systematically while others appearing unchanged across wells. For a developing colorimetric assay, a mix of unchanged, moderately changed, and markedly different well values between reads is therefore entirely plausible, reflecting both the underlying chemistry of the assay and the instrument's optical and processing characteristics.

> Further, we have updated our PubPeer response to include a reanalysis that excludes the duplicated data. Our conclusion is that removing the problematic data actually strengthens the paper's main conclusions rather than undermining them.

### My response

> Englund's claim that the Model 680 "records raw light measurements as it sees them without any post-processing" is incorrect. \[...\] It converts analog intensity signals to absorbance values using Beer's law, rounding results to the nearest 0.001 OD.

Ok, that was incorrect on my part and shows my lack of knowledge about photometers. I was attempting to paraphrase an email from Bio-rad where they said: “ *The system \[Bio-rad 680\] was very basic and recorded OD as seen, it did not do any onboard manipulation of the data, it gave raw results for the user to interpret.*”

> Consequently, values fluctuating within a narrow range may round in ways that produce apparent digit-level patterns with some digits varying systematically while others appearing unchanged across wells.

I don’t see how that follows as a consequence at all. The formula used by plate readers is from what I understand just a log10-transformation of the raw analog signals. How could that possibly produce the pattern where the last digit (the thousandth place) remains the same across readings?

Here's an example of what I would expect multiple readings of the same plate to look like:

![1st reading](https://storage.ghost.io/c/ba/88/ba885ce2-6877-4f70-9886-fcfa8ede8c06/content/images/2026/04/Screenshot-from-2026-04-11-14-11-38.png)

Use buttons to toggle between readings to compare differences

These images are of three consecutive readings of the same plate using the BioTek EL800, which like the Bio-rad 680 is an old filter-based microplate reader. It's not identical to the Bio-rad model 680, but from what I gather it's similar. Like all absorbance plate readers, it uses the same log10-transformation to get the final values. The test was done on a chemically stable dye called PNP at different concentrations. The experiment shows minor differences between readings of 0.001-0.002 for many of the wells which is caused by noise. [Full data here](https://www.sciencedetective.org/content/files/2026/04/GF-dilution-sereis-PNP-3-platereaders.xlsx).

The test was run by Dr Gert Folkers at Utrecht University (not affiliated with Science detective). He also did the same test on two more modern plate readers, which counter-intuitively have larger variance across readings than the old BioTek reader. Shown below is data from the same test done on the BMG clariostar:

The tests from all plate readers show many changes in OD values between readings, and none of them show a tendency to preserve the last digit. Have you - or anyone from the scientific community reading this - actually observed “digit-level patterns with some digits varying systematically while others appearing unchanged” when working with the Bio-rad 680 or other plate-readers? If so, please show some data that demonstrates this.

I'm not saying these data are proof of manipulation. The BioTek is not an identical machine to the BioRad. Also, the fact that the modern reader has much higher variance (possibly due to "plate background correction" according to Dr Folkers) is a good reminder that these machines can produce unexpected patterns. But I've yet to see evidence that the pattern where the last digit remains the same across readings could be caused by the log formula used by plate readers.