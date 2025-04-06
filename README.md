# Automated-report-generation

*COMPANY*: CODTECH IT SOLUTIONS

*NAME*: MANASA.S

*INTERN ID*: CT04WT288

*DOMAIN*: PYTHON PROGRAMMING

*DURATION*: 4 WEEKS

*MENTOR*: NEELA SANTOSH

# Explanation of the Student Score Report Generator Code

This code creates an automated PDF report that displays student scores and summary statistics. Let me break down each section:

## Data Preparation
import pandas as pd
from fpdf import FPDF

# Read data from CSV

- **Imports**: The code imports two libraries:
  - `pandas`: For data manipulation and analysis
  - `fpdf`: For PDF generation

- **Data Creation**: Instead of reading from an actual CSV file, the code creates a sample DataFrame directly with:
  - 5 students (Alice, Bob, Charlie, David, Emma)
  - Their corresponding scores (85, 92, 78, 95, 88)

## Data Analysis
# Analyze data
average_score = data['Score'].mean()
max_score = data['Score'].max()
min_score = data['Score'].min()
top_student = data.loc[data['Score'].idxmax(), 'Name']

- **Calculates statistics** on the student scores:
  - `average_score`: The mean of all scores
  - `max_score`: The highest score
  - `min_score`: The lowest score
  - `top_student`: The name of the student with the highest score
    - `data['Score'].idxmax()` finds the index of the maximum score
    - `data.loc[index, 'Name']` retrieves the name at that index

## PDF Report Class Definition
  
- **Custom PDF Class**: Creates a class `PDFReport` that inherits from FPDF
- **Header Method**: Automatically adds to the top of each page:
  - Sets font to bold Arial, size 16
  - Adds a centered title "Student Score Report"
  - Adds 10 units of vertical space
- **Footer Method**: Automatically adds to the bottom of each page:
  - Positions 15 units from bottom (`set_y(-15)`)
  - Sets font to italic Arial, size 10
  - Adds a centered page number

## PDF Generation
- Creates an instance of the custom PDF class
- Adds the first page to the document
- Sets the default font to regular Arial, size 12

## Adding Student Data

- Adds a section title "Scores by Student:"
- - Adds 5 units of vertical space
- Loops through each row in the DataFrame:
  - For each student, adds a line with their name and score
  - `ln=True` creates a new line after each entry

## Adding Summary Statistics

- Adds 10 units of vertical space
- Sets font to bold for the section title
- Adds "Summary Statistics:" as a section header
- Returns to regular font
- Adds three lines with the calculated statistics:
  - Average score (formatted to 2 decimal places)
  - Highest score (including the name of the top student)
  - Lowest score (including the name of the top student)

## Saving the PDF

- Saves the generated PDF to a file named "report.pdf"
- Prints a confirmation message to the console

This code demonstrates a simple but effective automated report generation system that takes data, performs analysis, and creates a formatted PDF document with both raw data and derived insights.

*Output*

![Image](https://github.com/user-attachments/assets/2e2b001e-85c7-46b3-933f-5768497116a1)


![Image](https://github.com/user-attachments/assets/c1447241-a677-4d6a-b53f-cf2d6b11d9b3)

