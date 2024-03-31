---
Vibrational Data for Faulty Induction Motor
---
This dataset was recorded by Swapnoneel Kayal in the NCAIR Lab, IIT Bombay under the guidance of Prof. Asim Tewari for his Bachelor's Thesis Project where he was working in the domain of leveraging AI to be able to segregate complex fault states of induction motors using vibrational data

In order to research about the potential mapping of vibrational signals to defect states within rotary machines, a pedestal fan of a leading brand was chosen as test induction motor system. Within this system, four different but reversible faults were introduced. 

These faults were : 
- Mass Imbalance
- Motor Bolt Looseness
- Fan Bolt Looseness
- Fan Blade Cage Looseness.

We recorded the vibration signals generated during operation of the pedestal fan (with the above mentioned faults) using an in-house data acquisition system which comprised of 6 axis MEMS sensor (accelerometer + gyroscope) for measuring vibration and gyroscopic signals. These signals were recorded at 2000 Hz, far exceeding the Nyquist criteria.

| 4-bit code | Mass Imbalance (MI) | Bottom Bolt Looseness (BBL) | Motor Bolt Looseness (MBL) | Front Cage Looseness (FCL) |
|------------|----------------|-----------------------|----------------------|----------------------|
| 0          | 0              | 0                     | 0                    | 0                    |
| 1          | 0              | 0                     | 0                    | 1                    |
| 2          | 0              | 0                     | 1                    | 0                    |
| ...        | ...            | ...                   | ...                  | ...                  |
| 15         | 1              | 1                     | 1                    | 1                    |

The data acquisition for this project was performed by taking two levels for each fault. Level 0 indicating the corresponding fault was not present and Level 1 indicating that the fault was present. All combinations of faults were carefully performed resulting in 16 different fault classes. These 16 fault classes are also indicated by a 4-bit number and have been summarizerd in the above table.  

The data was collected for each class by running the fan for a fixed duration of 50s. For every fault class, the data was recorded independently 4 times to capture any statistical variation in the signal. The final data which been provided is a segment of length = 8s (which is the approximate time duration for one complete swing).

The naming convention for the data files are as follows : 
- TV0000.csv : Refers to the fault combination class belonging to MI = BBL = MBL = FCL = 0 
- TV0002.csv : Refers to the fault combination class belonging to MI = BBL = MBL = 0 and FCL = 1
- TV0020.csv : Refers to the fault combination class belonging to MI = BBL = FCL = 0 and MBL = 1
- and so on...

Within each data file, you will find the following columns : 
- srNo : Serial number for the particular sample
- timestamp : Timestamp for the particular sample
- ax : Linear acceleration in the X-direction
- ay : Linear acceleration in the Y-direction
- az : Linear acceleration in the Z-direction
- gx : Angular velocity in the X-direction
- gy : Angular velocity in the Y-direction
- gz : Angular velocity in the Z-direction
- temp : Temperature (This module of the sensor was not working during our data acquisition experiments)
