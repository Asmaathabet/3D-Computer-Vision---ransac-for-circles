# RANSAC Circle Fitting with OpenCV

This project demonstrates the use of the RANSAC algorithm to fit a circle to a set of 2D points in an image. The points include both inliers (which lie close to the circle) and outliers (which do not). The RANSAC algorithm robustly fits a circle by iteratively selecting random subsets of points and finding the best fitting circle.

## Features

- **Data Generation:** Randomly generates points lying on a circle with added noise, along with some outliers.
- **RANSAC Algorithm:** Iteratively fits a circle to the data by randomly sampling subsets of points.
- **Visualization:** Displays the generated points and the fitted circle on an image.

## Prerequisites

- **OpenCV:** Make sure OpenCV is installed on your system. You can install it using:
  ```bash
  pip install opencv-python
  ```
- **C++ Compiler:** Ensure you have a C++ compiler that supports C++11 or later.

## How to Build

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/yourusername/ransac-circle-fitting.git
   cd ransac-circle-fitting
   ```

2. **Compile the Program:**
   ```bash
   g++ -o ransac_circle main.cpp `pkg-config --cflags --libs opencv4`
   ```

3. **Run the Program:**
   ```bash
   ./ransac_circle
   ```

## How It Works

1. **Data Generation:**
   - Generates random points lying on a circle with a given radius.
   - Adds Gaussian noise to the points.
   - Adds a specified number of random outliers.

2. **RANSAC Circle Fitting:**
   - Randomly selects three points from the data to compute a candidate circle.
   - Calculates the number of inliers (points close to the circle).
   - Repeats the process for a specified number of iterations.
   - Returns the circle with the most inliers.

3. **Visualization:**
   - Plots the generated points in red.
   - Plots the best-fitting circle in green.

## Parameters

- `noise`: The amount of noise added to the points on the circle.
- `point_number`: The number of points generated on the circle.
- `outlier_number`: The number of random outliers added to the data.
- `circle_radius`: The radius of the circle used for generating the points.
- `size`: The size of the output image.
- `ransac_iterations`: The number of iterations the RANSAC algorithm will run.
- `ransac_threshold`: The distance threshold used to determine inliers.

## Project Structure

- **main.cpp**: The main source code file containing the data generation and RANSAC implementation.
- **README.md**: Documentation file (this file).

## Future Enhancements

- Add support for fitting other shapes like ellipses or lines.
- Implement a GUI to adjust the parameters interactively.
- Improve the performance by parallelizing the RANSAC iterations.

