# Gesture-Controlled Robot Car 
Similarly to how TV shows and movie series animate powers which can move objects without manually holding them, I am working on a robot car which can move according to different hand gestures! 

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Lorelei X. | IHS | Engineering | Incoming Sophomore

<img width="668" alt="Screen Shot 2021-07-02 at 11 24 57 AM" src="https://user-images.githubusercontent.com/86121949/124314998-23c1a480-db28-11eb-9c10-9e171ad591e7.png">

# Final Presentation
[![Final Milestone](https://res.cloudinary.com/marcomontalbano/image/upload/v1625247910/video_to_markdown/images/youtube--I4hq-7FCWKA-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://www.youtube.com/watch?v=I4hq-7FCWKA "Final Presentation")

Overall, my experience at Bluestamp- being able to work on an extraordinary project, designing and modifying based on what I want it to do- has increased my interest in software and mechanical engineering. I'm excited to use the rest of the project equipment recieved to add addional modifcations to my gesture-controlled robot! 
  
# Final Milestone

For my final milestone, I added a small modifcation of 4 LED lights. These LED lights are used to replicate the tailights of a regular car. For example, when the car is stopping, the red light would turn on. When the car is in reverse, the white lights would turn on. When the car is turning, the orange light would turn on. In this milestone, I did not have too much trouble configuring the LED lights, however it was a bit tedious to get all 4 sets of wires to stick onto the breadboard along with the rest of my gesture-controlled car. 

[![Final Milestone](https://res.cloudinary.com/marcomontalbano/image/upload/v1625247707/video_to_markdown/images/youtube--kCBN4kyTVtA-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://www.youtube.com/watch?v=kCBN4kyTVtA "Lorelei's Third Milestone")

# Second Milestone 

My second milestone was to configure a setup where accelerometer values would be read and used to move the car accordingly. I began with testing out the accelerometer output values, which x,y, and z values changed according to the orientation of the device. I think plugged it into a secondary ESP, which would transmit the accelerometer values to the ESP attached to the vehicle. With this, I coded different thresholds that when crossed, the car would move accordingly. At the end, I was able to move the car according to the direction that I orient the accelerometer device. For my next milestone, I hope to achieve a LED light indicator system, which would light up according to the direction that the vehicle is going, similarly to a regular car. 

[![Second Milestone](https://res.cloudinary.com/marcomontalbano/image/upload/v1625095547/video_to_markdown/images/youtube--osunMRoNDPg-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://www.youtube.com/watch?v=osunMRoNDPg "Lorelei's Second Milestone"){:target="_blank" rel="noopener"}

# First Milestone

My first milestone was to understand the functioning of motors and motor drivers, and how I can implicate those into my robot car. I began with working on powering only two motors/wheels and using a jumper wire to manually turn on each motor and drive in different directions. Due to its success, I added two more motors, stuffing the extra sets of jumper wires into the motor-driver outputs. However, instead of powering it manually, I coded a simple code which would move all 4 tires simultaneously at a fixed speed. Once finished, I disassembled the parts of my prototype and transferred the pieces onto a chassis, where I reassembled the pieces to complete my first milestone. 

[![Lorelei's First Milestone](https://res.cloudinary.com/marcomontalbano/image/upload/v1624639367/video_to_markdown/images/youtube--0S75vxPjRFs-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://www.youtube.com/watch?v=0S75vxPjRFs "Lorelei's First Milestone"){:target="_blank" rel="noopener"}

# Photos

<img width="1183" alt="Screen Shot 2021-07-02 at 10 29 31 AM" src="https://user-images.githubusercontent.com/86121949/124309979-667f7e80-db20-11eb-9599-c7caafa0427b.png">

<img width="660" alt="Screen Shot 2021-07-02 at 10 27 09 AM" src="https://user-images.githubusercontent.com/86121949/124309763-143e5d80-db20-11eb-94f0-f17f3a7cd45c.png">

<img width="1183" alt="Screen Shot 2021-07-02 at 10 30 37 AM" src="https://user-images.githubusercontent.com/86121949/124310089-8c0c8800-db20-11eb-9e63-1dab85038ee8.png">

<img width="667" alt="Screen Shot 2021-07-02 at 10 31 07 AM" src="https://user-images.githubusercontent.com/86121949/124310136-9dee2b00-db20-11eb-8143-cec64759bf97.png">

<img width="1184" alt="Screen Shot 2021-07-02 at 10 31 52 AM" src="https://user-images.githubusercontent.com/86121949/124310226-b8c09f80-db20-11eb-9ed4-040d68e4fdf5.png">

# Circuit Diagram

Robot Car: 

<img width="857" alt="Screen Shot 2021-07-02 at 10 34 42 AM" src="https://user-images.githubusercontent.com/86121949/124310504-2371db00-db21-11eb-85a2-0c0b84b1987a.png">

Glove: 

<img width="483" alt="Screen Shot 2021-07-02 at 10 40 21 AM" src="https://user-images.githubusercontent.com/86121949/124311019-e9550900-db21-11eb-95da-e19f1833557c.png">

# Code 

Sender Code: 

<pre>
<font color="#95a5a6">&#47;*</font>
<font color="#95a5a6"> &nbsp;Rui Santos</font>
<font color="#95a5a6"> &nbsp;Complete project details at </font><u><font color="#95a5a6">https:&#47;&#47;RandomNerdTutorials.com&#47;esp-now-esp32-arduino-ide&#47;</font></u><font color="#95a5a6"></font>
<font color="#95a5a6"> &nbsp;</font>
<font color="#95a5a6"> &nbsp;Permission is hereby granted, free of charge, to any person obtaining a copy</font>
<font color="#95a5a6"> &nbsp;of this software and associated documentation files.</font>
<font color="#95a5a6"> &nbsp;</font>
<font color="#95a5a6"> &nbsp;The above copyright notice and this permission notice shall be included in all</font>
<font color="#95a5a6"> &nbsp;copies or substantial portions of the Software.</font>
<font color="#95a5a6">*&#47;</font>

<font color="#5e6d03">#include</font> <font color="#434f54">&lt;</font><font color="#000000">esp_now</font><font color="#434f54">.</font><font color="#000000">h</font><font color="#434f54">&gt;</font>
<font color="#5e6d03">#include</font> <font color="#434f54">&lt;</font><b><font color="#d35400">WiFi</font></b><font color="#434f54">.</font><font color="#000000">h</font><font color="#434f54">&gt;</font>

<font color="#5e6d03">#include</font> <font color="#434f54">&lt;</font><font color="#000000">Adafruit_MPU6050</font><font color="#434f54">.</font><font color="#000000">h</font><font color="#434f54">&gt;</font>
<font color="#5e6d03">#include</font> <font color="#434f54">&lt;</font><font color="#000000">Adafruit_Sensor</font><font color="#434f54">.</font><font color="#000000">h</font><font color="#434f54">&gt;</font>
<font color="#5e6d03">#include</font> <font color="#434f54">&lt;</font><font color="#d35400">Wire</font><font color="#434f54">.</font><font color="#000000">h</font><font color="#434f54">&gt;</font>

<font color="#000000">Adafruit_MPU6050</font> <font color="#000000">mpu</font><font color="#000000">;</font>

<font color="#00979c">int</font> <font color="#000000">gyro_x</font><font color="#434f54">,</font> <font color="#000000">gyro_y</font><font color="#434f54">,</font> <font color="#000000">gyro_z</font><font color="#000000">;</font>
<font color="#00979c">long</font> <font color="#000000">acc_x</font><font color="#434f54">,</font> <font color="#000000">acc_y</font><font color="#434f54">,</font> <font color="#000000">acc_z</font><font color="#434f54">,</font> <font color="#000000">acc_total_vector</font><font color="#000000">;</font>
<font color="#00979c">int</font> <font color="#000000">temperature</font><font color="#000000">;</font>
<font color="#00979c">long</font> <font color="#000000">gyro_x_cal</font><font color="#434f54">,</font> <font color="#000000">gyro_y_cal</font><font color="#434f54">,</font> <font color="#000000">gyro_z_cal</font><font color="#000000">;</font>
<font color="#00979c">long</font> <font color="#000000">loop_timer</font><font color="#000000">;</font>
<font color="#00979c">int</font> <font color="#000000">lcd_loop_counter</font><font color="#000000">;</font>
<font color="#00979c">float</font> <font color="#000000">angle_pitch</font><font color="#434f54">,</font> <font color="#000000">angle_roll</font><font color="#000000">;</font>
<font color="#00979c">int</font> <font color="#000000">angle_pitch_buffer</font><font color="#434f54">,</font> <font color="#000000">angle_roll_buffer</font><font color="#000000">;</font>
<font color="#00979c">boolean</font> <font color="#000000">set_gyro_angles</font><font color="#000000">;</font>
<font color="#00979c">float</font> <font color="#000000">angle_roll_acc</font><font color="#434f54">,</font> <font color="#000000">angle_pitch_acc</font><font color="#000000">;</font>
<font color="#00979c">float</font> <font color="#000000">angle_pitch_output</font><font color="#434f54">,</font> <font color="#000000">angle_roll_output</font><font color="#000000">;</font>


<font color="#434f54">&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;</font>


<font color="#434f54">&#47;&#47; REPLACE WITH YOUR RECEIVER MAC Address</font>
<font color="#00979c">uint8_t</font> <font color="#000000">broadcastAddress</font><font color="#000000">[</font><font color="#000000">]</font> <font color="#434f54">=</font> <font color="#000000">{</font><font color="#000000">0xE0</font><font color="#434f54">,</font> <font color="#000000">0xE2</font><font color="#434f54">,</font> <font color="#000000">0xE6</font><font color="#434f54">,</font> <font color="#000000">0xC6</font><font color="#434f54">,</font> <font color="#000000">0x35</font><font color="#434f54">,</font> <font color="#000000">0x38</font><font color="#000000">}</font><font color="#000000">;</font>

<font color="#434f54">&#47;&#47; Structure example to send data</font>
<font color="#434f54">&#47;&#47; Must match the receiver structure</font>
<font color="#00979c">typedef</font> <font color="#00979c">struct</font> <font color="#000000">struct_message</font> <font color="#000000">{</font>
 &nbsp;<font color="#00979c">float</font> <font color="#000000">b</font><font color="#000000">;</font>
 &nbsp;<font color="#00979c">float</font> <font color="#000000">c</font><font color="#000000">;</font>
 &nbsp;<font color="#00979c">bool</font> <font color="#000000">e</font><font color="#000000">;</font>
<font color="#000000">}</font> <font color="#000000">struct_message</font><font color="#000000">;</font>

<font color="#434f54">&#47;&#47; Create a struct_message called myData</font>
<font color="#000000">struct_message</font> <font color="#000000">myData</font><font color="#000000">;</font>

<font color="#434f54">&#47;&#47; callback when data is sent</font>
<font color="#00979c">void</font> <font color="#000000">OnDataSent</font><font color="#000000">(</font><font color="#00979c">const</font> <font color="#00979c">uint8_t</font> <font color="#434f54">*</font><font color="#000000">mac_addr</font><font color="#434f54">,</font> <font color="#000000">esp_now_send_status_t</font> <font color="#d35400">status</font><font color="#000000">)</font> <font color="#000000">{</font>
 &nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">print</font><font color="#000000">(</font><font color="#005c5f">&#34;\r\nLast Packet Send Status:\t&#34;</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">println</font><font color="#000000">(</font><font color="#d35400">status</font> <font color="#434f54">==</font> <font color="#000000">ESP_NOW_SEND_SUCCESS</font> <font color="#434f54">?</font> <font color="#005c5f">&#34;Delivery Success&#34;</font> <font color="#434f54">:</font> <font color="#005c5f">&#34;Delivery Fail&#34;</font><font color="#000000">)</font><font color="#000000">;</font>
<font color="#000000">}</font>
 
<font color="#00979c">void</font> <font color="#5e6d03">setup</font><font color="#000000">(</font><font color="#000000">)</font> <font color="#000000">{</font>
 &nbsp;<font color="#434f54">&#47;&#47; Init Serial Monitor</font>
 &nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">begin</font><font color="#000000">(</font><font color="#000000">115200</font><font color="#000000">)</font><font color="#000000">;</font>


 &nbsp;&nbsp;&nbsp;<font color="#434f54">&#47;&#47; Try to initialize!</font>
 &nbsp;<font color="#5e6d03">if</font> <font color="#000000">(</font><font color="#434f54">!</font><font color="#000000">mpu</font><font color="#434f54">.</font><font color="#d35400">begin</font><font color="#000000">(</font><font color="#000000">)</font><font color="#000000">)</font> <font color="#000000">{</font>
 &nbsp;&nbsp;&nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">println</font><font color="#000000">(</font><font color="#005c5f">&#34;Failed to find MPU6050 chip&#34;</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;<font color="#5e6d03">while</font> <font color="#000000">(</font><font color="#000000">1</font><font color="#000000">)</font> <font color="#000000">{</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">delay</font><font color="#000000">(</font><font color="#000000">10</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;<font color="#000000">}</font>
 &nbsp;<font color="#000000">}</font>
 &nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">println</font><font color="#000000">(</font><font color="#005c5f">&#34;MPU6050 Found!&#34;</font><font color="#000000">)</font><font color="#000000">;</font>

 &nbsp;<font color="#000000">mpu</font><font color="#434f54">.</font><font color="#000000">setAccelerometerRange</font><font color="#000000">(</font><font color="#000000">MPU6050_RANGE_8_G</font><font color="#000000">)</font><font color="#000000">;</font>

 &nbsp;<font color="#000000">mpu</font><font color="#434f54">.</font><font color="#000000">setGyroRange</font><font color="#000000">(</font><font color="#000000">MPU6050_RANGE_500_DEG</font><font color="#000000">)</font><font color="#000000">;</font>

 &nbsp;<font color="#000000">mpu</font><font color="#434f54">.</font><font color="#000000">setFilterBandwidth</font><font color="#000000">(</font><font color="#000000">MPU6050_BAND_5_HZ</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;

<font color="#434f54">&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;&#47;</font>

 
 &nbsp;<font color="#434f54">&#47;&#47; Set device as a Wi-Fi Station</font>
 &nbsp;<b><font color="#d35400">WiFi</font></b><font color="#434f54">.</font><font color="#d35400">mode</font><font color="#000000">(</font><font color="#00979c">WIFI_STA</font><font color="#000000">)</font><font color="#000000">;</font>

 &nbsp;<font color="#434f54">&#47;&#47; Init ESP-NOW</font>
 &nbsp;<font color="#5e6d03">if</font> <font color="#000000">(</font><font color="#000000">esp_now_init</font><font color="#000000">(</font><font color="#000000">)</font> <font color="#434f54">!=</font> <font color="#000000">ESP_OK</font><font color="#000000">)</font> <font color="#000000">{</font>
 &nbsp;&nbsp;&nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">println</font><font color="#000000">(</font><font color="#005c5f">&#34;Error initializing ESP-NOW&#34;</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;<font color="#5e6d03">return</font><font color="#000000">;</font>
 &nbsp;<font color="#000000">}</font>

 &nbsp;<font color="#434f54">&#47;&#47; Once ESPNow is successfully Init, we will register for Send CB to</font>
 &nbsp;<font color="#434f54">&#47;&#47; get the status of Trasnmitted packet</font>
 &nbsp;<font color="#000000">esp_now_register_send_cb</font><font color="#000000">(</font><font color="#000000">OnDataSent</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;
 &nbsp;<font color="#434f54">&#47;&#47; Register peer</font>
 &nbsp;<font color="#000000">esp_now_peer_info_t</font> <font color="#000000">peerInfo</font><font color="#000000">;</font>
 &nbsp;<font color="#d35400">memcpy</font><font color="#000000">(</font><font color="#000000">peerInfo</font><font color="#434f54">.</font><font color="#000000">peer_addr</font><font color="#434f54">,</font> <font color="#000000">broadcastAddress</font><font color="#434f54">,</font> <font color="#000000">6</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;<font color="#000000">peerInfo</font><font color="#434f54">.</font><font color="#000000">channel</font> <font color="#434f54">=</font> <font color="#000000">0</font><font color="#000000">;</font> &nbsp;
 &nbsp;<font color="#000000">peerInfo</font><font color="#434f54">.</font><font color="#000000">encrypt</font> <font color="#434f54">=</font> <font color="#00979c">false</font><font color="#000000">;</font>
 &nbsp;
 &nbsp;<font color="#434f54">&#47;&#47; Add peer &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</font>
 &nbsp;<font color="#5e6d03">if</font> <font color="#000000">(</font><font color="#000000">esp_now_add_peer</font><font color="#000000">(</font><font color="#434f54">&amp;</font><font color="#000000">peerInfo</font><font color="#000000">)</font> <font color="#434f54">!=</font> <font color="#000000">ESP_OK</font><font color="#000000">)</font><font color="#000000">{</font>
 &nbsp;&nbsp;&nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">println</font><font color="#000000">(</font><font color="#005c5f">&#34;Failed to add peer&#34;</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;<font color="#5e6d03">return</font><font color="#000000">;</font>
 &nbsp;<font color="#000000">}</font>
<font color="#000000">}</font>
 
<font color="#00979c">void</font> <font color="#5e6d03">loop</font><font color="#000000">(</font><font color="#000000">)</font> <font color="#000000">{</font>
 &nbsp;<font color="#434f54">&#47;&#47; Set values to send</font>
 &nbsp;<font color="#000000">sensors_event_t</font> <font color="#000000">a</font><font color="#434f54">,</font> <font color="#000000">g</font><font color="#434f54">,</font> <font color="#000000">temp</font><font color="#000000">;</font>
 &nbsp;<font color="#000000">mpu</font><font color="#434f54">.</font><font color="#000000">getEvent</font><font color="#000000">(</font><font color="#434f54">&amp;</font><font color="#000000">a</font><font color="#434f54">,</font> <font color="#434f54">&amp;</font><font color="#000000">g</font><font color="#434f54">,</font> <font color="#434f54">&amp;</font><font color="#000000">temp</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;
 &nbsp;<font color="#000000">acc_total_vector</font> <font color="#434f54">=</font> <font color="#d35400">sqrt</font><font color="#000000">(</font><font color="#000000">(</font><font color="#000000">a</font><font color="#434f54">.</font><font color="#000000">acceleration</font><font color="#434f54">.</font><font color="#000000">x</font><font color="#434f54">*</font><font color="#000000">a</font><font color="#434f54">.</font><font color="#000000">acceleration</font><font color="#434f54">.</font><font color="#000000">x</font><font color="#000000">)</font><font color="#434f54">+</font><font color="#000000">(</font><font color="#000000">a</font><font color="#434f54">.</font><font color="#000000">acceleration</font><font color="#434f54">.</font><font color="#000000">y</font><font color="#434f54">*</font><font color="#000000">a</font><font color="#434f54">.</font><font color="#000000">acceleration</font><font color="#434f54">.</font><font color="#000000">y</font><font color="#000000">)</font><font color="#434f54">+</font><font color="#000000">(</font><font color="#000000">a</font><font color="#434f54">.</font><font color="#000000">acceleration</font><font color="#434f54">.</font><font color="#000000">z</font><font color="#434f54">*</font><font color="#000000">a</font><font color="#434f54">.</font><font color="#000000">acceleration</font><font color="#434f54">.</font><font color="#000000">z</font><font color="#000000">)</font><font color="#000000">)</font><font color="#000000">;</font> &nbsp;<font color="#434f54">&#47;&#47;Calculate the total accelerometer vector</font>
 &nbsp;<font color="#434f54">&#47;&#47;57.296 = 1 &#47; (3.142 &#47; 180) The Arduino asin function is in radians</font>
 &nbsp;<font color="#000000">angle_pitch_acc</font> <font color="#434f54">=</font> <font color="#d35400">asin</font><font color="#000000">(</font><font color="#000000">(</font><font color="#00979c">float</font><font color="#000000">)</font><font color="#000000">a</font><font color="#434f54">.</font><font color="#000000">acceleration</font><font color="#434f54">.</font><font color="#000000">y</font><font color="#434f54">&#47;</font><font color="#000000">acc_total_vector</font><font color="#000000">)</font><font color="#434f54">*</font> <font color="#000000">57.296</font><font color="#000000">;</font> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#434f54">&#47;&#47;Calculate the pitch angle</font>
 &nbsp;<font color="#000000">angle_roll_acc</font> <font color="#434f54">=</font> <font color="#d35400">asin</font><font color="#000000">(</font><font color="#000000">(</font><font color="#00979c">float</font><font color="#000000">)</font><font color="#000000">a</font><font color="#434f54">.</font><font color="#000000">acceleration</font><font color="#434f54">.</font><font color="#000000">x</font><font color="#434f54">&#47;</font><font color="#000000">acc_total_vector</font><font color="#000000">)</font><font color="#434f54">*</font> <font color="#434f54">-</font><font color="#000000">57.296</font><font color="#000000">;</font> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#434f54">&#47;&#47;Calculate the roll angle</font>

 &nbsp;<font color="#000000">angle_pitch_acc</font> <font color="#434f54">-=</font> <font color="#000000">0</font><font color="#000000">;</font> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#434f54">&#47;&#47;Accelerometer calibration value for pitch</font>
 &nbsp;<font color="#000000">angle_roll_acc</font> <font color="#434f54">-=</font> <font color="#000000">0</font><font color="#000000">;</font>
 &nbsp;
 &nbsp;<font color="#000000">myData</font><font color="#434f54">.</font><font color="#000000">b</font> <font color="#434f54">=</font> <font color="#000000">angle_pitch_acc</font><font color="#000000">;</font>
 &nbsp;<font color="#000000">myData</font><font color="#434f54">.</font><font color="#000000">c</font> <font color="#434f54">=</font> <font color="#000000">angle_roll_acc</font><font color="#000000">;</font>
 &nbsp;<font color="#000000">myData</font><font color="#434f54">.</font><font color="#000000">e</font> <font color="#434f54">=</font> <font color="#00979c">true</font><font color="#000000">;</font>

 &nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">print</font><font color="#000000">(</font><font color="#005c5f">&#34;acc_pitch: &#34;</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">print</font><font color="#000000">(</font><font color="#000000">myData</font><font color="#434f54">.</font><font color="#000000">b</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">print</font><font color="#000000">(</font><font color="#005c5f">&#34; &nbsp;&nbsp;&nbsp;acc_roll: &#34;</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">println</font><font color="#000000">(</font><font color="#000000">myData</font><font color="#434f54">.</font><font color="#000000">c</font><font color="#000000">)</font><font color="#000000">;</font>

 &nbsp;<font color="#434f54">&#47;&#47; Send message via ESP-NOW</font>
 &nbsp;<font color="#000000">esp_err_t</font> <font color="#000000">result</font> <font color="#434f54">=</font> <font color="#000000">esp_now_send</font><font color="#000000">(</font><font color="#000000">broadcastAddress</font><font color="#434f54">,</font> <font color="#000000">(</font><font color="#00979c">uint8_t</font> <font color="#434f54">*</font><font color="#000000">)</font> <font color="#434f54">&amp;</font><font color="#000000">myData</font><font color="#434f54">,</font> <font color="#00979c">sizeof</font><font color="#000000">(</font><font color="#000000">myData</font><font color="#000000">)</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;
 &nbsp;<font color="#5e6d03">if</font> <font color="#000000">(</font><font color="#000000">result</font> <font color="#434f54">==</font> <font color="#000000">ESP_OK</font><font color="#000000">)</font> <font color="#000000">{</font>
 &nbsp;&nbsp;&nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">println</font><font color="#000000">(</font><font color="#005c5f">&#34;Sent with success&#34;</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;
 &nbsp;<font color="#000000">}</font>
 &nbsp;<font color="#5e6d03">else</font> <font color="#000000">{</font>
 &nbsp;&nbsp;&nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">println</font><font color="#000000">(</font><font color="#005c5f">&#34;Error sending the data&#34;</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;<font color="#000000">}</font>
 &nbsp;<font color="#d35400">delay</font><font color="#000000">(</font><font color="#000000">1000</font><font color="#000000">)</font><font color="#000000">;</font>
<font color="#000000">}</font>

</pre>

Reciever Code: 

<pre>
<font color="#95a5a6">&#47;*</font>
<font color="#95a5a6"> &nbsp;Rui Santos</font>
<font color="#95a5a6"> &nbsp;Complete project details at </font><u><font color="#95a5a6">https:&#47;&#47;RandomNerdTutorials.com&#47;esp-now-esp32-arduino-ide&#47;</font></u><font color="#95a5a6"></font>
<font color="#95a5a6"> &nbsp;</font>
<font color="#95a5a6"> &nbsp;Permission is hereby granted, free of charge, to any person obtaining a copy</font>
<font color="#95a5a6"> &nbsp;of this software and associated documentation files.</font>
<font color="#95a5a6"> &nbsp;</font>
<font color="#95a5a6"> &nbsp;The above copyright notice and this permission notice shall be included in all</font>
<font color="#95a5a6"> &nbsp;copies or substantial portions of the Software.</font>
<font color="#95a5a6">*&#47;</font>

<font color="#5e6d03">#include</font> <font color="#434f54">&lt;</font><font color="#000000">esp_now</font><font color="#434f54">.</font><font color="#000000">h</font><font color="#434f54">&gt;</font>
<font color="#5e6d03">#include</font> <font color="#434f54">&lt;</font><b><font color="#d35400">WiFi</font></b><font color="#434f54">.</font><font color="#000000">h</font><font color="#434f54">&gt;</font>
<font color="#5e6d03">#include</font><font color="#434f54">&lt;</font><font color="#d35400">analogWrite</font><font color="#434f54">.</font><font color="#000000">h</font><font color="#434f54">&gt;</font>

<font color="#434f54">&#47;&#47; Structure example to receive data</font>
<font color="#434f54">&#47;&#47; Must match the sender structure</font>
<font color="#00979c">typedef</font> <font color="#00979c">struct</font> <font color="#000000">struct_message</font> <font color="#000000">{</font>

 &nbsp;&nbsp;&nbsp;<font color="#00979c">float</font> <font color="#000000">b</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;<font color="#00979c">float</font> <font color="#000000">c</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;<font color="#00979c">bool</font> <font color="#000000">e</font><font color="#000000">;</font>
<font color="#000000">}</font> <font color="#000000">struct_message</font><font color="#000000">;</font>

<font color="#00979c">int</font> <font color="#000000">len</font><font color="#000000">;</font>

<font color="#00979c">String</font> <font color="#000000">command</font><font color="#000000">;</font>
 &nbsp;
 &nbsp;<font color="#00979c">const</font> <font color="#00979c">int</font> <font color="#000000">in1</font> <font color="#434f54">=</font> <font color="#000000">23</font><font color="#000000">;</font>

 &nbsp;<font color="#00979c">const</font> <font color="#00979c">int</font> <font color="#000000">in2</font> <font color="#434f54">=</font> <font color="#000000">5</font><font color="#000000">;</font>

 &nbsp;<font color="#00979c">const</font> <font color="#00979c">int</font> <font color="#000000">in3</font> <font color="#434f54">=</font> <font color="#000000">18</font><font color="#000000">;</font>

 &nbsp;<font color="#00979c">const</font> <font color="#00979c">int</font> <font color="#000000">in4</font> <font color="#434f54">=</font> <font color="#000000">19</font><font color="#000000">;</font>

 &nbsp;<font color="#00979c">const</font> <font color="#00979c">int</font> <font color="#000000">enA</font> <font color="#434f54">=</font> <font color="#000000">22</font><font color="#000000">;</font>

 &nbsp;<font color="#00979c">const</font> <font color="#00979c">int</font> <font color="#000000">enB</font> <font color="#434f54">=</font> <font color="#000000">21</font><font color="#000000">;</font>

<font color="#434f54">&#47;&#47; Create a struct_message called myData</font>
<font color="#000000">struct_message</font> <font color="#000000">myData</font><font color="#000000">;</font>

<font color="#434f54">&#47;&#47; callback function that will be executed when data is received</font>
<font color="#00979c">void</font> <font color="#000000">OnDataRecv</font><font color="#000000">(</font><font color="#00979c">const</font> <font color="#00979c">uint8_t</font> <font color="#434f54">*</font> <font color="#000000">mac</font><font color="#434f54">,</font> <font color="#00979c">const</font> <font color="#00979c">uint8_t</font> <font color="#434f54">*</font><font color="#000000">incomingData</font><font color="#434f54">,</font> <font color="#00979c">int</font> <font color="#000000">len</font><font color="#000000">)</font> <font color="#000000">{</font>
 &nbsp;<font color="#d35400">memcpy</font><font color="#000000">(</font><font color="#434f54">&amp;</font><font color="#000000">myData</font><font color="#434f54">,</font> <font color="#000000">incomingData</font><font color="#434f54">,</font> <font color="#00979c">sizeof</font><font color="#000000">(</font><font color="#000000">myData</font><font color="#000000">)</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;
 &nbsp;<font color="#95a5a6">&#47;*</font>
<font color="#95a5a6"> &nbsp;Serial.print(&#34;Bytes received: &#34;);</font>
<font color="#95a5a6"> &nbsp;Serial.println(len);</font>
<font color="#95a5a6"> &nbsp;Serial.print(&#34;Char: &#34;);</font>
<font color="#95a5a6"> &nbsp;Serial.println(myData.a);</font>
<font color="#95a5a6"> &nbsp;Serial.print(&#34;Int: &#34;);</font>
<font color="#95a5a6"> &nbsp;Serial.println(myData.b);</font>
<font color="#95a5a6"> &nbsp;Serial.print(&#34;Float: &#34;);</font>
<font color="#95a5a6"> &nbsp;Serial.println(myData.c);</font>
<font color="#95a5a6"> &nbsp;Serial.print(&#34;String: &#34;);</font>
<font color="#95a5a6"> &nbsp;Serial.println(myData.d);</font>
<font color="#95a5a6"> &nbsp;Serial.print(&#34;Bool: &#34;);</font>
<font color="#95a5a6"> &nbsp;Serial.println(myData.e);</font>
<font color="#95a5a6"> &nbsp;Serial.println(); *&#47;</font>
<font color="#000000">}</font>
 
<font color="#00979c">void</font> <font color="#5e6d03">setup</font><font color="#000000">(</font><font color="#000000">)</font> <font color="#000000">{</font>
 &nbsp;<font color="#434f54">&#47;&#47; Initialize Serial Monitor</font>
 &nbsp;<font color="#d35400">pinMode</font><font color="#000000">(</font><font color="#000000">in1</font><font color="#434f54">,</font> <font color="#00979c">OUTPUT</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;<font color="#d35400">pinMode</font><font color="#000000">(</font><font color="#000000">in2</font><font color="#434f54">,</font> <font color="#00979c">OUTPUT</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;<font color="#d35400">pinMode</font><font color="#000000">(</font><font color="#000000">in3</font><font color="#434f54">,</font> <font color="#00979c">OUTPUT</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;<font color="#d35400">pinMode</font><font color="#000000">(</font><font color="#000000">in4</font><font color="#434f54">,</font> <font color="#00979c">OUTPUT</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;<font color="#d35400">pinMode</font><font color="#000000">(</font><font color="#000000">enA</font><font color="#434f54">,</font> <font color="#00979c">OUTPUT</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;<font color="#d35400">pinMode</font><font color="#000000">(</font><font color="#000000">enB</font><font color="#434f54">,</font> <font color="#00979c">OUTPUT</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">begin</font><font color="#000000">(</font><font color="#000000">115200</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;
 &nbsp;<font color="#434f54">&#47;&#47; Set device as a Wi-Fi Station</font>
 &nbsp;<b><font color="#d35400">WiFi</font></b><font color="#434f54">.</font><font color="#d35400">mode</font><font color="#000000">(</font><font color="#00979c">WIFI_STA</font><font color="#000000">)</font><font color="#000000">;</font>

 &nbsp;<font color="#434f54">&#47;&#47; Init ESP-NOW</font>
 &nbsp;<font color="#5e6d03">if</font> <font color="#000000">(</font><font color="#000000">esp_now_init</font><font color="#000000">(</font><font color="#000000">)</font> <font color="#434f54">!=</font> <font color="#000000">ESP_OK</font><font color="#000000">)</font> <font color="#000000">{</font>
 &nbsp;&nbsp;&nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">println</font><font color="#000000">(</font><font color="#005c5f">&#34;Error initializing ESP-NOW&#34;</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;<font color="#5e6d03">return</font><font color="#000000">;</font>
 &nbsp;<font color="#000000">}</font>
 &nbsp;
 &nbsp;<font color="#434f54">&#47;&#47; Once ESPNow is successfully Init, we will register for recv CB to</font>
 &nbsp;<font color="#434f54">&#47;&#47; get recv packer info</font>
 &nbsp;<font color="#434f54">&#47;&#47; &nbsp;esp_now_register_recv_cb(OnDataRecv);</font>
<font color="#000000">}</font>
 
<font color="#00979c">void</font> <font color="#5e6d03">loop</font><font color="#000000">(</font><font color="#000000">)</font> <font color="#000000">{</font>
 &nbsp;<font color="#000000">esp_now_register_recv_cb</font><font color="#000000">(</font><font color="#000000">OnDataRecv</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;
 &nbsp;<font color="#5e6d03">if</font><font color="#000000">(</font><font color="#000000">myData</font><font color="#434f54">.</font><font color="#000000">e</font><font color="#000000">)</font><font color="#000000">{</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">print</font><font color="#000000">(</font><font color="#005c5f">&#34;Bytes received: &#34;</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">println</font><font color="#000000">(</font><font color="#000000">len</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">print</font><font color="#000000">(</font><font color="#005c5f">&#34;Pitch: &#34;</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">println</font><font color="#000000">(</font><font color="#000000">myData</font><font color="#434f54">.</font><font color="#000000">b</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">print</font><font color="#000000">(</font><font color="#005c5f">&#34;Roll: &#34;</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">println</font><font color="#000000">(</font><font color="#000000">myData</font><font color="#434f54">.</font><font color="#000000">c</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">print</font><font color="#000000">(</font><font color="#005c5f">&#34;Bool: &#34;</font><font color="#000000">)</font><font color="#000000">;</font> 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">println</font><font color="#000000">(</font><font color="#000000">myData</font><font color="#434f54">.</font><font color="#000000">e</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">println</font><font color="#000000">(</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#000000">myData</font><font color="#434f54">.</font><font color="#000000">e</font> <font color="#434f54">=</font> <font color="#00979c">false</font><font color="#000000">;</font>
 &nbsp;<font color="#000000">}</font>

 &nbsp;<font color="#5e6d03">if</font><font color="#000000">(</font><font color="#000000">myData</font><font color="#434f54">.</font><font color="#000000">b</font> <font color="#434f54">&lt;=</font> <font color="#434f54">-</font><font color="#000000">50.00</font> <font color="#434f54">&amp;&amp;</font> <font color="#000000">myData</font><font color="#434f54">.</font><font color="#000000">c</font> <font color="#434f54">&gt;=</font> <font color="#434f54">-</font><font color="#000000">2</font><font color="#000000">)</font><font color="#000000">{</font> <font color="#434f54">&#47;&#47; forwards</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">in1</font><font color="#434f54">,</font> <font color="#00979c">HIGH</font><font color="#000000">)</font><font color="#000000">;</font> 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">in2</font><font color="#434f54">,</font> <font color="#00979c">LOW</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">in3</font><font color="#434f54">,</font> <font color="#00979c">HIGH</font><font color="#000000">)</font><font color="#000000">;</font> 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">in4</font><font color="#434f54">,</font> <font color="#00979c">LOW</font><font color="#000000">)</font><font color="#000000">;</font> &nbsp;
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">analogWrite</font><font color="#000000">(</font><font color="#000000">enA</font><font color="#434f54">,</font> <font color="#000000">245</font><font color="#000000">)</font><font color="#000000">;</font> 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">analogWrite</font><font color="#000000">(</font><font color="#000000">enB</font><font color="#434f54">,</font> <font color="#000000">245</font><font color="#000000">)</font><font color="#000000">;</font> 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">println</font><font color="#000000">(</font><font color="#005c5f">&#34;Forwards&#34;</font><font color="#000000">)</font><font color="#000000">;</font>

 &nbsp;<font color="#000000">}</font>

 &nbsp;<font color="#5e6d03">if</font><font color="#000000">(</font><font color="#000000">myData</font><font color="#434f54">.</font><font color="#000000">c</font> <font color="#434f54">&gt;=</font> <font color="#000000">40.00</font><font color="#000000">)</font><font color="#000000">{</font> <font color="#434f54">&#47;&#47; right </font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">in1</font><font color="#434f54">,</font> <font color="#00979c">HIGH</font><font color="#000000">)</font><font color="#000000">;</font> 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">in2</font><font color="#434f54">,</font> <font color="#00979c">LOW</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">in3</font><font color="#434f54">,</font> <font color="#00979c">LOW</font><font color="#000000">)</font><font color="#000000">;</font> 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">in4</font><font color="#434f54">,</font> <font color="#00979c">LOW</font><font color="#000000">)</font><font color="#000000">;</font> &nbsp;
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">println</font><font color="#000000">(</font><font color="#005c5f">&#34;Right&#34;</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">analogWrite</font><font color="#000000">(</font><font color="#000000">enA</font><font color="#434f54">,</font> <font color="#000000">245</font><font color="#000000">)</font><font color="#000000">;</font> 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">analogWrite</font><font color="#000000">(</font><font color="#000000">enB</font><font color="#434f54">,</font> <font color="#000000">245</font><font color="#000000">)</font><font color="#000000">;</font> 

 &nbsp;<font color="#000000">}</font>

 &nbsp;<font color="#5e6d03">if</font><font color="#000000">(</font><font color="#000000">myData</font><font color="#434f54">.</font><font color="#000000">c</font> <font color="#434f54">&lt;=</font> <font color="#434f54">-</font><font color="#000000">40.00</font><font color="#000000">)</font><font color="#000000">{</font> <font color="#434f54">&#47;&#47; left </font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">in1</font><font color="#434f54">,</font> <font color="#00979c">LOW</font><font color="#000000">)</font><font color="#000000">;</font> 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">in2</font><font color="#434f54">,</font> <font color="#00979c">LOW</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">in3</font><font color="#434f54">,</font> <font color="#00979c">HIGH</font><font color="#000000">)</font><font color="#000000">;</font> 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">in4</font><font color="#434f54">,</font> <font color="#00979c">LOW</font><font color="#000000">)</font><font color="#000000">;</font> &nbsp;
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">println</font><font color="#000000">(</font><font color="#005c5f">&#34;Left&#34;</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">analogWrite</font><font color="#000000">(</font><font color="#000000">enA</font><font color="#434f54">,</font> <font color="#000000">245</font><font color="#000000">)</font><font color="#000000">;</font> 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">analogWrite</font><font color="#000000">(</font><font color="#000000">enB</font><font color="#434f54">,</font> <font color="#000000">245</font><font color="#000000">)</font><font color="#000000">;</font> 

 &nbsp;<font color="#000000">}</font>

 &nbsp;<font color="#5e6d03">if</font><font color="#000000">(</font><font color="#000000">myData</font><font color="#434f54">.</font><font color="#000000">b</font> <font color="#434f54">&gt;=</font> <font color="#000000">40</font><font color="#000000">)</font><font color="#000000">{</font> <font color="#434f54">&#47;&#47; backwards</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">in1</font><font color="#434f54">,</font> <font color="#00979c">LOW</font><font color="#000000">)</font><font color="#000000">;</font> 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">in2</font><font color="#434f54">,</font> <font color="#00979c">HIGH</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">in3</font><font color="#434f54">,</font> <font color="#00979c">LOW</font><font color="#000000">)</font><font color="#000000">;</font> 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">in4</font><font color="#434f54">,</font> <font color="#00979c">HIGH</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">analogWrite</font><font color="#000000">(</font><font color="#000000">enA</font><font color="#434f54">,</font> <font color="#000000">245</font><font color="#000000">)</font><font color="#000000">;</font> 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">analogWrite</font><font color="#000000">(</font><font color="#000000">enB</font><font color="#434f54">,</font> <font color="#000000">245</font><font color="#000000">)</font><font color="#000000">;</font> &nbsp;&nbsp;
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">println</font><font color="#000000">(</font><font color="#005c5f">&#34;Backwards&#34;</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 &nbsp;<font color="#000000">}</font>



<font color="#000000">}</font>

</pre>

