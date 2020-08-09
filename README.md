# spec
Specification for the gpioduino serial communication protocol

## overview

the gpioduino protocol is designed to be easy to implement and flexible.

- command based
- text based
- first `WORD` is the command
- might contain additional arguments, space separated (for example `PIN` number on the arduino)
- commands ends with a semi-colon: `;`
- server will respond with `ACK` after each command if successful, this response might contain an argument if applicable (for example a "read" command).
- server will respond with `ERROR` in case the server had an error executing the command.
- state handling is not automatic, your clients need to keep track of state of the server
- reference implementation is via serial port `@9600` bps, but spec itslef its transport agnostic (you would need to update the libraries and the firmware).
- no retry-ing or error checking at the protocol level, clients should handle retrying and error handling.
- no board specific checking for pin modes or digital/analog capabilities. Its up to the user.

## [Commands](COMMANDS.md)

### example "ECHO" command flow:

Success:

![Ok](https://raw.githubusercontent.com/gpioduino/spec/master/assets/Ok.png)

Error:

![Error](https://raw.githubusercontent.com/gpioduino/spec/master/assets/Error.png)
