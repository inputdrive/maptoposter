# Plan: Make create_map_poster.py Interactive

## 1. Remove Argparse Logic
- Locate the section using argparse for CLI argument parsing.
- Remove or comment out argparse setup and usage.

## 2. Add Interactive Input Function
- Create a function (e.g., `interactive_input()`) that:
  - Prints a welcome message.
  - Prompts the user for each parameter (city, country, theme, distance, etc.) using `input()`.
  - Provides sensible defaults (e.g., theme = "feature_based", distance = 29000).
  - Optionally, allow the user to leave city/country blank and enter a zip code if supporting zip codes.

## 3. Update Main Entry Point
- In the `if __name__ == "__main__":` block:
  - Call `interactive_input()` to get user input.
  - Pass the collected values to the main poster creation logic (e.g., `create_poster()`).

## 4. Adjust Poster Creation Logic
- Ensure `create_poster()` and related functions accept parameters directly (not via `args`).
- Update any references to `args.city`, `args.country`, etc., to use the new variables.

## 5. (Optional) Add Input Validation
- Check that required fields are not empty.
- Validate that distance is a positive integer.
- Optionally, re-prompt if invalid input is given.

## 6. (Optional) Update README
- Add a section describing the new interactive usage.
- Remove or update CLI flag instructions.

## 7. Test
- Run the script and verify it prompts for all parameters and works as expected.