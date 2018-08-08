# PER-analysis
The program used here measures the distance on a pre-processed video between the eye of Drosophila melanogaster and the end of the proboscis. This allows the tracking and analysis of proboscis movement from the single dataset obtainned.

Video pre-processing (before running through the code) using ImageJ/Fiji:

Record the frame in which the first flash occurs, this is needed for later analysis.
Remove frames where the flash obscures the image (usually arounf 14 frames per flash).
Crop the video so that only the head remains/Find the region of interest (ROI) - leave room for the proboscis extension to be caught in the video
Record x, y coordinates of the center of the eye this will be needed to calcualte probocsis distance when entered into the program.
Place file in same folder as running script. 

How the code works:

The codes finds the binary image of each frame of the video, it then processes each frame as an individual image. 
From the binary images the contour surrounding the object (the fly) is found and added to the video display.
Upon finding the contour the lowest coordinate of this contour is found and measured as an x, y coordinate, this should be the lowest point of the proboscis.
By entering the coordinates of the centre of the fly eye and applying this to a list with the probosics coordinates the euclidean distance between both coordinates can be found in each frame and given as the output of distance in pixels. 

PER characteristic extraction: 

To find the latency in response upon the first frame of light from the pulse stimuation, the distance from 1 frame previous to the flash was obserevd and when the value increased by atleast 3% in the follwoing frames, this was determined to be the point at which PER had begun and the corresponding time since the first flash frame was recorded. This gives the time taken for the response to begin upon initial stimualtion. 

To find the duration the distance obserevd where PER began (initial distance increased by 3%) was determined the start of teh responce and PER was determined to have ended when the distance returnned to this value. Where the value did not return to this value within the video footage, where the distance remainned steady within 1 significant figure was determined to be the end of PER. The time between each the start and end point was then recorded. 

Maximal proboscis extension was obainned by finding the highest value (distance) within the dataset and subtracting the distance between eye and probosics before the light stimulation had occured. 

Tremor can be observed by plotting the distance data obtainned against time to show tremor in terms of in and out movements. 
