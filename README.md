# COVID - Maximum Occupany Tracking

Sadhana Sainarayanan


## Introduction

This project aims to detect the occupancy a confined/ closed area to ensure that the maximum occupany of the space is not exceeded to ensure social distancing measures. There are parallel sensing systems to assess the occupancy. First, PIR sensor was used to assess movement near the door (Occupancy instance). Further, a break beam sensor is planned to be added to the sensing system. Once the maximum occupancy is reached a buzzer will be sounded when a person enters in order to avoid exeeding the allowed occupancy limit.

## Motivation

With social distancing becoming a highly important due to the COVID pandemic, it has become important to ensure that the maximum occupancy in any room or confined space is not exceeded. It is thus important to alert the occupants and the person entering incase the maximum occupancy is reached.

## Goals

The goal is to record the number of occupants in a room and assess if it has reached the maximum allowed occupancy according to guidlines and sound a buzzer when someone attempts to enter the room that has already reached its limit.

## Current Progress

### Highlights
I have learned to make the response system wait for record multiple signals counts and attempt to input it back to the buzzer. I believe I will have to learn to incorporate order of signals for the validation.

![](https://github.com/SadhanaSai/12740-COVIDOccupancy/blob/main/WhatsApp%20Image%202020-10-06%20at%2012.11.40%20PM.jpeg)
![](https://github.com/SadhanaSai/12740-COVIDOccupancy/blob/main/WhatsApp%20Image%202020-10-06%20at%2012.12.55%20PM.jpeg)

### Problems Encountered
1) Attempted to add a sound detection sensor, but the signals were not enough to validate occupancy or a person leaving the room. The ambient noice did not change much. This is could also be due to inability to test it in a real public space.
 
2) Due to the lack of experience with coding foe sensing, figuring out how to store ertain values before sounding alarm was difficult
 
3) PIR could be used to detect both object that are approaching and leaving. Will have to incorporate a secondary sensor to find the direction of movement.

4) PIR sensor's sensitivity needs to be adjusted. Sometimes it is too sensitive and at other times it doesnt detect motion at all. Further, there is a time lag in the signal notification, hence it is difficult to give accurate counts.

4) I am still waiting for my break beam sensor to be delivered. I will have to change the way the project works once the sensor arrives.

### Future Plan
1) Troubleshoot the existing code to allow buzzer to sound after the limit is reached
2) Add a validation sensing system (potentially a break beam sensor) to confirm entry or exit from a room. The break beam will be placed at the door and the Motion sensor will be placed inside the room, right after the entrance. Thus, if the PIR signal is followed by the Break beam signal, the person has left the room, and if the Break beam sensor signal is followed by the motion sensor signal a person has entered the room. This validation method would prevent false positives.

## Methodology

### Phenomena of Interest

#### Entry detection


#### Human Motion

## Sensors Used

### Passive infrared sensor (PIR Motion sensor)

#### Physical principles


#### Static and dynamic behavior


#### Sensor characteristics

Working voltage: 4.5V to 20V

Output: High: 3.3V, Low: 0V

Detection angle: Approximately 120 degrees

Range: Adjustable, up to 7m

Trigger modes: L unrepeatable trigger / H repeatable trigger (default)

Dwell time: (Stay-ON time) adjustable between 5-300 Seconds. –– it can be further increased by increasing the value of the CY1-Timing capacitor on pin 4 of the IC

Operating Temperature: -20 – +80 Degrees C.

PCB Dimensions: 33x25mm, 14mm High not including the Lens; Lens: 11mm high, 23mmDiameter.

Weight: 6g 

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

#### Applications

This sensor could be used in speed timers, foot count detectors in various places.

#### Signal characteristics



## Experiments and Results
At this point, the PIR counts the number of instances but the buzzer sounds at every point.
I will have to incorporate a break beam sensor to make the counts recorded more accurate and make the buzzer sound only when the threshold is reached.

## Reference

[1] https://simonprickett.dev/using-a-break-beam-sensor-with-python-and-raspberry-pi/

[2] https://www.adafruit.com/product/2167

