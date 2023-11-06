# UFO Sightings Data Cleaning & AWS Integration

## Overview
In this project, I set out to clean a dataset laden with incomplete records of UFO sightings sourced from Kaggle. The primary challenge was the absence of 'country' information in many records, which is vital for geographical analysis of sightings. Fortunately, the dataset was not completely devoid of locational data – it contained 'state', 'province', 'latitude', and 'longitude' details. Leveraging Python, AWS Location Services, and several data manipulation strategies, I enriched the dataset with the missing 'country' data.

## Steps Undertaken

### Dataset Acquisition:
- **Download**: The UFO sightings dataset was obtained from [Kaggle](https://www.kaggle.com/code/hakeemtfrank/ufo-sightings-data-exploration).
- **Preparation**: Post-download, the dataset was extracted and read into a Pandas DataFrame.
- **Inspection**: The 'country' column was identified to have missing values. Interestingly, most records had 'state', 'province', and geographical coordinates intact.

### Data Augmentation with Python Dictionary:
- **Mapping**: I constructed a Python dictionary to associate 'state' and 'province' with corresponding countries.
- **Fill-in**: This mapping facilitated the population of missing 'country' data using the 'state' or 'province' values.
- **Standardization**: Additionally, two supplementary dictionaries were implemented to normalize country identifiers, converting mixed 2 and 3-letter country codes to uniform full country names.

### Leveraging AWS Location Services:
- **Setup**: AWS Location Services was initialized, including the creation of a place index.
- **Geolocation**: The place index was utilized to deduce countries for records lacking this information, based on their latitude and longitude.
  
### Data Export:
- **Cleanup**: I refined the dataset by addressing additional missing or inconsistent values.
- **Output**: The improved dataset was then exported to a new CSV file, primed for deeper analysis.

## Security Considerations
- **API Key Confidentiality**: To safeguard sensitive API credentials, the .env file with the API keys was diligently included in the .gitignore file. This precaution prevents the accidental exposure of API keys in public repositories.

## Required Libraries
To replicate the project or conduct further enhancements, the following libraries are necessary:
```plaintext
- pandas
- boto3
- kaggle
- python-dotenv
- zipfile
```

## Future Improvements
While this project successfully employed AWS Location Services for geolocation purposes, future iterations could explore alternative services like the `geopy` package for diversified data triangulation. Moreover, the sanitized dataset opens up new avenues for more intricate pattern analysis concerning UFO sightings.