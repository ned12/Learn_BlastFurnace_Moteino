# Moteino Wireless Comms for IoT
This event will step through using the moteino RF microcontrollers for create a low cost wireless comms network. 

## IoT Network Options
When working with IoT the basic concept is to have some sensor that is collecting data from the real world (at the ground level) and moving that information into the cloud. We call the software that enables this process __Ground-to-Cloud__ software. Usually some sort of wireless technology is involved to get the data from the sensor into the internet. Common conduits for this are:
* Mobile Network - Transmititng data over the mobile network. Good coverage but requires a sim card. This includes 5G, 4G, CAT M1, NB-IoT
* LoRA Network - A free to use network built on the ISM bands. It's free but bandwidth is highly limited and coverage is dependant on someone in the area providing a gateway.
* WiFi - You can connect IoT sensor to a normal wifi network. This is low cost but you will need a wifi router in range that requires a fixed internet connection.
* Combinations of the above - you can obvioulsy have combinations of the above. For example a wifi router running of a 4G LTE sim card.

The Moteino board enable you to create your own mini network for a number of sensors in a given area. All these devices can communicate with each over [300 - 400m open air](https://lowpowerlab.com/shop/product/99#:~:text=Open%20air%20range%3A,fine%20tuning%20the%20RX%20bandwidth). These can all funnel there information back to a single gateway that has access to the internet via one of the aforementioned methods. Advantages of this are:
* You are free to use a lot of bandwidth
* You don't need to inundate your router with heaps of devices
* You can get excellent range
* You don't need a sim card per sensor
* You aren't tying each sensor node to a particular commms method back to the internet
* They are super low power if they need to be.

![Moteino Network](https://user-images.githubusercontent.com/9794797/118072288-cf822a00-b3ec-11eb-943a-9dcd6b250f65.png)


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

## Challenge 1 - Serial Monitor Node
For the first challenge we are going to modify our node code so it can take messages from the Serial Monitor and send them to the gateway. The challenge is complete when you can do the following:

1. Open a Serial Monitor to your Node
2. Type a message into the Serial Monitor and press __Enter__ on the keyboard
3. See that message appear on the Gateway.

## Challenge 2 - Walkie Talkie
For the second challenge we are going to create walkie talkies. The goal is to have two moteinos that can send strings between each other. To complete this challenge you will need to buddy up with another group and communicate with them. These are the features your code should enable to finish the challenge:

* Read strings from serial monitor
* Send strings from Monitor to partner moteino
* Display stirngs recieved from partner moteino on serial monitor
