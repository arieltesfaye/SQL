The Mission
**any difficulties**
Limited Sample Size:  While 1000 people is a good start, it might not be representative of the entire population, especially considering you only have 3 regions (Australia, UK, and AS - assuming AS is Asia). This could lead to biased results if you try to generalize the findings to a larger population.
Non-Binary Grouping: Grouping non-binary individuals into a single category might hide valuable insights about their specific social media habits or demographics.
Debt & Homeownership: There seems to be a slight discrepancy. With 164 people in debt, there are 166 homeowners, suggesting some homeowners might also be in debt. More information on mortgage status or debt type could clarify this.

1 interesting thing
The females and non-binary genders are on average 66% more users of social media

simple SQL queries would you use to play with the data.
Debt vs. Homeownership:

SELECT (CASE WHEN debt = 1 THEN 'In Debt' ELSE 'No Debt' END) AS debt_status, COUNT(*) AS user_count
FROM your_data_table
GROUP BY debt_status
ORDER BY user_count DESC;



Find 2 cool facts hidden within the data (e.g., most popular interests)
Software engineers seem to be more drawn to sports compared to lifestyle or travel. This could be because sports often involve data analysis (e.g., player stats) or a strategic mindset that aligns with software development.
Marketing managers appear to be fairly evenly distributed across all three interests (sports, lifestyle, travel). This might indicate their diverse interests and need to stay updated on various trends for marketing purposes.

Data Fun (20 pts):

Use simple SQL queries to play with the data.Find 2 cool facts hidden within the data (e.g., most popular interests).
Use basic SQL queries like (COUNT, AVG, and SUM) to understand more about the data you have.

SELECT interests, profession, COUNT(*) AS user_count
FROM your_data_table
WHERE profession IN ('Software Engineer', 'Marketing Manager')
GROUP BY interests, profession
ORDER BY user_count DESC;

SELECT location, AVG(debt) AS avg_debt
FROM your_data_table
GROUP BY location
ORDER BY avg_debt DESC;

Ask Away (30 pts):

Formulate 2 questions about the data (e.g., what are popular shows in different countries?).
Write basic SQL queries (WHERE, ORDER BY) to find answers.
Share what you learned from the answers.

Question: Are there any popular shows that stand out in specific countries?
SELECT country, show_name, COUNT(*) AS view_count
FROM your_data_table
GROUP BY country, show_name
ORDER BY view_count DESC;

Expected Outcome:

This query groups viewership data by country and show name, potentially revealing shows with high viewership in specific regions. Examining the top entries for each country can highlight popular shows in different locations.

Question 2: Age and Social Media Usage

Question: Does social media usage differ between age groups?
Query 1 (Assuming an "age_group" column):
SELECT age_group, AVG(social_media_hours) AS avg_hours
FROM your_data_table
GROUP BY age_group
ORDER BY age_group;

Query 2 (Assuming separate age columns):

SELECT 
  CASE WHEN age BETWEEN 18 AND 24 THEN '18-24'
       WHEN age BETWEEN 25 AND 34 THEN '25-34'
       ELSE '35+'
  END AS age_group,
  AVG(social_media_hours) AS avg_hours
FROM your_data_table
GROUP BY age_group
ORDER BY age_group;

Expected Outcome:

These queries calculate the average social media usage time for each age group, revealing potential trends in social media engagement across different age demographics.
