# 3D-Object-Tracking
Tracking multiple objects over different frames

Steps:

**1. Detection**
  - Detect objects using YOLOv5
 
**2. Association**
  - Crop the bounding boxes
  - Calculate the cosine similarity (measures the similarity between two vectors), this is the feature cost
  - Add other costs: IOU cost, linear cost, exponential cost
  - Associate bounding boxes of different frames using the Hungarian Algorithm
 
**3. Improvements**
  - Changing the Non Maxima Suppression formula
  - Introduce age: `MIN_AGE` we display obstacles that only have been matched more than 2 times in a row. `MAX_AGE` we continue displaying obstacles even if they are suddenly unmatched.
