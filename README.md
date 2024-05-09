# Quectel_EG25-G_Module_Breakout

<img src= "https://cdn.shopify.com/s/files/1/1217/2104/files/quectelbanner.png?v=1713866683" />

This Github provides a getting started guide for Quectel EG25-G Module Breakout.

### Features:
- LTE Cat 4 module optimized for M2M and IoT applications
- Worldwide LTE, UMTS/HSPA(+) and GSM/GPRS/EDGE coverage
- Multi-constellation GNSS receiver available for applications requiring fast and accurate fixes in any environment
- Feature refinements: supports DFOTA and DTMF
- MIMO technology meets demands for data rate and link reliability in modem wireless communication systems
- LTE Cat 4 Max. 150 Mbps (DL) Max. 50 Mbps (UL)
- Max. 42 Mbps (DL) Max. 5.76 Mbps (UL)
- LGA Package
- Wi-Fi Interface
- Bluetooth Interface
- USB 2.0 High-Speed Interface
- Embedded Abundant Protocols
- Multi-constellation GNSS
- Quectel Enhanced AT Commands
- USB Drivers

### Hardware Overview
#### Pinout

<img src= "https://cdn.shopify.com/s/files/1/1217/2104/files/PINOUTQUECTEL.png?v=1713866803" />

|									                   |									                |								                |
|------------------------------------|----------------------------------|-------------------------------|
|(1) Auxiliary Antenna SMA connector |(2) Main Antenna SMA connector	  |(3) Quectel EG25-G Module      |
|(4) nano SIM slot  				         |(5) Type C interface              |(6) Module Power BTN    	      |
|(7) NET_STATUS LED                  |(8) Network LED      		          |(9) NET_MODE LED              	|
|(10) Power LED              		     |(11) GPS Antenna uFL connector    |(12) GPIOs and Power Breakout  |	


## Setup to use 4G Module 
- Simply connect breakout to PC/laptop via USB Type C. 

- Now press, hold Power Key button and release after 3-4 seconds to activate module. LEDs associated with the network will light up, first NET_STATUS then NET_MODE will be on and finally NetLight LED starts blinking. This confirms module ready for use.
  
