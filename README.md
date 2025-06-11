# Simulated Sonar Swath Data Visualization

## Description
This MATLAB script simulates sonar swath data by creating a grid representing the seafloor. The seabed depth is modeled as a wavy surface using sine and cosine functions to mimic natural underwater terrain features. Realistic measurement noise is added to simulate the imperfections typically encountered in sonar data. The result is visualized as a 3D surface plot showing the simulated bathymetry.

## Code

```matlab
% Simulate sonar swath data (create a grid to simulate the seafloor)
n = 50;
x = linspace(0, 100, n);
y = linspace(-25, 25, n);
[X, Y] = meshgrid(x, y);
Z = 50 + 10*sin(0.1*X) + 5*cos(0.1*Y);  % Seabed depth simulation (make the seafloor wavy with sine/cosine)

% Add some noise (make it realistic by simulating measurement noise)
Z = Z + randn(size(Z));

% Plot depth (show the 3D seabed so we can see the terrain)
figure;
surf(X, Y, Z);
xlabel('Forward (m)'); ylabel('Beam Width (m)'); zlabel('Depth (m)');
title('Simulated Bathymetry');
