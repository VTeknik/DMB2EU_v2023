# Depth to Magnetic Basement and Crustal Susceptibility Estimation (DMB2EU_v2023)

This repository contains MATLAB code for estimating the **depth to magnetic basement (DMB)** and the **average crustal magnetic susceptibility** across Europe. The estimation is based on the Radially Averaged Power Spectrum (RAPS) method applied to magnetic anomaly data.

---

## Features

- **Depth to Magnetic Basement (DMB)**: Estimates DMB using magnetic data and power spectrum analysis.
- **Average Magnetic Susceptibility**: Provides an average estimate of the crustal magnetic susceptibility.
- **Flexible Windowing**: Supports customizable data windowing for localized analysis.
- **Nan Handling**: Automatically replaces missing data with mean values for robust computations.
- **Wave Number Calculations**: Includes functions for defining wave numbers and correcting Gibbs phenomena.
- **Visualization**: Offers tools for displaying results and radial power spectrum plots.

---

## Repository Structure

### Main Files

- **`DMB_v2023.m`**: Main script for running the DMB estimation workflow.
- **`checkshow.m`**: Displays intermediate results for quality checks.
- **`fillnan.m`**: Handles missing values by replacing them with mean values.
- **`getpar.m`**: Loads input parameters for analysis.
- **`griding.m`**: Grids magnetic data for further processing.
- **`kpick.m`**: Selects key parameters interactively.
- **`ldata.m`**: Loads magnetic data in the required format.
- **`model.m`**: Core functions for modeling depth and susceptibility.
- **`nanremove.m`**: Removes NaN values from the dataset.
- **`par.m`**: Defines parameters required for processing.
- **`phi_fun.m`**: Contains functions for theoretical calculations.
- **`phi_m.m`**: Implements mathematical models for RAPS analysis.
- **`pointxy.m`**: Defines window centers for data analysis.
- **`rapspec.m`**: Computes the radial power spectrum.
- **`rmsshow.m`**: Displays RMS errors for model validation.
- **`showresults.m`**: Visualizes the final results.
- **`showwhole.m`**: Displays the entire dataset.
- **`theory.m`**: Theoretical formulations for power spectrum analysis.
- **`wavenumber.m`**: Calculates wave numbers for processing.
- **`wavenumber_m.m`**: Advanced wave number computations.
- **`windata.m`**: Handles data windowing.
- **`winfun.m`**: Generates window functions for Gibbs phenomenon correction.

---

## Requirements

- **MATLAB**: Version R2018b or newer is recommended.
- **Operating System**: Works on Windows, macOS, and Linux.

---

## Usage

### 1. Clone the Repository
```bash
git clone https://github.com/VTeknik/DMB2EU_v2023.git
cd DMB2EU_v2023
```

### 2. Load Magnetic Data
Prepare your magnetic data in the required format and load it using the `ldata.m` function.

### 3. Set Parameters
Customize your parameters in `getpar.m` or directly through the main script.

### 4. Run the Script
Run the main script `DMB_v2023.m` to start the estimation process:
```matlab
run('DMB_v2023.m')
```

### 5. Visualize Results
Use the provided visualization functions (e.g., `showresults.m`, `checkshow.m`) to analyze the output.

---

## Example Workflow

1. Load magnetic data with:
   ```matlab
   [x, y, mag, long, lat] = ldata;
   ```
2. Define parameters using:
   ```matlab
   [win_l, overlap, beta, cs, dcs, per] = getpar;
   ```
3. Grid the data:
   ```matlab
   [X, Y, MAG] = griding(x, y, mag, cs);
   ```
4. Compute the power spectrum:
   ```matlab
   [k_r, log_k_r, RAPS, LOG_RAPS] = rapspec(mag_fft, k);
   ```
5. Visualize results with:
   ```matlab
   showresults;
   ```

---

## Contributing

Contributions are welcome! To contribute:
1. Fork the repository.
2. Create a new branch for your feature or bugfix.
3. Submit a pull request with detailed explanations of your changes.

---

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

---

## Contact

For questions or further information, contact [Vahid Teknik](mailto:vahid.teknik@gmail.com).

