# DS231 Assignment 2

## Overview and Objectives
In this assignment, you will write a series of programs that simulate how a plant grows in a greenhouse under different conditions. Through this multi-part problem set, you will practice using conditional statements and loops to model real-world processes that change over time.

## Instructions
1. Create a separate Python file (`.py`) for each part. The filename must match the one specified in the part exactly (e.g., `part1.py`).
2. Ensure that each program runs without errors. If your code fails to execute, a flat 20% penalty will be applied, regardless of the nature of the error.
3. Your program output must match the expected format shown in the "Example output" of each part.
4. Unless stated otherwise, follow these formatting rules for all printed values. **User inputs** should be printed with no unnecessary trailing zeros — use the `g` format specifier in an f-string for this. For example, `f"{2.0:g}"` gives `"2"` and `f"{1.50:g}"` gives `"1.5"`. **Computed values** should always be printed rounded to exactly 2 decimal places — use the `round()` function for this. The function works as `round(number, decimal_places)`. For example, `round(11.5752, 2)` gives `11.58`.
5. Use the `input()` function to collect user input. Since `input()` always returns a string, you must convert it to the appropriate type before using it in calculations.


## Part 1. Fixed Daily Compound Growth [25 Points]
Create a file named `part1.py`.

You're managing a research greenhouse that monitors the growth of experimental plants. Your goal is to project a plant's height after a period of time using a program that models how plants grow under different conditions. As a start, we assume the plant grows by a fixed percentage of its current height every day — this is called **daily compound growth**.

### Task 1.1 — User Input

Ask the user to enter the following information. You must use the exact variable names listed below, and prompt for them in this exact order:

- `initial_height` — starting height of the plant in cm
- `daily_growth` — daily growth rate as a decimal (e.g. `0.02` for 2%)
- `days` — number of days to simulate

### Task 1.2 — Calculate Final Height

Calculate the final height of the plant at the end of the period specified by the user. The plant's height should be initialized at `initial_height`, and for each following day it increases by the `daily_growth` rate.

### Task 1.3 — Print the Result

Print the projected height of the plant after the given period of time.

***Example output.*** Your program's output must match the format below exactly. The input values used for each example are shown above each block.

`initial_height = 10`, `daily_growth = 0.05`, `days = 3`
```text
After 3 days, the plant is 11.58 cm tall.
```

`initial_height = 25`, `daily_growth = 0.10`, `days = 5`
```text
After 5 days, the plant is 40.26 cm tall.
```

`initial_height = 15.5`, `daily_growth = 0.03`, `days = 7`
```text
After 7 days, the plant is 19.06 cm tall.
```


## Part 2. Include Weekly Nutrient Boost [25 Points]
Create a file named `part2.py`.

In your greenhouse setup, a nutrient boost is automatically administered every 7 days. This causes a one-time increase in the plant's height on top of the regular daily growth. Your goal is to project the plant's height after a given number of days, accounting for both daily compound growth and periodic additive boosts.

### Task 2.1 — User Input

Ask the user to enter the following information. You must use the exact variable names listed below, and prompt for them in this exact order:

- `initial_height` — starting height of the plant in cm
- `daily_growth` — daily growth rate as a decimal (e.g. `0.02` for 2%)
- `days` — number of days to project
- `boost_amount` — how many cm the plant grows instantly every 7th day

### Task 2.2 — Calculate Final Height with Boost

Project the plant's height over the given number of days. On each day, apply the daily compound growth first. On every 7th day, apply the nutrient boost **after** the daily growth — this ensures the boost does not contribute to compound growth on the day it is given.

### Task 2.3 — Print the Result

Print a clearly formatted message summarizing the number of days, the size and frequency of the nutrient boost, and the final projected height.

***Example output.*** Your program's output must match the format below exactly. The input values used for each example are shown above each block.

`initial_height = 10`, `daily_growth = 0.05`, `days = 7`, `boost_amount = 2.0`
```text
After 7 days (with a 2 cm boost every 7th day), the plant is 16.07 cm tall.
```

`initial_height = 15.5`, `daily_growth = 0.03`, `days = 14`, `boost_amount = 1.5`
```text
After 14 days (with a 1.5 cm boost every 7th day), the plant is 26.79 cm tall.
```

