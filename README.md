# P1_FIFA_MoneyBall

#### Objective

The objective of this project is to build a machine learinng model that predicts the market value of a FIFA player.
Moreover, this project also has as a goal to answer three predefined questions about our data set.

#### Questions & Hypothesis 

1. What's the distribution of wage vs value of the top players (overall rating greater than 80)?
2. What are the emerging talents? Top 10 players under 21, ranked by potential.
3. What's the distribution of height & weight vs stamina? 

#### Data Set

Data used from the kaggle Complete Player data set.

This data set includes information like players name, age, nationality, club, overall rating, scores in different skills, positions, body metrics, etc.

#### Data Processing and Data Cleaning

I have decided to clean the following columns, based on the three questions and the data that I think I will need to build my mode:

- Monetary columns: wage, value and release clause. I have removed € symbol, K and M characteres and converted the data into floats with the correct scale (thousands, million, etc).
- Body metrics columns: weight and hegiht. I have converted pounds to quilos, inches to cm, and removed unecessary indicators (lbs, ') 

For my model I have created a new data frame that includes the following variables:
 - Overall rating, potential, value, wage, height, weight, age, skill, mentality, passing, physical, shooting, goalkeeping.
I have performed data transformation, checked correlations and fit my model based on this variables only.

Questions answered

1. What's the distribution of wage vs value of the top players (overall rating greater than 80)?


![Plot1](newplot.png)


Based on the visualization, L.Messi is the most overpaid player according to his value and K.Mbappe is the most underpaid player according to his value.

4- Summary of the results
5- Sources (link to the source of the data https://www.kaggle.com/ekrembayar/fifa-21-complete-player-dataset)

Libraries

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
import scipy.stats as stats
import os
import plotly.express as px
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import r2_score, mean_squared_error, mean_absolute_error

