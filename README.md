## Compared with TFmini, TFminiPlus has the following advantages:

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190927161205913.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzc1NDAzNg==,size_16,color_FFFFFF,t_70)

- [Benewake homepage](http://en.benewake.com/product/detail/5c345cd0e5b3a844c472329b.html), you can find order link here.  

- [TFmini-Plus data download](http://en.benewake.com/download).  

---

1. Description
2. Appearance and Structure
3. Electrical Characteristics
4. Line Sequence and Data Communication Protocol
5. Quick Test
6. Descriptions on User-defined Parameter Configuration
7. Remote Upgrading
8. Malfunction: Causes and Troubleshooting
---
# 1. Description
## 1.1 Product description

TFmini Plus is a milestone of Benewake in the process of promoting the cost-effective -LiDAR. Apart from low-cost, small-size and low-power-consumption, TFmini Plus also improves the frame rate, introduces IP65 enclosures and optimizes various compensation algorithms. These new characters greatly expand the application fields and scenarios of TFmini Plus. The product is compatible with both the UART and I2C interface. Different interfaces can be switched by commands.

## 1.2 Principle of Distance Measurement
TFmini Plus is based on TOF, namely, Time of Flight principle. To be specific, the product emits modulation wave of near infrared ray on a periodic basis, which will be reflected after contacting object. The product obtains the time of flight by measuring round-trip phase difference and then calculates relative range between the product and the detection object, as shown in Figure1.

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190927113910943.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzc1NDAzNg==,size_16,color_FFFFFF,t_70)

## 1.3 Key Characteristic Parameters
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190927113948485.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzc1NDAzNg==,size_16,color_FFFFFF,t_70)

 1. Operating range based on a standard whiteboard with reflectivity 90% in indoor condition
2. The distance measurement here is absolute accuracy, and the specific repeat accuracy will be described in the next section 2.4.
3. 3.6°is the theoretical value, from which the actual value will be different. The theoretical divergence angle is 6°.
4. Only frame rates meeting the formula–1000/n (n is positive integer) can be set. The default frame rate is 100Hz.

## 1.4 Repeatability
The TFmini Plus's range repeat accuracy is directly related to the strength value measured and the output frame rate (frequence). The ranging repeat accuracy is characterized by the standard deviation of ranging. The average ranging accuracy of the TFmini Plus can be estimated by the following formula:
`Distance_STD[cm] = p00 + p10 ∗ x + p01 ∗ y + p20 ∗ x^2 + p11 ∗ x ∗ y`
In the formula, x is log10 𝑆𝑡𝑟𝑒𝑛𝑔𝑡ℎ, y is log10 𝐹𝑟𝑒𝑞𝑢𝑒𝑛𝑐𝑒[𝐻𝑧], p00, p01, p10, p20 and p11 are constant coefficients, and the values are as follows:
p00 = 0.9758
p01 = 1.175
p10 = −0.6072
p20 = 0.09501
p11 = −0.2904
The above formula only calculates the average reference value. There are some differences in actual results due to differences in each product.

For your convenience, add a simple statistics table for this query, as shown below:

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190927114413957.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzc1NDAzNg==,size_16,color_FFFFFF,t_70)

**Note**: the unit of AMP is a.u., the unit of frequency is Hz, and the unit of distance standard deviation is cm.

## 1.5 Distance Measurement Characteristics

With optimization of light path and algorithm, TFmini Plus has minimized influence from external 
environment on distance measurement performance. Despite that, the range of distance measurement may still be affected by the environment illumination intensity and the reflectivity of detection object. As shown in Figure 2:
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190927114553917.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzc1NDAzNg==,size_16,color_FFFFFF,t_70)
1. Represents the detection blind zone of TFmini Plus, 0-10cm, within which the output data is unreliable. 
2. Represents the operating range of TFmini Plus detecting black target with 10% reflectivity, 0.1-5m. 
3.  Represents the operating range of TFmini Plus detecting white target with 90% reflectivity, 0.1-12m. 

Vertical Coordinates: Represents the radius of light spot for TFmini Plus at the different distances. The diameter of light spot depends on the FOV of TFmini Plus (the term of FOV generally refers to the smaller value between the receiving angle and the transmitting angle), which is calculated as follows: 
`d= D ∙ tanβ`
In the formula above, d is the diameter of light spot; D is detecting range; β is the the value of the 
receiving angle of TFmini Plus, 3.6°. Correspondence between the diameter of light spot and detecting range is given in Table 3.

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190927114739602.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzc1NDAzNg==,size_16,color_FFFFFF,t_70)

