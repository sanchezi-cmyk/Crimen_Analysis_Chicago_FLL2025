# Chicago Crime Dynamics: A Spatio-Temporal Analysis of Trends and Hotspots (2001–Present)

## Group Members
* **Drew Flinn**
* **Iker Sanchez**

## Project Links
* [Google Colab Worksheet](https://colab.research.google.com/drive/1cmOJK7s04Herf4NESWXpy-bdT0StSGvp?usp=sharing)

---

## Introduction

### Data and Data Source
The dataset analyzed in this project is the "Chicago Crime Incidents 2001 to Present," sourced from the Chicago Police Department's CLEAR (Citizen Law Enforcement Analysis and Reporting) system. We accessed this data via Kaggle, where it is maintained as a public record of reported incidents of crime (excluding murders, where data exists for each victim) that occurred in the City of Chicago. The dataset is extensive, containing millions of records spanning over two decades. Each record represents a distinct incident and includes key variables such as the date and time of the occurrence, block-level address, crime type (categorized by Illinois Uniform Crime Reporting - IUCR codes), location description (e.g., street, residence), arrest status, and domestic classification. Crucially for our spatial analysis, the data includes latitude and longitude coordinates for the majority of incidents.

### Research Questions
This analysis attempts to answer two primary questions regarding the evolution of crime in Chicago:
1.  **Spatial Evolution:** How have the geographic locations ("hotspots") of crimes changed from year to year? We aim to determine if crime remains concentrated in specific neighborhoods or if these high-density areas migrate over time.
2.  **Volume and Composition:** Has there been a significant change in the overall volume and specific types of crimes committed over the years? We seek to identify trends in the most frequently reported crimes and observe how their prevalence has shifted throughout the 21st century.

### Analysis Approach
Our approach involves a combination of time-series aggregation and geospatial visualization. To address the first question, we will utilize latitude and longitude data to generate heatmaps for different years, allowing us to visually track the movement and intensity of crime hotspots. For the second question, we will aggregate the data by year and `Primary Type` to calculate incident volumes. We will employ animated bar graphs or stacked bar charts to illustrate the changing composition of crime over the study period, highlighting the rise or decline of specific offenses.

---

## Methods & Results

### Data Preparation
The dataset was obtained as a CSV file containing records from 2001 to the present. The initial data preparation involved several key steps to ensure the data was suitable for analysis:
* **Date Conversion:** The `Date` column, originally in string format, was converted into datetime objects. This allowed us to extract the specific `Year` and `Month` for each incident to facilitate temporal grouping and aggregation.
* **Handling Missing Values:** We inspected the dataset for null values, particularly in columns critical to our analysis such as `Latitude`, `Longitude`, and `Primary Type`. Records lacking valid spatial coordinates were excluded from the heatmap analysis to effectively map "hotspots," though they were retained for overall volume counts where location was not a factor.
* **Data Cleaning:** We filtered out anomalies, such as coordinates falling outside the boundaries of Chicago or logical errors in data entry (e.g., duplicate records).
* **Standardization:** We verified the consistency of crime categories in the `Primary Type` column to ensure that slight variations in naming conventions over the 20-year period did not skew the aggregation results.

### Issues and Concerns with the Data
While the dataset is comprehensive, we identified specific limitations and concerns:
* **Location Privacy:** To protect the privacy of victims, the Chicago Police Department redacts exact addresses, providing them only at the block level. While this is sufficient for identifying neighborhood-level hotspots, it limits our ability to pinpoint exact locations.
* **Reporting Bias:** The data represents *reported* incidents rather than the total actual crime committed. Changes in policing strategy, public willingness to report crime, or the ease of reporting (e.g., online systems) could influence the volume metrics independent of actual crime rates.
* **Incompleteness:** As noted in the dataset documentation, the data does not cover the most recent seven days, and older records (particularly from the early 2000s) may have different standards of data entry compared to recent years, potentially introducing inconsistencies in how specific incidents were coded (IUCR codes).

### Visualizations and Analysis

This Visualization can be found [here](https://docs.google.com/document/d/1I3QQ0bDR7hCdG-QR8zkChz1qCWiMUUIg_YHB_vAp18s/edit?usp=sharing).  
*Figure 1: Heatmap showing the density of reported crimes in Chicago (2001 vs. Present).*

<iframe src="fig_annual_trends.html" width="100%" height="500" style="border:none;"></iframe>

*Figure 2: Yearly volume of reported crimes by primary type.*

---

## Conclusions
Based on the results of the visualization, crime hotspots in Chicago do not move locations over time. From 2001 through 2025, the highest-crime areas remain in the same areas of the city, with no evidence of movement or the creation of new high-crime zones. The only changes observed are fluctuations of crime levels within the already established zones.  
	Beyond this spatial consistency, the temporal analysis reveals a significant overall decline in reported crime volumes from 2001 to 2025. Despite this positive long-term trajectory, specific challenges persist, particularly with the sustained high frequency of Theft and Battery incidents. On the other hand, Narcotics offenses have seen a steep reduction over the last 2 decades, potentially reflecting shifts in enforcement strategies or underlying activity. Ultimately, while the locations of crime in Chicago have remained static, the composition and volume of these incidents have evolved, underscoring the need for policy interventions that address these changing dynamics within the city’s established hotspots.

