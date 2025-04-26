# Bill Parser and Cashback Analyzer

This Python script parses a credit card bill PDF (specifically for Citibank SMRT cards) and identifies which transactions contributed to the bonus cashback earned.  
It automates the process of figuring out which merchants gave 5% bonus cashback and estimates the total cashback breakdown.

## Features
- Extracts and parses transactions directly from a PDF bill.
- Identifies bonus cashback earned from eligible merchants.
- Uses multiprocessing to speed up the search for the best merchant combinations.
- Calculates both the bonus (4.7%) and standard (0.3%) cashback portions.
- Helps you optimize spending based on cashback performance.

## Requirements
- Python 3.8+
- Libraries:
  - `pdfplumber`
  - `re` (built-in)
  - `itertools` (built-in)
  - `multiprocessing` (built-in)

You can install `pdfplumber` with:

```bash
pip install pdfplumber
```
## Usage
```bash
python billprser.py /path/to/your/credit_card_bill.pdf
```

## How it works
1. Extracts the bonus cashback amount ("earned this month") from the bill.
2. Parses all transaction lines and sums up spending by merchant.
3. Searches for the best combination of merchants that explains the bonus cashback.
4. Outputs:
  - List of merchants that contributed to bonus cashback.

## Notes
- This script assumes a specific text layout similar to Citibank SMRT statements.
- It uses simple regex parsing; future formatting changes in the bill may require updates.
- Confirmed included and excluded merchants can be adjusted manually in the script.
