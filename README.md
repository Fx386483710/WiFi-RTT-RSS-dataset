# WiFi-RTT-RSS-dataset

Description
========================

We provide publicly available datasets of three different indoor scenarios: building floor, office and apartment. The datasets contain both WiFi RSS and RTT signal measures with groud truth coordinates label and LOS condition label.

1. Building FLoor
This is a detailed WiFi RTT and RSS dataset of a whole floor of a university building. We divided the area of interest was divided into discrete grids and labelled them with correct ground truth coordinates and the LoS APs from the grid. The dataset contains WiFi RTT and RSS signal measures recorded in 642 reference points for 3 days and is well separated so that training points and testing points will not overlap. 

Below is the layout of the testbed. The orange dots indicate the locations of the RTT-enabled Access Point (AP). All measurements are taken in the grey area.
![Building testbed](https://user-images.githubusercontent.com/101070586/162602929-f545b461-3630-4898-bb86-e6f86e9b6ea9.png)

2. Office

Office scenario is of more than 4.5 x 5.5 metres. 3 APs are set to cover the whole space. At least two LOS AP could be seen at any reference point (RP).
Below is the layout of the testbed. The orange dots indicate the locations of the RTT-enabled Access Point (AP). All measurements are taken in the grey area.
![room_testbed](https://github.com/Fx386483710/WiFi-RTT-RSS-dataset/assets/101070586/7687d697-56b2-4974-81d9-85f6ed80e0fa)

3. Apartment
Apartment scenario is of more than  7.7 x 9.4 metres.Four APs were leveraged to generate WiFi signal measures for this testbed. Note that AP 1 in the apartment dataset was positioned so that it could had an NLOS path to most of the testbed. 
Below is the layout of the testbed. The orange dots indicate the locations of the RTT-enabled Access Point (AP). All measurements are taken in the grey area.
![marina_testbed](https://github.com/Fx386483710/WiFi-RTT-RSS-dataset/assets/101070586/11919754-132b-4809-88dd-1d99293371dd)

The features of the datasets
========================

The features of the building floor dataset are as follows:

```
Testbed area:	92 × 15 m2
Grid size: 0.6 × 0.6 m2
Number of reference points: 642
Samples per reference point: 120
Number of all data samples: 77040
Number of training samples: 57960
Number of testing samples: 19080
Signal measure: WiFi RTT, WiFi RSS
Collection time interval: 3 days
```

The features of the office dataset are as follows:
```
Testbed area:	4.5 × 5.5 m2
Grid size: 0.455 × 0.455 m2
Reference points: 37
Samples per reference point: 120
Data samples: 4,440
Training samples: 3,240
Testing samples: 1,200
Signal measure: WiFi RTT, WiFi RSS
Other information: LOS condition of every AP
Collection time: 1 day
Notes: A LOS scenario
```

The features of the apartment dataset are as follows:
```
Testbed area:	7.7 × 9.4 m2
Grid size: 0.48 × 0.48 m2
Reference points: 110
Samples per reference point: 120
Data samples: 13,200
Training samples: 9,720
Testing samples: 3,480
Signal measure: WiFi RTT, WiFi RSS
Other information: LOS condition of every AP
Collection time: 1 day
Notes: Contains an AP with NLOS paths for most of the RPs
```

Dataset explanation
========================

The columns of the dataset are as follows:

```
Column 'X': the X coordinates of the sample.
Column 'Y': the Y coordinates of the sample.
Column 'AP1 RTT(mm)', 'AP2 RTT(mm)', ..., 'AP13 RTT(mm)': the RTT measure from corresponding AP at a reference point.
Column 'AP1 RSS(dBm)', 'AP2 RSS(dBm)', ..., 'AP13 RSS(dBm)': the RSS measure from corresponding AP at a reference point.
Column 'LOS APs': indicating which AP has a LOS to this reference point.
```

Please note:

* The RSS value -200 dBm indicates that the AP is too far away from the current reference point and no signals could be heard from it. 

* The RTT value 100,000 mm indicates that no signal is received from the specific AP.

Prediction sample
========================
See [here](prediction_sample_random_forest.ipynb) for a machine learning prediction sample.
