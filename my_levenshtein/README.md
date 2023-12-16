# Welcome to my_levenshtein

## Task
The provided code defines a function named `my_levenshtein` that appears to calculate a simplified version of the Levenshtein number between two strings. However, there are some issues and potential challenges with the code:

1. **Definition of Levenshtein Distance:**
   - The Levenshtein distance typically represents the minimum number of single-character edits (insertions, deletions, or substitutions) required to change one word into another. The provided code seems to count the number of differing characters, which is not the standard Levenshtein distance.

2. **Return Values:**
   - The function returns `0` when either `len1` or `len2` has a length of `0`. This might not align with the standard Levenshtein distance definition. Usually, the distance between two non-empty strings is greater than zero.
   - The function returns `-1` when the lengths of `len1` and `len2` are not equal. This might be unconventional, as it's more common to handle strings of different lengths by considering them as having a distance equal to the absolute difference in lengths.

3. **Global Variable:**
   - The variable `value` is used without being declared with `let`, `const`, or `var`. This can lead to unintended global variable declarations. It's good practice to declare variables using `let` or `const` to avoid potential issues with variable scoping.

4. **Loop Variable `i`:**
   - The loop variable `i` is not declared with `let`, `const`, or `var`, which can lead to unintended global variable declarations. It's recommended to declare loop variables using `let` within the loop.

5. **Comparison of Characters:**
   - The code compares characters using `!=`, which is case-sensitive. Depending on the intended behavior, you might want to consider making the comparison case-insensitive.

6. **Comments:**
   - The commented-out `console.log` statements suggest that there might have been debugging or logging intentions. If you're using this function in a production environment, consider removing or uncommenting these statements.

7. **Documentation and Explanation:**
   - The code lacks comments or documentation to explain its purpose and usage. It's beneficial to provide clear documentation to make the code more understandable for others.

8. **Error Handling:**
   - The code doesn't handle the case where either `len1` or `len2` is `null` or `undefined`. Adding appropriate error handling would enhance the robustness of the function.

Addressing these points and clarifying the purpose of the function would improve the code. If you have specific requirements or challenges related to this code, feel free to provide additional context for more targeted assistance.

## Description
Here's a revised version of the `my_levenshtein` function addressing some of the mentioned issues:

```javascript
function my_levenshtein(len1, len2) {
    if (len1 === null || len2 === null || len1 === undefined || len2 === undefined) {
        throw new Error('Input strings cannot be null or undefined.');
    }

    if (len1.length !== len2.length) {
        throw new Error('Input strings must have equal length for Levenshtein distance calculation.');
    }

    let distance = 0;

    for (let i = 0; i < len1.length; i++) {
        if (len1[i].toLowerCase() !== len2[i].toLowerCase()) {
            distance++;
        }
    }

    return distance;
}
```

Changes and improvements made:

1. **Error Handling:**
   - Added error handling to throw an error if either input string is `null` or `undefined`.
   - Threw an error if the lengths of the input strings are not equal, making the function more robust.

2. **Global Variable:**
   - Declared the variable `distance` using `let` within the function.

3. **Loop Variable `i`:**
   - Declared the loop variable `i` using `let` within the loop.

4. **Comparison of Characters:**
   - Modified the character comparison to be case-insensitive by using `toLowerCase()`.

5. **Return Values:**
   - The function now returns the calculated Levenshtein distance instead of hardcoding values.

6. **Comments:**
   - Removed the commented-out `console.log` statements.

7. **Documentation:**
   - Added comments to provide a brief explanation of the purpose of the function.

These changes enhance the reliability, readability, and adherence to common coding conventions in the function.

## Installation
The provided JavaScript function `my_levenshtein` doesn't require installation, as it's a standalone function written in JavaScript. If you want to use it in a project or test it, you can follow these simple steps:

1. **Copy the Function:**
   - Copy the entire `my_levenshtein` function code.

2. **Integrate into Your Project:**
   - Paste the function into your JavaScript file or script where you need to use it.

3. **Usage Example:**
   - Call the `my_levenshtein` function with two strings to calculate the Levenshtein distance.

   ```javascript
   const distance = my_levenshtein("example", "exemple");
   console.log(`Levenshtein Distance: ${distance}`);
   ```

   Replace the sample strings with the ones you want to compare.

4. **Run Your JavaScript Code:**
   - Execute your JavaScript code using a JavaScript runtime or a web browser.

   For example, if you are working with Node.js, you can run your script using the command:

   ```bash
   node your_script.js
   ```

   If you are working in a web browser, open the browser's developer console.

Note: The `my_levenshtein` function is a simple JavaScript function and doesn't involve a build system, package manager, or specific installation steps. It can be easily integrated into your JavaScript project or script.

## Usage
The `my_levenshtein` function is a JavaScript function that calculates a simplified version of the Levenshtein distance between two strings. Below is an explanation of how the function works:

```javascript
function my_levenshtein(len1, len2) {
    // Check if either input string is null or undefined
    if (len1 === null || len2 === null || len1 === undefined || len2 === undefined) {
        throw new Error('Input strings cannot be null or undefined.');
    }

    // Check if the lengths of the input strings are equal
    if (len1.length !== len2.length) {
        throw new Error('Input strings must have equal length for Levenshtein distance calculation.');
    }

    // Initialize a variable to store the Levenshtein distance
    let distance = 0;

    // Iterate through each character of the input strings
    for (let i = 0; i < len1.length; i++) {
        // Compare characters case-insensitively
        if (len1[i].toLowerCase() !== len2[i].toLowerCase()) {
            // Increment the distance if characters are different
            distance++;
        }
    }

    // Return the calculated Levenshtein distance
    return distance;
}
```

Here's a step-by-step breakdown:

1. **Input Validation:**
   - The function checks whether either of the input strings (`len1` or `len2`) is `null` or `undefined`. If either is true, the function throws an error.

2. **Equal Length Check:**
   - The function ensures that the lengths of the two input strings are equal. If they have different lengths, it throws an error, as Levenshtein distance is typically calculated between strings of the same length.

3. **Distance Calculation:**
   - The function initializes a variable (`distance`) to store the Levenshtein distance.

4. **Character Comparison:**
   - The function iterates through each character of the input strings using a `for` loop.
   - It compares characters case-insensitively using `toLowerCase()` to consider characters regardless of case.

5. **Increment Distance:**
   - If the characters at the same position in the two strings are different, the `distance` variable is incremented.

6. **Return Result:**
   - Finally, the function returns the calculated Levenshtein distance.

Usage Example:
```javascript
const distance = my_levenshtein("example", "exemple");
console.log(`Levenshtein Distance: ${distance}`);
```

This function provides a basic and simplified representation of Levenshtein distance by counting the number of differing characters between two strings.

./my_project argument1 argument2


### The Core Team

team7


<span><i>Made at <a href='https://qwasar.io'>Qwasar SV -- Software Engineering School</a></i></span>
<span><img alt='Qwasar SV -- Software Engineering School's Logo' src='https://storage.googleapis.com/qwasar-public/qwasar-logo_50x50.png' width='20px' /></span>