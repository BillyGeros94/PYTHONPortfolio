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

- **Project 1: FBREF**
   
   In this project, I set out to gather detailed Premier League statistics for the 2023-2024 season from the FBref website. I started by making a request to the URL where the data is 
   hosted. Using BeautifulSoup, a tool that helps parse HTML content, I was able to navigate the page and locate the table containing the stats I needed.

   My first task was to identify the correct table on the page and extract the column headers, which describe various statistics like player age, possession percentages, goals scored, 
   and so on. These headers became the columns in my DataFrame, which I set up using pandas—a Python library that's great for handling tabular data.

   Next, I needed to extract the actual data for each team. I carefully pulled the rows of data from the table, making sure to clean up any HTML formatting and convert the data into a 
   readable format. Each row represents a different team's statistics, and I added a column to label each row with the team’s name to keep everything organized.

   Once all the data was properly formatted and placed into the DataFrame, I saved it to a CSV file. This step was crucial because it allowed me to create a file that I can easily use 
   for further analysis or share with others. The final CSV file contains a structured summary of Premier League teams' performance metrics, neatly arranged for any subsequent review or 
   reporting. Overall, the project highlights my ability to scrape, process, and organize web data into a useful format.
  
- **Project 2: FIFA 21**

   In my project, I started by working with a dataset from FIFA 21 that includes various details about football players. The first task was to clean up the dataset by removing columns 
   that weren’t needed for my analysis. Specifically, I dropped columns like 'photoUrl', 'playerUrl', and 'Hits', which didn’t provide useful information for my purposes.

   Next, I focused on the 'Team & Contract' column, which contained both the team names and contract details in a single string. To make this data more manageable, I separated this 
   column into two new columns: 'Team' and 'Contract'. I did this by stripping any extra spaces and then splitting the information based on newline characters.

   After splitting the data, I removed the original 'Team & Contract' column along with the 'LongName' column, as they were no longer needed. This helped simplify the dataset by keeping 
   only the relevant columns.

   Another important step was to clean up the monetary values in the dataset. The 'Value', 'Wage', and 'Release Clause' columns contained amounts with various formats and symbols. I 
   standardized these values by removing currency symbols and converting them into a uniform format. For consistency, I converted all values to euros and used integer values to 
   represent the amounts.

   Following the cleaning of monetary values, I rearranged the columns to improve the organization of the dataset. I moved the 'Team' and 'Contract' columns to more logical positions 
   and placed the 'Name' column at the beginning to make it easier to identify players.

   Finally, I made some additional formatting adjustments. I updated the 'Contract' column to replace the '~ ' symbol with '- ', and adjusted the 'Positions' column to use commas 
   instead of spaces. These changes helped to make the dataset more consistent and easier to work with.

   Overall, these steps resulted in a cleaner, more organized dataset that is better suited for further analysis or reporting.
  
- **Project 3: Forbes Sports Teams**
  
   This project focuses on scraping Forbes data from Wikipedia on the most valuable sports teams across various major leagues and consolidating it into a single dataset. The project 
   uses pandas to read HTML tables from multiple Wikipedia pages and then performs a series of transformations to clean and standardize the data for further analysis. Here's a step-by- 
   step breakdown of the process:

   The script begins by scraping data from the Wikipedia page for the most valuable NBA clubs using pd.read_html(), which extracts the tables on the page into a list of DataFrames. The 
  second table (df_temp[1]) is selected, and unnecessary columns like 'Rank', 'Swing', 'Change', and 'Debt' are dropped. The column names are cleaned and renamed to a more standardized 
  format, such as 'Value', 'Revenue', and 'Operating Income'. Additional columns 'Sport' and 'League' are created to specify the sport and league for each team. The 'Country' column is 
  inserted, and a specific string replacement is performed on the 'Value' column to correct an outlier value format.

   Similarly, the script scrapes the data for football (soccer) clubs from another Wikipedia page. The first table (df_temp[0]) is selected, and columns like 'Rank 2023', 'Rank 2024', 
   and '% change on year' are removed. Column names are standardized, and the script adds columns for 'Sport' and 'League', with specific leagues such as La Liga, Premier League, etc. 
   Teams' territories (cities) are added, and the monetary values in the 'Value', 'Revenue', and 'Operating Income' columns are converted into a consistent format (billions and 
   millions) by string formatting and multiplying values accordingly.

   The same steps are repeated for NFL, MLB, and NHL teams. For NFL teams, unnecessary columns such as 'Rank' and 'Swing' are dropped, and the 'Value', 'Revenue', and 'Operating Income' 
   columns are renamed. Like with the NBA dataset, 'Sport' and 'League' columns are added, and the 'Country' column is inserted. A similar cleaning and transformation process is done 
   for MLB and NHL teams.

   Finally, the DataFrames for each sport are concatenated into one large DataFrame, combining NBA, football, NFL, MLB, and NHL teams into a single dataset. The index is reset to ensure 
   clean row numbering, and the consolidated DataFrame is saved to a CSV file named 'Sports Teams Valuations.csv'. This final dataset provides a comprehensive view of team valuations 
   across major sports leagues, which could be used for further financial or comparative analysis.