If the light spot reaches two objects with different distances, as shown in Figure 3, the output distance value will be a value between the actual distance values of the two objects. For a high accuracy requirement in practice, the above situation should be noticed to avoid the measurement error.

![在这里插入图片描述](https://img-blog.csdnimg.cn/2019092711480436.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzc1NDAzNg==,size_16,color_FFFFFF,t_70)

# 2 Appearance and Structure

## 2.1 Product Structure
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190927114844238.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzc1NDAzNg==,size_16,color_FFFFFF,t_70)

M2 positioning screw was recommended, and please choose an appropriate length according to installation requirements.

# 3 Electrical Characteristics
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190927114916689.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzc1NDAzNg==,size_16,color_FFFFFF,t_70)

This product has no overvoltage nor polarity protection, so please make sure that connection and power supply are normal. The fluctuation of the power supply voltage in a range of ±0.5V is allowable. Average current varies along with the operating modes of the product in two patterns, more specifically, its current is around 50mA under short distance mode and it is around 140mA under long distance mode. 

# 4 Line Sequence and Data Communication Protocol

## 4.1 Description about Line Sequence and Connection

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190927114958376.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzc1NDAzNg==,size_16,color_FFFFFF,t_70)

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190927115017331.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzc1NDAzNg==,size_16,color_FFFFFF,t_70)

TFmini Plus has a 30cm long connecting wire with a GH1.25-4P (Molex51021-0400) connector. The 
connecting wire can be extended as needs. To ensure effective data transmission, the length of connecting wire should be short than 1m.

## 4.2 Serial port Communication Protocol
TFmini Plus adopts the serial port data communication protocol, as given in Table 6.

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190927115056331.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzc1NDAzNg==,size_16,color_FFFFFF,t_70)

## 4.3 Data Output Format of Serial port

 
TFmini Plus is available with two formats of data output, namely, the standard data output format and the character string data format, both of which are switchable with command. 

 - Standard data output format (default):

	Data structure: each data frame contains 9 bytes, including the distance value, signal strength, temperature of chip and data check byte (Checksum), etc. Data format is hexadecimal (HEX). Data codes are detailed in Table 7.

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190927115147385.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzc1NDAzNg==,size_16,color_FFFFFF,t_70)

 - Character string data format(Pix Mode)
	The data output is in the format of character string and its unit is m(meter). For example, if the measurement distance is 1.21m, the string 1.21 will be output, followed by the escape character \r\n. 
This data format is for Ardupilot firmware version lower than v3.6.2. If your Ardupilot firmware version is greater than or equal to v3.6.2, you can use the standard data format directly.

## 4.4 Descriptions of default Output Data

**Dist(Distance):** Represents the output of the distance value detected by TFmini Plus, with the unit in cm by default. This value is interpreted into the decimal value in the range of 0-1200. When the signal strength is lower than 100 or equal to 65535, the detection is unreliable, TFmini Plus will set distance value to 0. 

**Strength**：Represents the signal strength with the default value in the range of 0-65535. After the distance mode is set, the longer the measurement distance is, the lower the signal strength will be; the lower the reflectivity is, the lower the signal strength will be. When the signal strength is lower than 100 or equal to 65535, the detection is unreliable, TFmini Plus will set distance value to 0. 

**Temp(Temperature)**: Represents the chip temperature of TFmini Plus. Degree centigrade = Temp / 8 -256
 

## 4.5 I^2^C data communication
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190927115346570.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzc1NDAzNg==,size_16,color_FFFFFF,t_70)

## 4.6 Timing sequence description of I^2^C mode 
Different from the serial mode, the I2C communication is initiated by the master. TFmini Plus as the slave, can only send and receive data passively. After the sending the config-frame from the master to the slave, one needs to wait for a period for the command to be processed. Then continue the reading procedure. The suggested waiting period is 100ms. To ensure the instantaneity of the measured distance, there is no need to set up the waiting period when sending the ‘obtain measuring result’ frame. Once the command frame is sent by the master, the measured distance can be obtained immediately.

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190927134621452.png)

## 4.7 I/O mode description

