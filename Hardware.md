# ChaosPager Hardware

The 39c3 prototypes are structured around on a mainboard comprising of a microcontroller and RF-

## Mainboard
> ❗️WIP

The mainboard is the heart of our pager, connecting all functional sections to each other while still giving us plenty of opportunities to implement spontaneous ideas through connection points at the side of the board. Size-wise, our 39c3 prototypes are a bit larger than commercially available counterparts. This trade-off had to be made for the goal of a very flexible experimentation platform. On top of the pager functionality, we try to stay compatible with the Meshtastic firmware so that the project can get a second use.

### User Interface

An important specification by CERT is that our pagers need to have a similar UI to commonly used pagers in Germany by BOS ("Behörden und Organisationen mit Sicherheitsaufgaben", eng. 'public safety agencies'. In short: ambulances, firefighters, police, ...). The main competitors on the market are Swissphone POCSAG pagers and the more modern Motorola TETRA pagers. We had many discussions about the best design and button layout and settled for a T-shaped layout, which we expect to be intuitive for the majority of users. With this design, you get two buttons for up/down navigation and two buttons below the display which get assign functions depending on the currently displayed menu. This designs fullfills the specification of a commonly used design, as well as giving unexperienced operators a headstart through direct labeling through the display output. 

For 39c3 there are two PCB versions with different button layouts. We would love to have many people try out the UIs at our assembly and discuss the user experience. You can find us on C3NAV during congress as "Signalspielplatz".

### Hardware deepdive

For everyone interested in technical details:

As main-controller, an ESP32-C3 SuperMini board is used. This has already a USB port on it for firmware upload which is a bit error prone in hand assembly of the boards. The controller has plenty of computational power for our application, maybe even a bit too much power 😉. Currently, the WiFi and Bluetooth features are not used by our firmware but there are several ideas for ongoing development to utilize those interfaces. A nice side effect of the controller is that it is also supported by the Meshtastic firmware.

Due to a lack of usable GPIO pins on the ESP32-C3, a port expander, namely TCA9554PW from Texas Instruments, is used.

## Radio Board

For the radio board, we were inspired by the HPD14A modules which are available in China and are used on many Meshtastic compatible boards. So, our radio board was designed in a way that our board can be used as drop-in replacement for those modules. This decision was made mainly as fallback solution in case we can't get the radio modules populated in time.

On the radioboard, a SX1262 is used as the heart of all the heavy RF lifting. As a starting point, most of the design from the reference design by Semtech was used. Next to the SX1262 a microcontroller was added directly on the stamp-sized board. This allows the configuration and control of the SX1262 directly without the need for a main processor to wake up. The microcontroller will need only a few hundred microamperes in average and is responsible for the POCSAG message decoding and RIC matching. Only when the programmed RICs are received, the main controller will be waked up and can handle all of the rest. 

To stay compatible with the HPD14 Modules there is an option to configure the modules communication (MISO/MOSI) and interrupt pins to be either connected directly to the SX1262 or to the microcontrollers UART interface. If the microcontroller is configured as SX1262 controller, there will be a simple UART interface present so that the RF board can be used in other projects with minimal configuration overhead and low current consumption, even though normally power hungry main controllers like the ESP32 are used.
