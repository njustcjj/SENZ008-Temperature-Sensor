# SENZ008-Temperature-Sensor

###### Translation

> For `English`, please click [`here.`](https://github.com/njustcjj/SENZ008-Temperature-Sensor/blob/master/README.md)

> For `Chinese`, please click [`here.`](https://github.com/njustcjj/SENZ008-Temperature-Sensor/blob/master/README_CN.md)

![](https://github.com/njustcjj/SENZ008-Temperature-Sensor/blob/master/pic/SENZ008.jpg "SENZ008")


### Introduction

>  The SENZ008 Temperature Sensor is a very small thermometer which can be easily hooked into the Arduino MCU through any digital input! It requires very little in the way of additional support, a couple of resistors and some hookup cables and you're set to go.


### Specification

* Supply Voltage: 3.3V ~ 5 V
- Temperature range :-55 ~ +125℃ ( -67 ~ +257℉ ）
- Error of ± 0.5℃ ( among -10℃ to +85℃ ), ±2℃ ( others )
- Resolution : ±0.5℃
- Size: 2.1cm x 1.0cm

### Tutorial

#### Pin Definition

|Sensor Pin|Ardunio Pin|Function Description|
|-|:-:|-|
|VCC|3.3V~5V|Power|
|GND|GND||
|DO|Digital pin|Digital Output|

![](https://github.com/njustcjj/SENZ008-Temperature-Sensor/blob/master/pic/SENZ008_pin.jpg "Pin Definition") 

#### Connecting Diagram

![](https://github.com/njustcjj/SENZ008-Temperature-Sensor/blob/master/pic/SENZ008_connect.png "Connecting Diagram") 

#### Sample Code


	#include <DallasTemperature.h>
 
	DallasTemperature tempSensor;
 
	void setup(void) {
	  Serial.begin(9600);
	  tempSensor.begin(3); // Connect DS18B20 to Digital Pin 3
	}
 
	void loop(void) {
	    // Check if the sensor is working correctly
	    switch(tempSensor.isValid())
	    {
	        case 1:
	            Serial.println("Invalid CRC");
	            tempSensor.reset(); // Reset Sensor
	            return;
	        case 2:
	            Serial.println("Not a valid device");
	            tempSensor.reset(); // Reset Sensor
	            return;
	    }
 
	  // Read Temperature from DS18B20
	  Serial.print(tempSensor.getTemperature());
	  Serial.print("C");
	  Serial.println();
	}


### Purchasing [*SENZ008 Temperature Sensor*](https://www.ebay.com/).
