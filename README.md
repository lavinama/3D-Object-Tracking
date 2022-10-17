# 3D-Object-Tracking
Tracking multiple objects over different frames

Steps:
  1. Detection
    1. Detect objects using YOLOv5
  2. Association
    1. Crop the bounding boxes
    2. Calculate the cosine similarity (measures the similarity between two vectors), this is the feature cost
    3. Add other costs: IOU cost, linear cost, exponential cost
    4. Associate bounding boxes of different frames using the Hungarian Algorithm
  3. Improvements
    1. Changing the Non Maxima Suppression formula
    2. Introduce age: MIN_AGE: we display obstacles that only have been matched more than 2 times in a row. MAX_AGE we continue displaying obstacles even if they are suddenly unmatched.
