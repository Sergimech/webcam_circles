# webcam_circle detector

###Find circles in the image ###

Webcam_circles allows you to set certain parameters in detecting circles. For example: MIN_CIRCLE DIST, we can modify the minimum distance to find a circle, so we can use this parameter to filter the number of circles to find. Const int MAX_RADIUS or const int MIN_RADIUS or the can be used to filter or limit the size of the circle we want to find considering des focal length of the camera.

The Hough transform

The Hough transform is a technique based on algorithms used in digital image processing, image analysis and computer vision to take or to find features in order to recognized patterns or other arbitrary shapes of interest in an image.

Theory

One of difficult things in image analysis is detecting simple shapes, as straight lines, circles or ellipses. Normally an edge detector can be used as a pre-processing stage to obtain image points or image pixels that are on the desired curve in the image space. 

In general, the straight line y = mx + b can be represented as a point (b, m) in the parameter space, but vertical lines pose a problem because this not intersect on y axis.

For computational reasons, Duda and Hart proposed the use of the Hesse normal form, where “r” is the distance from the origin to the closest point on the straight line, and (theta) is the angle between the “x” axis and the line connecting the origin with that closest point.

The linear Hough transform algorithm uses a two-dimensional array, called an accumulator, to detect the existence of a line described by:

The final result of the linear Hough transform is a two-dimensional array (matrix) similar to the accumulator—one dimension of this matrix is the quantized angle θ and the other dimension is the quantized distance r. Each element of the matrix has a value equal to the sum of the points or pixels that are positioned on the line represented by quantized parameters (r, θ). So the element with the highest value indicates the straight line that is most represented in the input image.

Example

Consider three data points, shown here as black dots.

For each data point, a number of lines are plotted going through it, all at different angles. These are shown here as solid lines. 
For each solid line a line is plotted which is perpendicular to it and which intersects the origin. These are shown as dashed lines. 
The length (i.e. perpendicular distance to the origin) and angle of each dashed line is measured. In the diagram above, the results are shown in tables. 
This is repeated for each data point. 
A graph of the line lengths for each angle, known as a Hough space graph, is then created. 

Variations and extensions
Circle detection process
The circle Hough Transform (CHT) is a features extraction technique for detecting circles. It is a specialization of Hough Transform. The purpose of the technique is to find circles in imperfect image inputs. The circle candidates are produced by “voting” in the Hough parameter space and then select the local maxima in a so-called accumulator matrix.
In a two-dimensional space, a circle can be described by:

where (a,b) is the center of the circle, and r is the radius. If a 2D point (x,y) is fixed, then the parameters can be found according to (1). The parameter space would be three dimensional, (a, b, r). And all the parameters that satisfy (x, y) would lie on the surface of an inverted right-angled cone whose apex is at (x, y, 0). In the 3D space, the circle parameters can be identified by the intersection of many conic surfaces that are defined by points on the 2D circle. This process can be divided into two stages. The first stage is fixing radius then find the optimal center of circles in a 2D parameter space. The second stage is to find the optimal radius in a one dimensional parameter space.

If the radius is fixed, then the parameter space would be reduced to 2D (the position of the circle center). For each point (x, y) on the original circle, it can define a circle centered at (x, y) with radius R according to (1). The intersection point of all such circles in the parameter space would be corresponding to the center point of the original circle.

References:

Wiki link:

https://en.wikipedia.org/wiki/Hough_transform

https://en.wikipedia.org/wiki/Circle_Hough_Transform

http://docs.opencv.org/2.4/doc/tutorials/imgproc/imgtrans/hough_lines/hough_lines.html

Youtube link:

https://www.youtube.com/watch?v=4zHbI-fFIlI
