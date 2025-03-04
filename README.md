# Startup-Funding-Analysis

## Introduction
India has been very active in creating a healthy startup ecosystem, and the growth in the number of startups is increasing year on year. In fact, it is among the top five startup communities in the world.<br>
Being so startup friendly the country has attracted numerous numbers of investors, both national and international. Therefore a large amount of money is poured into the startup ecosystem. Also due to government support, technology boon and rise of tier-2 and tier-3 cities has boosted the startup ecosystem.<br>
Events like launch of Startup India initiative, US elections and the Indian banknote demonetization had a huge impact on the startup community. The dataset acquired via kaggle will help to analyze the startup trends from start of 2015 to start of 2020 and how above events have affected the trend.

## Data Source
Kaggle: [Indian Startup Funding](https://www.kaggle.com/sudalairajkumar/indian-startup-funding)

## Technologies used
* Programming Language: **T-SQL (SQL Server)**
* Software used: **Microsoft SQL Server Management Studio 18**
* Cloud: **Azure SQL Server**

## Scope of the Analysis
The followings are the scope for this case study:

* [The important investor of the Indian ecosystem](#Goal_Statement_1)
* [The pattern of fundings does start up generally gets in India](#Goal_Statement_2)
* [Various sectors or industries which are more favoured by investors for funding](#Goal_Statement_3)
* [How funding has changed overtime](#Goal_Statement_4)
* [Angel Investors of India](#Goal_Statement_5)
* [Max and Min investment out of all start-ups in India](#Goal_Statement_6)

## Dataset
**The dataset consisted of a CSV file:**

|Column|Description|
|---|---|
|Sr No|Unique Serial Nos.|
|Date|Date of investment|
|Startup Name|Name of the Startup Company|
|Industry Vertical|Group of companies and customers that are all interconnected around a specific niche|
|SubVertical|Nearly related to vertical but not quite vertical|
|City Location|City of Startup Company|
|Investor Name|Name of the Investor|
|Investement Type|Type of investment made by investor|
|Amount in USD|Amount invested by investors in USD|
|Remarks|Remarks given by the investors|

## T-SQL functionalities used
* SELECT, FROM, WHERE, GROUP BY & ORDER BY statements
* ALTER statement
* UPDATE statement
* ALTER TABLE statement
* Aggregate functions - SUM, COUNT, MAX, MIN etc.


## Methodology
* **Data Cleaning** ([Change datatypes & Data Cleaning](https://github.com/Rajiv-Nayan/Startup-Funding-Analysis/blob/main/data%20cleaninng.sql))
  * Update columns with correct datatypes 
  * Substitue for missing values in Startup Funding table
  * Drop Sr No & Remarks column as it unnecessary and contains high number of missing values
  * Check for all names of investors and rename duplicates if any ('undisclosed investor' to 'Undisclosed Investors')

## Goal_Statement_1
```
```
## Goal_Statement_2
```
```
## Goal_Statement_3
### Various sectors or industries which are more favoured by investors for funding<br>
``` JS
SELECT  Industry_Vertical, COUNT(*) as Frequency
FROM [dbo].[startup_funding]
GROUP BY Industry_Vertical 
ORDER BY Frequency DESC
Go
```
## Goal_Statement_4
### How funding has changed overtime

* **Monthwise**

``` JS
SELECT CAST(YEAR(Date_yyyy_mm_dd) as NVARCHAR)+'-'+CAST(MONTH(Date_yyyy_mm_dd) as NVARCHAR) AS [Monthwise],SUM(Amount_in_USD) AS Total_Amount 
FROM [dbo].[startup_funding] 
GROUP BY YEAR(Date_yyyy_mm_dd),MONTH(Date_yyyy_mm_dd) 
ORDER BY YEAR(Date_yyyy_mm_dd),MONTH(Date_yyyy_mm_dd)
GO
```
* **Yearwise**

``` JS
SELECT YEAR(Date_yyyy_mm_dd) AS [Yearwise],  SUM(Amount_in_USD) AS Total_Amount 
FROM [dbo].[startup_funding]
GROUP BY YEAR(Date_yyyy_mm_dd) 
ORDER BY YEAR(Date_yyyy_mm_dd)
GO
```

## Goal_Statement_5
```
```
## Goal_Statement_6
```
```

## Contributors

<table>
  <tr>
    <td align="center"><a href="https://www.linkedin.com/in/rajivnlink/"><img src="https://media-exp1.licdn.com/dms/image/C5103AQFTLW05sU_9Mg/profile-displayphoto-shrink_200_200/0/1581673573356?e=1626912000&v=beta&t=kxnGgp2mNebqqNi_JZ5iFiA6tuQiPNTR9YpZYHS3dAw" width="100px;" alt=""/><br /><sub><b>Rajiv Nayan</b></sub></a><br /></td>
    <td align="center"><a href="https://www.linkedin.com/in/arpita-patidar-82958712a/"><img src="https://media-exp1.licdn.com/dms/image/C5103AQFlVe7Ge33jTw/profile-displayphoto-shrink_200_200/0/1549727888584?e=1626912000&v=beta&t=UW16-nfbklu5n5R815IZwdK2si7XCgw8d15gGNV9qTQ" width="100px;" alt=""/><br /><sub><b>Arpita Patidar</b></sub></a><br /></td>
    <td align="center"><a href="https://www.linkedin.com/in/komal-dhyani/"><img src="https://media-exp1.licdn.com/dms/image/C4E03AQGp0wW5xh7fuA/profile-displayphoto-shrink_200_200/0/1619702786501?e=1626912000&v=beta&t=fPLm79yD22TPw3bYncTLmPiUaeYp9-JbjJkQ68mJc-M" width="100px;" alt=""/><br /><sub><b>Komal Dhyani</b></sub></a><br /></td>
    <td align="center"><a href="https://www.linkedin.com/in/komal-tirthani-114a81179/"><img src="https://media-exp1.licdn.com/dms/image/C4E03AQHAPY6Y4fKU0w/profile-displayphoto-shrink_200_200/0/1597092716698?e=1626912000&v=beta&t=hDNhogHYQZcciwiB6MFVAm-ELlmLSRJxx0lQwJxsnpY"  width="100px;" alt=""/><br /><sub><b>Komal Tirthani</b></sub></a><br /></td>
    <td align="center"><a href="https://www.linkedin.com/in/lalatendu-padhi-41b560195/"><img src="https://media-exp1.licdn.com/dms/image/C4D03AQEnOYjQaNB3rQ/profile-displayphoto-shrink_200_200/0/1605682139315?e=1626912000&v=beta&t=4p8INeqZ3XmvJKtMFnGw0ngbWzzijhQ_zbJYOriqFsA" width="100px;" alt=""/><br /><sub><b>Lalatendu Padhi</b></sub></a><br /></td>
    <td align="center"><a href="https://www.linkedin.com/in/yogesh-kumar-287137203/"><img src="https://avatars.githubusercontent.com/u/83998436?v=4" width="100px;" alt=""/><br /><sub><b>Yogesh Kumar</b></sub></a><br /></td>
  </tr>
 </table>

