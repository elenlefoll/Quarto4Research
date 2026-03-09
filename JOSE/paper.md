---
title: "Quarto for reproducible research workflows and academic publishing"
subtitle: "A step-by-step tutorial"
tags:
- Quarto
- R
- literate programming
- reproducibility
- academic writing
authors:
- name: Elen Le Foll
  orcid: "0000-0002-5839-8010"
  affiliation: 1
affiliations:
- name: Department of Romance Studies, University of Cologne
  index: 1
date: 9 March 2026
bibliography: paper.bib
---

# Summary

Quarto is a multi-language, open-source scientific and technical
publishing system that turns plain text and code into publication-ready
papers, slides, websites, books, and teaching materials. It unifies
writing and computation, supports the implementation of seamless
reproducible workflows, and bridges the gap between conducting, writing,
and communicating research [@wickhamDataScienceImport2023]. As such, it is ideally suited for academic research and publishing.

The present article describes an accessible, hands-on introduction to
Quarto for university students and academics with little to no prior
experience with programming and markdown syntax. The online version of
the tutorial is published on
[QuartoPub](https://elenlefoll.quarto.pub/quarto4research/). It includes
interactive quiz questions that encourage the reader to try things out
immediately, providing immediate, motivating feedback. The tutorial
itself was written in Quarto and the source code is published alongside
the tutorial as an accompanying Open Educational Resource (OER) on Zenodo [@lefollQuartoReproducibleResearch2026]. As per
its CC-BY license, it may be adapted, remixed, and reused in different
educational contexts. Making use of Quarto's multi-format rendering
options, a [PDF version](https://elenlefoll.quarto.pub/quarto4research/Quarto4Research.pdf) of the tutorial is also available for offline
reading and annotation.

![A schematic representation showing Quarto can understand
multi-language input and produce multi-format outputs (Artwork [CC BY
4.0](https://creativecommons.org/licenses/by/4.0/) [Allison
Horst](https://allisonhorst.com/cetinkaya-rundel-lowndes-quarto-keynote)
from the ["Hello, Quarto"
keynote](https://mine.quarto.pub/hello-quarto/#/hello-quarto-title) by
Julia Lowndes and Mine Çetinkaya-Rundel, first presented at the RStudio
Conference 2022)](AHorst_Quarto.png){#fig-QuartoFormats
fig-alt="A schematic representing the multi-language input (e.g. Python, R, Observable, Julia) and multi-format output (e.g. PDF, html, Word documents, and more) versatility of Quarto."}

# Statement of need

As a new system, accessible resources on and in Quarto are still
relatively scarce. The official [Quarto Guide](https://quarto.org/)
provides extensive documentation; however, its "Get Started" pages
assume prior knowledge that, in my experience, not all students and
academics can be assumed to have, especially in the humanities and
social sciences. Whilst the benefits of Quarto for academic research
have been highlighted from the launch of the new format in July 2022 [@teamAnnouncingQuartoNew2022],
early adopters have tended to come from disciplines where (statistical)
programming has long become part and parcel of everyday research
activities. Many of these colleagues were already using Rmarkdown and/or
Jupyter Notebooks, from which switching costs to Quarto are low. In the
humanities and social sciences, however, students and academics are
still largely drafting their research outputs in (proprietary)
text-processing software, foremost Microsoft Word, Google Docs, and Overleaf. For these students and colleagues, switching to
Quarto represents a much steeper learning curve. As a result, this OER
not only provides a hands-on introduction to Quarto, it also makes the
case for how literate programming and multi-format exporting options
have the potential to genuinely improve research workflows, by making
them both more efficient and less error-prone. To this end, a
step-by-step tutorial was designed that includes concrete examples and
immediate opportunities for success.

The tutorial is an adaptation of Chapter 14 on "Reproducible research
and academic writing in Quarto" in @lefollDataAnalysisLanguage2025. The
textbook chapter has been extensively tested and revised over multiple
iterations following feedback from three cohorts of B.A., M.A., and
Ph.D. students of linguistics, Romance languages, and language teaching
at the University of Cologne, as well as students and colleagues from
other institutions. The textbook, however, was written for linear
reading and, as a result, is unsuitable as a standalone resource on
Quarto for reproducible workflows and academic research. The tutorial
described in the present article, by contrast, assumes no prior
knowledge. It can be used both for self-study or as part of a course or
workshop.

In contrast to most beginner-level Quarto tutorials, the present OER
begins by outlining all installation steps in detail. It focuses on a
single IDE, RStudio, that comes bundled with Quarto, in order to reduce
cognitive load. It also relies on the use of locally-stored datasets, as
opposed to data more conveniently accessible from an (R) package. The aim
is to ensure that students and researchers who complete the tutorial
have all the necessary keys in hand to be able to apply what they have
learnt on their own research projects with their own data. 

Educators are encouraged to adapt this OER to their students' needs and interests. The easiest way to achieve this is to change the dataset to something directly relevant to the target audience. The datasets currently used come from @DabrowskaExperienceAptitudeIndividual2019. They were chosen
for three reasons. First, because they feature easily understandable
variables that require little to no domain-specific knowledge. Second,
because they are of interest to both linguistics and education students
and researchers. And, last but not least, because they represent raw
data featuring typical pitfalls of real-life research data such as
inconsistent capitalisation, trailing whitespaces, and typos, that
vividly illustrate the need for reproducible data wrangling workflows.

# Learning objectives

As a beginner-friendly OER, "Quarto for reproducible research workflows
and academic publishing: A step-by-step tutorial" aims to impart a basic
understanding of literate programming and of the importance of
reproducibility in research workflow.

The OER covers:

-   how to install and use Quarto in RStudio
-   how to write research reports, term papers, theses, and journal
    articles in Quarto by weaving together prose, code chunks, and code
    outputs
-   how to format prose in markdown
-   how to insert tables, images, plots with cross-references and
    alt-text in a Quarto document
-   how to add and format bibliographic references in Quarto documents
-   how to document package usage, as well as credit package developers
    with package references
-   how to export and share Quarto documents in multiple formats
    including HTML, PDF, LibreOffice Writer, and Microsoft Word.

By the time learners have read the entire tutorial and completed all the
tasks and quiz questions, they should have developed an understanding
of the benefits of literate programming as implemented in Quarto,
including how such a system can contribute to improving the
reproducibility of their workflows. They are ready to start writing
their own term paper, dissertation, thesis, research report, or journal
article in Quarto and possess sufficient foundational knowledge with
which they can start exploring some of the more advanced recommended resources
listed at the end of the tutorial.

# Instructional design

The tutorial includes clear step-by-step instructions illustrated with
annotated screenshots with the aim of rendering maximally accessible to
students and researchers from all disciplines, with a particular focus
on humanities and social science scholars who may not have prior
experience with literate programming, the use of IDEs such as RStudio,
or YAML, Markdown, and BibTex syntax. To achieve this, the tutorial
begins with an introduction to literate programming, explaining its
benefits and focuses much of the writing process on using RStudio's
visual mode for Quarto files, which is less intimidating than the source
mode for learners with no programming experience. This approach helps to
ease learners into the concept of weaving prose and code, showcasing how
dynamic and reproducible research can be.

To make the learning experience engaging and relevant, the tutorial
relies on real data from a published study
[@DabrowskaExperienceAptitudeIndividual2019]. This not only serves to
motivate learners, but also makes the newly acquired knowledge more
readily implementable with their own data, given that the tutorial
includes code to import the data into R. The HTML version of the
tutorial includes mini-tasks that are based on the same study and aim to
reinforce learning through hands-on practice. To encourage readers to
explore Quarto during the completion of these tasks, twelve quiz
questions with single or multiple-choice answers are integrated
throughout the tutorial, providing immediate feedback to help learners
assess their understanding. The conclusion section offers a tally of all
correct responses, allowing learners to track their own progress without
any penalties for multiple attempts. It also provides a list of learning
objectives that they can tick off with cross-references to the
corresponding sections of the tutorial, should they identify any gaps in
their understanding at this stage.

The tutorial aims to introduce all relevant aspects of Quarto for
academic writing and publishing in a single, cohesive document. Rather
than overwhelming the reader with extensive details, the tutorial
provides links to further resources throughout, as well as in the
concluding "Going Further with Quarto" section. This approach ensures
that learners have a solid foundation from which they can explore
further resources detailing the endless more specialised options that
Quarto has to offer.

Last but not least, the tutorial is designed with a strong emphasis on accessibility and inclusivity. The OER's Quarto source code is available for adaptation (including translation), allowing educators to tailor the content to specific learner groups. All images include captions and alt-text
descriptions to support blind and low-vision readers. The HTML version
also features a dark mode for enhanced readability. The PDF version
ensures that the resource is also accessible in areas with unstable internet
connections.

# Usage

'Quarto for reproducible research workflows and academic publishing: A step-by-step tutorial' has been tested in a variety of educational and professional contexts. It has been integrated as teaching material in semester-long courses on data analysis in R for linguistics and language education research at the University of Cologne. Furthermore, it has been used as standalone workshop material for doctoral and post-doctoral researchers from the humanities and social sciences. Additionally, it has served as a self-study learning and revision resource for students required to submit their term papers or dissertations in Quarto. Colleagues have also reported that it has been a valuable starting point for them when writing academic papers, research reports, or online supplements for the first time in Quarto.

Learner feedback has been overwhelmingly positive. Both students and seasoned researchers appear to appreciate the easy-to-follow instructions accompanied by screenshots, the concrete examples, and the mini-tasks and quiz questions that allow for immediate feedback. M.A. students and researchers were quick to grasp the benefits of literate programming in Quarto for research workflows and academic writing. Many expressed surprise at how accessible Quarto in RStudio is and were keen to continue exploring its capabilities. This positive reception underscores the tutorial's effectiveness in making Quarto approachable and genuinely valuable for a wide range of users within academia, including in traditionally less computational disciplines.

# Acknowledgements

I am grateful to my students and the participants of the Quarto workshops that I have taught in the past for their insightful feedback on earlier drafts of the tutorial and, more generally, on how to approach teaching computational thinking to humanities and social science students and researchers. 

# References
