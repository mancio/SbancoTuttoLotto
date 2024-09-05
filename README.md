
# Polish Lotto Extraction Analysis

This repository contains a Jupyter notebook that automates the extraction, analysis, and visualization of Polish Lotto draw results. The notebook processes lotto data from provided text files, analyzes the frequency of drawn numbers, filters results by date, and provides various statistical insights, including visualization through color gradients and trend analysis.

## Features

- **Data Download:** Automatically downloads Lotto, Lotto Plus, and Mini Lotto results from a designated source and saves them as text files.
- **Data Analysis:** Parses and structures the downloaded data into a format suitable for analysis.
- **Date Filtering:** Allows users to filter Lotto results by a specified date range.
- **Frequency and Trend Analysis:** Counts and visualizes the frequency of drawn numbers, with trends over time.
- **Number Combination Analysis:** Analyzes pairs, triplets, and quadruplets of numbers for their likelihood of being drawn.
- **Dynamic Number Suggestions:** Offers suggestions for the most probable numbers based on the game type (Lotto vs. Mini Lotto).
- **Support for Multiple Lotto Types:** The notebook supports Polish Lotto, Lotto Plus, and Mini Lotto.

## Prerequisites

Make sure you have the following libraries installed before running the notebook:

```bash
pip install matplotlib numpy requests
```
## Usage

1. **Download the Notebook:** Clone this repository and navigate to the project directory.

2. **Download Lotto Data:**
   - Visit the [Polish Lotto results page](http://www.mbnet.com.pl/wyniki.htm) to manually download the Lotto results.
   - Save the files in the main directory as:
     - `lotto.txt`
     - `miniLotto.txt`
     - `lottoPlus.txt`
   - Alternatively, the notebook will automatically download and rename these files when run.

3. **Run the Notebook:**
   - Open `lottoPLFromTxt.ipynb` in Jupyter Notebook.
   - Run the cells sequentially to:
     1. Download or load Lotto data.
     2. Parse and process the data.
     3. Filter and analyze the results.
   
4. **Select a Date Range:**
   - Modify the `start_date` and `end_date` variables in Cell 7 to filter the Lotto results by a specific date range.

5. **Frequency and Trend Analysis:**
   - The notebook calculates and visualizes the frequency of drawn numbers in the selected date range.
   - Trend analysis examines how the likelihood of specific numbers or combinations changes over time.

## Functions and Code Details

- **`read_lotto_data_from_txt(file_path)`**: 
  - Reads Lotto data from a text file and parses it into a structured dictionary format.

- **`filter_lotto_results_by_date(lotto_results, start_date, end_date)`**:
  - Filters the Lotto results by the given start and end dates.

- **Visualization**:
  - Visualizations are created using `matplotlib` to plot frequency results with color gradients for easy interpretation.


## Notes

- Ensure that the text files (`lotto.txt`, `miniLotto.txt`, `lottoPlus.txt`) are placed in the correct directory before running the notebook.
- Lotto data is dynamically fetched and analyzed; users can visualize results within the defined date ranges.

## License

This project is open-source under the [MIT License](LICENSE).
