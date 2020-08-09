# Commands

Supported arduino commands include:

- pinMode
- digitalRead
- digitalWrite
- analogRead
- analogWrite

plus an special `ECHO` command, to test connectivity.

## pinMode

Syntax: `PM <pin> <I/O>`  
Returns: `ACK`  

To set pin mode to output on pin 13: `PM 13 O`

## digitalRead

Syntax: `DR <H/L>`  
Returns: `ACK <H/L>`  

To get the current value from pin 12: `DR 12`  
You should get back a `ACK <H/L>` on the serial port

## digitalWrite

Syntax: `DW <pin> <H/L>`  
Returns: `ACK`  

To send a high value on pin 10: `DW 10 H`

## analogRead

Syntax: `AR <pin>`  
Returns: `ACK <value>`  

To get the current value from pin 5: `AR 5`  
You should get back a `ACK <value>` where `value` is a number between `0` and `255`

## analogWrite

Syntax: `AW <pin> <value>`  
Retursn: `ACK`  

To send a pwm of value  `50` on pin 6: `AW 6 50`  
You should get back a `ACK` on the serial port

## ECHO:

Syntax: `ECHO <value>`  
Returns: `ACK <value>`  

To test connectivity you can use the `ECHO` command which will return everything you send.
