import numpy as np
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D
from matplotlib.animation import FuncAnimation

# Create torus (donut) coordinates
theta = np.linspace(0, 2 * np.pi, 100)
phi = np.linspace(0, 2 * np.pi, 100)
theta, phi = np.meshgrid(theta, phi)

# Radius values
R = 1  # major radius
r = 0.4  # minor radius

# 3D coordinates for torus
X = (R + r * np.cos(theta)) * np.cos(phi)
Y = (R + r * np.cos(theta)) * np.sin(phi)
Z = r * np.sin(theta)

# Create the figure
fig = plt.figure(figsize=(6, 6))
ax = fig.add_subplot(111, projection='3d')
ax.set_xlim(-2, 2)
ax.set_ylim(-2, 2)
ax.set_zlim(-2, 2)
ax.axis('off')

# Draw the donut surface
donut = [ax.plot_surface(X, Y, Z, color='gold', edgecolor='black', linewidth=0.3)]

# Animation function
def update(frame):
    ax.view_init(elev=30, azim=frame)
    return donut

# Create animation
ani = FuncAnimation(fig, update, frames=np.arange(0, 360, 2), interval=50)

plt.show()




#Simply ask Ai

