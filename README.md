# ThermalComfort
This repository includes the BiLSTM-based approach for the paper: "K. Katsarou, C. Ounoughi, A. Mouakher and C. Nicolle, "STCMS: A Smart Thermal Comfort Monitor For Senior People," 2020 IEEE 29th International Conference on Enabling Technologies: Infrastructure for Collaborative Enterprises (WETICE), Bayonne, France, 2020, pp. 187-192, doi: 10.1109/WETICE49692.2020.00044".
## Getting Started
The project is about predicting the thermal comfort of senior people. 
For running the framework, this work recommends creating a new virtual environment which uses the python version 3.8.8
Afterwards, install the packages in the requirements.txt of the requirements_files directory to get started.

**For Bash:**  

python3 -m venv .venv  
source .venv/bin/activate  
pip install -r requirements.txt

**Datasets:**

We use the datasets from the papers of Hughes and Natarajann: 
1) Hughes, C. (Creator), Natarajan, S. (Creator), Liu, C. (Creator), Chung, W. (Creator), Herrera Fernandez, M. (Creator) (4 Sept 2019). Dataset for "Winter thermal comfort and health in the elderly". University of Bath. 10.15125/BATH-00537
https://researchdata.bath.ac.uk/537/




The dataset is included in the folder "Winter_thermal_comfort_dataset" where Bedroom_data.csv has the temperature time series for in the bedroom the different House IDs, the living_room_data.csv has the temperature time series for the living room, and PMV_TSV.xlsx has the PMV and TSV values for each House ID and different month and year. From the Temperatures.csv we use the t_mean_ext that has the mean external temperatures per month.

**Preprocessing the temperature sequences**

For transforming the living room and bedroom temperature time series in the right format to be used by the LSTM model we use the Thermal_Comfort_preprocessing.ipynb.

Resulting Sequences After the preprocessing we create seperated csv files per month and year for 11/2016, 12/2016, 01/2017, 02/2017, 03/2017, 12/2017, 01/2018, 02/2018, 03/2018. These files include the time series for each House ID for the bedroom and living room for the specific month and year. The last value for each time series has the TSV value (if there is one), while living room and bedroom teperature time series has the same TSV value as a last value.

**LSTM training and inference**

The file Thermal_Comfort_LSTM.ipynb has the trained model and the inference results.


