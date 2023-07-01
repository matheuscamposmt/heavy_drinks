# Bar Crawl: Detecting Heavy Drinking Dataset

This dataset, originated from the paper "[Bar Crawl: Detecting Heavy Drinking](https://doi.org/10.24432/C5TK6G.)" contains accelerometer and transdermal alcohol content (TAC) data collected during a college bar crawl. The dataset is used to predict heavy drinking episodes using mobile data.

![Alcohol](https://rivierabarcrawltours.com/wp-content/uploads/2020/05/what-is-a-pub-crawl-meaning-pic2.jpg)

## Dataset Characteristics

- Type: Multivariate, Time-Series
- Subject Area: Life
- Associated Tasks: Classification, Regression
- Attribute Type: Real

## Dataset Details

- **Donation Date**: 2/23/2020
- **Number of Instances**: 14,057,567
- **Number of Attributes**: 15

## Dataset Information

### Relevant Information

- All data in this dataset is fully anonymized.
- Originally collected from 19 participants, but TAC readings of 6 participants were deemed unusable.
- The dataset includes data from the remaining 13 participants.
- Accelerometer data was collected from smartphones at a sampling rate of 40Hz.
- TAC data was collected using SCRAM ankle bracelets at 30-minute intervals.

### Bar Crawl

![Bar Crawl](https://www.chicagomag.com/wp-content/archive/Chicago-Magazine/December-2018/A-Celebration-of-Winter/Go-on-the-Ultimate-Indoor-Bar-Crawl/map2.png)

A bar crawl is an event where participants visit multiple bars or pubs in a single night, typically consuming alcoholic beverages at each venue. In college, the participants, typically college students, visit multiple bars or pubs in a single night, usually consuming alcoholic beverages at each venue. It is a social activity often organized by student groups or as part of campus events. College bar crawls provide an opportunity for students to socialize, celebrate, and experience the nightlife surrounding their campus.

During a bar crawl, participants may consume varying amounts of alcohol, and heavy drinking episodes can occur. This dataset aims to predict heavy drinking episodes by analyzing accelerometer data from smartphones and transdermal alcohol content (TAC) data collected through SCRAM ankle bracelets.

### Accelerometer Data

Accelerometer data was collected from a mix of 11 iPhones and 2 Android phones. The data file "all_accelerometer_data_pids_13.csv" contains 5 columns: timestamp, participant ID, and samples from each axis of the accelerometer (x, y, z).

### TAC Data

TAC readings are available in two directories: "raw_tac" and "clean_tac." The "raw_tac" directory contains the raw TAC readings, while the "clean_tac" directory contains processed TAC readings. The cleaned TAC readings have two columns: timestamp and TAC reading. The cleaned TAC readings were processed as follows:
1. Zero-phase low-pass filter was applied to smooth noise without shifting phase.
2. The TAC readings were shifted backwards by 45 minutes to align the labels with the true intoxication of the participants.

### Phone Types

The file "phone_types.csv" provides information about the phone types used during data collection. It contains two columns: participant ID and phone type (iPhone or Android).

### Additional Information

For more detailed information on how the data was processed, refer to the referenced study: [The determination of blood alcohol concentration by transdermal measurement](https://www.scramsystems.com/images/uploads/general/research/the-determination-of-blood-alcohol-concentrationby-transdermal-measurement.pdf) by J. Robert Zettl (2002).

## Attribute Information

### Main Attributes

1. `all_accelerometer_data_pids_13.csv`:
   - `time`: Integer, Unix timestamp in milliseconds.
   - `pid`: Symbolic, participant ID from the 13 categories listed in `pids.txt`.
   - `x`: Continuous, time-series data from the x-axis of the accelerometer.
   - `y`: Continuous, time-series data from the y-axis of the accelerometer.
   - `z`: Continuous, time-series data

 from the z-axis of the accelerometer.

2. `clean_tac/*.csv`:
   - `timestamp`: Integer, Unix timestamp in seconds.
   - `TAC_Reading`: Continuous, time-series data of transdermal alcohol content.

3. `phone_types.csv`:
   - `pid`: Symbolic, participant ID from the 13 categories listed in `pids.txt`.
   - `phonetype`: Symbolic, phone type (iPhone or Android).

### Other Attributes

Additional attributes can be found in the `raw` directory in the form of Excel files. These attributes include:
- TAC Level: Continuous, time-series data representing the level of transdermal alcohol content.
- IR Voltage: Continuous, time-series data related to infrared voltage.
- Temperature: Continuous, time-series data representing temperature.
- Time: Datetime information.
- Date: Datetime information.

## Missing Attribute Values

None

## Target Distribution

The target variable, TAC (Transdermal Alcohol Content), is measured in g/dl, where 0.08 is the legal limit for intoxication while driving.
- Mean TAC: 0.065 +/- 0.182
- Max TAC: 0.443
- TAC Inner Quartiles: 0.002, 0.029, 0.092
- Mean Time-to-last-drink: 16.1 +/- 6.9 hrs