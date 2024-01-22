+++
title = "Data Project Life Cycle"
date = 2024-01-08T10:24:35-06:00
draft = false
weight = 1
+++

A data analysis project typically starts with a specific business need or goal in mind. While each organization will tailor their project lifecycle to align with their own objectives and strategies, there are common stages across any data analysis workflow. The steps below will provide you with an idea of what that workflow and process entails in addition to questions you want to answer at each stage of the project.

## Understanding the Problem

The first step in a data analysis project revolves around understanding what, if any, problem you are trying to solve. Business or organizational stakeholders will usually provide clear objectives or key deliverables to help you better grasp what information they want. This will help with scoping a project and targeting specific data for analysis. Like any project, asking clarifying questions related to the problem is crucial during this stage so that it can help shape expectations, methods or techniques, and outcomes.

Below are the key questions you want to answer during this stage:
- What problem are you trying to solve or address?
- Who are the main stakeholders?
- What value will this bring to your organization?

## Collecting Data

Once you understand the problem and have clear objectives and goals, you can begin to collect data related to those criteria. Sometimes data is already provided that needs to be cleaned in preparation for exploration and model building. If data is not already provided, the goal is to use the questions and outline from the initial problem so that you can target relevant sources for your data.

Below are the key questions you want to answer during this stage:
- What are the relevant sources of data?
- How can you access that data?
- What are the guidelines / regulations around collecting the data

## Cleaning and Exploration

After data has been collected, it will most often need to be cleaned. Since collected data may often be improperly formatted, duplicated, have errors or typos, missing values, or simply incorrect, correcting these mistakes or “cleaning” the data is a very logical step. One of the most important reasons to clean data is so that you do not reach false or inaccurate conclusions when presenting it.

Exploring or investigating data is an important step in understanding it. Exploratory analysis may often be referenced as exploratory data analysis (EDA) which will be covered more in depth later in the course. Finding connections and similarities within your data often comes from exploration, which will help you with other methods that include cleaning, organization, and visualization.

Below are the key questions you want to answer during this stage:
- What issues need to be addressed?
- What are the anolomies within the data?
- What trends or movements arrise?
- What presumptions or premise can be formed?

## Building a Model

After the data has been organized, you can begin to build out your model(s) to uncover insights related to your primary objectives. The goal of this step is to supply stakeholders with actionable insights that will fit into the directives given at the inception of the project.

Below are the key questions you want to answer during this stage:
- What model or technique best works for your scenario?
- How complex does the model need to be?

## Model Validation

Is your model performing as expected? Are you gathering the data you want? These are questions you need to answer during this stage of the project. If you are not receiving the expected or desired outcomes from your chosen model or technique you may need to re-think the approach.

Below are the key questions you want to answer during this stage:
- Does the model need to be changed?
- Is the model accurate?
- Does it produce the desired outcomes?

## Visualization and Presentation

After collecting insights and deliverables you will need to present the data in a way that makes sense. Visualizing data makes it easier for everyone to understand but there are many strategies used to do so. Teams may choose to visualize their data with a simple chart, graphs, tables or create dashboards, bar charts, heat maps, pie charts, or histograms. There are numerous ways to visualize your data but knowing your target audience is important because it will help you convey your information or tell a story catered to them. Other key aspects of data visualization include:
- Accuracy: Presenting data without distorting it is important! Be precise with trends or movements within the data so that nothing is misinterpreted.
- Clarity: You want your visuals to provide a clear representation of your findings
- Tools: Any tool used to create your visualizations needs to be well thought out, as others may be using these same tools when interacting with the data
- Accessibility: Making sure your visualizations meet accessibility standards will accommodate a more diverse audience: things like text size, and color specifications for individuals who might be color-blind or have low vision.

Below are the key questions you want to answer during this stage:
- What data is the most relevant / significant from the analysis
    - How do you most effectively communicate that
- What presentation method will be used
- What are the next steps?

### Data Analysis Lifecycle Visual

{{< mermaid align="center" zoom="true" >}}
graph TD
    A[Understand the Problem] --> B[Collect Relevant Data]
    B --> C[Clean and Explore Data]
    C --> D[Build Analytical Models]
    D --> E[Evaluate Model Performance]
    E --> F[Visualize and Present Insights]
    F --> G[Recommend Actions]

    A-- What is the business problem? Who are stakeholders?-->B
    B-- What data sources are needed? How to access data?-->C
    C-- Fix data issues. Explore for trends and patterns.-->D
    D-- Select modeling techniques. Tune models.-->E 
    E-- Assess accuracy. Validate model outputs.-->F
    F-- Tailor visuals for audience. Focus on key insights.-->G
    G-- Drive business value through data-driven decisions.-->A
{{< /mermaid >}}