[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/Y4rZMh1t)
# Junior Seminar (CMPSC 580) Exemplar Project Repository

## Semester: Spring 2024

This repository contains student project materials, including project report, data, code, and references to literature for this departmentally-sponsored project. __As you complete each of the below sections in this document, please be sure to remove the preamble text so that it does not appear in your work.__ Please work with your first reader to answer any questions or concerns that you may have.

## GitHub Handle: boulais01

## Name: Mordred Boulais

## Major: Previous CS Major (Current Project: Software Engineering)

## Project Name: COMMA(Chasten Output Mutation Mutmut Analysis)

---

## Overview

This project seeks to create a Python version of the `Zhu2021` work, so as to
examine code's testability utilizing mutants. The `Zhu2021` work is focused on
Java, while our project is based in and around Python. The project, being
completed by the team `SEERS`, has been titled `COMMA`, which stands for
"Chasten Output Mutation Mutmut Analysis". Our work is done by using the tool
`Chasten` to locate patterns within the code, and then using the tool `mutmut`
to run a mutation analysis. The patterns `Chasten` locates are types of code
that appear frequently, such as for loops and if statements. The mutation done
by `mumut` is running the code through the tests with random alterations to
inject bugs into the code, and gives the output of how many of these bugs are
caught and how many are not. The output of these two checks are saved in a json
file together, through which an analysis can then be run on the correlation
between them. Specifically, the analysis is done via a statistical analysis and
machine learning. The statistical analysis is the correlation between patterns
and the mutation scores - i.e. how many mutants are 'killed' or 'survived',
meaning how many of the errors created through mutation the tests catch.
The intention is then to be able to identify 'high-risk'
patterns/antipatterns that make the code being examined less testable. This will
give users the ability to review their coding practices and examine how
practical some of their choices are for testing. 

## Literature Review

TODO: Conduct literature review by describing relevant work related to the project and hence providing an overview of the state of the art in the area of the project. This section serves to contextualize the study within the existing body of literature, presenting a thorough review of relevant prior research and scholarly contributions. In clear and meaningful language, this section aims to demonstrate the problems, gaps, controversies, or unanswered questions that are associated with the current understanding of the topic. In addition, this section serves to highlight the current study's unique contribution to the field. By summarizing and critiquing existing works, this section provides a foundation for readers to appreciate the novelty and significance of the study in relation to the broader academic discourse. The "Literature Review" section further contributes to the `why is the project important?` question. The number of scholarly work included in the literature review may vary depending on the project.

## Methods

TODO: Discuss the methods of the project to be able to answer the `how` question (`how was this project completed?`). The methods section in an academic research outlines the specific procedures, techniques, and methodologies employed to conduct the study, offering a transparent and replicable framework for the research. It details the resources behind the work, in terms of, for example, the design of the algorithm and the experiment(s), data collection methods, applied software libraries, required tools, the types of statistical analyses and models which are applied to ensure the rigor and validity of the study. This section provides clarity for other researchers to understand and potentially replicate the study, contributing to the overall reliability and credibility of the research findings.

This project was created through the collaboration of the members of the `SEERS`
team, who communicated via Discord and Github. We split into subteams in order
to handle each element of the work, from drafting initial scripts and writing
the checks for patterns to integrating machine learning and consolidating the
scripts into a functional project usable from the command line. We each located
a selection of open-source Python projects that use `poetry` to handle
dependencies to test our work on. 

## Using the Artifact

Instructions are in the README of the `scripts` folder of the 
[SEERS repo](https://github.com/AstuteSource/SEERS).
Currently in the `Json-tidyData` branch, until PR #16 is merged.

## Results and Outcomes

TODO: Discuss the outcomes of your project in this section. Depending on the project type, the presented results and outcomes will vary. In some projects, you will be asked to present a theoretical analysis, and in others your experimental study and its results. In this section, you are also to demonstrate an enhanced version of your artifact by showing its capabilities and applications, in light of the evaluation metrics for assessing the artifact

---

## Exemplar Projects Discussions

The department's project descriptions can be found at [https://github.com/ReadyResearchers-2023-24/cmpsc-580-exemplar-projects](https://github.com/ReadyResearchers-2023-24/cmpsc-580-exemplar-projects)

## Schedule

The schedule for this work can be found at [https://github.com/CMPSC-580-Allegheny-College-Spring-2024/classDocs?tab=readme-ov-file#schedule](https://github.com/CMPSC-580-Allegheny-College-Spring-2024/classDocs?tab=readme-ov-file#schedule)
