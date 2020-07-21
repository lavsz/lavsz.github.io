---
layout: post
title:      "Simple Visualization: the Heatmap with Seaborn"
date:       2020-07-21 01:56:19 -0400
permalink:  simple_visualization_the_heatmap_with_seaborn
---


Seaborn is a very widely used library for data visualization. It is very notable for it's concise, eye-friendly, and attractive style. The library includes many types of plots that can make statistical graphics more story-telling. While working on my first project at Flatiron, I explored a new plots and want to share some thoughts on **Heatmap**. 


### The Creations

First, data was organized into a pivot table, demonstrating the average Revenue per genre per year (shown below). 


![Pivot Table](https://raw.githubusercontent.com/lavsz/some_files/master/Screen%20Shot%202020-07-21%20at%201.38.52%20AM.png)



Then, to create a heatmap, the Seaborn library was used. With many plots built-in, the heatmap can be called out directly. 


```
# Creating subplot first

f,ax1 = plt.subplots(figsize=(7,6))

# Genre and overall revenue average

r1 = sns.heatmap(genre_pivot, cmap='Blues', ax=ax1)
r1.set_title("Average Revenue \n Per Genre (Million $) \n", fontsize=15)
r1.tick_params(axis='y', labelsize=13)
r1.tick_params(axis='x', labelsize=12)
r1.set_ylabel('Genre \n', fontsize=15)
r1.set_xlabel('\n Year', fontsize=15)
```



### The Look

A **Heatmap** uses a set of color in various hue and intensity to present different data. In the project, our project team decided on using heatmaps for overall performance review of different movies genres through years. From a simple one, shown below, we can grab some quick ideas on how some movie genres tend to consistent on yield while some can change year by year. 



![Heatmap](https://raw.githubusercontent.com/lavsz/some_files/master/Heatmap.png)


### Other Common Applications

In addition to the **Heatmap** demonstrated here, chloropleth heatmaps are also widely used to demonstrate geographical features including but not limited to:



* Traffic Signal


* Elevation


* Demographic features








