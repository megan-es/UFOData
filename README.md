UFO Sightings Data Cleaning & AWS Integration 

Overview:
In this project, a dataset containing records of UFO sightings was acquired from Kaggle. A significant issue encountered was the omission of country values, making analysis of UFO sightings' locations challenging. However, the available state, province, latitude, and longitude data provided an opportunity to deduce or retrieve the missing country information. Through the utilization of Python dictionaries, AWS Location Services, and data manipulation techniques, we successfully enhanced the dataset.

Steps:
Dataset Acquisition:
Downloaded the UFO sightings dataset from Kaggle. (https://www.kaggle.com/code/hakeemtfrank/ufo-sightings-data-exploration)
Extracted the dataset and read it into a Pandas DataFrame.

Identified missing values in the 'country' column.
Observed that many records had the 'state' and 'province' columns filled in.
Latitude and longitude values were often present even when the country was missing.

Data Augmentation with Python Dictionary:
Created a dictionary to map state and province values to their respective countries.
Used the dictionary to fill in missing countries based on available state or province data.
Additionally, two more dictionaries were utilized to standardize the country naming format in the dataset, converting a mix of 2 and 3-letter country codes to full country names.

Leveraging AWS Location Services:
Initialized AWS Location Services and created a place index.
Used the place index to retrieve countries based on latitude and longitude for rows with missing country values.
Data Export:
Finalized the dataset by cleaning up any additional missing or inconsistent values.
Exported the augmented dataset to a new CSV file for further analysis.

Security Considerations:
Hiding API Key:
For security reasons, especially to avoid exposing sensitive API credentials, the .env file containing API keys was added to the .gitignore file. This ensures that the API keys are not accidentally pushed to public repositories.

Required Libraries:
pandas
boto3
kaggle
python-dotenv
zipfile

Future Improvements:
While AWS Location Services was used in this project, there's potential to integrate other geolocation services like the geopy package.
Further data exploration can be done to understand UFO sighting patterns based on the cleaned dataset.