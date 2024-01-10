# Camera-EDA-pythonNikhil Analytics Camera EDA Project
Overview
This repository contains an exploratory data analysis (EDA) project conducted in Python focusing on a dataset of approximately 1000 cameras. The project aims to explore, clean, and derive insights from this dataset containing various properties such as weight, focal length, price, etc.

Project Tasks
The following tasks were accomplished in this EDA project:

Task 1: Created a DataFrame "Camera_data" using the provided "Camera.csv". 

Task 2: Calculated the percentage of blank values in each column.

Task 3: Viewed the statistical summary of the data.
Task 4: Replaced all blank values with NaN.
Task 5: Replaced blank values with respective column medians.
Task 6: Added a new column "Discounted_Price" with a 5% discount on the Price column.
Task 7: Dropped columns "Zoom Tele" & "Macro Focus range".
Task 8: Replaced the Model Name "Agfa ePhoto CL50" with "Agfa ePhoto CL250".
Task 9: Renamed the column from "Release Date" to "Release Year".
Task 10: Identified the most expensive camera.
Task 11: Found the camera with the least weight.
Task 12: Grouped the data based on release year.
Task 13: Extracted specific columns: Name, Storage Include, Price, Discounted_Price & Dimensions.
Task 14: Extracted records for cameras released in 2005 & 2006.
Task 15: Identified the most expensive & cheapest camera in 2007.
Task 16: Determined the year with the maximum number of models released.
Files
Camera.csv: Dataset used for the analysis.
python_script.py (or notebook.ipynb): Python script or Jupyter Notebook containing the code for the tasks.
Usage
Clone the repository:
bash
Copy code
git clone https://github.com/YourUsername/Nikhil-Analytics-Camera-EDA-Python.git
Install the required dependencies (if specified).
Run the Python script or open the Jupyter Notebook to reproduce the analysis.
Explore the code and findings for each task.
Dependencies
Python 3.x
pandas
numpy
Contribution
Contributions are welcome! Feel free to fork this repository, create your branch, and propose changes via pull requests.

License
This project is licensed under the MIT License.
