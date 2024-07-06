Feature Detection and Matching: Uses SIFT to detect keypoints and compute descriptors for both the sample and each fingerprint image. Matches these descriptors using FLANN (Fast Library for Approximate Nearest Neighbors) based matcher and filters good matches based on a distance ratio.

Scoring: Calculates a score based on the number of good matches relative to the number of keypoints detected in both images.

Finding the Best Match: Keeps track of the image with the highest match score (best_score) and displays it.

Displaying Results: Draws the matching keypoints between the sample and the best matching fingerprint image and displays the result.

Usage Instructions:

1-Replace 'SOCOFing/Altered/Altered-Hard/150__M_Right_index_finger_Obl.BMP' with your own sample fingerprint image path.

2-Ensure the 'SOCOFing/Real' directory contains the fingerprint images you want to compare against.

3-Run the script to find and display the best matching fingerprint image and its score.
