Name: Caroline Li

EID: cjl3656

Team Number: F4

## Questions

1. Why does your program need a setup and a loop?

    The setup part initializes any frameworks and global variables needed, and also sets te serial communication rate.
The loop part executes code repetitively in a loop to either wait for input or produce output until either a new program
is uploaded or the arduino is disconnected. In this way, the arduino can be controlled in an easy way.

2. What is the downside to putting all your code in a loop?

    The downside is that we can't control which statements we want executed repetitively, and which ones we want to control with parameters
or conditionals. All statements in the loop will be executed repetitvely. To deal with this, we define functions outside the loop and call these
functions when needed in the looping part. That way we won't have to repeat code with the dimming function, for example, with different frequencies
and duty values.

3. Why does your code need to be compiled?

    Code must be compiled, which means translated to machine code, in order to be executed by the CPU on the board.

4. When lowering the frequency in procedure A, step 4, what is going wrong? Brainstorm some solutions. Dimmers exist in the real world. What is their solution?

    When the frequency is lower, the time between high and low voltage becomes longer, and the time for voltage high and low is longer as well.
This is because the period of each cycle is a larger value, which causes the LED to flash and dim, instead of only dimming. To fix this, we need
a higher frequency to ensure the LED flashes between high and low voltage at a rate undetectable to the eye. Modern dimmers in the real
world use higher frequencies.

5. Why do you need to connect the logic analyzer ground to the ESP32 ground?

    That way, the logic analyzer and the ESP32 share the same ground, so voltage signals relative to this ground will appear
at the same relative value in both the logic analyzer and ESP32.

6. What is the difference between synchronous and asynchronous communication?

    Synchornous communication is fast but requires sychronization between a sender and reciever by an external clock line
that ensures both sender and reciever are communicating at the same rate. Data is sent in blocks. However, Asynchronous
communication is slow but does not require synchronization by external clock. Rather, both sender and reciever agree
to a communication rate using their own clocks, and sychronization bits marking starts and stops are placed in 
tranferred data to correct inaccuracies in communication rates. This makes data transfer slower.

7. Profile of UART: Sent X bytes in Y time 

    It took about 1.373 ms to send "Hello".

8. Profile of SPI: Sent X bytes in Y time

    Sent 5 bytes in 0.1205 ms

9. Why is SPI so much faster than UART?

    SPI doesn't have the overhead of using synchronization bits when transfering data and it can transfer data
in large blocks, while UART must insert synchronization bits between bytes of data.

10. list one pro and one con of UART

    Pro: No need for clock line
Con: Slow data transfer and complex hardware

11. list one pro and one con of SPI

    Pro: Fast Data transfer
Con: Requires clock line

12. list one pro and one con of I2C

    Pro: I2C only needs clock and tranfer data line
Con: I2C draws more power and is slower at half duplex speed (data flows one direction only at a time)

13. Why does I2C need external resistors to work?

    I2C needs external resistors to handle multiple master/slave relationships. The resistors
are used to pull voltage back up to high if no device is currently using the transfer line. In this way,
there are no conflicts between different devices because devices can only pull the line to low voltage, not high
or low. High voltage is set by the resistors if no devices are using it.
## Screenshots

Procedure A, step 1:
![Put path to your image here ->](img/placeholder.png)
img/blink_part1.jpg
img/blink_part1_zoomedOut.JPG

Procedure A, step 4:
![Put path to your image here ->](img/placeholder.png)
img/dimmer_signal.JPG
img/dimming_signal_2.JPG

Procedure B, UART:
![Put path to your image here ->](img/placeholder.png)
img/UART_Fixed_Text.JPG

Procedure B, SPI:
![Put path to your image here ->](img/placeholder.png)
img/SPI_text.JPG
