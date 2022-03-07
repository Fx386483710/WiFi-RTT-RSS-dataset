# WiFi-RTT-RSS-dataset

Description
========================

This is a detailed WiFi RTT and RSS dataset of a whole floor of a university building. We divided the area of interest was divided into discrete grids and labelled them with correct ground truth coordinates and the LoS APs from the grid. The dataset contains WiFi RTT and RSS signal measures recorded in 642 reference points for 3 days and is well separated so that training points and testing points will not overlap. 

Below is the layout of the testbed. The orange dots indicate the locations of the RTT-enabled Access Point (AP). All measurements are taken in the grey area.
![Building testbed](https://user-images.githubusercontent.com/101070586/156947312-631bf14c-1a4f-4f05-9ccf-f0cc74009330.png)


The features of the dataset
========================

The features of the dataset are as follows:

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
See [directory]prediction_sample_random_forest.ipynb for a machine learning prediction sample.
