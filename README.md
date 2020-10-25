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
<p align = "justify">
The light intensity near the point of entry and the IR beam state at the point of entry or exit are the phenomena of interest.

#### Visible light intensity
<p align = "justify">
The visible light spectrum is a part of the electromagnetic spectrum that can be viewd by the human eye. Wavelenghts from 380 to 700 nanometers are visible and this is called the visible light spectrum.[3]
<p align = "center">
<img src="https://github.com/SadhanaSai/12740-COVIDOccupancy/blob/main/Visible.png" width="400" height="100"></p>
<p align = "center">Fig1: Visible light spectrum</p>[3]



#### Infrared Radiation
<p align = "justify">
Infrared radiation is a part of the electromagnetic spectrum. In the electromagnetic radiation spectrum, it lies between 780 nm and 1 mm, above the visible red light wavelength.[3]
<p align = "center">
<img src="https://github.com/SadhanaSai/12740-COVIDOccupancy/blob/main/Spectrum.png"></p>
<p align = "center">Fig2: Electromagnetic spectrum</p>[3]

## Sensors Used

### Photosensitive Light Sensor Module


#### Physical principles
<p align = "justify">
The principle of the photoresistor is based on the internal photoelectric effect. These light dependet resistors are formed by mounting electrode leads at both ends of the semiconductor photosensitive material. These are encapsulated in a tube case with a transparent window. The two electrodes are often made into a comb shape in order to increase sensitivity.  </p>
<p align = "justify">
As elaborated in Photoresistor Basics: Types, Principles and Applications: "After the incident light disappears, the electron-hole pairs generated by the photon excitation will recombine, and the resistance of the photoresistor will return to its original value. When a voltage is applied to the metal electrodes at both ends of the photoresistor, a current passes through it. When the photoresistor is irradiated by the light with a certain wavelength, the current will increase with the light intensity, thereby achieving photoelectric conversion."[5] The photoresistor is a purely resistive device and can be used with DC and AC.</p>

The below image shows the LDR.
<p align = "center">
<img src="https://github.com/SadhanaSai/12740-COVIDOccupancy/blob/main/ldr.jpg"></p>
<p align = "center">Fig3: Photoresistor</p>[5]


#### Sensor characteristics

Input voltage: 3.3V to 5V

LDR module 4 PIN

Output: Digital Switch I/O or Anlog Voltage (For this project Digital Switch I/O was used)

Range, Sensitivity: Adjustable

PCB Dimensions: 3.3 cm x 1.4 cm

Weight: 4g

Additional feature: Indicator Light on sensor [6]

<p align = "center">
<img src="https://github.com/SadhanaSai/12740-COVIDOccupancy/blob/main/LS.jpg" width="200" height="200"></p>
<p align = "center">Fig4: Photosensitive Light Sensor Module</p>[6]

#### Applications
<p align = "justify">
This sensor could be used for outdoor lights, lift lobby and common staircases. Also, it could be used in shopping mall or used as garden lights.</p>

#### Signal characteristics
<p align = "justify">
The Photosensitive Light sensor module has to modes of outputs. One being the Digital switch I/O, and the Analog voltage output. In this case I had used the digital switch output signals to identify the state of the sensor. </p>

### Breakbeam sensor 

#### Physical principles

<p align = "justify">
Break beam sensors come under the class of Photoelectric Sensors. They use pulse modulated light for contact less sensing. In this case IR is emitted by the sensor.[4]</p>
<p align = "justify">
Pulse modulated light is light that is emitted repeatedly at fixed intervals. 
Effects of external light interference are removed and thus objects at a distance can easily be detected. The below image shows the kind of light produced by the emitter.[4]</p>

<p align = "center">
<img src="https://github.com/SadhanaSai/12740-COVIDOccupancy/blob/main/pml.gif" ></p>
<p align = "center">Fig5: Pulse modulated light</p>[4]
<p align = "justify">
The Emitter and Receiver are installed opposite each other. The receives the light produced by the emitter. </p>

<p align = "center">
<img src="https://github.com/SadhanaSai/12740-COVIDOccupancy/blob/main/bb.jpg" ></p>
<p align = "center">Fig6: Break beam sensors working</p>[4]
<p align = "justify">
An object passing between the Emitter and Receiver interrupts the emitted light. This obstruction to the light is used to detect an object.</p>

<p align = "center">
<img src="https://github.com/SadhanaSai/12740-COVIDOccupancy/blob/main/egbb.gif" ></p>
<p align = "center">Fig7: Break beam object sensing</p>[4]
<p align = "justify">
The main working principles are the rectilinear propagation of light and its reflective properties.</p>[4]


#### Sensor characteristics

Sensing Distance: Approx 25cm / 10"

Power Voltage: 3.3 - 5.5VDC

Emitter Current Draw: 10mA @ 3.3V, 20mA @ 5V

