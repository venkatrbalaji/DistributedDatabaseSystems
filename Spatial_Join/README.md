# Spatial_Join

### Data:

Input datasets consist of two spatial datasets: a point dataset and a rectangle dataset. 
The point dataset (points.csv) consists of latitudes and longitudes of various points while the rectangle dataset (rectangles.csv) consists of latitudes and longitudes of two diagonal points of rectangles.
Each row in points.csv file has the format longitude,latitude while the same for the rectangles.csv file is longitude1,latitude1,longitude2,latitude2.
Goal is to perform spatial join between points dataset and rectangles dataset and return the number of points inside each rectangle (including points on rectangle boundary).


## PART A:

### Tasks:
- Create four partitions/fragments of both pointsTable and rectsTable. You should consider space partitioning such that all points or rectangles of a partition should lie within the corresponding fragment. Fragments doesn’t need to satisfy disjointness property.
- Run four parallel threads. Each thread should perform a spatial join between a fragment of pointsTable and a fragment of rectsTable. The purpose of the join is to find the number of points (pointsTable.geom) inside each rectangle or Envelop (rectsTable.geom) within the corresponding fragment. You must make use of ST_Contains method supported by PostGIS.
- Sort the output of each fragment in the ascending order of counts of points inside the parallel threads.
- Merge the outputs of four parallel joins into outputTable in the ascending order of counts of points. You can design the structure of the outputTable as you wish, but it should have a column named points_count containing counts of points.
- Write the counts of points into the outputPath in the ascending order. You don’t need to write rectangle coordinates.


## PART B:

### Tasks:

Given a Apache Sedona project named Map-Reduce-Apache-Sedona. 
- Find the Scala file SparkMapReduce.scala. Complete the incomplete function runMapReduce(). 
- Instead of using group by operation, you must make use of Spark map and reducebyKey operations to complete the task. 
- Convert the resultant RDD back to a DataFrame before returning the result. 
- The returned DataFrame should contain the number of points within each rectangle in an ascending order of count values.