I/O output mode is supported and could be enabled by related command.open mode(Mode),critical distance(Dist) and hysteresis zone(Zone) could be configurable: 
Mode:0(data output mode),1(I/O mode,low level near and high level far);default value is 0. 

Dist:critical value,near end value in hysteresis zone,unit is cm,default number is 0. 

Zone:hysteresis zone range,unit is cm;default value is 0(there is no hysteresis zone) 

The hysteresis zone could be set by this command,when output is near zone level,output will be switched to far zone level if measured result is higher than far end point;when output is far zone level,output is switched to near zone level if measured result is lower than near end point.(high level:3.3V,low level:0V)

# 5 Quick Test
## 5.1 Required Tools of Product Test
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190927134755266.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzc1NDAzNg==,size_16,color_FFFFFF,t_70)

## 5.2 Test Procedures
 1. **Download the Test software**
	Please download the Test software of TFmini Plus at our official website (en.benewake.com). 
**Caution**: please shut down any anti-virus software before uncompressing the PC software. Otherwise, maybe the software is deleted as virus. The software is only runnable under Windows environment for the time being. Please refer to Attachment 1 - Product manual of TF Test software. 
 2. **Connection of the hardware**
Connect “TFmini Plus”, “TTL - USB board” and “USB cable” as shown in Figure 5. Make sure there is no loose connection. Then connect “USB cable” with “PC”.
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190927134910425.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzc1NDAzNg==,size_16,color_FFFFFF,t_70)

3. **Connection to the Test software and data output** 
Open the PC software and select “① TFmini Plus” and select automatically recognized occupied serial port (here it is “② COM57”), as shown in Figure 6. 

	Then click “CONNECT”. Upon successful connection, The continuous images of the output data will be displayed in area “④ TIME LINE CHART” on the right. Besides, the real-time data of the Current measure distance (Dist), effective data points per second (Effective Points) and signal strength (Strength) will be displayed in area “⑥ REAL TIME DATA” below.
	![在这里插入图片描述](https://img-blog.csdnimg.cn/20190927135024493.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzc1NDAzNg==,size_16,color_FFFFFF,t_70)

Notes: 

1. If no data is available in area “④TIME LINE CHART”, please check the line connection and 
line sequence. When TFmini Plus is successfully powered on, there will be a red indicator light 
inside transmitting lens viewing from the front. 
2. If the user want the TFmini Plus output in the Pixhawk format, please select “③Pix Mode” at 
first, otherwise area “④TIME LINE CHART” will not output the right data image normally.
After Pix Mode is checked, the unit of distance will be changed into m automatically. 
3. The value of distance output Dist may vary with the output unit, which is cm by default. If the 
unit of distance is changed to the unit-mm with specific command, and the PC software will be 
unable to identify it, and so the unit of “④TIME LINE CHART” will still be cm. For example, 
the actual TFmini Plus measurement is 1m, the distance value of TFmini Plus is 1000 in mm, the value read by the PC software also is 1000, but the unit will not change and still display cm.

# 6 Descriptions on User-defined Parameter Configuration
## 6.1 Function Overview
The function of user-defined configuration of product parameters is hereby enabled for more flexible settlement of your problems by TFmini Plus. User may modify original parameters by sending relevant commands, such as output data format and frame rate, etc. 

Please modify product configuration depending upon your actual demands. Do not frequently try irrelevant commands to prevent incorrect sending of command which many cause unnecessary loss. Please make sure to make the configuration as the commands listed herein. Do not send unstated command.

## 6.2 Command Convention

Multi-bytes data or command frame is transmitted in little endian format. 
For example, decimal number 1000 can be transferred to 0x03E8 in hexadecimal. Then it will be saved in the data or command frame as: 0x5A 0x06 0x03 0xE8 0x03 0x4E 

## 6.3 Command Frame Definition
Caution: All configuration commands are sent as hexadecimal digits (HEX).
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190927135229651.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzc1NDAzNg==,size_16,color_FFFFFF,t_70)

## 6.4 General Parameter Configuration and Description

Before setting the relevant parameters of TFmini Plus, user needs to establish the connection between TFmini Plus and PC at first. About the connection details, refer to the test connection given in Chapter 5.2. User can send the relevant configuration-related instructions to the product via TFmini Plus PC software or other serial port debugging software. All commands are compatible with both the UART mode and the I^2^C mode. **Important: After setting parameters, the ‘Save setting’ command needs to be sent.**

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190927135343400.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzc1NDAzNg==,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190927135357594.png)

