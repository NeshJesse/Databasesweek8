# Databasesweek8
My Databases week 8 assignment submission

I find it interesting that a csv file that small can hold that huge amount of data
### Data Fun (20 pts)

**1. Discover Cool Facts:**
   - **Fact 1: Most Active Director**
     - Query to find the director who directed the most shows:
       ```sql
       SELECT director, COUNT(*) AS show_count
       FROM netflix_shows
       GROUP BY director
       ORDER BY show_count DESC
       LIMIT 1;
       ```
       - This will reveal the most prolific director on Netflix.
   
   - **Fact 2: Country with Most Content**
     - Query to find which country has the most content:
       ```sql
       SELECT country, COUNT(*) AS show_count
       FROM netflix_shows
       GROUP BY country
       ORDER BY show_count DESC
       LIMIT 1;
       ```
       - This will show which country contributes the most content to Netflix's library.

**2. Use Basic Queries to Understand the Data:**
   - **Average Duration of Shows:**
     - Query to find the average duration of shows:
       ```sql
       SELECT AVG(duration) AS average_duration
       FROM netflix_shows;
       ```
   
   - **Total Number of Shows Released Each Year:**
     - Query to count the number of shows released each year:
       ```sql
       SELECT release_year, COUNT(*) AS total_shows
       FROM netflix_shows
       GROUP BY release_year
       ORDER BY release_year;
       ```

### Ask Away (30 pts)

**Formulate Questions and Find Answers:**

**Question 1: What are the popular genres in different countries?**
   - Query to find popular genres by country:
     ```sql
     SELECT country, genre, COUNT(*) AS genre_count
     FROM netflix_shows
     GROUP BY country, genre
     ORDER BY country, genre_count DESC;
     ```
   - **Learning:** This will help understand which genres are most popular in different regions, providing insights into regional preferences.

**Question 2: What are the highest-rated shows released in the last 5 years?**
   - Query to find top-rated shows from the last 5 years:
     ```sql
     SELECT title, rating, release_year
     FROM netflix_shows
     WHERE release_year >= YEAR(CURDATE()) - 5
     ORDER BY rating DESC
     LIMIT 10;
     ```
   - **Learning:** This will highlight the best-rated shows in recent years, indicating current trends and quality content.

### Showtime! (20 pts)

**Create Charts to Visualize Findings:**

1. **Bar Chart: Number of Shows by Year**
   - Shows the total number of shows released each year, revealing trends over time.
   
2. **Pie Chart: Distribution of Content by Country**
   - Illustrates the share of content contributed by different countries.

3. **Bar Chart: Top Genres by Country**
   - Displays the most popular genres in various countries, highlighting regional preferences.

### Presentation Power (20 pts)

**Prepare a Pitch Deck Presentation:**

**1. Introduction:**
   - Briefly introduce the dataset and outline your goals.
     - Example: "We analyzed a dataset of 8.8k Netflix shows to uncover hidden trends and insights, focusing on directors, countries, genres, and ratings."

**2. Data Import Process:**
   - Explain the process of importing the CSV file into your SQL environment.
     - Example: "We imported the CSV file containing Netflix show data into our SQL database for detailed analysis."

**3. Cool Facts:**
   - Share the two cool facts discovered:
     - Most active director: "Our analysis revealed that the most active director on Netflix is [Director Name], with [X] shows."
     - Country with the most content: "We found that [Country Name] contributes the most content to Netflix, with [Y] shows."

**4. Questions and Learnings:**
   - Discuss the formulated questions, the SQL queries used, and the insights gained.
     - Example: "We explored popular genres by country and identified that [Genre] is highly popular in [Country]. Additionally, our query on highest-rated shows in the last 5 years revealed that [Show Title] has received top ratings."

**5. Charts:**
   - Present and explain the charts:
     - Number of Shows by Year: "This bar chart illustrates the number of shows released each year, showing a trend of increasing content production."
     - Distribution of Content by Country: "Our pie chart shows that [Country] leads in content contribution, followed by [Other Countries]."
     - Top Genres by Country: "This bar chart highlights the most popular genres in different countries, with [Genre] being predominant in [Country]."

**6. Summary:**
   - Conclude with a brief summary of the project:
     - Example: "Through our analysis, we gained valuable insights into Netflix's content distribution, popular genres, and top-rated shows, which can inform content strategy and regional preferences."

By following this structured approach, you'll effectively showcase your analysis and findings in a comprehensive and engaging manner.
