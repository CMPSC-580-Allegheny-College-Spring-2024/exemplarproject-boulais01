[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/Y4rZMh1t)

# Junior Seminar (CMPSC 580) Exemplar Project Repository

## Semester: Spring 2024

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

The previously mentioned (`Zhu2021`)[https://github.com/ReadyResearchers-2023-24/cmpsc-580-exemplar-projects/blob/main/software-engineering/paper-pdfs/Zhu2021.pdf]
work is a tool similar to the one worked on here, although it is only for Java,
while the SEERS tool is for Python. An important central question of this work
is if only improving the test cases for a project is enough, and examining the
improvement of source code to be more testable as well. This is done by an
analysis of the patterns found in code that can increase complex compared to
the mutation scores, hence the SEERS performing something similar with Python.

This is built off of work such as that of 
(`Spadini2018`)[https://github.com/ReadyResearchers-2023-24/cmpsc-580-exemplar-projects/blob/main/software-engineering/paper-pdfs/Spadini2018.pdf].
This research concerns itself with the relationship of 'test smells'(similar
to the patterns/antipatterns discussed in other works, being defined here as
sub-optimal design choices) and of code quality. This is done by running an
assortment of tests on the code, and analyzing how well it accepts a wide
variety of situations.

The above is related closely to the work of
(`Virginio2019`)[https://github.com/ReadyResearchers-2023-24/cmpsc-580-exemplar-projects/blob/main/software-engineering/paper-pdfs/Virginio2019.pdf].
This introduces a tool for detecting test smells and explores the relationship
between those test smells and test coverage. If code is not testable, it is
likely to be detected by the test smells, and will result in a lower coverage.
As such, using test smell detection programs can help the programmer find the
code most in need of optimization.

The above all deal with Java - but the work of
(`Wang2021`)[https://github.com/ReadyResearchers-2023-24/cmpsc-580-exemplar-projects/blob/main/software-engineering/paper-pdfs/Wang2021.pdf]
is a Python tool for detecting code smells. This is meant to extend the above
work beyond Java, similar to the way the SEERS tool is attempting to expand the
work of `Zhu2021`. This gives the identification of some test smells which aided
in the construction of the SEERS tool.

In regards to the mutation analysis aspect, there is the analysis presented in
(`Jia2011`)[https://github.com/ReadyResearchers-2023-24/cmpsc-580-exemplar-projects/blob/main/software-engineering/paper-pdfs/Jia2011.pdf].
This research shows the development of effective mutation tools as well as the
assorted methods and trends. This helps build towards the mutation analysis
aspect of the SEERS tool, and provides evidence that the mutation tools are
relatively reliable.

## Methods

This project was created through the collaboration of the members of the `SEERS`
team, who communicated via Discord and Github. We split into subteams in order
to handle each element of the work, from drafting initial scripts and writing
the checks for patterns to integrating machine learning and consolidating the
scripts into a functional project usable from the command line. We each located
a selection of open-source Python projects that use `poetry` to handle
dependencies to test our work on. Our code and documentation is viewable at
our [Github repository](https://github.com/AstuteSource/SEERS), which includes
our progress reports.

## Using the Artifact

Instructions are in the README of the 
[SEERS repo](https://github.com/AstuteSource/SEERS),
containing the tool `COMMA`.

## Results and Outcomes

Discuss the outcomes of your project in this section. Depending on the project type, the presented results and outcomes will vary. In some projects, you will be asked to present a theoretical analysis, and in others your experimental study and its results. In this section, you are also to demonstrate an enhanced version of your artifact by showing its capabilities and applications, in light of the evaluation metrics for assessing the artifact

```
{
    "file": "/Users/jaclynpham/AstuteSource/SEERS/scripts/analyzer/demo/lazytracker/lazytracker/lazytracker.py",
    "pattern": {
      "lineno": 29,
      "coloffset": 4,
      "linematch": "def add_files(self, filepaths: List[str], chunk_num_blocks=128):",
      "context": "        files_to_check = sorted(files_to_check)\n\n        self.add_files(files_to_check, chunk_num_blocks)\n\n    def add_files(self, filepaths: List[str], chunk_num_blocks=128):\n        \"\"\"Include hash of files\n\n        Args:\n            filepaths (List[str]): List of paths to files\n            chunk_num_blocks (int, optional): How many chunks to read at once. Defaults to 128.",
      "min": 1,
      "max": 10,
      "pattern": ".//FunctionDef",
      "check_id": "F001",
      "check_name": "all-function-definition",
      "description": "Ensure the presence of function definitions in the codebase."
    },
    "function_name": "add_files",
    "function_scope": "29-42",
    "mutants": [
      {
        "name": "Mutant #6",
        "line": 29,
        "description": [
          "    def add_files(self, filepaths: List[str], chunk_num_blocks=128):"
        ],
        "failure": [
          {
            "inner": "--- lazytracker/lazytracker.py\n+++ lazytracker/lazytracker.py\n@@ -26,7 +26,7 @@\n \n         self.add_files(files_to_check, chunk_num_blocks)\n \n-    def add_files(self, filepaths: List[str], chunk_num_blocks=128):\n+    def add_files(self, filepaths: List[str], chunk_num_blocks=129):\n         \"\"\"Include hash of files\n \n         Args:\n",
            "type": "failure",
            "message": "bad_survived"
          }
        ]
      },
      {
        "name": "Mutant #7",
        "line": 38,
        "description": [
          "                with open(p, \"rb\") as f:"
        ],
        "failure": []
      },
      {
        "name": "Mutant #8",
        "line": 39,
        "description": [
          "                    while chunk := f.read(chunk_num_blocks * self._hasher.block_size):"
        ],
        "failure": []
      }
    ],
    "mutation_score": 0.3333333333333333
  },
```

---

## Exemplar Projects Discussions

The department's project descriptions can be found at [https://github.com/ReadyResearchers-2023-24/cmpsc-580-exemplar-projects](https://github.com/ReadyResearchers-2023-24/cmpsc-580-exemplar-projects)

## Schedule

The schedule for this work can be found at [https://github.com/CMPSC-580-Allegheny-College-Spring-2024/classDocs?tab=readme-ov-file#schedule](https://github.com/CMPSC-580-Allegheny-College-Spring-2024/classDocs?tab=readme-ov-file#schedule)
