# COVID - Maximum Occupany Tracking

Sadhana Sainarayanan

Video: 

<iframe src="https://player.vimeo.com/video/471266004" width="640" height="361" frameborder="0" allow="autoplay; fullscreen" allowfullscreen></iframe>

## Introduction
<p align = "justify">
This project aims to detect the occupancy a confined/ closed area to ensure that the maximum occupany of the space is not exceeded to ensure social distancing measures. There are parallel sensing systems to assess the occupancy. First, a Photosensitive Light sensor module was used to assess movement near the door (Occupancy instance). Further, a break beam sensor has been added to the sensing system to aid detection of people entering and exiting the room. Once the maximum occupancy is reached a Red LED is triggered. </p>

## Motivation
<p align = "justify">
With social distancing becoming a highly important due to the COVID pandemic, it has become important to ensure that the maximum occupancy in any room or confined space is not exceeded. CDC regulations require that occupancy limit of public spaces is not exceeded. It is thus important to a person attempting to enter the room incase the maximum occupancy is reached.</p>

## Goals
<p align = "justify">
The goal is to record the number of occupants in a room and assess if it has reached the maximum allowed occupancy according to guidlines and alert with an LED light once the capacity is reached. The following points give a breakdown of the goals:</p>
<ul>
<li> Sense entry and exit of people using the digital switch input and output of the photosensitive light sensor module and the signals from the break beam sensor. </li>
<li> Monitor the signals from the sensors and publish them ton the Openchirp platform. </li>
 <li> Calculate the nuber of occupants in the room from the signals acquired from the sensors</li>
 <li> Compare the number against the set limit for the number of occupants in the room and set off a Red LED once the limit is reached. </li> </ul>
 

## Methodology

### Phenomena of Interest



#### Entry detection


#### Human Motion

## Sensors Used

### Photosensitive Light Sensor Module

#### Physical principles


#### Static and dynamic behavior


#### Sensor characteristics

Input voltage: 3.3V to 5V

LDR module 4 PIN

Output: Digital Switch I/O or Anlog Voltage (For this project Digital Switch I/O was used)

Range, Sensitivity: Adjustable

PCB Dimensions: 3.3 cm x 1.4 cm

Weight: 4g

Additional feature: Indicator Light on sensor

<p align = "center">
<img src="https://github.com/SadhanaSai/12740-COVIDOccupancy/blob/main/LS.jpg" width="200" height="200"></p>

#### Applications

This sensor could be used for outdoor lights, lift lobby and common staircases. Also, it could be used in shopping mall or used as garden lights.

#### Signal characteristics


### Adafruit Breakbeam sensor 

#### Physical principles


#### Static and dynamic behavior


#### Sensor characteristics

Sensing Distance: Approx 25cm / 10"

Power Voltage: 3.3 - 5.5VDC

Emitter Current Draw: 10mA @ 3.3V, 20mA @ 5V

Output Current Capability of receiver: 100mA sink

Transmitter/Receiver LED Angle: 10°

Response Time: <2 ms

Dimensions: 20mm x 10mm x 8mm / 0.8" x 0.4" x 0.3"

Cable Length: 234mm / 9.2"

Weight (of each half): ~3g
<p align = "center">
<img src="https://github.com/SadhanaSai/12740-COVIDOccupancy/blob/main/breakbeam.jpg" width="200" height="200"></p>

#### Applications

This sensor could be used in speed timers, foot count detectors in various places.

#### Signal characteristics



## Experiments and Results
<p align = "justify">
I plan to use a room with a single point of entry as my testing field. The PIR sensor will be placed right at the entry in front of the door inside the room. When people enter or leave the room, the PIR sensor will detect the motion and will get triggered. The break beam sensor will be place across the floor to allow for the beam to be broken and the sensor to be triggered.
The maximum occupancy is planned to be set at 4 people. 
At this point, the PIR counts the number of instances but the buzzer sounds at every point.
I will have to incorporate a break beam sensor to make the counts recorded more accurate and make the buzzer sound only when the threshold is reached.</p>

## Reference

[1] https://simonprickett.dev/using-a-break-beam-sensor-with-python-and-raspberry-pi/

[2] https://www.adafruit.com/product/2167

