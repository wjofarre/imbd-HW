# imbd-HW
# -*- coding: utf-8 -*-
"""
Created on Tue Jun 16 22:26:43 2015

@author: liamofarrell
"""

# Pandas HW


# Basic

# 1
import pandas as pd
import matplotlib.pyplot as plt

movies = pd.read_csv('imdb_1000.csv')

# 2
movies.shape
movies.describe()

# 3
avg = movies['duration'].sum()/979
print avg

# 4
movies.duration.order()

# 5
movies.duration.plot(kind='hist', bins=20) # not sure exactly what the appropriate number of bins is but hopefully this will do

movies.duration.plot(kind='box') 

# intermmediate

#1 
movies.content_rating.value_counts()

# 2
a = movies.content_rating.value_counts()
a[['R','PG-13']].plot(kind='box', stacked=True)
movies.groupby('content_rating').count()

# 3-5 ?????

# 6 and 7
movies[movies.duration>120].count()
movies[movies.duration<120].count()
avg_2 = movies[movies.duration>120].sum()/436
avg_1 = movies[movies.duration<120].sum()/525

# 8
movies.plot(kind='scatter', x='duration', y='star_rating', alpha=.3)

movies[movies.genre].value_counts()
movies.groupby('genre').duration.agg('mean')
