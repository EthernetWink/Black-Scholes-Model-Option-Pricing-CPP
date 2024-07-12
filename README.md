# Option Pricing with Black-Scholes Model

This project contains a simple C++ implementation of the Black-Scholes model for pricing European call and put options. The implementation calculates various option Greeks and other relevant parameters.

## Features

- Calculates the premium of European call and put options.
- Computes option Greeks: Delta, Gamma, Theta, Vega, and Rho.
- Calculates the implied volatility.
- Determines the intrinsic value of the options.

## Getting Started

### Prerequisites

- C++ compiler (e.g., g++, clang++)
- Standard C++ Library

### Compilation

To compile the code, use the following command:

```sh
g++ -o option_pricing main.cpp -lm
```

### Running the Program

After compiling the code, you can run the program using:

```sh
./option_pricing
```

### Example Output

The program calculates the option prices and Greeks for a sample set of input parameters and prints the results:

```sh
European Call Option Price: 10.4506, dte: 365, delta: 0.6368, gamma: 0.0189, theta: -6.4157, vega: 37.5764, rho: 53.2325, implied volatility: 0.2000, intrinsic value: 0.0000
European Put Option Price: 5.5735, dte: 365, delta: -0.3632, gamma: 0.0189, theta: -1.9332, vega: 37.5764, rho: -41.8905, implied volatility: 0.2000, intrinsic value: 0.0000
```

## Code Structure

- **main.cpp**: Contains the main implementation of the Black-Scholes model, option pricing functions, and the `main` function for execution.

### Key Functions

#### `double erf(double x)`

Approximates the error function, which is used in the calculation of the cumulative standard normal distribution.

#### `double cumulativeStandardNormal(double x)`

Computes the cumulative standard normal density function.

#### `Contract blackScholesOptionPricing(double S0, double K, double r, double sigma, double T, bool isCallOption)`

Calculates the option price and Greeks for a given set of parameters:
- `S0`: Initial stock price
- `K`: Strike price
- `r`: Risk-free interest rate
- `sigma`: Volatility of the stock
- `T`: Time to maturity (in years)
- `isCallOption`: Boolean flag indicating whether the option is a call option (`true`) or a put option (`false`)

### Contract Struct

The `Contract` struct holds the results of the option pricing calculations:
- `double premium`
- `int dte` (days till expiry)
- `double delta`
- `double gamma`
- `double theta`
- `double vega`
- `double rho`
- `double implied_volatility`
- `double intrinsic_value`

## Notes

- This implementation uses an approximation for the error function (erf) which might introduce minor inaccuracies in the cumulative standard normal distribution calculation.
- The program assumes the input parameters are valid and does not include extensive error handling.


Feel free to modify and extend the code to suit your needs. Happy coding!