`initial_height = 8`, `daily_growth = 0.08`, `days = 6`, `boost_amount = 2.0`
```text
After 6 days (with a 2 cm boost every 7th day), the plant is 12.69 cm tall.
```


## Part 3. Estimating Time to Reach a Target Height [25 Points]
Create a file named `part3.py`.

In this part, you will write a program to determine how many days it takes for a plant to reach or exceed a target height. The plant grows by a fixed percentage each day, and every 7th day it receives a one-time nutrient boost. Your program must account for both types of growth when estimating the time needed.

### Task 3.1 — User Input

Ask the user to enter the following information. You must use the exact variable names listed below, and prompt for them in this exact order:

- `initial_height` — starting height of the plant in cm
- `daily_growth` — daily growth rate as a decimal (e.g. `0.02` for 2%)
- `target_height` — the desired height to reach
- `boost_amount` — height added every 7th day

### Task 3.2 — Simulate Growth Day by Day

Simulate the plant's growth one day at a time until the height reaches or exceeds `target_height`. On each day, apply the daily compound growth first. On every 7th day, apply the nutrient boost after the daily growth. Keep track of the number of elapsed days.

### Task 3.3 — Print the Result

After computing the number of days needed to reach the target height, print the result.

***Hint.*** The number of days here is a count, not a measurement, so it should be printed as a whole number. If you track it using an integer variable, it will print correctly without any extra formatting.

***Example output.*** Your program's output must match the format below exactly. The input values used for each example are shown above each block.

`initial_height = 10`, `daily_growth = 0.05`, `target_height = 25`, `boost_amount = 1.5`
```text
After 16 days (with a 1.5 cm boost every 7th day), the plant reaches at least 25 cm.
```

`initial_height = 7.5`, `daily_growth = 0.02`, `target_height = 10`, `boost_amount = 1.0`
```text
After 9 days (with a 1 cm boost every 7th day), the plant reaches at least 10 cm.
```

`initial_height = 12`, `daily_growth = 0.01`, `target_height = 13`, `boost_amount = 0.5`
```text
After 7 days (with a 0.5 cm boost every 7th day), the plant reaches at least 13 cm.
```


## Part 4. Finding the Minimum Boost Frequency [25 Points]
Create a file named `part4.py`.

You are running a time-sensitive plant experiment and want your plant to reach a specific height within a fixed number of days. The plant grows by a fixed percentage every day, and you can apply a nutrient boost periodically. Your goal is to determine how infrequently you can apply the boost and still meet the target height by the end of the experiment.

### Task 4.1 — User Input

Ask the user to enter the following information. You must use the exact variable names listed below, and prompt for them in this exact order:

- `initial_height` — starting height of the plant in cm
- `daily_growth` — daily growth rate as a decimal (e.g. `0.02` for 2%)
- `target_height` — desired height to reach by the end
- `days` — total number of days available
- `boost_amount` — amount added to height each time a boost is applied

### Task 4.2 — Find the Least Frequent Boost Schedule

Determine the least frequent boost schedule that still allows the plant to reach `target_height` within the given number of days. Consider all possible boost intervals and identify the largest interval that works — that is, the one that requires boosting least often. If multiple intervals allow the plant to meet the target, report the largest one. If no interval works, including applying the boost every single day, report that the target is not achievable within the given number of days.

### Task 4.3 — Print the Result

After your program determines the least frequent boost interval, print the result.

***Hint.*** The boost interval here is a count of days, not a measurement, so it should be printed as a whole number. If you track it using an integer variable, it will print correctly without any extra formatting.

***Example output.*** Your program's output must match the format below exactly. The input values used for each example are shown above each block.

`initial_height = 10`, `daily_growth = 0.05`, `target_height = 30`, `days = 20`, `boost_amount = 1.5`
```text
To reach at least 30 cm in 20 days, apply a 1.5 cm boost every 10 days.
```

`initial_height = 8`, `daily_growth = 0.01`, `target_height = 50`, `days = 15`, `boost_amount = 1.0`
```text
Target height not achievable within 15 days, even with daily boosts.
```
