# astack
This is a demonstration of radio interferometric imaging techniques based on A-stacking.

## Demos
Three demo scripts are supplied, along with an example input data set. The input data contains array layout and antenna radiation characteristics of the LOFAR LBA station at Onsala, Sweden.
1. Forward calculation `demo_astack_forward_calculation.m`
2. Visibility Domain Source Subtraction `demo_astack_vdss_clean.m`
3. Image Domain Source Subtraction `demo_astack_idss_clean.m`

### Forward calculation (sky-to-visibility)
This script calculates visibilities from a random generated sky model based on the given input data, and produces a plot which shows the accuracy of the calculation as a function of the number of terms used to describe the direction- and baseline-dependent radiation patterns of the array.

An intermediate result produced by this script is the full exact direction- and baseline-dependent gain matrix B in eq (7) from [1], as well as the direction-dependent expansion functions (f_i) and baseline-dependent weighting coefficients (a_i) in eq (17). These results are required by the source subtraction demonstration scripts.

### Visibility Domain Source Subtraction (VDSS-CLEAN)
This script simulates measured visibilities from a random generated sky model based on the given input data, and then performs a CLEAN-like operation by subtracting source contributions in the visibility plane. See Section 6.2 in [1] for more details.

This script requires data generated by `demo_astack_forward_calculation.m`.

### Image Domain Source Subtraction (IDSS-CLEAN)
This script simulates measured visibilities from a random generated sky model based on the given input data, and then performs a CLEAN-like operation by subtracting source contributions in the image domain. See Section 4.1 in [1] for more details.

This script requires data generated by `demo_astack_forward_calculation.m`.

## Requirements
This project was developed to run in Octave 3.8.2 and requires the following octave-forge packages:
* statistics 1.2.3
The code may also work on earlier versions of the software.

Although not fully supported, the code should also run in Matlab; the example input data set is also provided in Matlab v6 binary format.


## References
[[1] A. Young, S. J. Wijnholds, T. D. Carozzi, R. Maaskant, M. V. Ivashina and D. B. Davidson, "Efficient correction for both direction-dependent and baseline-dependent effects in interferometric imaging: An A-stacking framework," *Astronomy & Astrophysics* (forthcoming)](http://dx.doi.org/10.1051/0004-6361/201425492) in *Astronomy and Astrophysics*.
