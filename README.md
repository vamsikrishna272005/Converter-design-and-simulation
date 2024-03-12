# Converter-design-and-simulation

# Aim
To design and simulate AC to DC converter & DC voltage regulator using proteus.

# Software’s required

	Proteus simulator

# Procedure

	Open the Proteus software </br>
	Go to file select new design and click ok button.</br>
	Select component mode and click pick devices from the library. </br>
	Type the component name in the keyword to select the components and click ok button.</br>
	Connect the components as per the circuit diagram</br>
		Click start button and verify the output </br>

# Theory
## Full Wave Bridge Rectifier

A full wave bridge rectifier is a rectifier that will use four diodes or more than that in a bridge formation. A full wave bridge rectifier system consists of Four Diodes and Resistive Load

![image](https://github.com/anishkumar-Embedded/Converter-design-and-simulation/assets/71547910/c1d1bd75-67d3-4887-9ec0-e94bb69220f9)
Principle of Full Wave Bridge Rectifier

We apply an AC across the bridge. During the positive half-cycle, terminal 1 becomes positive, and terminal 2 becomes negative. This will cause the diodes A and C to become forward-biased, and the current will flow through it. Meanwhile, diodes B and D will become reverse-biased and block current through them. The current will flow from 1 to 4 to 3 to 2.
During the negative half-cycle, terminal 1 will become negative, and terminal 2 will become positive. This will cause the diodes B and D to become forward-biased and will allow current through them. At the same time, diodes A and C will be reverse-biased and will block the current through them. The current will flow from 2 to 4 to 3 to 1.

![image](https://github.com/anishkumar-Embedded/Converter-design-and-simulation/assets/71547910/4e0da706-8e63-495c-acfb-9f507aab3225)
## Filter Circuit
We get a pulsating DC voltage with many ripples as the output of the full wave bridge rectifier. We cannot use this voltage for practical applications.
So, to convert the pulsating DC voltage to pure DC voltage, we use a filter circuit as shown above. Here we place a capacitor across the load. The working of the capacitive filter circuit is to short the ripples and block the DC component so that it flows through another path, and that is through the load. During the half-wave, the diodes A and C conduct. It charges the capacitor immediately to the maximum value of the input voltage. 

![image](https://github.com/anishkumar-Embedded/Converter-design-and-simulation/assets/71547910/5a47b9ae-041a-419b-8eef-2c163f4fb234)

## Full Wave Rectifier Formula

### Ripple Factor of a Full Wave Rectifier (γ)

‘Ripple’ is the unwanted AC component remaining when converting the AC voltage waveform into a DC waveform.Even though we try out best to remove all AC components, there is still some small amount left on the output side which pulsates the DC waveform. This undesirable AC component is called ‘ripple’.To quantify how well the half-wave rectifier can convert the AC voltage into DC voltage, we use what is known as the ripple factor (represented by γ or r).The ripple factor is the ratio between the RMS value of the AC voltage (on the input side) and the DC voltage (on the output side) of the rectifier. The formula for ripple factor is:
 
Where Vrms is the RMS value of the AC component, and Vdc is the DC component in the rectifier.The ripple factor of a centre-tapped full-wave rectifier is equal to 0.48 (i.e. γ = 0.48).Note: To construct a good rectifier, we need to keep the ripple factor as minimum as possible. We can use capacitors or inductors to reduce the ripples in the circuit.

![image](https://github.com/anishkumar-Embedded/Converter-design-and-simulation/assets/71547910/800a4598-6db1-455a-8b21-539fd0666474)


### Efficiency of a Full Wave Rectifier (η)

Rectifier efficiency (η) is the ratio between the output DC power and the input AC power. The formula for the efficiency is equal to:The efficiency of a centre-tapped full-wave rectifier is equal to 81.2% (i.e. ηmax = 81.2%).
![image](https://github.com/anishkumar-Embedded/Converter-design-and-simulation/assets/71547910/a3e9e2f4-ec5b-47d6-a326-3b3b516ab7cc)


### Form Factor of a Full Wave Rectifier (F.F)

The form factor is the ratio between RMS value and average value.The formula for form factor is given below:The form factor of a centre-tapped full wave rectifier is equal to 1.11 (i.e. FF = 1.11).
![image](https://github.com/anishkumar-Embedded/Converter-design-and-simulation/assets/71547910/7f9dd86a-b340-463f-bbb6-3c6c4ee5f448)


### Advantages of Full Wave Rectifiers

•	Full wave rectifiers have higher rectifying efficiency than half-wave rectifiers. This means that they convert AC to DC more efficiently.</br>
•	They have low power loss because no voltage signal is wasted in the rectification process.</br>
•	The output voltage of a centre-tapped full wave rectifier has lower ripples than a halfwave rectifiers.</br>

### Disadvantages of Full Wave Rectifiers

•	The centre-tapped rectifier is more expensive than a half-wave rectifier and tends to occupy a lot of space.</br>

## DC voltage regulator 

A regulated power supply is very much essential for several electronic devices due to the semiconductor material employed in them have a fixed rate of current as well as voltage. The device may get damaged if there is any deviation from the fixed rate. One of the important sources of DC Supply are Batteries. But using batteries in sensitive electronic circuits is not a good idea as batteries eventually drain out and loose their potential over time.Also, the voltage provided by batteries are typically 1.2V, 3.7V, 9V and 12V. This is good for circuits whose voltage requirements are in that range. But, most of the TTL IC’s work on 5V logic and hence we need a mechanism to provide a consistent 5V Supply. 7805 is a three terminal linear voltage regulator IC with a fixed output voltage of 5V which is useful in a wide range of applications. Currently, the 7805 Voltage Regulator IC is manufactured by Texas Instruments, ON Semiconductor, STMicroelectronics, Diodes incorporated, Infineon Technologies, etc. hey are available in several IC Packages like TO-220, SOT-223, TO-263 and TO-3. Out of these, the TO-220 Package is the most commonly used one (it is the one shown in the above image).

Some of the important features of the 7805 IC are as follows: 

•	It can deliver up to 1.5 A of current (with heat sink).</br> 
•	Has both internal current limiting and thermal shutdown features. </br>
•	Requires very minimum external components to fully function. </br>

### Pin Diagram of 7805 Voltage Regulator IC

As mentioned earlier, 7805 is a three terminal device with the three pins being 1. INPUT, 2. GROUND and 3. OUTPUT. The following image shows the pins on a typical 7805 IC in To-220 Package.

![image](https://github.com/anishkumar-Embedded/Converter-design-and-simulation/assets/71547910/8744affc-c781-4bbf-a0ee-23dbf81afb53)

## Working 

The AC power supply from mains first gets converted into and unregulated DC and then into a constant regulated DC with the help of this circuit. The circuit is made up of transformer, bridge rectifier made up from diodes, linear voltage regulator 7805 and capacitors. If you observe, the working of the circuit can be divided into two parts. In the first part, the AC Mains is converted into unregulated DC and in the second part, this unregulated DC is converted into regulated 5V DC. So, let us start discussing the working with this in mind.Initially, a 230V to 12V Step down transformer is taken and its primary is connected to mains supply. The secondary of the transformer is connected to Bridge rectifier (either a dedicated IC or a combination of 4 1N4007 Diodes can be used). A 1A fuse is placed between the transformer and the bridge rectifier. This will limit the current drawn by the circuit to 1A. The rectified DC from the bridge rectifier is smoothened out with the help of 1000μF Capacitor. So, the output across the 1000μF Capacitor is unregulated 12V DC. This is given as an input to the 7805 Voltage Regulator IC. 7805 IC then converts this to a regulated 5V DC and the output can be obtained at its output terminals

![image](https://github.com/anishkumar-Embedded/Converter-design-and-simulation/assets/71547910/6ab6579b-5bca-4ce5-b485-ca8cb1ebca1f)

# Circuit Diagram

## AC to DC Converter

![image](https://github.com/anishkumar-Embedded/Converter-design-and-simulation/assets/71547910/9fbaa555-6932-4643-982c-63dbb0d6607b)

## DC to DC voltage regulator

![image](https://github.com/anishkumar-Embedded/Converter-design-and-simulation/assets/71547910/0cfd4fc7-1eff-42e3-9806-319bfe174926)

# Output





# Result 

Thus the AC to DC converter and DC voltage regulator are designed and simulated using Proteus.


