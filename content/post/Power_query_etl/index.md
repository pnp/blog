---
title: "Power Query ETL Capabilities"
date: 2022-07-15T08:40:00-04:00
author: "Ifeanyi Benny Iheagwara"
githubname: Bennykillua
# don't change
categories: ["Community post"]
# link to the thumbnail image for the post
images:
- images/power_query_etl.png
# don't change
tags: []
# don't change
type: "regular"
---

Garbage in, garbage out. A phrase conveys that incorrect or poor data quality will produce faulty output. ETL is necessary for this reason.

ETL means Extract, Transform, and Load. These three steps are the foundation of any data analytics and machine learning project, especially if you want promising findings. And I bet you do. The ETL process is also a form of a data pipeline, especially when integrating data from various data sources.

Microsoft Excel and Power BI have an ETL tool and many more tools in them. However, today we are focusing on this ETL tool: Power Query.

## What is ETL?

ETL is an acronym for extract, transform, and load.

- Extract: Data is extracted from legacy applications and various data sources.

- Transform: Data is cleaned and transformed into a more useable form. Duplicates are removed, new columns are formed or split, and much more transformation happens.

- Load: The data is loaded into the target database or analytic software.

## What is Power Query?

Power Query is a data preparation and transformation ETL engine that lets you connect to various data sources. Power Query is available in Microsoft Excel, Power BI, Power BI dataflow, Azure data factory wrangling dataflows, SQL Server Analysis Services, and much more. 

The good news is that Power Query is the same across all platforms, so if you learn it on one, you can use it on the others. Now that's simplicity and ease!

In Power Query,

- You can use the visual editor, interactive components, and ribbons to carry out over 350 data transformations like splitting, grouping, or removing duplicates.

- You could write out your transformation in Power Query's native language: the M language.

- You can also merge and combine data tables, or queries, as Power Query calls them.

- You can write Python or R scripts.

- You can carry out some AL insights like text analysis on your data using Azure Machine Learning and Cognitive Services.

![power_query.png](images/power_query.png)
