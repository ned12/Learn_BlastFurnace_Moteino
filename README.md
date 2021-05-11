# Moteino Wireless Comms for IoT
This event will step through using the moteino RF microcontrollers for create a low cost wireless comms network. 

## The Hardware
In my opinion one of the best wireless MCU dev boards around are the Moteino boards. I like them for the following reasons:
* They are low cost (~$15-20 AUD)
* You can configure your RF frequency and type on purchase
* You ca programme them with the Arduino IDE
* The libraries and examples are well documented

If you want to read more about them [visit the moteino website](https://lowpowerlab.com/guide/moteino/)

![Moteino USB](https://farm4.staticflickr.com/3813/10585334166_4da71b7c31_z.jpg)

## The Software
As mentioned one of the advantages is being able to program the boards with the Arduino IDE. For this tutroial we will use the Arduino Web IDE to reduce the setup time.

We will also leverage the libraries and examples from moteino. I have put copies in this repo.

## Setup The Software
To get going Lets setup the IDE so we can program the boards:
1. Clone or Download this Repo
2. Download and install [VS Code](https://code.visualstudio.com/download)
3. Add the [Platform IO plugin](https://platformio.org/install/ide?install=vscode) to VS code
4. Install [Virtul Com Port Drivers](https://ftdichip.com/drivers/vcp-drivers/) for the Moteino Boards
5. Connect you Moteino board to your computer
6. In VS code select __File > Open Workspace__ and open __src/bf-iot-ws.code-workspace__

We are now ready to start programming.

## Part 1 - TX RX Blinky
This is a simple example application to demonstrate how to control the LED of one Moteino from another. Setup your Moteino as a sender:

1. Select `part1-receiver` as the environment
2. Select Upload

The board should now be flashed. The state of the LED will change with each command from the sender.