Output Current Capability of receiver: 100mA sink

Transmitter/Receiver LED Angle: 10°

Response Time: <2 ms

Dimensions: 20mm x 10mm x 8mm / 0.8" x 0.4" x 0.3"

Cable Length: 234mm / 9.2"

Weight (of each half): ~3g[2][1]
<p align = "center">
<img src="https://github.com/SadhanaSai/12740-COVIDOccupancy/blob/main/breakbeam.jpg" width="200" height="200"></p>
<p align = "center">Fig8: 5mm Break beam Sensor</p>[2]

#### Applications
<p align = "justify">
This sensor could be used in speed timers, foot count detectors in various places.</p>

#### Signal characteristics
<p align = "justify">
The signals output given by the break beam sensor are logical 1/0 outputs. 1 representing that the receiver received the IR beam. 0 representing that the beam was broken.</p>

## Signal Conditioning and Processing
<p align = "justify">
Signals from the sensors were acquired in binary 0/1 format. This made it easier to identify instances of objects moving past the sensors.</p>
<p align = "justify">
If an object moves past the Photosensitive light sensor, the light intensity decreases and thus it outputs 1. and When the beam in the break beam sensor is broken, its values drops to 0 from its natural state 1.</p>

### Logic
<p align = "justify">
If the Light sensor is triggered and then the break beam sensor is triggered, a person has entered the room.</p>
<p align = "justify">
If the Break beam sensor signal is first triggered and then the lightsensor is triggered, a person has exited the room. Using this as the base logic, a counter was created. This count was then used to trigger the LED once the maximum occupancy is reached. </p>

<pre>
<code>
 if GPIO.input(LIGHT_PIN):
                        time.sleep(1)
                        countl = countl +1
                        print ("LS count",countl)
                        if countl >countb:
                                Count = min(max(Count +1, 0),10)
                                print (Count)
                                time.sleep(1)
                                pass
                else:
                        pass
                if  GPIO.input(BEAM_PIN):
                        pass
                else:
                        time.sleep(1)
                        countb = countb+1
                        print ("BB count",countb)
                        pass
                        if countb >countl:
                                Count = max(Count -1, 0)
                                print (Count)
                                time.sleep(1)
                                pass
                        elif countl ==countb:
                                Count = Count
                                pass
                if Count>3:
                        print ("Don't enter")
                        GPIO.output(18,GPIO.HIGH)
                        time.sleep(1)
                        pass
 </code>
 </pre>

## Experiments and Results
<p align = "justify">
I had done multiple levels of testing and experimentation. First I tested the circuits and the code by using in animate objects as objects of interest that enter and leave a region. Assessed the efficiency in of the code and set the thresholds.</p>

<p align = "center">
<img src="https://github.com/SadhanaSai/12740-COVIDOccupancy/blob/main/circuit.jpeg" width="250" height="400"></p>
<p align = "center">Fig9: Circuit</p>

<p align = "justify">
I had further used the common space in my apartment which had a single point of entrance and exit as my test field. I had placed the light sensor on the door frame, and taped the break beam sensor across the floor. The maximum occupancy was set to 3 people since the area was small.</p>

<p align = "justify">
With each entry the count of the number of people was set to increase by one and with each exit the number would decrease until the room is empty.</p>

<p align = "justify">
I had initially tested out the set up by my self. Further, this system was tested for a couple of hours. It counted the number of people in the room based on the data and triggered the LED once the set limit was reached.</p>

<p align = "justify">The below plots show the signals after processing, and the occupant count created from the signals received. For the 30 minute period of this experiment, the signal based counts matched the ground truth.</p>

<p align = "center">
<img src="https://github.com/SadhanaSai/12740-COVIDOccupancy/blob/main/results.jpg"></p>
<p align = "center">Fig10: Results obtained over 30 minutes</p>

## Discussion
<p align = "justify">
This project was aimed at ensuring that maximum occupancy of a room is not crossed. This was done by using 2 sensors to detect the direction of motion and thus count the number of occupants in the room.</p>

<p align = "justify">
The data collected from the sensors was used to send commands to the actuator, in this case an LED. </p>

<p align = "justify">
The scope of this project is limited. There are better and more efficient ways to count the number of occupants in a room. The project allowed me to understand the principles behind the sensors used and how to use the sensors to create a primitive prototype of an occupancy estimator.</p>


## Reference

[1] https://simonprickett.dev/using-a-break-beam-sensor-with-python-and-raspberry-pi/

[2] https://www.adafruit.com/product/2167

[3] https://en.wikipedia.org/wiki/Light

[4] http://www.ia.omron.com/support/guide/43/introduction.html

[5]  https://www.utmel.com/blog/categories/resistor/photoresistor-basics-types-principles-and-applications

[6] https://robu.in/product/lm393-photosensitive-light-dependent-control-sensor-module/



