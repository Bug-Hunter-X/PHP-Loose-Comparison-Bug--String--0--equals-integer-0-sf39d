# PHP Loose Comparison Bug

This repository demonstrates a common but subtle bug in PHP related to loose comparison (using `==` instead of strict comparison `===`).  The issue arises when comparing a string representation of "0" with the integer 0.  PHP's type juggling will treat them as equal, leading to unexpected results.

## The Bug

The `bug.php` file contains the problematic code.  It attempts to check if user input is equal to 0. However, due to loose comparison, it will incorrectly evaluate the string "0" as equal to the integer 0. 

## The Solution

The `bugSolution.php` file shows the corrected code. By using strict comparison (`===`), we ensure type safety and prevent the unexpected behavior. This ensures that only a numerical value of 0 will pass the condition.

## How to Reproduce

1. Clone this repository.
2. Run `bug.php` with various inputs (e.g., 0, "0", 1, "1"). Note that it will print "Input is zero" for both 0 and "0".
3. Run `bugSolution.php` with the same inputs.  This will accurately distinguish between numeric 0 and string "0".