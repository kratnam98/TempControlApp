# TempControlApp

User Manual Kumaran Ratnam


Purpose
The purpose of this project is to use allow for a user to accurately measure a distance within an accuracy of 10cm, and have the system return feedback based on how far or close to the ideal value they are. The system should allow for the user to increment or decrement the ideal value. The 5 LED should be used to let user know if they are too close, too far, or just there. As there are 5 LED’s, if the first 3 are lit up, then the user is too close. If the 2nd and 3rd are lit up, they are almost there, but still too close. If only the middle is lit up, then they are right there. If 3rd and fourth are lit, then they are just a little far away. If last 3 LED’s are all lit up, then they are way too far. In addition to the LED’s, there is also a buzzer, that beep at different intervals depending on the distance from the object. If the user is within 5 cm of the ideal distance, the buzzer will beep really fast. If they are a little far or little close, the buzzer will beep less frequently. If there are too far or too close form the ideal distance, the buzzer will beep even less frequently. The buttons on the side can be used to change to ideal distance you want to target. Use the right button to increment to target distance, left button to decrement the target distance. All data is displayed neatly on the LCD, including current distance and target distance.

Parts
    Part
   Model Number
      Usage
     Ultrasonic sensor
HC-SR04
  This part is used to get an accurate reading of how far an object is from the sensor
    I2C
 PCF8574T
     This is used to take the 12 outputs from the LCD, and convert them so there are 4
    LCD
 GeeekPi LCD
     This is used to display current distance and ideal distance to the user
    Buzzer
 CEM-1203
     The buzzer is used to signal to the user how close to their goal they are
    LED
   Standard kit LED
      5 LED’s are used to map how close or how far from target a person is
     Button
Standard push Button
   Used to either increment or decrement the target distance
 
Final Setup
 
         Programmer
  Buttons
Buzzer
LCD with I2C
    HC-SR04 Ultrasonic sensor
ATMega168
5 LED’s

Schematic
 
ATMega168
The role of the ATmega is to be the brains for this operation. Tasks include getting readings from the ultrasonic sensor, converting said readings to readable binary, outputting a digital voltage with DAC, etc. Another task is to use readings from sensor, and to check if certain KED’s need to be turned on. Another task is using ultra sonic sensor readings to signal buzzer to beep at various intervals, and change intervals accordingly. Lastly, the ATmega needs to output data to the LCD screen, such as distances from Ultra sonic sensor readings. This was done through the ATMega connecting to the I2C of the LCD, and sending data through the SDA and SCL channels on the I2C. The ultrasonic sensor readings can be taken in through a DAC, while the LCD interface is an I2C type.

Interaction and Instructions
To interact with this device, the user would hold the ultrasonic sensor at any distance from an object they are trying to measure. The LCD will display the current distance, as well as 50cm as the ideal distance. The user can then press either button to increase or decrease the distance they want. This will be updated on the LCD. The buzzer and LED’s will beep/light up differently depending on distance from target, which the user can use to move forward or backwards to verify they are getting closer or further from target.
To set up the project, build the circuit as per the diagram, and download the given code. Run the make file, and wait for the code to compile. The LCD will then turn on, buzzer with start beeping, and you can start using the system. Be sure that the libraries used are directly in the main file, not in a separate folder, or the make file won’t see them.

Libraries
The external library used is called LCDPFT8574, which is a file that allows me to use the I2C compatible LCD and send data through 2 wires. It can be found here: https://davidegironi.blogspot.com/2013/06/an-avr-atmega-library-for-hd44780- based.html?m=1 - .Wmk-GTNzK70. It takes the PFT8574 I2C, and creates LCD functions which can be used to print data to the LCD screen, move cursor, reset LCD, etc.
This library Is what allows the I2C to work on the LCD screen. It gives functions to print strings or char’s, change cursor position, many more related to the LCD. This is the library I used to print values to the LCD.
Used “util/delay” for delay function, especially with the ultra sonic sensor pings and echo’s.
  
Limitations
Everything that I had envisioned for this semester project was able to be built here. The LCD, buzzer, ultrasonic sensor, LED’s was all completed. Some limitations of this include not being able to be more accurate than 5 cm. With a more sophisticated design, it would have been able to input a number manually, and set that as the target distance, instead on only being able to change distance by ± 5. Also, the buzzer was fairly weak, so having a proper speaker would have made for a better experience. If I could add more features, I would have included some 3D printed parts that would allow for easier use for the user. This would include a handle for the sensor and LCD, as well as attachments for the LED and buzzer, with ease of access to the buttons.
 
YouTube
https://youtu.be/DZlvicCC-L8
 
