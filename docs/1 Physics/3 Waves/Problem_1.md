# PROBLEM 1


# Constants
A = 1               # Amplitude of the wave (meters)
lambda_wave = 5     # Wavelength (meters)
k = 2 * np.pi / lambda_wave  # Wave number, k = 2π/λ
omega = 2 * np.pi   # Angular frequency (rad/s), ω = 2πf
phi = 0             # Phase constant
x0, y0 = 0, 0       # Point source location at the origin (x0, y0)
f = 1               # Frequency (Hz)
t = 0               # Start at t = 0 (you can modify this for time-dependent simulation)

# Create a grid of points (x, y)
x = np.linspace(-10, 10, 400)  # X position range
y = np.linspace(-10, 10, 400)  # Y position range
X, Y = np.meshgrid(x, y)       # Create mesh grid

# Calculate the distance r from the point source at (x0, y0) to each point (x, y)
r = np.sqrt((X - x0)**2 + (Y - y0)**2)

# Formula: η(x, y, t) = (A / √r) * cos(k * r - ω * t + φ)
# Compute the wave displacement η(x, y, t) at each point for time = 0
eta = (A / np.sqrt(r)) * np.cos(k * r - omega * t + phi)


![alt text](image-5.png)
