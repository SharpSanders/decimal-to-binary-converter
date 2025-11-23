# Decimal to Binary Converter

A simple web app that converts a non-negative decimal number to its binary representation, with an optional call stack animation that visually demonstrates how recursion works.

## Demo

- Enter a decimal number in the input field.
- Click **Convert** or press **Enter**.
- The binary result will appear in the output box.
- If you enter **5**, you’ll also see a call stack animation that walks through each recursive step.

## Tech Stack

- **HTML** – structure and layout
- **CSS** – styling and responsive design
- **JavaScript** – input handling, recursion, and call stack animation

## Features

- Converts any non-negative integer to binary.
- Handles invalid input with a clear alert message.
- Allows submission via button click or Enter key.
- Special case for input `5`:
  - Shows a step-by-step **call stack animation**.
  - Explains what each recursive call returns and when it “pops” off the stack.
- Responsive layout using modern CSS (`clamp`, flexbox, media queries).

## How to Run the Project

1. **Clone or download** the repository:

   ```bash
   git clone https://github.com/SharpSanders/decimal-to-binary-converter.git
   cd decimal-to-binary-converter
Open the app:

Option A: Double-click index.html to open it in your browser.

Option B (recommended during development): Use a local server such as the Live Server extension in VS Code.

Once open, you should see the Decimal to Binary Converter interface.

How to Use
In the “Enter a decimal number” input, type a non-negative integer (0 or greater).

Click Convert or press Enter.

The binary result will appear in the highlighted output box.

Special behavior:

If you enter 5, the app:

Shows “Call Stack Animation” in the result area.

Animates three frames inside the Call stack section, explaining:

decimalToBinary(1) (base case)

decimalToBinary(2)

decimalToBinary(5)

After the animation finishes, it displays the final binary result for 5.

How It Works (Recursion + Call Stack)
The core logic lives in script.js:

decimalToBinary(input) is a recursive function:

Base case: if input is 0 or 1, it returns that value as a string.

Recursive case:

Calls itself with Math.floor(input / 2).

Appends (input % 2) to the result.

This builds the binary representation from the most significant bit to the least.

checkUserInput():

Parses and validates the value from the input field.

Shows an alert if the input is empty, not a number, or negative.

If the input is 5, it triggers showAnimation(); otherwise, it directly shows the binary result.

showAnimation():

Uses a predefined animationData array.

Schedules updates with setTimeout to:

Add frames for each recursive call to the DOM.

Replace their text with an explanation message.

Remove them after a delay.

After the animation, it sets the final result text to decimalToBinary(5).

This combination gives a visual, step-by-step demonstration of how the call stack behaves when using recursion.

Project Structure
text
Copy code
decimal-to-binary-converter/
├── index.html   # Markup for the converter UI and call stack section
├── styles.css   # Styling for layout, colors, and responsive design
└── script.js    # Logic for input handling, recursion, and animation
What I Practiced
Working with the DOM API (getElementById, event listeners, etc.).

Implementing and understanding recursive functions.

Visualizing the call stack using timed DOM updates.

Using setTimeout for basic UI animations.

Building a small, self-contained front-end project suitable for a portfolio.

Future Improvements
Add support for:

Larger numbers with formatted output.

Negative numbers using two’s complement (or clearly rejecting them in the UI).

Show the call stack animation for any valid input, not just 5.

Add a history section listing previous conversions.

Add a toggle for light/dark themes and more advanced styling.

Add tests for the conversion logic.
**Live Site**
https://sharpsanders.github.io/decimal-to-binary-converter/

Author
Created by Trevyn Sanders.