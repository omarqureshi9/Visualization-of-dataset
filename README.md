# Visualization-of-dataset
This is the visualization of the following Kaggle dataset: https://www.kaggle.com/datasets/konradb/gun-deaths-in-the-us-1968-2021

#As a first step, I merged all csv files into one master file and named it master.csv

#Importing required libraries
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
import numpy as np

#Importing dataset to python
dataset=pd.read_csv("Master.csv")

#Making pivot table
table = pd.pivot_table(dataset, values="age",index="month", columns="year", aggfunc=len)

#Making a basic heatmap
plt.title("Number of deaths")
sns.heatmap(table);


#Making a refined heatmap
plt.figure(figsize=(12, 6))
plt.title("Number of Deaths")
sns.heatmap(table, fmt="d", annot=True, linewidths=0.5, cmap='Blues');
