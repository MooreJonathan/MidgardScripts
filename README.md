# Data Cleaning Scripts for Google Sheets

This repository contains two Google Apps Script functions: `rentalDataClean` and `trafficDataClean`. Both scripts are designed to clean and transform data within a Google Sheets document. Below is a summary of each script, including the main steps they perform.

## 1. rentalDataClean Script

The `rentalDataClean` script is used to clean and process rental data stored in Google Sheets. It performs the following steps:

1. **Filter Rows**: Remove all rows where the URL part 1 is not 'locations' or the URL is simply '/'.
2. **Trim URLs**: Delete rows where there are more than 3 parts in the URL and the value in column B is `0`. Then, reduce all URLs to only parts 1 and 2.
3. **Sum Duplicate URLs**: Combine rows that have duplicate URLs, summing their column B values.
4. **Update Sheet**: Clear the existing data in the sheet and populate it with the cleaned data.

### Usage:
1. The script reads the data from the active Google Sheet.
2. After processing, it updates the sheet by clearing the previous data and setting the new combined values.

## 2. trafficDataClean Script

The `trafficDataClean` script is used to clean up traffic data within a Google Sheets document. It performs the following steps:

1. **Filter Rows**: Remove rows that contain specific keywords such as `area`, `blog`, `locations`, `boat-rv`, `business`, `contact us`, `faq`, `find-storage`, and `test`.
2. **Trim URLs**: Reduce each URL to a simpler format with only one slash and the main part (e.g., `/test`).
3. **Sum Values for Duplicate URLs**: Combine rows with the same URL, summing both `valueA` (column B) and `valueB` (column C).
4. **Update Sheet**: Clear the existing data in the sheet and write the cleaned data back.

### Usage:
1. The script reads the data from the active Google Sheet.
2. It processes the data by filtering rows, trimming URLs, and aggregating values.
3. Finally, it updates the sheet by clearing the previous data and adding the cleaned data.

## Running the Scripts
To run either of the scripts:
1. Open your Google Sheet document.
2. Go to `Extensions` > `Apps Script`.
3. Copy the desired function (`rentalDataClean` or `trafficDataClean`) into the script editor.
4. Save the script and click the run button to execute it.

## Notes
- These scripts work with the currently active sheet in your Google Spreadsheet. Ensure that the correct sheet is active before running the script.
- The scripts clear the existing data before updating the sheet with the cleaned data, so make sure to backup your data if needed.

## License
Feel free to use and modify the scripts as needed.