- **Project 4: Global Companies** 

    In this project, I performed an exploratory data analysis (EDA) on a dataset of the world’s largest companies, focusing on revenue, profits, assets, and market value. After loading 
    the data, I cleaned the financial columns, which included values with 'B' for billions and 'M' for millions, converting them into comparable numerical values. Once I ensured the 
    dataset was ready, I checked for any missing values and confirmed there were none.
  
    The analysis began by examining the distribution of revenue, profits, and market value. The histograms showed a skewed distribution, with a few large companies dominating the 
    financial landscape. Using a correlation heatmap, I found a strong correlation between market value and profits (0.76), but a weaker relationship between assets and other 
    variables, particularly market value (0.15). This suggests that assets do not strongly predict a company's market valuation, which is likely influenced by profitability and future 
    growth expectations.

    I then focused on the top 10 companies by revenue, profits, and market value. Companies like Saudi Aramco, Apple, and Microsoft were consistently at the top. A scatter plot of 
    revenue versus profits highlighted the positive correlation but also showed outliers with exceptionally high profits.

    Next, I explored the data by country. The United States and China dominated, both in terms of the number of companies and total revenue generated. I also calculated the profit 
    margin for each company, identifying the most efficient companies in turning revenue into profits. Additionally, I looked at the market value to revenue ratio, which revealed 
    companies highly valued by the market relative to their revenue, indicating strong investor confidence.

    Lastly, I analyzed the financial performance of companies by country, finding that the U.S. and China dominate in total revenue, while Saudi Arabia, largely due to Saudi Aramco, 
    leads in average market value. This project provided a comprehensive view of the financial power of the world’s largest companies, highlighting key players and trends across 
    different metrics.

- **Project 5: IBM**

    In this project, I focused on analyzing IBM's financial performance using Python, leveraging libraries like Pandas, Numpy, Matplotlib, and Seaborn for data manipulation, 
    visualization, and analysis. The data came from three primary financial statements: the balance sheet, cash flow statement, and income statement, all imported from CSV files.

    I started by cleaning and preparing the data, converting the fiscal dates to a uniform format to facilitate time series analysis. After checking for missing values, I filled the 
    gaps with zeros to ensure smooth calculations, ensuring the dataset was complete and ready for analysis.

    For the balance sheet, I calculated important liquidity ratios, including the current ratio, quick ratio, and cash ratio. These ratios help gauge IBM's ability to meet short-term 
    obligations, with the quick ratio providing a more conservative estimate by excluding inventory. I also looked at growth rates for assets, liabilities, and shareholder equity, 
    measuring how these critical financial items have changed year over year, offering insights into IBM’s expansion and leverage over time.

    Moving to the income statement, I calculated the gross profit margin and net profit margin. These profitability ratios reflect how efficiently IBM is managing costs and turning 
    revenue into profit. The gross profit margin indicates how well the company controls production costs, while the net profit margin shows overall profitability after all expenses are 
    accounted for.

    In the cash flow analysis, I explored IBM’s cash from operations, investments, and financing activities over time. I also calculated free cash flow by subtracting capital 
    expenditures from operating cash flow, a key measure that shows IBM’s ability to generate cash to fund growth, dividends, or repay debt. Visualizing cash flows over time helped 
    illustrate how IBM manages its day-to-day operations, capital investments, and financing needs.

    The visualizations played a crucial role in this analysis. I used line plots to track trends in IBM's financial data, showing changes in assets, liabilities, and shareholder equity 
    over time, along with liquidity ratios and cash flows. These visual representations allowed for clearer insights into the company's financial evolution. For example, seeing how 
    liquidity ratios like the current and quick ratios fluctuate over time helped assess how IBM's ability to meet short-term debts has evolved.

    In addition to trend analysis, I generated a correlation heatmap for the balance sheet items. This helped identify relationships between key financial metrics, such as the 
    correlation between liabilities and assets, or between equity and debt. The heatmap's color gradients made it easy to spot strong and weak correlations, adding a deeper layer of 
    analysis.

    In summary, this project offered a thorough examination of IBM's financial health through ratio calculations, trend analysis, and data visualization. By combining these elements, I 
    was able to analyze profitability, liquidity, capital structure, and cash flow dynamics, providing a holistic view of IBM's financial performance over time.

- **Project 6: Telecom Churn**

    In this project, I analyzed a dataset on customer churn from a telecommunications company. I started by loading the data and checking for missing values, which confirmed that the 
    dataset was clean. Next, I ensured appropriate data types for key columns, particularly converting TotalCharges to numeric and treating SeniorCitizen as a categorical variable.

    To explore customer behavior, I created various visualizations. A histogram with a kernel density estimate illustrated that most customers had short tenures, raising concerns about 
    retention. A count plot of churn revealed a significant portion of customers had left. A boxplot comparing monthly charges against churn showed that customers who churned typically 
    faced higher charges, suggesting a potential pricing issue. I also examined the relationship between tenure and monthly charges with a scatter plot, highlighting that higher charges 
    correlated with shorter tenures.

    I explored the impact of internet service types on tenure and churn with a boxplot, indicating that fiber optic customers tended to have longer tenures. A heatmap of the correlation 
    matrix showed a negative correlation between tenure and monthly charges, suggesting long-term customers might benefit from lower prices.

    To segment customers, I categorized them based on tenure and monthly charges. Count plots revealed distinct churn rates across these groups, indicating low-charging customers were 
    less likely to churn while high-charging customers faced higher risks. Finally, analyzing churn by internet service type showed DSL users were less likely to leave compared to those 
    on fiber optic. Overall, this project provided valuable insights into customer behavior, guiding strategies for improving retention in the telecommunications sector.
    
## Each project contains the following:

- **.ipynb:** The main notebook file with code, analysis, and visualizations.

If you have any questions or feedback, feel free to reach out!
