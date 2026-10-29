# Smartphone Behaviour and Student Stress: A CRISP-DM Analysis of StudentLife
**DBMS71008 Data Analytics – CA2 CRISP-DM Analytics Project** <br>

![](images/Data%20Analytics%20DBMS71008.png)

![Python](https://img.shields.io/badge/Python-3.11-3776AB?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)

![Module](https://img.shields.io/badge/Module-DBMS71008-5B6CE1)
![Methodology](https://img.shields.io/badge/Methodology-CRISP--DM-5B6CE1)
![Phase](https://img.shields.io/badge/Phase-Business_Understanding-yellow)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)]()


## Problem and Question

**Context:** University students frequently report high stress levels, with heavy smartphone use and poor sleep commonly suggested as contributing factors. However, wellbeing services usually rely on students self-reporting difficulties. Passive smartphone sensing offers a way to observe daily behaviour continuously. This project uses the StudentLife dataset (Weichen, 2020) to investigate whether such behavioural signals are associated with students self-reported stress.

**Intended User:** The intended audience of this analytics project is university support services. The findings should allow staff, such as counsellors, to identify patterns associated with elevated stress, which can inform outreach.

**Question:** To what extent can passively sensed smartphone usage and sleep behaviour distinguish days on which university students report elevated stress from days on which they do not?

**Unit of analysis:** One student on one calendar day.

**Candidate Method:** The objective is to distinguish high-stress days from other days, which is a binary classification task.


## Objectives

*Practical Objective:* Help support services understand which daily behaviours are associated with elevated stress, to inform when proative support is offered.

*Analytics Objective:* Build a binary classifier that distinguishes high stress from other student days using phone use, sleep, and activity features.

## Potential Risks

| Risk | Why it matters | Mitigation |
| --- | --- | --- |
Sparse stress responses | Students did not answer everyday, meaning fewer labelled rows | Drop or flag students with too few responses |
| Missing sensor data | Phone off, uncharged, or not carried | Exclude days with too little data |
| Ethics and Privacy | Behavioural and mental health data about real people | Frame the findings as patterns, not individual labels |


## Dataset

| Detail | Info |
| --- | --- |
| Name | StudentLife |
| Publisher | dart_weichen |
| Link | https://www.kaggle.com/datasets/dartweichen/student-life/data |

## Repository Structure
    README.md
    notebooks/   – main CRISP-DM notebook
    data/        – raw/ (untouched) and processed/ (prepared outputs)
    figures/     – charts used in the paper
    paper/       – conference paper source and PDF
    references/  – reference list / source notes