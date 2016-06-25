Raspberry PI Lora Gateway/Node for HopeRF RFM95 RFM96 RFM98 Modules
===================================================================

This shield is used to hold HopeRF [Lora module][4] Software with Raspbery PI. it has just few minimal features and it's working for [TTN network][1]
I tweaked the [Single LoraWan Gateway][5] to get it working out of the box. It should also works with [HAB Supplies Lora Gateway][7] (same pinout), see this excellent [Dave's article][6].

Features
========
- Placement for RFM95/96/98 Lora module
- Placement for choosing single Wire, SMA or u-FL Antenna type
- 2 x LED LED for visual indication

~~I'm waiting boards~~ Boards arrived from OSHPark, all is working as expected. ~~so I didn't fully tested them yet, I will update ASAP~~.

Detailed Description
====================

Look at the schematics for more informations.

SPI connexion is classic (MOSI/MISO/CLK), Chip Select can be connected to CE0 or CE1 of PI depending on bord solder PAD jumper.
Take care that by default it's connected to CE0 (wired) so you don't have to do anything. If you want to connect to CE1 you'll need to cut CE0 trace on the PCB (on the solder pad).

~~Other pins that may need be adapted into code (for example if you use TTN network gateway code) according to the following pinout~~ This [Single LoraWan Gateway][5] has been tweaked and works right out of the box.

```
Raspberry PI   RFM9x Module
   GPIO22  <---->  Reset
   GPIO25  <---->  DIO0 (RX or TX Done)
   GPIO24  <---->  DIO5 (Ready)

Raspberry PI   On Board LEDS
   GPIO23  <---->  LED D1
CE0 or CE1 <---->  LED D2
```

### Schematic  
![schematic](https://raw.githubusercontent.com/hallard/LoRasPI/master/images/LoRasPI-sch.png)  

### Boards  
<img src="https://raw.githubusercontent.com/hallard/LoRasPI/master/images/LoRasPI-top.png" alt="Top" width="40%" height="40%">&nbsp;
<img src="https://raw.githubusercontent.com/hallard/LoRasPI/master/images/LoRasPI-bot.png" alt="Bottom" width="40%" height="40%">&nbsp; 

You can order the PCB of this board at [OSHPARK][3]

### Assembled boards

Assembled and working board connected to Raspberry PI.

<img src="https://raw.githubusercontent.com/hallard/LoRasPI/master/images/LoRasPI-on-Pi.jpg" alt="LoRasPI plugged on PI">

##License

You can do whatever you like with this design.

##Misc
See news and other projects on my [blog][2] 

[1]: https://staging.thethingsnetwork.org/wiki/Hardware/Gateways/DIY 
[2]: https://hallard.me
[3]: https://oshpark.com/shared_projects/BBhyhBkz
[4]: http://www.hoperf.com/rf_transceiver/lora/
[5]: https://github.com/hallard/single_chan_pkt_fwd
[6]: http://www.daveakerman.com/?p=1719
[7]: https://store.uputronics.com/index.php?route=product/product&search=lora&product_id=68