# Pandas Join Function - IMDB Top 1000 Movies

This project demonstrates how to use DataFrame.join() in Pandas using IMDB Top 1000 Movies dataset.

## Dataset Used
imdb-top-1000 (1).csv
Columns: Series_Title, Genre, IMDB_Rating

## What I Did?

### Step 1: Created Two Tables from One CSV

Table 1: movies - Movie and Genre
Table 2: ratings - Movie and Rating

import pandas as pd

df = pd.read_csv(r"C:\Users\SHWETA\Downloads\imdb-top-1000 (1).csv")

# Table 1: Movie aur Genre
movies = df[["Series_Title", "Genre"]].copy()

# Table 2: Movie aur Rating
ratings = df[["Series_Title", "IMDB_Rating"]].copy()

# Movie name ko index banayein
movies = movies.set_index("Series_Title")
ratings = ratings.set_index("Series_Title")

# Dono tables join karein
result = movies.join(ratings)
print(result.head())

### Step 2: Types of Join

# Left Join
result = movies.join(ratings, how='left')
print(result)

# Right Join
result = movies.join(ratings, how='right')
print(result)

# Inner Join
result = movies.join(ratings, how='inner')
print(result)

# Outer Join
result = movies.join(ratings, how='outer')
print(result)

## Output
Series_Title | Genre | IMDB_Rating
The Shawshank Redemption | Drama | 9.3
The Godfather | Crime | 9.2
The Dark Knight | Action | 9.0
Total: [1002 rows x 2 columns]

## Types of Join Used
- left: Left table ka sara data rakhega
- right: Right table ka sara data rakhega
- inner: Dono me jo common hai wahi dega
- outer: Dono table ka sara data dega

## Library Used
- pandas

## Author
SHWETA NIMKAR
