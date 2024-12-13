# Project1

README: Spain Airport Traffic Analysis

Overview

This project analyzes airport traffic in Spain, combining multiple datasets and generating insights into passenger flows, flight patterns, and tax revenues. The analysis covers:

Airport Traffic Data: Integration and cleaning of traffic data for Spanish airports.

Flight Leg Matching: Identification and validation of flight origin and destination.

Passenger Tax Analysis: Calculation of national and international airport taxes.

Visualization: Graphical representation of tax revenues by year.

Datasets Used

1. Combined Airport Traffic Data

Source: Internal/External CSV/Excel files.

Key Columns:

APT_ICAO: ICAO airport codes.

FLT_DATE: Flight date.

STATE_NAME: Country of the airport.

2. Airport Taxes Data

Source: Airport_Taxes.xlsx

Key Columns:

IATA: IATA airport codes.

YR, Security (National), Security (International):
Components of national and international taxes.

3. Spain Flights Data

Source: avia_par_es.xlsx

Key Columns:

LEG: Flight route as "Origin - Destination".

TIME: Period of operation.


Workflow

Data Preprocessing

Merge multiple data sources on IATA and ICAO codes.

Extract and format dates (FLT_DATE to YYYY-MM-DD).

Reorganize columns for logical consistency.

Flight Leg Validation

Validate LEG (flight routes) using regex patterns.

Split flight legs into Origin and Destination.

Standardize airport names for consistency.

Best Match for Airports

Using process.extractOne, match flight origins/destinations with known airport names:

Outputs: Best_Match_Origin, Score_Origin, Best_Match_Destination, Score_Destination.

Correct mismatches manually for high-confidence matches.

Passenger Type and Tax Analysis

Separate passenger data by Flight_Type (Domestic D or International I).

Melt and pivot data for granular insights.

Calculate taxes:

National_tax = (YR + Security (National)) * Domestic_Passengers

International_tax = (YR + Security (International)) * International_Passengers

Visualization

Tax Revenue Analysis

A bar chart showing national and international tax revenues by year.

Highlights:

Custom color palette for clarity.

Data labels for precise values.

Dependencies

Python Libraries:

pandas: Data manipulation.

matplotlib: Visualization.

seaborn: Enhanced plotting.

fuzzywuzzy: String matching.

Files Required:

Airport_Taxes.xlsx

avia_par_es.xlsx

How to Run

Install required Python libraries.

pip install pandas matplotlib seaborn fuzzywuzzy

Place data files in the appropriate directory.

Run the script.

Output

Processed Datasets:

Cleaned and merged traffic data.

Validated and standardized flight legs.

Visualizations:

Yearly tax revenue charts.

Insights:

Key trends in passenger flow and tax revenues.

Future Improvements

Automate airport name matching for scalability.

Incorporate more robust validation for flight legs.

Enhance visualizations with interactive dashboards (e.g., Plotly, Dash).

Contributors

Adolfo Artola Madrigal
