---
layout: post
title:      "Near? Far? Wherever Your Nearest is."
date:       2020-11-17 04:53:54 +0000
permalink:  near_far_wherever_your_nearest_is
---


In study many geospatial related topics, we would need to identify the nearest feature and calculate the distance to this feature. There are a few Python libraries that can help you achieve this easily. 

First, how do we find out where's our nearest feature?

A function called nearest_points from shapely.ops will be needed. 
```
import shapely
from shapely.ops import nearest_points
from shapely.geometry import MultiPoint
from shapely.geometry import Point
```

Then, a function can be built through the nearest_points. 

def nearest(housing, feature):
     # find the nearest point
    nearest_point = nearest_points(housing, feature)[1]
    return nearest_point
		
Now we have the nearest points. How do we calculate the distance between the two features? A nearest distance function can be built through numpy and math. 

```

def real_distance(point1, point2):
    R_earth = 6360.57
    lat1=point1.coords[0][1]
    lat2=point2.coords[0][1]
    lon1=point1.coords[0][0]
    lon2=point2.coords[0][0]
        
    dlon = math.radians(lon2 - lon1)
    dlat = math.radians(lat2 - lat1)
    a = float((sin(dlat/2))**2 + cos(lat1) * cos(lat2) * (sin(dlon/2))**2)
    c = float(2 * atan2(sqrt(a), sqrt(1-a)))
    distance = float(R_earth * c)
    return distance
		
```

Here it is! Those are designed to identify points and calculate distance between points. 
		
