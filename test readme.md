Sure, here's a README.md file that explains the code:

# CSV Data Extractor

This Python script reads a CSV file and extracts specific data from each row, formatting the output in a specific way.

## Usage

To run the script, you need to provide the CSV file name as a command-line argument:

```
python script.py <filename.csv>
```

Replace `<filename.csv>` with the actual name of the CSV file you want to process.

## How it Works

1. The script first checks if the correct number of arguments (2) is provided. If not, it prints a usage message and exits.
2. It then reads the file name from the second argument (`sys.argv[1]`) and opens the file for reading.
3. The script skips the header row and then iterates through each row in the CSV file.
4. For each row, it extracts the following data:
   - Date
   - S (SPY) open and close values
   - Q (QQQ) open and close values
   - V (VIX) open and close values
5. It then prints the extracted data in the following format:

   ```
   S is SPY opened as <s_open> and closed as <s_close>
   Q is QQQ opened as <q_open> and closed as <q_close>
   V is VIX opened as <open_price> and closed as <close>
   Date: <date>
   ```

   This is repeated for each row in the CSV file.

## Requirements

- Python 3.x

## Example Output

```
S is SPY opened as 409.179993 and closed as 413.470001
Q is QQQ opened as 314.829987 and closed as 319.170013
V is VIX opened as 18.83 and closed as 17.799999
Date: 2023-04-13

S is SPY opened as 412.809998 and closed as 412.459991
Q is QQQ opened as 317.589996 and closed as 318.570007
V is VIX opened as 17.940001 and closed as 17.07
Date: 2023-04-14

...
```
