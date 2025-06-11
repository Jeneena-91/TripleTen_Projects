# Video Game Sales Analysis 
## Project Overview
This data analysis project was conducted for Ice, an international online video game store. The goal is to identify marketing trends and patterns that determine a game’s success, enabling data-driven forecasting and strategic planning for future advertising campaigns — specifically for the year 2017.
## Project Structure
The project follows a structured, multi-phase approach:
- Data Initialization and Loading: Load the dataset and inspect the general structure.
- Data Preprocessing
       * Normalize column names.
       * Convert data types (e.g., Year_of_Release to integer).
       * Fill or appropriately handle missing values:
       * Median used for missing years.
       * "Unknown" assigned to missing ESRB ratings.
       *Missing critic/user scores left as-is to preserve data integrity.
- Exploratory Data Analysis (EDA)
       * Trends in game releases and platform life cycles.
       * Sales distribution by platform and genre.
       * Identify platforms gaining or losing popularity.
       * Correlation between user/critic reviews and sales.
- Regional User Profile Creation: Separate analysis for North America (NA), Europe (EU), and Japan (JP):
- Top 5 platforms by sales.
- Most popular genres.
- Impact of ESRB ratings on sales.
- Hypothesis Testing: Statistical testing using scipy.stats to validate:
      - Whether Xbox One and PC user ratings are statistically the same.
      - Whether Action and Sports genre user ratings are significantly different.
## Key Insights
- Game Release Trends:
      * Most games were released between 2006–2011, peaking in 2008–2009.
      * Older platforms such as PS2, NES, and GB have completely phased out.
      * Average platform life cycle: 5–6 years.
- Top Platforms by Sales
Based on recent trends (2013–2016):
     - PS4, XOne, and 3DS are leading platforms in terms of revenue.
     - Platforms with highest overall historical sales: PS2, X360, PS3, Wii, and DS.
- Genre Insights
      - Most profitable genres: Action, Shooter, Sports, Role-Playing.
      - High variance in sales within genres; niche genres often have dedicated audiences but lower average sales.
- Regional Profiles
      - North America (NA)
            * Top Platforms: PS4, XOne, X360, 3DS, PS3
            * Top Genres: Shooter, Action, Sports, Role-Playing
            * ESRB ratings have a notable influence on sales.
  - Europe (EU)
            * Top Platforms: PS4, XOne, PS3, PC, 3DS
            * Top Genres: Action, Sports, Shooter, Racing
            * Similar trends to NA with slight variance in platform preferences.
  - Japan (JP)
            * Top Platforms: 3DS, PS4, PSV, PS3, WiiU
            * Top Genres: Role-Playing, Action, Fighting, Shooter
            * Strong preference for Role-Playing games; ESRB ratings are less influential.

- Hypothesis Testing
    - Xbox One vs. PC Ratings
Null Hypothesis (H₀): The average user ratings are the same.
Result: Failed to reject H₀. Ratings are statistically similar.
   - Action vs. Sports Genres
Null Hypothesis (H₀): The average user ratings are the same.
Result: Rejected H₀. Action and Sports genres have significantly different ratings.
## Conclusion
Sales vary significantly by region, platform, and genre.Platform selection and game genre are key factors in success.
Regional preferences must be considered in marketing strategies (e.g., focus on shooter games in NA and role-playing games in JP).
The data supports strategic game development and advertising campaigns tailored by platform and geography.

## Tools Used
- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- SciPy for statistical testing
- Jupyter Notebook
