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
3. Add the [Platform IO plugin](https://platformio.org/install/ide?install=vscode) to VS code. [Watch](https://user-images.githubusercontent.com/9794797/117762834-3678d500-b26d-11eb-83a1-2ab196106b5b.mp4)
4. Install [Virtul Com Port Drivers](https://ftdichip.com/drivers/vcp-drivers/) for the Moteino Boards
5. Connect you Moteino board to your computer
6. In VS code select __File > Open Workspace__ and open __src/bf-iot-ws.code-workspace__. [Watch](https://user-images.githubusercontent.com/9794797/117763046-7c359d80-b26d-11eb-92ab-f1d1a5536e0c.mp4) 

We are now ready to start programming.

## Part 1 - TX RX Blinky
This is a simple example application to demonstrate how to control the LED of one Moteino from another. This will demonstrate a simple method of wirelessly controlling the LED of a moteino from another. To setup your Moteino as a receiver:

1. In the `src/main.cpp` of the `part1-receiver` folder change the __NODEID__ to your unique node number.
2. Select `src/part1-receiver` as the environment
3. Select Build and Upload

![Build and Upload Button](https://user-images.githubusercontent.com/9794797/118064401-4532c980-b3de-11eb-8c36-2b3c21ab5347.png)

The board should now be flashed. The state of the LED will change with each command from the sender. Open the serial monitor by clicking on the serial monitor icon.

![Open Serial Monitor](https://user-images.githubusercontent.com/9794797/118064318-1fa5c000-b3de-11eb-9321-d3f9cc11c7c2.png)

To setup your board as a sender follow the same steps but use the `src/part1-sender` code instead.

## Part 2 - Nodes and Gateways
This section will deomstrate a more practical use for IoT. This is called a node and gateway configuration. The presenter will demonstrate setting his device up as a gateway. You will then setup your device as a node and send information to the gateway moteino. To setup your device as a node:

1. In the `src/main.cpp` of the `part2-node` folder change the __NODEID__ to your unique node number.
1. Select `src/part2-node` as the environment
2. Select Upload

Once the presenter has the gateway running on his screen you will see any messages, your node sends, appear on the gateway serial monitor.
