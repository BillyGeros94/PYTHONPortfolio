# Python Portfolio

Overview

  Welcome to my Python for Data Analysis Portfolio! This repository showcases various projects that highlight my skills in using Python for data manipulation, exploration, visualization, and analysis. The projects here demonstrate a wide range of techniques, tools, and libraries commonly used in data analysis workflows, with an emphasis on real-world datasets and insightful outcomes.

  Throughout the projects in this portfolio, I utilize several powerful Python libraries for data analysis:

  - **Pandas:** For data manipulation, cleaning, and wrangling.
  
  - **NumPy:** For numerical computing and efficient data handling.
  
  - **Matplotlib & Seaborn:** For data visualization and exploratory data analysis (EDA).

  - **Jupyter Notebooks:** For interactive data exploration and visualization.
    
Each project in this repository showcases these libraries in action, addressing different challenges in data analysis and producing meaningful insights.

Projects Overview

- **Project 1: FBREF Scraper**
   
    In this project, I created a web scraping tool to extract Premier League statistics from the 2023–2024 season directly from the FBRef website. Using Python libraries such as requests, BeautifulSoup, and Pandas, I automated the process of pulling raw HTML data, cleaning and organizing it, and ultimately converting it into a structured CSV file for further analysis.

    The process began by sending an HTTP request to the specified URL of the Premier League stats page, using the requests.get() function to retrieve the page content. Once the content was obtained, the BeautifulSoup library was used to parse and clean the HTML structure. The .prettify() method was applied to make the HTML easier to read and work with, after which I navigated through the HTML tags to find the relevant data table.

    The core dataset is located within a specific HTML table on the webpage, which I accessed using the find_all('table') method to select the third table from the page. The headers for the data columns, such as "Squad," "Goals," "Assists," "xG," and others, were extracted from the table's th elements, and I cleaned them up using a list comprehension to remove any unnecessary whitespace around the text.

    The data rows, which contained the team statistics, were stored within the td elements of the table's rows (tr). I then looped over each row, extracting and organizing the relevant data into a Pandas DataFrame. This DataFrame was initialized with the headers and filled row by row with the corresponding values from the table data. Additionally, I inserted the team names (the "Squad" column) as the first column to ensure that the data could be clearly referenced by team.

    Once the DataFrame was fully populated, it consisted of 20 rows and 32 columns, where each row represented a Premier League club, and each column contained statistical metrics for the 2023–2024 season. These metrics included goals scored, assists, expected goals (xG), possession percentage, and others, allowing for detailed team performance analysis.

    Finally, I saved the structured data into a CSV file using the df.to_csv() method, making the data easily accessible for further analysis or visualization. The resulting file, named FBREF_Scraper.csv, contains all the scraped statistics and can be used for advanced data analysis such as comparing team performances, visualizing trends, or even feeding the data into a machine learning model for predictive analysis.

    This project demonstrates the power of web scraping combined with Python's data analysis tools. It automates the otherwise manual process of collecting data, making it highly scalable and efficient. The resulting dataset provides a rich resource for understanding Premier League team performance during the 2023–2024 season.

- **Project 2: FIFA 21 Data Cleaning**

    In this project, a FIFA 21 dataset is cleaned and transformed to make it more suitable for analysis. The dataset is first imported using pandas, and unnecessary columns such as 'photoUrl', 'playerUrl', and 'Hits' are removed using the drop() function. Afterward, the 'Team & Contract' column, which contains two separate pieces of information (team name and contract details), is split into two new columns, 'Team' and 'Contract', using the str.split() method. The original 'Team & Contract' column, along with another irrelevant column 'LongName', is then dropped to streamline the dataset.

    Further transformations are performed on key financial columns like 'Value', 'Wage', and 'Release Clause'. Each of these columns contains monetary data, and the currency symbols (such as '€') and unit abbreviations ('M' for million, 'K' for thousand) are stripped using string methods like str.strip(). After cleaning the data, the values are converted into numerical types. The 'Value' and 'Release Clause' are multiplied by one million, and 'Wage' is multiplied by one thousand to bring all monetary values to a consistent format in euros, which will facilitate accurate numerical analysis later on.

    Next, columns are rearranged to enhance readability and logical flow. Specifically, the 'Team', 'Contract', and 'Name' columns are repositioned within the dataset. This is done by first finding their current index positions, then moving them to more appropriate locations. For example, 'Team' is moved to the 6th position, 'Contract' to the 7th, and 'Name' is placed at the very beginning of the dataset. This reordering makes it easier to focus on key player attributes when reviewing the dataset.

    Finally, string replacements are applied to clean up specific columns. The Contract column is refined by replacing the tilde symbol ('~') with a dash ('-'), standardizing how contract durations are represented. Additionally, spaces between positions in the Positions column are replaced with commas to separate multiple positions. This final transformation ensures that each player’s possible positions are clearly delineated, making it easier to work with the data in any subsequent analysis or modeling efforts. Overall, this project focuses on preparing the dataset for further exploration by cleaning, formatting, and organizing the data.
  
- **Project 3: Web Scraping And Data Cleaning**
  
   This project focuses on scraping Forbes data from Wikipedia on the most valuable sports teams across various major leagues and consolidating it into a single dataset. The project uses pandas to read HTML tables from multiple Wikipedia pages and then performs a series of transformations to clean and standardize the data for further analysis. Here's a step-by-step breakdown of the process:

   The script begins by scraping data from the Wikipedia page for the most valuable NBA clubs using pd.read_html(), which extracts the tables on the page into a list of DataFrames. The second table (df_temp[1]) is selected, and unnecessary columns like 'Rank', 'Swing', 'Change', and 'Debt' are dropped. The column names are cleaned and renamed to a more standardized format, such as 'Value', 'Revenue', and 'Operating Income'. Additional columns 'Sport' and 'League' are created to specify the sport and league for each team. The 'Country' column is inserted, and a specific string replacement is performed on the 'Value' column to correct an outlier value format.

   Similarly, the script scrapes the data for football (soccer) clubs from another Wikipedia page. The first table (df_temp[0]) is selected, and columns like 'Rank 2023', 'Rank 2024', and '% change on year' are removed. Column names are standardized, and the script adds columns for 'Sport' and 'League', with specific leagues such as La Liga, Premier League, etc. Teams' territories (cities) are added, and the monetary values in the 'Value', 'Revenue', and 'Operating Income' columns are converted into a consistent format (billions and millions) by string formatting and multiplying values accordingly.

   The same steps are repeated for NFL, MLB, and NHL teams. For NFL teams, unnecessary columns such as 'Rank' and 'Swing' are dropped, and the 'Value', 'Revenue', and 'Operating Income' columns are renamed. Like with the NBA dataset, 'Sport' and 'League' columns are added, and the 'Country' column is inserted. A similar cleaning and transformation process is done for MLB and NHL teams.

   Finally, the DataFrames for each sport are concatenated into one large DataFrame, combining NBA, football, NFL, MLB, and NHL teams into a single dataset. The index is reset to ensure clean row numbering, and the consolidated DataFrame is saved to a CSV file named 'Sports Teams Valuations.csv'. This final dataset provides a comprehensive view of team valuations across major sports leagues, which could be used for further financial or comparative analysis.

- **Project 4:** Cooking up something, don’t go far!

- **Project 5:** Heating up, something’s coming!

- **Project 6:** In the works, get ready!
    
## Each project contains the following:

- **.ipynb:** The main notebook file with code, analysis, and visualizations.

If you have any questions or feedback, feel free to reach out!
