# SENZ008 数字温度传感器

###### 翻译

> For `English`, please click [`here.`](https://github.com/njustcjj/SENZ008-Temperature-Sensor/blob/master/README.md)

> For `Chinese`, please click [`here.`](https://github.com/njustcjj/SENZ008-Temperature-Sensor/blob/master/README_CN.md)

![](https://github.com/njustcjj/SENZ008-Temperature-Sensor/blob/master/pic/SENZ008.jpg "SENZ008")
 

### 产品介绍

> SENZ008是基于DS18B20的数字温度传感器，可以用来对环境温度进行定量的检测。DS18B20数字温度传感器是美国DALLAS公司生产的一总线数字温度传感器。其测温范围 －55℃～＋125℃，固有测温分辨率0.5℃，支持多点组网功能，多个SENZ008可以并联在唯一的三线上，实现多点测温，测量结果以9~12位数字量方式串行传送。

> 
> 用途：测量环境温度

### 产品参数

* 工作电压 : 3.3V ~ 5V （ DC ）
* 类型：数字模块
* 温度范围 : -55 ~ +125℃
* 误差 : ±0.5℃（ -10℃ 至 +85℃ 范围内）；±2℃（其他测温范围）
* 分辨率 : ±0.5℃
* 尺寸 : 2.1cm x 1.0cm

### 使用教程

#### 引脚定义

|Sensor Pin|Ardunio Pin|Function Description|
|-|:-:|-|
|VCC|3.3V~5V|Power|
|GND|GND||
|DO|Digital pin|Digital Output|



![](https://github.com/njustcjj/SENZ008-Temperature-Sensor/blob/master/pic/SENZ008_pin.jpg "引脚定义") 


#### 连线图

![](https://github.com/njustcjj/SENZ008-Temperature-Sensor/blob/master/pic/SENZ008_connect.png "连线图") 


### 示例代码

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



### 购买[*SENZ008 数字温度传感器*](https://www.ebay.com/).