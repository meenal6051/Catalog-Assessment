# Polynomial Constant Term Finder

This project provides a method for finding the constant term of a polynomial using **Lagrange Interpolation**. The code processes JSON input containing encoded values in different bases, decodes these values, and then calculates the constant term of a polynomial based on the provided data points.

## Overview

The project includes the following key components:

1. **`decodeValue` Function**: Decodes a given value from a specified base.
2. **`findPolynomialConstantTerm` Function**: Uses Lagrange Interpolation to find the constant term of a polynomial.
3. **`main` Function**: Processes JSON input, decodes the values, and computes the constant term.

## Functions

### `decodeValue(valueStr, base)`
Decodes a string `valueStr` from the specified base to a decimal integer.

- **Parameters**:
  - `valueStr` (string): The encoded value as a string.
  - `base` (number): The base of the encoded value.
 
- **Returns**:
  - `(number)`: The decoded decimal value.

### `findPolynomialConstantTerm(xValues, yValues)`
Finds the constant term of a polynomial using Lagrange Interpolation.

- **Parameters**:
  - `xValues` (Array<number>): An array of x-values (input data points).
  - `yValues` (Array<number>): An array of y-values (decoded data points).
 
- **Returns**:
  - `(number)`: The constant term of the polynomial.

### `main(jsonInput)`
Processes the JSON input to decode the values and compute the polynomial constant term.

- **Parameters**:
  - `jsonInput` (string): A JSON string containing encoded data.
 
- **Returns**:
  - `(number)`: The constant term of the polynomial.

## Usage

### 1. Prepare JSON Input

The JSON input should follow the structure below:

```json
{
    "keys": {
        "n": <total number of data points>,
        "k": <number of data points to use>
    },
    "<x-value>": {
        "base": "<base of the encoded value>",
        "value": "<encoded value>"
    }
}
```

### 2. Call the `main` Function

Pass the JSON string to the `main` function.

```javascript
const jsonInput = JSON.stringify({
    "keys": {
        "n": 4,
        "k": 3
    },
    "1": {
        "base": "10",
        "value": "4"
    },
    "2": {
        "base": "2",
        "value": "111"
    },
    "3": {
        "base": "10",
        "value": "12"
    },
    "6": {
        "base": "4",
        "value": "213"
    }
});

console.log(main(jsonInput));  // Output the constant term
```

### 3. Example 1

Here’s an example of how to use the code with a sample JSON input:

```javascript
const jsonInput1 = JSON.stringify({
    "keys": {
        "n": 4,
        "k": 3
    },
    "1": {
        "base": "10",
        "value": "4"
    },
    "2": {
        "base": "2",
        "value": "111"
    },
    "3": {
        "base": "10",
        "value": "12"
    },
    "6": {
        "base": "4",
        "value": "213"
    }
});

console.log(main(jsonInput1));  // Output the constant term
```

### 4. Example 2

Another example with a larger JSON input:

```javascript
const jsonInput2 = JSON.stringify({
    "keys": {
        "n": 9,
        "k": 6
    },
    "1": {
        "base": "10",
        "value": "28735619723837"
    },
    "2": {
        "base": "16",
        "value": "1A228867F0CA"
    },
    "3": {
        "base": "12",
        "value": "32811A4AA0B7B"
    },
    "4": {
        "base": "11",
        "value": "917978721331A"
    },
    "5": {
        "base": "16",
        "value": "1A22886782E1"
    },
    "6": {
        "base": "10",
        "value": "28735619654702"
    },
    "7": {
        "base": "14",
        "value": "71AB5070CC4B"
    },
    "8": {
        "base": "9",
        "value": "122662581541670"
    },
    "9": {
        "base": "8",
        "value": "642121030037605"
    }
});

console.log(main(jsonInput2));  // Output the constant term
```

## Steps to Run the Code

### Prerequisites
To run the JavaScript code, ensure you have **Node.js** installed on your system. You can download and install it from [nodejs.org](https://nodejs.org/).

### Steps

1. **Clone the repository**:
   Open your terminal and run:
   ```bash
   git clone <repository-url>
   cd <repository-folder>
   ```

2. **Create a JavaScript file**:
   Create a new file (e.g., `polynomial.js`) and paste the provided code into the file.

3. **Run the code**:
   Run the following command in your terminal to execute the JavaScript code:
   ```bash
   node polynomial.js
   ```

   This will execute the `main` function with the sample JSON input and print the constant term of the polynomial to the console.

### Example Output

```bash
3
```

## Error Handling

- If there are not enough data points (less than `k`) to determine the polynomial, an error will be thrown.
- Ensure that the JSON input follows the specified structure to avoid parsing errors.
