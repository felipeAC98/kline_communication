###Kline communication using MC33290 and OBD9141

This is a simple project that we can use to read the data via Kline protocol from a vehicle. Usually a vehicle has
an OBD-II interface and this interface can be used to read the data using Kline pin. However, this project was based in an
motorcyclie Kawasaki Ninja 400, and this motorcyclie does not has the OBD2 interface, it only has the Kline, ground and battery pins.

####Main necessary hardware

- 1 x MC33290
- 1 x Arduino (I used an Arduino UNO)
- 1 x Protoboard
- 1 x 1k Ohm resistor
- 2 x Diodo 1n4001
- 1 x 100uF capacitor

####Hardware connection setup
You can check all the wire communication between Arduino, MC33290 and the vehicle via the schematic below.
https://drive.google.com/drive/folders/1BmMt0eseSZ9TKvVSNzHTqApfs-kdl_L0?usp=sharing

#####Notes:
- Please observe that the button and the battery from the diagram is just to represent the vehicle power/ground (battery) and the kline pin (button). Remember that this 3 pins will be connect using your vehicle OBD-II/Kline interface.
- The microcontroler 555 from the schematic represents the MC33290.

####Arduino IDE libraries setup
In order to communicate using ISO 9141-2 I used the [OBD9141][obd9141] library, so you need to download and install it in your Arduino enviroment as well. To do so you only need to go to [OBD9141][obd9141], download the project as .zip and add this .zip in your Arduino IDE.
It is also necessary to install the AltSoftSerial library, it can be easily installed from Arduino IDE Library Manager

####The base example code

[obd9141]: https://github.com/iwanders/OBD9141