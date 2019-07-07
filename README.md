# Best Fit Plane using Regression

This is a really simple way to do best fit planes. It simply uses regression instead of singular value decomposition.

# Here's how it works:

- First it computes the centroid and subtracts it from the data set. We know that the best fit plane will contain the centroid (geometric center). (See: https://math.stackexchange.com/questions/635670/show-that-the-least-squares-line-must-pass-through-the-center-of-mass)
- Then it creates a random direction using a random **(phi, theta)** pair (spherical coordinates). These will be our weights to adjust via gradient descent.
- The cost function is simply the sum of all point distances to the plane.
- If the cost starts increasing, it will reduce the factor. If the cost decreases very little 3 times in a row it will use that as an exit condition and decide that the plane is now fit. It most likely will fall in at least in one local minima.

# How to use

Simply open the .HTML file and hit refresh for new data points. The blue quad lies on **'ground truth'** and the red quad lies is our learned plane. The green markers are data points generated within a random distance from ground truth.

# Example

https://jsfiddle.net/5ogvjzhq/

# Known issues

Some generated sets seem somewhat skewed while they shouldn't be: as per the default settings they should be perfectly symmetric. Have yet to fully investigate.