- To verify open device Manager and check if below listing you can see into COM port. If you cannot see device then driver is missing, download and install driver from [here](https://github.com/sbcshop/Quectel_EG25-G_Module_Breakout_Software/blob/main/Quectel_LTE_EG25-G_Windows_USB_Driver_V2.1.7.rar)

   <img src="https://github.com/sbcshop/Pico_Cell_4G_Software/blob/main/images/device_manager_4Gmodule.jpg" width="614" height="460" />
   
- If everything goes well it will connect as a cellular network in your system as shown below. After the succesfull 4G Module connection you will able to use your cellular network to connect with internet.
  
  <img src="https://github.com/sbcshop/PiTalk_4G_Dongle_Software/raw/main/images/Scr7.png" />

### For AT Commands Testing
- Open XCTU software and select the Serial console option to run as shown below.

  <img src="https://github.com/sbcshop/Pico_Cell_4G_Software/blob/main/images/img1_xctu.jpg" width="519" height="456"/>

- Select Configure option and then suitable AT COM port. Change Baud Rate and other details only if needed, for the 4G module we will keep default settings. Select OK and After that just Close the connection to start.

  <img src="https://github.com/sbcshop/Pico_Cell_4G_Software/blob/main/images/img2_xctu.jpg" width="519" height="456" />

  <img src="https://github.com/sbcshop/Pico_Cell_4G_Software/blob/main/images/img3_xctu.jpg" width="519" height="456" />

- Now the 4G module is ready to accept AT commands for testing. Either you can send commands through console log or create packets to send AT commands.
  
  <img src="https://github.com/sbcshop/Pico_Cell_4G_Software/blob/main/images/img4_xctu.jpg" width="519" height="456" />

  * AT
  * AT+CPIN?
  You can refer to the [manual](https://github.com/sbcshop/Quectel_EG25-G_Module_Breakout_Software/blob/main/Documents/Quectel_EC2xEG2xEG9xEM05_Series_QCFG_AT_Commands_Manual_V1.0.pdf) for more such AT Commands

- Creating packets is a good option for multiple commands testing. Don’t forget to add 0D and 0A required for carriage return and enter.
  
  <img src="https://github.com/sbcshop/Pico_Cell_4G_Software/blob/main/images/img5_xctu.jpg" width="519" height="456" />
  
  <img src="https://github.com/sbcshop/Pico_Cell_4G_Software/blob/main/images/img6_xctu.jpg" width="519" height="456" />

  <img src="https://github.com/sbcshop/Pico_Cell_4G_Software/blob/main/images/img7_xctu.png" width="519" height="456" /> 

### Interfacing with MCUs

- Pico and Breakout interfacing

  | Pico       | 4G Module 	 	    | Function                |
  |------------|------------------|-------------------------|
  | GP0 (TXD0) | RXD    	        | UART Communication Pin 	|
  | GP1 (RXD0) | TXD    	        | UART Communication Pin  |
  | GP22  		 | PowerKey         | Module Power Key  			|	
  | GP20  	   | Reset	          | Module Reset Pin 				|

You follow above connection to interface 4G module breakout with Pico/Pico W. Once done checkout demo example to test Call and SMS features [here](https://github.com/sbcshop/Pico_Cell_4G_Software/tree/main/examples) and make sure to install required [E25 library](https://github.com/sbcshop/Pico_Cell_4G_Software/blob/main/examples/lib/eg25.py).
  
## Resources
  * [Schematic](https://github.com/sbcshop/Quectel_EG25-G_Module_Breakout_Hardware/blob/main/Design%20Data/SCH%20Quectel%204G%20bkt.pdf)
  * [Hardware Files](https://github.com/sbcshop/Quectel_EG25-G_Module_Breakout_Hardware)
  * [3D Step File](https://github.com/sbcshop/Quectel_EG25-G_Module_Breakout_Hardware/blob/main/Mechanical%20Data/STEP%20QUECTEL%204G.step)
  * [Quectel EG25-G Module Datasheet](https://github.com/sbcshop/Pico_Cell_4G_Software/blob/main/documents/Quectel%20EG25-G%204G%20module%20datasheet.pdf)
  * [EG25-G Module Command Manual](https://github.com/sbcshop/Pico_Cell_4G_Software/blob/main/documents/Quectel_EC2xEG2xEG9xEM05_Series_QCFG_AT_Commands_Manual_V1.0.pdf)

## Related Products  
  * [PiTalk - 4G IoT HAT](https://shop.sb-components.co.uk/products/pitalk-4g-iot-hat-1?_pos=4&_sid=815794148&_ss=r)

    ![PiTalk - 4G IoT HAT](https://shop.sb-components.co.uk/cdn/shop/products/06_2664295e-045b-48c3-bb02-f45ae2d7b4ea.png?v=1677660393&width=150)
    
  * [PiTalk - 2G HAT](https://shop.sb-components.co.uk/products/pitalk-2g-hat?_pos=2&_sid=815794148&_ss=r)

    ![PiTalk - 2G HAT](https://shop.sb-components.co.uk/cdn/shop/products/05_d481ca52-c552-4972-b4b6-d7199af0a3fc.png?v=1674819241&width=150)

  * [Simcom SIM7600G (4G) Breakout](https://shop.sb-components.co.uk/products/simcom-4g-module-breakout?_pos=1&_sid=5a6b2df96&_ss=r)

    ![Simcom SIM7600G (4G) Breakout](https://shop.sb-components.co.uk/cdn/shop/files/2SIMCOM.png?v=1713788098&width=150)

  * [Quectel EG25G (4G) Breakout](https://shop.sb-components.co.uk/products/quectel-4g-module-breakout?_pos=2&_sid=5a6b2df96&_ss=r)

    ![Quectel EG25G (4G) Breakout](https://shop.sb-components.co.uk/cdn/shop/files/2quectel.png?v=1713789371&width=150)

       
## Product License

This is ***open source*** product. Kindly check LICENSE.md file for more information.

Please contact support@sb-components.co.uk for technical support.
<p align="center">
  <img width="360" height="100" src="https://cdn.shopify.com/s/files/1/1217/2104/files/Logo_sb_component_3.png?v=1666086771&width=300">
</p>

