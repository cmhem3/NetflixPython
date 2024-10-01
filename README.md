# NetflixPython
DataCamp Project: Investing Netflix Movies with Python

![image](https://github.com/user-attachments/assets/37402b9f-cb8f-4ee6-beea-887b6ec2cc09)

**Netflix!** What started in 1997 as a DVD rental service has since exploded into one of the largest entertainment and media companies.

Given the large number of movies and series available on the platform, it is a perfect opportunity to flex your exploratory data analysis skills and dive into the entertainment industry.

You work for a production company that specializes in nostalgic styles. You want to do some research on movies released in the 1990's. You'll delve into Netflix data and perform exploratory data analysis to better understand this awesome movie decade!

You have been supplied with the dataset netflix_data.csv, along with the following table detailing the column names and descriptions. Feel free to experiment further after submitting!

![image](https://github.com/user-attachments/assets/0dc294e4-b618-484d-aab0-d9fde7c22116)

**Getting Started: Inspect the Data**

```python
# Importing pandas and matplotlib
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

# Read in the Netflix CSV as a DataFrame
netflix_df = pd.read_csv("netflix_data.csv")
print(netflix_df.head(10))
```
![image](https://github.com/user-attachments/assets/53e6b633-506a-4e55-bd30-0e5b22ca3267)

### Questions
Perform exploratory data analysis on the netflix_data.csv data to understand more about movies from the 1990s decade.
- What was the most frequent movie duration in the 1990s?  Save an approximate answer as an integer called duration (use 1990 as the decade's start year).
- A movie is considered short if it is less than 90 minutes. Count the number of short action movies released in the 1990s and save this integer as short_movie_count.

```python
#Step 1: movies after 1990
netflix_1990 = netflix_df[netflix_df["release_year"] > 1990]
print(netflix_1990)

#Step 2: common duration
duration = netflix_df["duration"].mode()[0]
print(duration)

#Step 3: short duration action movies
# Your current code adjusted with np.sum to get an integer count
short_movie_count = np.sum(
    np.logical_and(
        np.logical_and(netflix_df['duration'] < 90, netflix_df['genre'] == "Action"),
        np.logical_and(netflix_df['release_year'] >= 1990, netflix_df['release_year'] <= 1999)
    )
)
print(short_movie_count)
```
![image](https://github.com/user-attachments/assets/1caf73d9-96d5-4b15-88f9-184974b5c7a6)




