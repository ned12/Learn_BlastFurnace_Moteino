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

We will also leverage the libraries and examples from moteino. I have put copies in this repo however we will only need them as a backup. 

## Setup The Software
To get going Lets setup the IDE so we can program the boards:
1. Sign up or Login in to the [Arduino Web IDE](https://create.arduino.cc/editor)
2. Install the [Arduino Agent](https://create.arduino.cc/getting-started/plugin/welcome)
3. Got to the **Libraries** section and click the **Import** icon
4. Select the **RFM69_LowPowerLab-1.4.3.zip** from this repo and click upload
