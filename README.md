# Gratitude Project:

### Summary: A simple project about data I collected from writing down three things I am grateful for every morning over the last two years. The raw data was cleaned and categorized for simplicity and privacy purposes. The project contains a spreadsheet, basic SQL queries, and visualizations created on Python.

----------------------------------------------------------------------------------------------------

**SQL Queries**
----------------------------------------------------------------------------------------------------

* *Sample size of what the data contains:*

```SQL
SELECT DISTINCT gratitude_type, time_of_event 
FROM gratitude_data
```
<img width="225" alt="image" src="https://user-images.githubusercontent.com/126549337/231056732-16506b81-6f6d-4182-bfaa-c66c77d1b9e4.png">


* *How many total entries were written in my gratitude notebook? Group by year.* 
```SQL
SELECT COUNT(gratitude_type), time_of_event AS year
FROM gratitude_data
GROUP BY GROUPING SETS ((time_of_event), ())
ORDER BY time_of_event;
```
<img width="225" alt="image" src="https://user-images.githubusercontent.com/126549337/231054597-6d7a3b0e-9af2-4503-9538-9cf075902015.png">


* *What were the top 10 things I was most grateful for?*
```SQL
SELECT DISTINCT gratitude_type, COUNT(gratitude_type)
FROM gratitude_data
GROUP BY gratitude_type
ORDER BY count(gratitude_type) DESC
LIMIT 10
```
<img width="225" alt="image" src="https://user-images.githubusercontent.com/126549337/231058891-3f36ff04-1952-40ec-b684-13084fda65f2.png">

* *What about the 5 that I wrote the least about?*
```SQL
SELECT DISTINCT gratitude_type, COUNT(gratitude_type)
FROM gratitude_data
GROUP BY gratitude_type
ORDER BY count(gratitude_type) ASC
LIMIT 5
```
<img width="225" alt="image" src="https://user-images.githubusercontent.com/126549337/231059331-118c897a-fa24-40a5-b472-4a9e3ac5f410.png">

* *Finally, given that 2022 had the most entries, what was I most grateful about in 2022?*

```SQL
SELECT gratitude_type, COUNT(*) AS count
FROM gratitude_data
WHERE time_of_event = 2022
GROUP BY gratitude_type
ORDER BY COUNT(*) DESC
LIMIT 1;
```
<img width="225" alt="image" src="https://user-images.githubusercontent.com/126549337/231060325-99f7a9df-b5bd-48ac-bdff-a33f49525d56.png">

------------------------------------------------------------------------------------------------------------------------------------
## Conclusion:

From doing this project and taking data on myself for the last two years, I've learned: 

  1. I'm extremely grateful for my parents and family, as that has been consistent over the years and at a much larger scale than everything else I'm grateful for.
  
  2. I don't think much about my love life, material possessions, or the weather; which are all things that I've thought would make a bigger impact on my life. In terms of love life, maybe I've just been single for too long.
  
  3. Finally, sleep, sports, and being awake for a new day give me purpose and motivation to continue the fight of life. It's important to get good sleep, have a passion for something, and genuinenely be grateful for a new oppurtunity because it comes **every day**.
  
  
