Polynomial Constant Term Finder:

This project provides a method for finding the constant term of a polynomial using Lagrange Interpolation.
The code processes JSON input containing encoded values in different bases, decodes these values, and then calculates the constant term of a polynomial based on the provided data points.

Overview
The main components of the project include:
decodeValue Function: Decodes a given value from a specified base.
findPolynomialConstantTerm Function: Uses Lagrange Interpolation to find the constant term of a polynomial.
main Function: Processes JSON input, decodes the values, and computes the constant term.
Functions
decodeValue(valueStr, base)
Decodes a string valueStr from the specified base to a decimal integer.

Parameters:
valueStr (string): The encoded value as a string.
base (number): The base of the encoded value.
Returns:
(number): The decoded decimal value.
findPolynomialConstantTerm(xValues, yValues)
Finds the constant term of a polynomial using Lagrange Interpolation.

Parameters:
xValues (Array<number>): An array of x-values (input data points).
yValues (Array<number>): An array of y-values (decoded data points).
Returns:
(number): The constant term of the polynomial.
main(jsonInput)
Processes the JSON input to decode the values and compute the polynomial constant term.

Parameters:
jsonInput (string): A JSON string containing encoded data.

Returns:
(number): The constant term of the polynomial.

Usage
Prepare JSON Input: The JSON input should follow the structure below.
json:
{
    "keys": {
        "n": <total number of data points>,
        "k": <number of data points to use>
    },
    "<x-value>": {
        "base": "<base of the encoded value>",
        "value": "<encoded value>"
    },
    ...
}
Call the main Function: Pass the JSON string to the main function.

javascript:
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


Examples
Example 1:
javascript
Copy code
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


Example 2:
javascript
Copy code
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


Error Handling
If there are not enough data points (less than k) to determine the polynomial, an error will be thrown.
Ensure that the JSON input follows the specified structure to avoid parsing errors.

License
This project is licensed under the MIT License. See the LICENSE file for details.