Note:Bytes with yellow undertone represents checksum. Bytes with blue undertone represents data segment. 
1. The default update rate is 100Hz. The customized update rate should be calculated by the formula: 1000/n (n is positive integer). Increasing frame rate will decrease the data stability. 
2. Only standard baud rates are supported. When setting a high update rate, a high baud rate is recommended to ensure data security. 
3. Please always send the command of save settings when try to modify parameters of TFmini Plus, otherwise the settings will not take effect.

# 7 Remote Upgrading
TFmini Plus supports the remote upgrade. When the user’s product cannot satisfy the current application requirements and Benewake official website has relevant firmware upgrades, the user may upgrade the product firmware via remotely upgrading the PC software. Please contact us to get the Updater.

![](https://img-blog.csdnimg.cn/2019092713552361.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zNzc1NDAzNg==,size_16,color_FFFFFF,t_70)

The tools for the firmware upgrade of TFmini Plus are mostly the same as the Quick Test, which requires one TTL-USB board to connect the TFmini Plus with PC. 

Upon successful connection, open the Updater.exe. Select right port, here is “①COM8”. Input the right baud rate in “② 115200” and click “③ CONNECT” to connect the TFmini Plus with the Updater. Click “④ Open Bin” to choose the updating firmware, whose directory will be showed in the textbox above. Then click “⑤ Download Bin” to start upgrading. The information of upgrading will be showed in “⑥”. 

**Caution**: please confirm that the communication bit rate of this product is 115200 before the firmware upgrade, as TFmini will be unable to upgrade at other bit rates.

# 8 Malfunction: Causes and Troubleshooting
1. **Distance value occasionally will abruptly change into 0 beyond the range during normal operation. 
Cause**: The different test environments (reflectivity of detected object, disturbance of ambient light, etc.) will affect the signal strength of TFmini Plus. For a reliable and stable measurement data, the algorithm elimination is internally used for TFmini Plus. In case of the insufficient signal strength, TFmini Plus will output 0. This value is not measurement data of TFmini Plus, which is only used to remind the user that such data is unreliable. 
**Troubleshooting**: please use such value as the trigger signal of some unreliable data, and it will ensure that your system can use other reliable data for further assessment and decision-making if there are some unreliable data. 
2. **Significant error between the output distant value of LiDAR and actual distance 
Cause** ①: Incorrect interpretation of the data communication protocol of TFmini Plus. 
**Troubleshooting**: check data communication interpretation means. In case of such error, please check the data format to adjust interpretation means. 

	**Cause** ②：Due to the physical principles of TFmini Plus, the above phenomenon is likely to occur if the detection object is the material with high reflectivity (such as mirror, smooth floor tile, etc.) or transparent substance (such as glass and water, etc.) 
**Troubleshooting**: Please avoid use of this product under such circumstance in practice. 

	**Cause ③**: The IR-pass filters are blocked. 
**Troubleshooting**: please use dry dust-free cloth to gently remove the foreign matter 
3. **No data output 
Cause**: The product will be strictly inspected before leaving our factory, ensuring that all the shipped products can work normally. However, some abnormal working matters maybe still occur because of incidents during the transportation or use. 
**Troubleshooting**: Check whether the power supply is normal; check whether the voltage is within rated voltage range. If power supply is normal, there will be a red light inside the transmitting lens of TFmini Plus. 

	Check TFmini Plus with correct connection sequence and reliable connection. 
Check whether the data interpretation is correct. Please carry out the interpretation as per the data format specified herein. If the problem persists, please contact our technical support. 
4. **There is no data output when LiDAR is connected to PC software. 
Cause ①**: The PC software only supports the Windows operation system for the time being 
**Troubleshooting**: Use the PC supporting Windows operation system. 

	**Cause ②**: TTL - USB board is poorly connected. 
**Troubleshooting**: Check the TTL -USB board with the correct and reliable connection with TFmini Plus and PC. 

	**Cause ③**: Driver of serial port is not correctly installed. 
**Troubleshooting**: Plug and unplug USB cable again. Try to reinstall the driver or directly download and install a driver from the internet. 

	If the PC software still work abnormally, please contact our technical support.
