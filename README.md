# Field Validation and Filtering

You are working on a system where users can type any kind of characters into a free-form text field. Some users enter letters, some enter numbers, and some enter complete nonsense.
To clean this input before it is processed by the system, a filtering mechanism must be applied.
The rules for what should stay and what should be transformed are defined by two lists provided by the business team: one list of allowed letters and one list of allowed numbers.

Your task is to implement this filtering logic.

You are given:

- A string input
- An array of allowed letters `allowedLetters`
- An array of allowed numbers `allowedNumbers`

Your task is to produce a filtered version of the input string following the rules below.

## Rules

If input is null or an empty string, the result should be an empty string.

The input may contain letters, digits, and any other characters.

### Letters

Only characters that appear in `allowedLetters` should remain in the result.

Any other letters should be excluded.

### Numbers

Only numeric characters that appear in `allowedNumbers` should be considered.

The numeric characters that are considered valid should not keep their original ordering.

Instead, the numeric positions in the final string must use these valid numbers arranged in increasing order.

The order where letters appear must remain unchanged.

### Additional Requirement

Neither `allowedLetters` nor `allowedNumbers` should be modified.

## Examples

### Example 1
**Input:** `"a1b2c3"`  
**allowedLetters:** `['a', 'c']`  
**allowedNumbers:** `[2, 3]`  
**Output:** `"a2c3"`

*Explanation:* Letter 'b' is removed (not in allowedLetters). Number '1' is removed (not in allowedNumbers). Valid numbers 2,3 are arranged in increasing order at their numeric positions.

### Example 2
**Input:** `"x5y9z1"`  
**allowedLetters:** `['x', 'z']`  
**allowedNumbers:** `[1, 5]`  
**Output:** `"x1z5"`

*Explanation:* Letter 'y' is removed. Number '9' is removed. Valid numbers 1,5 are sorted and placed at numeric positions.

### Example 3
**Input:** `"abc"`  
**allowedLetters:** `['a', 'b', 'c']`  
**allowedNumbers:** `[1, 2, 3]`  
**Output:** `"abc"`

*Explanation:* No numbers in input, so only letters are filtered.

### Example 4
**Input:** `"123"`  
**allowedLetters:** `['a', 'b']`  
**allowedNumbers:** `[2, 3]`  
**Output:** `"23"`

*Explanation:* No letters in input. Number '1' is removed. Valid numbers 2,3 remain in sorted order.

### Example 5
**Input:** `""`  
**allowedLetters:** `['a']`  
**allowedNumbers:** `[1]`  
**Output:** `""`

*Explanation:* Empty input returns empty string.
