# Gesture-Controlled Robot Car 
Similarly to how TV shows and movie series animate powers which can move objects without manually holding them, I am working on a robot car which can move according to different hand gestures. 

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Lorelei X. | IHS | Electrical Engineering | Incoming Sophomore

![Headstone Image](![avatars-000297971625-hku9dk-t500x500](https://user-images.githubusercontent.com/86121949/122603724-a6773980-d029-11eb-95e3-0591bc015a68.jpeg))
  
# Final Milestone

![avatars-000297971625-hku9dk-t500x500](https://user-images.githubusercontent.com/86121949/122603767-b55dec00-d029-11eb-8ef5-acfa045e1816.jpeg)


# Second Milestone 

My second milestone was to configure a setup where accelerometer values would be read and used to move the car accordingly. I began with testing out the accelerometer output values, which x,y, and z values changed according to the orientation of the device. I think plugged it into a secondary ESP, which would transmit the accelerometer values to the ESP attached to the vehicle. With this, I coded different thresholds that when crossed, the car would move accordingly. At the end, I was able to move the car according to the direction that I orient the accelerometer device. For my next milestone, I hope to achieve a LED light indicator system, which would light up according to the direction that the vehicle is going, similarly to a regular car. 


<img width="839" alt="Screen Shot 2021-06-25 at 11 02 59 AM" src="https://user-images.githubusercontent.com/86121949/123467071-f06d9b80-d5a4-11eb-9fe7-20a84b5fdc0a.png">

<pre>

 &nbsp;<font color="#5e6d03">#include</font><font color="#434f54">&lt;</font><font color="#d35400">analogWrite</font><font color="#434f54">.</font><font color="#000000">h</font><font color="#434f54">&gt;</font>
 &nbsp;
 &nbsp;<font color="#00979c">String</font> <font color="#000000">command</font><font color="#000000">;</font>
 &nbsp;<font color="#00979c">float</font> <font color="#000000">num</font><font color="#000000">;</font>
 &nbsp;
 &nbsp;<font color="#00979c">const</font> <font color="#00979c">int</font> <font color="#000000">in1</font> <font color="#434f54">=</font> <font color="#000000">4</font><font color="#000000">;</font>

 &nbsp;<font color="#00979c">const</font> <font color="#00979c">int</font> <font color="#000000">in2</font> <font color="#434f54">=</font> <font color="#000000">5</font><font color="#000000">;</font>

 &nbsp;<font color="#00979c">const</font> <font color="#00979c">int</font> <font color="#000000">in3</font> <font color="#434f54">=</font> <font color="#000000">18</font><font color="#000000">;</font>

 &nbsp;<font color="#00979c">const</font> <font color="#00979c">int</font> <font color="#000000">in4</font> <font color="#434f54">=</font> <font color="#000000">19</font><font color="#000000">;</font>

 &nbsp;<font color="#00979c">const</font> <font color="#00979c">int</font> <font color="#000000">enA</font> <font color="#434f54">=</font> <font color="#000000">15</font><font color="#000000">;</font>

 &nbsp;<font color="#00979c">const</font> <font color="#00979c">int</font> <font color="#000000">enB</font> <font color="#434f54">=</font> <font color="#000000">21</font><font color="#000000">;</font>
 &nbsp;
<font color="#00979c">void</font> <font color="#5e6d03">setup</font><font color="#000000">(</font><font color="#000000">)</font> <font color="#000000">{</font>
 &nbsp;<font color="#d35400">pinMode</font><font color="#000000">(</font><font color="#000000">in1</font><font color="#434f54">,</font> <font color="#00979c">OUTPUT</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;<font color="#d35400">pinMode</font><font color="#000000">(</font><font color="#000000">in2</font><font color="#434f54">,</font> <font color="#00979c">OUTPUT</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;<font color="#d35400">pinMode</font><font color="#000000">(</font><font color="#000000">in3</font><font color="#434f54">,</font> <font color="#00979c">OUTPUT</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;<font color="#d35400">pinMode</font><font color="#000000">(</font><font color="#000000">in4</font><font color="#434f54">,</font> <font color="#00979c">OUTPUT</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;<font color="#d35400">pinMode</font><font color="#000000">(</font><font color="#000000">enA</font><font color="#434f54">,</font> <font color="#00979c">OUTPUT</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;<font color="#d35400">pinMode</font><font color="#000000">(</font><font color="#000000">enB</font><font color="#434f54">,</font> <font color="#00979c">OUTPUT</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;
 &nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">begin</font><font color="#000000">(</font><font color="#000000">115200</font><font color="#000000">)</font><font color="#000000">;</font>

<font color="#000000">}</font>

<font color="#00979c">void</font> <font color="#5e6d03">loop</font><font color="#000000">(</font><font color="#000000">)</font> <font color="#000000">{</font>
 &nbsp;<font color="#434f54">&#47;&#47; put your main code here, to run repeatedly:</font>

 &nbsp;<font color="#5e6d03">if</font> <font color="#000000">(</font><b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">available</font><font color="#000000">(</font><font color="#000000">)</font><font color="#000000">)</font> <font color="#000000">{</font>

 &nbsp;&nbsp;&nbsp;<font color="#000000">command</font> <font color="#434f54">=</font> <b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">readStringUntil</font><font color="#000000">(</font><font color="#00979c">&#39;\n&#39;</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;<font color="#00979c">int</font> <font color="#000000">num</font> <font color="#434f54">=</font> <font color="#000000">command</font><font color="#434f54">.</font><font color="#000000">toFloat</font><font color="#000000">(</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">println</font><font color="#000000">(</font><font color="#000000">num</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#5e6d03">if</font><font color="#000000">(</font><font color="#000000">num</font> <font color="#434f54">==</font> <font color="#000000">1</font><font color="#000000">)</font><font color="#000000">{</font> <font color="#434f54">&#47;&#47; forwards</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">in1</font><font color="#434f54">,</font> <font color="#00979c">HIGH</font><font color="#000000">)</font><font color="#000000">;</font> 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">in2</font><font color="#434f54">,</font> <font color="#00979c">LOW</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">in3</font><font color="#434f54">,</font> <font color="#00979c">HIGH</font><font color="#000000">)</font><font color="#000000">;</font> 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">in4</font><font color="#434f54">,</font> <font color="#00979c">LOW</font><font color="#000000">)</font><font color="#000000">;</font> &nbsp;
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">analogWrite</font><font color="#000000">(</font><font color="#000000">enA</font><font color="#434f54">,</font> <font color="#000000">245</font><font color="#000000">)</font><font color="#000000">;</font> 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">analogWrite</font><font color="#000000">(</font><font color="#000000">enB</font><font color="#434f54">,</font> <font color="#000000">245</font><font color="#000000">)</font><font color="#000000">;</font> 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">println</font><font color="#000000">(</font><font color="#005c5f">&#34;Forwards&#34;</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#000000">}</font>

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#5e6d03">if</font><font color="#000000">(</font><font color="#000000">num</font> <font color="#434f54">==</font> <font color="#000000">2</font><font color="#000000">)</font><font color="#000000">{</font> <font color="#434f54">&#47;&#47; right </font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">in1</font><font color="#434f54">,</font> <font color="#00979c">HIGH</font><font color="#000000">)</font><font color="#000000">;</font> 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">in2</font><font color="#434f54">,</font> <font color="#00979c">LOW</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">in3</font><font color="#434f54">,</font> <font color="#00979c">LOW</font><font color="#000000">)</font><font color="#000000">;</font> 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">in4</font><font color="#434f54">,</font> <font color="#00979c">LOW</font><font color="#000000">)</font><font color="#000000">;</font> &nbsp;
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">println</font><font color="#000000">(</font><font color="#005c5f">&#34;Right&#34;</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">analogWrite</font><font color="#000000">(</font><font color="#000000">enA</font><font color="#434f54">,</font> <font color="#000000">245</font><font color="#000000">)</font><font color="#000000">;</font> 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">analogWrite</font><font color="#000000">(</font><font color="#000000">enB</font><font color="#434f54">,</font> <font color="#000000">245</font><font color="#000000">)</font><font color="#000000">;</font> 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#000000">}</font>

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#5e6d03">if</font><font color="#000000">(</font><font color="#000000">num</font> <font color="#434f54">==</font> <font color="#000000">3</font><font color="#000000">)</font><font color="#000000">{</font> <font color="#434f54">&#47;&#47; left </font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">in1</font><font color="#434f54">,</font> <font color="#00979c">LOW</font><font color="#000000">)</font><font color="#000000">;</font> 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">in2</font><font color="#434f54">,</font> <font color="#00979c">LOW</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">in3</font><font color="#434f54">,</font> <font color="#00979c">HIGH</font><font color="#000000">)</font><font color="#000000">;</font> 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">in4</font><font color="#434f54">,</font> <font color="#00979c">LOW</font><font color="#000000">)</font><font color="#000000">;</font> &nbsp;
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">println</font><font color="#000000">(</font><font color="#005c5f">&#34;Left&#34;</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">analogWrite</font><font color="#000000">(</font><font color="#000000">enA</font><font color="#434f54">,</font> <font color="#000000">245</font><font color="#000000">)</font><font color="#000000">;</font> 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">analogWrite</font><font color="#000000">(</font><font color="#000000">enB</font><font color="#434f54">,</font> <font color="#000000">245</font><font color="#000000">)</font><font color="#000000">;</font> 

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#000000">}</font>

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#5e6d03">if</font><font color="#000000">(</font><font color="#000000">num</font> <font color="#434f54">==</font> <font color="#000000">4</font><font color="#000000">)</font><font color="#000000">{</font> <font color="#434f54">&#47;&#47; backwards</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">in1</font><font color="#434f54">,</font> <font color="#00979c">LOW</font><font color="#000000">)</font><font color="#000000">;</font> 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">in2</font><font color="#434f54">,</font> <font color="#00979c">HIGH</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">in3</font><font color="#434f54">,</font> <font color="#00979c">LOW</font><font color="#000000">)</font><font color="#000000">;</font> 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">digitalWrite</font><font color="#000000">(</font><font color="#000000">in4</font><font color="#434f54">,</font> <font color="#00979c">HIGH</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">analogWrite</font><font color="#000000">(</font><font color="#000000">enA</font><font color="#434f54">,</font> <font color="#000000">245</font><font color="#000000">)</font><font color="#000000">;</font> 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#d35400">analogWrite</font><font color="#000000">(</font><font color="#000000">enB</font><font color="#434f54">,</font> <font color="#000000">245</font><font color="#000000">)</font><font color="#000000">;</font> &nbsp;&nbsp;
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b><font color="#d35400">Serial</font></b><font color="#434f54">.</font><font color="#d35400">println</font><font color="#000000">(</font><font color="#005c5f">&#34;Backwards&#34;</font><font color="#000000">)</font><font color="#000000">;</font>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<font color="#000000">}</font>

 &nbsp;<font color="#000000">}</font>
 
 &nbsp;
<font color="#000000">}</font>


</pre>

[![Second Milestone](https://res.cloudinary.com/marcomontalbano/image/upload/v1625095547/video_to_markdown/images/youtube--osunMRoNDPg-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://www.youtube.com/watch?v=osunMRoNDPg "Lorelei's Second Milestone"){:target="_blank" rel="noopener"}

# First Milestone

My first milestone was to understand the functioning of motors and motor drivers, and how I can implicate those into my robot car. Starting off, I downloaded the Arduino coding software, which I would use ot code the different commands that I wish my robot to execute. Moving on to the car, I began with working on powering only two motors/wheels, color-coding the different jumper wires used to connect the motors to the motor-driver outputs. From there, I plugged in a battery pack as my power source, while using a jumper wire to manually turn on each motor and drive in different directions. Due to its success, I added two more motors, stuffing the extra sets of jumper wires into the motor-driver outputs. However, instead of powering it manually, I used Arduino to code a simple code which would move all 4 tires simultaneously at a fixed speed. Once finished,  I disassembled the parts of my prototype and transferred the pieces onto a chassis, where I reassembled the pieces to complete my first milestone. 

[![First Milestone][![Lorelei's First Milestone](https://res.cloudinary.com/marcomontalbano/image/upload/v1624639367/video_to_markdown/images/youtube--0S75vxPjRFs-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://www.youtube.com/watch?v=0S75vxPjRFs "Lorelei's First Milestone"){:target="_blank" rel="noopener"}
