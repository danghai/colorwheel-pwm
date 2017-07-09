# Colorwheel Implementation
 
Colorwheel Implementation Generate a variable duty-cycle PWM (Pulse Width Modulation) output signal for the on board RGB LED’s and detect the duty cycle of that PWM output by hardware and software pulse-width detection algorithm. Project use a PmodENC to add a rotary encoder and additional pushbutton to Colorwheel implementation, and use a PmodOLEDrgb to provide color display output. Project was written by Verilog language for hardware parts, and C language for software parts. 

For the project we will be using the available peripherals of the board in the following manner:  
 
### a) The slide switches, pushbuttons and rotary encoder are used as follows:
1. Slide Switches [15:1] have no assigned functionality for this project.
 
2. Slide Switch [0] – This slide switch on the Nexys4 DDR selects between software and hardware pulse width detection. Hardware pulse width detection should be enabled when the switch is on (up) and software pulse width detection should be enabled when the switch is off (down). 
 
Rotary Encoder – The rotary encoder knob on the PmodENC is used to alter the Hue value of the Colorwheel. Hence as seen in the above figure, as hue changes, the color should change as well. The pushbutton of the Rotary Encoder should terminate the application. 
 

 
 
### b) Pushbuttons 

1. System reset is done by pressing the CPU Reset button (the button is red) on the Nexys4 DDR. This button is mapped to the sysreset_n (asserted low) and sysreset (asserted high) signals in the top level.
   
2. The btnR and btnL are used to vary the saturation value in the HSV scale. 3. The btnU and btnD are used to vary the Value in the HSV scale. 
 
The sample application uses the Rotary Encoder pushbutton (press the knob instead of turn it) to terminate the application.  The same could be done in your program but this is not required.  Typically an embedded application does not terminate, but instead runs in an infinite loop reading and processing inputs. 
 
The display of the PmodOLEDrgb should be as follows: 

1. There should be the display of the current Hue, Saturation and Value values on the left side of the display. 

2. There should be a Square or a Rectangle showing the color for the corresponding value of the Hue, Saturation and Value values in the HSV scale.  
 

 
The LEDs on the Nexys4 DDR board should be used as follows: 

1. LEDs [15:1] – These LEDS have no dedicated functionality for this project but you can use them to enhance your application. 

2. LED [0] – Is used to provide a visual indication of the PWM detection module. If it is lit, it must indicate that the detection is done from the hardware module and vice versa. 

3. RGB1 and RGB2 – The tri-color LEDs indicate the color selected from the colorwheel or the color displayed on the colorwheel, i.e. the color displayed on the rectangle in the PmodOLEDrgb display. The signal driving the RGB Display should be taken for PWM detection. 
 
The Seven Segment display on the Nexys4 DDR should be used as follows: 

1. Digits [7:6] should display the duty cycle detected for the RED RGB led. 
 
2. Digit [5] is left blank or for any enhancement of the display. 

3. Digits [4:3] should display the duty cycle detected for the GREEN RGB led.  

4. Digit [2] should be left blank. 5. Digits [1:0] should display the duty cycle detected for the BLUE RGB led. 
 
# Design
Project Design: [Project Design](https://github.com/danghai/colorwheel-pwm/blob/master/Design_Report.pdf) 
Link video for demo: [Video demo](https://www.youtube.com/watch?v=7sWxsoR2xG0&t=5s)


