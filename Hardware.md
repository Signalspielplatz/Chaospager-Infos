# ChaosPager Hardware

The 39c3 Prototypes are based on a mainboard which holds everything together and has some soldered on sub-PCBs for logical fuctions.

## Mainboard
> ❗️WIP

## Radio Board

For the radio board, we were inspired by the HPD14A modules which are available in China and are used on many Meshtastic compatible boards. So, our radio board was designed in a way that our board can be used as drop-in replacement for those modules. This decision was made mainly as fallback solution in case we can't get the radio modules populated in time.

On the radioboard, a SX1262 is used as the heart of all the heavy RF lifting. As a starting point, most of the design from the reference design by Semtech was used. Next to the SX1262 a microcontroller was added directly on the stamp-sized board. This allows the configuration and control of the SX1262 directly without the need for a main processor to wake up. The microcontroller will need only a few hundred microamperes in average and is responsible for the POCSAG message decoding and RIC matching. Only when the programmed RICs are received, the main controller will be waked up and can handle all of the rest. 

To stay compatible with the HPD14 Modules there is an option to configure the modules communication (MISO/MOSI) and interrupt pins to be either connected directly to the SX1262 or to the microcontrollers UART interface. If the microcontroller is configured as SX1262 controller, there will be a simple UART interface present so that the RF board can be used in other projects with minimal configuration overhead and low current consumption, even though normally power hungry main controllers like the ESP32 are used.
