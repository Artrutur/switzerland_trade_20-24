# 1. Intro


This repository is a starting point for further analysis of **Switzerland's trade over the last 5 available years: 2020-2024.**

The first approach is characterised by **drilling down through the structure of deficit-making countries to see if they share a certain pattern.**


## The Repository consists of:

### 1.1. Data Cleaning and Structuring

   The structure of the Data Source (UN Comtrade Database)
   
   The retrieval process
   
   Fact and dimensions tables
   
   Definitions
   
   The initial approach
   
   Cleaning and structuring process in SQL

### 1.2. Analysis of Deficit Drivers in Switzerland's trade

  Analysis was conducted in SQL IDE and exported as a Jupyter Notebook.
  
  The study answers questions:
  
    _How big is Switzerland's Trade?_
    
    _What is its structure in terms of trading partners and traded goods?_
    
    _Which countries have an advantage over Switzerland in bilateral trade, and how does it appear?_
    
    _What is the key driver making Switzerland only a buyer from the top deficit-making countries?_
    
    _How does a wider context of the World Trade explain these facts?_


### 1.3. Presentation

  After SQL analysis, the tables were secondarily reviewed in Power BI and confirmed the findings.
  
  After Power BI analysis, the pages with charts were exported as a PDF presentation.
  
  The presentation is an intuitive story built with key questions and charts to guide a reader through the analysis and its outcomes, giving explanations where needed.


# 2. Executive Summary

## 2.1. The „Big Picture” Context

  Switzerland is the undisputed leader in the global gold industry. According to UN data, the country controls **20% of the world’s gold trade**, trading an average of **$100 billion in imports and exports annually**.

  **Quality Standards:** Switzerland’s influence is cemented by its refining capacity. 3 out of the 7 global LBMA Referees (the organizations that set world quality standards) are Swiss-based.

  **The Business Model:** Switzerland imports raw gold (bars, bullion, or dore), purifies it to the highest standards, and sells it back to the global market.

## 2.2. Understanding the „Artificial” Deficit

  The trade deficit with certain nations is not a sign of economic weakness. Instead, it is a structural result of Switzerland’s role in the supply chain.

  **The „Gold 27” Impact:** When we look at countries where gold makes up **over 80% of their exports to Switzerland**, we find a group of 27 states. This group alone is responsible for a **$34.84 billion (54%) of deficit in trade. They alone supply 50% of all gold imported into Switzerland.**

  **Investment Focus:** This analysis focuses strictly on gold (HS 7108), excluding jewellery or recycled scrap, which makes the concentration even more striking.

## 2.3. Strategic Dependency
 
  Gold from these 27 countries alone accounts for **15% of Switzerland’s total imports**. To put this in perspective, this single commodity from this specific group of countries is **worth more than all goods imported from the USA**, Switzerland’s second-largest trading partner.

  To fulfil global demand for refined „Swiss-made” gold, the country has become strategically dependent on these 27 partners. **The deficit is simply the „price” of maintaining its position as the world’s gold refinery.**

