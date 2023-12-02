Kline communication using MC33290 and OBD9141
=======

This is a simple project that we can use to read the data via Kline protocol from a vehicle. Usually, a vehicle has
an OBD-II interface and this interface can be used to read the data using Kline pin. However, this project was based on a
motorcycle Kawasaki Ninja 400, and this motorcycle does not have the OBD2 interface, it only has the Kline, ground and battery pins.

Main necessary hardware
-----

- 1 x MC33290
- 1 x Arduino (I used an Arduino UNO)
- 1 x Protoboard
- 1 x 1k Ohm resistor
- 2 x Diodo 1n4001
- 1 x 100nf capacitor

Hardware connection setup
-----
You can check all the wire communication between Arduino, MC33290 and the vehicle via the schematic below.
![Schematic](/../main/images/schematic_v1.0.PNG?raw=true "Schematic")

Notes:
- Please observe that the button and the battery from the diagram are just to represent the vehicle power/ground (battery) and the kline pin (button). Remember that these 3 pins will be connected using your vehicle OBD-II/Kline interface.
- The microcontroller 555 from the schematic represents the MC33290.

Arduino IDE libraries setup
-----
In order to communicate using ISO 9141-2 I used the [OBD9141][obd9141] library, so you need to download and install it in your Arduino environment as well. To do so you only need to go to [OBD9141][obd9141], download the project as .zip and add this .zip to your Arduino IDE.
It is also necessary to install the AltSoftSerial library, which can be easily installed from Arduino IDE Library Manager

The base example code
-----
The base_example_code.ino is, as the name says, just a base example code. It will only print the RPM which is got via using the getCurrentPID method filled with 0x0C PID.
So in case you want to check different data you have to get the PID related to the info you want to get. Note that the PIDs are the same across all the devices that use the OBD9141 protocol.

Demonstration
-----
You can check the demonstration video and some photos of the project [here][gdrive].

Contact
-----

Feel free to contact me anytime!

 <div> 
  <a href = "mailto:felipe.alvcor@gmail.com"><img src="https://img.shields.io/badge/-Gmail-%23333?style=for-the-badge&logo=gmail&logoColor=white" target="_blank"></a>
  <a href="https://www.linkedin.com/in/felipeacordeiro/" target="_blank"><img src="https://img.shields.io/badge/-LinkedIn-%230077B5?style=for-the-badge&logo=linkedin&logoColor=white" target="_blank"></a> 
  
[obd9141]: https://github.com/iwanders/OBD9141
[gdrive]: https://drive.google.com/drive/folders/1BmMt0eseSZ9TKvVSNzHTqApfs-kdl_L0?usp=sharing