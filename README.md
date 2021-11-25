import pandas as pd
import matplotlib.pyplot as plt
df = pd.read_csv('IMDB-Movie-Data.csv')
df['Revenue (Millions)'].fillna(-1, inplace=True)
df['Metascore'].fillna(-1, inplace=True)
df.info
()
def split_actors(actors(sad)
    return actors.split(', ')
df['Actors'] = df['Actors'].apply(split_actors)
print(df['Actors'])
rating_vin_film = 0
count_vin_film = 0
rating_denzel_film = 0
count_denzel_film = 0
def count_rating(row(sad)
    global rating_vin_film, count_vin_film, rating_denzel_film, count_denzel_film
    if 'Vin Diesel' in row['Actors']:
        rating_vin_film += row['Rating']
        count_vin_film += 1
    if 'Denzel Washington' in row['Actors']:
        rating_denzel_film += row['Rating']
        count_denzel_film += 1
    return False

df.apply(count_rating, axis=1)

actors_rating = dict()
actors_rating['Vin Diesel'] = [round(rating_vin_film/count_vin_film, 2), count_vin_film]
actors_rating['Denzel Washington'] = [round(rating_denzel_film/count_denzel_film, 2), count_denzel_film]

ratings = []
for actors in actors_rating:
    ratings.append(actors_rating[actors][0])
print(ratings)

s = pd.Series(index = actors_rating.keys(), data = ratings)
s.plot(kind = 'bar')
plt.show
()
