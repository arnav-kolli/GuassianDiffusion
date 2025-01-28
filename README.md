# **Gaussian Noise Diffusion on Images**

## **Overview**
This repository contains an implementation of a Gaussian noise diffusion process on images, visualizing the effect of noise addition over discrete time steps. The project explores the Mean Squared Error (MSE) between the original image and its progressively noisier versions, providing insights into the dynamics of diffusion processes.

## **Features**
- **Image Processing**: Resizes and converts images to tensors for processing.
- **Noise Diffusion**: Applies Gaussian noise to images over a specified number of time steps.
- **Visualization**: Displays the original and noisy images at different time steps.
- **MSE Analysis**: Tracks the MSE between the noisy and original images over time.


 **Results**:
   - Visualizations of the original and noisy images at specific time steps.
   - Plots showing MSE over time for each image.

## **Code Explanation**
### **Key Components**
- **Noise Diffusion**:
  - Gaussian noise is added to the images using:
    ```python
    x_t = sqrt_alpha_bar_t * x0 + sqrt_one_minus_alpha_bar_t * epsilon
    ```
  - Time steps (`T`): The number of iterations for the diffusion process.
  - `alpha_bars`: Cumulative product of noise parameters for each time step.

- **Visualization**:
  - Displays the noisy images at specific time steps (`t=0, 10, 50, 100, 500`).
  - Uses `matplotlib` for generating the visual output.

- **MSE Analysis**:
  - Computes the MSE between the noisy image and the original:
    ```python
    mse = nn.MSELoss()(x_t, x0).item()
    ```

## **Results**
- **Visual Output**:
  - Side-by-side comparison of original and noisy images at various time steps.
- **MSE Plot**:
  - A graph showing how the MSE evolves as noise is added over time.
