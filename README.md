
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

## Notebook Structure and Cell Descriptions

1. **Cell 1: Description**
   - Provides an overview of the notebook, explaining that it fetches Lotto extraction data, performs frequency analysis, and visualizes the results.
   - Instructions to download the necessary Lotto data files manually from [here](http://www.mbnet.com.pl/wyniki.htm) and save them as `lotto.txt`, `miniLotto.txt`, and `lottoPlus.txt` in the main directory.

2. **Cell 2: Importing Required Libraries**
   - Installs the necessary libraries (`matplotlib`, `numpy`, `requests`) if they are not already installed.
   - Imports the following Python libraries:
     - `matplotlib.pyplot`: Used for plotting visualizations.
     - `numpy`: Useful for numerical operations.
     - `itertools.combinations`: Used to generate combinations of Lotto numbers.
     - `collections.Counter`: Useful for counting occurrences (used in frequency analysis).
     - `requests`: Used for downloading Lotto data from the web.
     - `datetime`: Used for manipulating date-related data.

3. **Cell 3: Download Latest TXT Files**
   - Defines the URLs for downloading Lotto, Lotto Plus, and Mini Lotto data.
   - Downloads these files from the web using `requests` and renames them to `lotto.txt`, `lottoPlus.txt`, and `miniLotto.txt`, respectively.
   - The files are saved in the main directory.
   - If the download is unsuccessful, an error message is printed.

4. **Cell 4: Select the File with the Lotto Number List**
   - Allows the user to choose the Lotto file (`lotto.txt`) for further data processing.

5. **Cell 5: Function to Fetch Lotto Data**
   - Defines a function `read_lotto_data_from_txt(file_path)` that reads Lotto data from the selected text file.
   - This function splits each line of the file to extract the draw number, date, and drawn Lotto numbers.
   - Returns a dictionary where each draw number is mapped to its respective date and Lotto numbers.

6. **Cell 6: Function to Filter Lotto Results by Date**
   - Defines a function `filter_lotto_results_by_date(lotto_results, start_date, end_date)` to filter Lotto results within a specified date range.
   - Converts `start_date` and `end_date` from strings to `datetime` objects and filters the dictionary based on these date limits.
   - Returns a dictionary of Lotto results within the given date range.

7. **Cell 7: Example Usage of Date Filtering**
   - An example usage where `start_date` is set to `"01.01.2024"` and `end_date` is set to `"30.12.2024"`.
   - Filters the Lotto results using the previously defined `filter_lotto_results_by_date` function.

8. **Cell 8: Display Total Draws in the Selected Period**
   - Displays the total number of Lotto draws in the selected date range by printing the length of the filtered results dictionary.

9. **Cell 9: Display the Last 10 Draws**
   - Prints the last 10 Lotto draws (most recent results) in the filtered dataset.
   - For each draw, it prints the play number, date, and the drawn numbers.

10. **Cell 10: Frequency Analysis**
    - Performs a frequency analysis of all Lotto numbers in the filtered data.
    - Uses `Counter` from the `collections` library to count how often each Lotto number appears in the selected date range.
    - Visualizes the frequency of each number using a bar chart created with `matplotlib`.
    - A color gradient is applied to visually differentiate between the frequencies of various numbers.

## Additional Analyses

### Trend Analysis

This analysis examines how the frequency of specific numbers or combinations changes over time. By analyzing historical data, users can identify whether certain numbers or combinations are becoming more or less frequent.

### Print the Five Most and Least Probable Numbers

```markdown
## Print the five more and less probable numbers
```

This section of the notebook identifies and prints the five most frequently drawn numbers as well as the five least frequently drawn numbers. This information helps users understand which numbers are trending and which are less likely to be drawn.

### Verifying if the Most or Least Probable Sets of Five Numbers Have Been Previously Drawn

```markdown
## Verifying if the Most or Least Probable Sets of Five Numbers Have Been Previously Drawn
```

This analysis checks whether the most probable or least probable sets of five numbers have ever been drawn together in previous Lotto results. This can offer insights into the patterns of drawn numbers.

### Comprehensive Analysis of Lotto Number Combinations: Pairs, Triplets, and Quadruplets

This section expands on the frequency analysis by looking at combinations of Lotto numbers, such as pairs, triplets, and quadruplets. The goal is to identify combinations of numbers that are more or less likely to appear together based on historical data.

### Detailed Analysis of Lotto Number Distributions and Trends

In this analysis, Lotto number distributions are further explored. It focuses on understanding how Lotto numbers are distributed across time, and it identifies any notable patterns or trends in the Lotto data.

### Dynamic Number Suggestion Based on Game Type (Lotto vs Mini Lotto)

This feature offers dynamic number suggestions based on the game type selected by the user. For example:
- **Lotto**: Suggests numbers based on the Lotto results.
- **Mini Lotto**: Suggests numbers based on Mini Lotto results.

This dynamic suggestion system adapts the analysis depending on which Lotto game the user is interested in.

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

## Example Usage

```python
# Example of filtering results by date
start_date = "01.01.2024"
end_date = "31.12.2024"
lotto_results = filter_lotto_results_by_date(lotto_results, start_date, end_date)
```

## Notes

- Ensure that the text files (`lotto.txt`, `miniLotto.txt`, `lottoPlus.txt`) are placed in the correct directory before running the notebook.
- Lotto data is dynamically fetched and analyzed; users can visualize results within the defined date ranges.

## License

This project is open-source under the [MIT License](LICENSE).
