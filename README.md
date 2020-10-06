# COVID - Maximum Occupany Tracking

Sadhana Sainarayanan


## Introduction

This project aims to detect the occupancy a confined/ closed area to ensure that the maximum occupany of the space is not exceeded to ensure social distancing measures. There are parallel sensing systems to assess the occupancy. First, PIR sensor was used to assess movement near the door (Occupancy instance). Further, a break beam sensor is planned to be added to the sensing system. Once the maximum occupancy is reached a buzzer will be sounded when a person enters in order to avoid exeeding the allowed occupancy limit.

## Motivation

With social distancing becoming a highly important 

## Goals

The goal is to record the number of occupants in a room and assess if it has 

## Current Progress

### Highlights
In particular, articulate thing(s) you have learned / solved outside of what was taught in class
### Problems Encountered
Articulate the problems you have encountered
This section is of the most importance in the progress report. It not only give the TA information on what help you may need, and also encourages you to think deeper about your problems.
### Future Plan
Describe what you plan to do in the next two weeks

## Methodology

### Phenomena of Interest

#### Entry detection

As human activity consumes energy and emit carbon dioxide, when the emission rate is greater than room ventilation rate, carbon dioxide will accumulate in indoor environment. Assume the ventilation is generally steady and might fluctuate within small range, the accumulation rate, also carbon dioxide change rate, will be affected by number of occupants. Moreover, since emitted carbon dioxide volume is proportional to CO2 source – occupants in the room, CO2 concentration at a balanced level should also suggest number of occupants.

#### Human Motion

Human consumes energy and generate heat, with radiating waves came at around 12 microns.[1] Since it falls within the range of 0.75 to 1000 micron of infrared radiation, human body could be seen as an infrared radiation source. Therefore, when someone moves around in a space, there should also be an infrared radiation moving in the space. Such phenomenon lays the ground for PIR motion sensor design. In our case, when someone enters or exits the room, since it firstly went within sensor detection range and then left this range, motion of this infrared radiation source will be detected and recorded as number of occupants change. Connection between this phenomenon and sensor will be illustrated in “Sensors Used” section.


#### Signal characteristics

Outputs of PIR motion sensor are a high and low voltage outputs corresponding to motion detected and motion not detected scenarios respectively. For the PIR sensor used in this project, the high voltage output is 3.3 V. Also, it has been addressed in user manual that initial delay time is around 3, which means after a detection of human motion, a signal of low voltage will be sent out, and for the 3 seconds afterwards, there will be no high voltage sent out even if motion detected. However, since it is adjustable, we used the minimum delay time and were thus able to capture real-time detection.

Nonetheless, this characteristic affects both data collection and processing. For data collection, based on this delay, we adjusted the sensor delay time to be smaller than sampling rate. In this way, we will have usually two consecutive, but sometimes only one “True” value signal showing number of occupants change.

As for numerical characteristic of PIR sensor, since there are only two output – high and low, the signal could actually be comprehended as a binary signal. Thus, signal processing techniques such as averaging filters or moving average could not be applied in this case.

## Sensors Used

### Passive infrared sensor (PIR Motion sensor)

#### Physical principles

The PIR motion sensor we selected is HC-SR501 infrared sensor which allows us to sense motion. Human bodies generate infrared heat which could be picked up by the PIR motion sensor. This sensor is made of a pyroelectric sensor which detects the level of infrared radiation, and a multifaceted lens (a Fresnel lens) which can enlarge the useful detection angle by improving the visibility of the smaller cones and decreasing the visibility of the intervening areas. [2]

#### Static and dynamic behavior

The maximum and minimum value of the physical variable that can be measured is from 4.5V to 20V and the output is 0V in low situation and 3.3V in high situation. The sensitivity ranges from 5s to 5 minutes. Our sensor is an active sensor, in dynamic condition, as soon as the sensor detects a person’s moving, it outputs a 5V signal to the Raspberry Pi. And in static condition, when there is no person or person’s moving, the output is 0V.[2]

#### Sensor characteristics

Working voltage: 4.5V to 20V

Output: High: 3.3V, Low: 0V

Detection angle: Approximately 120 degrees

Range: Adjustable, up to 7m

Trigger modes: L unrepeatable trigger / H repeatable trigger (default)

Dwell time: (Stay-ON time) adjustable between 5-300 Seconds. –– it can be further increased by increasing the value of the CY1-Timing capacitor on pin 4 of the IC

Operating Temperature: -20 – +80 Degrees C.

PCB Dimensions: 33x25mm, 14mm High not including the Lens; Lens: 11mm high, 23mmDiameter.

Weight: 6g [2]

#### Applicability

This sensor could be used for outdoor lights, lift lobby and common staircases. Also, it could be used in shopping mall or used as garden lights.

#### Signal characteristics

When the sensor is triggered by person moving, there will be a 5V output being received by Raspberry Pi which gets high level voltage, then return “1”. When there is no detection of the body motion, Raspberry Pi GPIO output get low level voltage, then return “0”. However, there is still time delay which begins when motion is first detected, and the time delay will be reset by each detected motion. The Figure 1 shows the signal sketch for the PIR motion sensor. link

Figure 1 Signal sketch for the PIR motion sensor


Signal processing and conditioning

The PIR sensor was able to detect any objects passing by with temperature different from its ambient environment, generally, this will lead to noises and errors. Instead of condition signal after collection, a “proactive” measure was adopted to adjust delay time and sensing range before data collection. However, time delay would not be considered in data analysis.

There have been some online resources showing the necessity for eliminating DC voltage output as noise and amplify the AC output. [4] However, after calibration and test, we decided such conditioning could be omitted for the PIR sensor used. Also, we applied moving average with window length of 3 to prioritize the consecutive "True" binary discrete signals as a way balancing eleminating false positive errors and unintentionally filtering out true positive signals.

## Experiments and Results
At this point, the PIR counts the number of instances and creates a buzzer 
## Discussion
Discuss the insights from the project

