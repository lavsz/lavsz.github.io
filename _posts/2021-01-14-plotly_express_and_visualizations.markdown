---
layout: post
title:      "Plotly Express and Visualizations"
date:       2021-01-15 02:31:21 +0000
permalink:  plotly_express_and_visualizations
---


People love to see 'cool' visualizations. You might think that a 'cool' visualization might take hours and hours to build and edit. This is true. However, when you are in a rush, and have data with a few layers that you want to show, you might want to take a look at what's available through Plotly Express. Here is the [link](https://plotly.com/python/plotly-express//) to their website. 

In my recent project, I was trying to find a way to demonstrate some breakdowns of different skincare products, their ratings, as well as functionality. Through Plotly Express, I found the Treemap that can intake many different informations and convey the ideas on just one graph. 

Here is how my graph looks like:

![Treemap](https://github.com/lavsz/Mod4_Project_Sephora/blob/main/Pictures/Screen%20Shot%202021-01-13%20at%205.39.27%20PM.pnghttp://)

In this graph, each box represents the product type; the number inside the box shows the maximum number of skin concerns this category can address; the color represents the average rating of this category. 

The graph was easy to make. Here are the lines I used, which was mostly learned from the Plotly Gallary examples. 

```
fig = px.treemap(df_group, path=['product_type_', 'Skinc_total_max'], 
                 values = 'stars_count', color = 'stars_mean')
fig.show()
```

Another interesting and versatile graph is the Sunburst. It's a pie chart showing propotions in different categories with color code to show continuous value. 
![Subburst](https://github.com/lavsz/Mod4_Project_Sephora/blob/main/Pictures/Screen%20Shot%202021-01-13%20at%205.37.11%20PM.pnghttp://)

Again, the graph was easy to make. The following lines are what I used:
```
fig = px.sunburst(df_clinic_select, path=['Clinical_tested', 'product_type'], values = 'starscount', 
                color_continuous_scale = 'solar',
                color = 'starsmean')
fig.show()
```



