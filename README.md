# TasmotaFriendshipLamp

Work in Progress

This documents how to make a friendship lamp from inexpensive parts. Inspired by UncommonGoods which sell for $175 a set.  These can be made for $10 each and have more features, such as Alexa support. You need a MQTT server which is exposed to the internet. Since I wanted to use Tasmota and not compile custom code, I could not get to work with a free MQTT server (like https://www.maqiatto.com/). If anyone knows how or of a free service, please let me know.

Parts:
```
Wemos D1 Mini (x2) - You can get for about $3 each on Aliexpress or Amazon. Real or knockoffs work. Can use almost any ESP board.
WS2812 LEDs - A couple bucks each. I am using an 8 LED ring for each. 
Touch Switch - Tin Foil and Resister (not done yet)
```

Software:
```
Tasmota - You need to compile script support instead of rules. Will post a compiled bin here. Or use https://github.com/benzino77/tasmocompiler
MQTT Server - Must be on an external network. I used a https://mosquitto.org/ in a docker. TLS should be used, but haven't done that yet.
```

Steps
```
0. Setup MQTT server, using authentication. 
  Such as: https://blog.feabhas.com/2020/02/running-the-eclipse-mosquitto-mqtt-broker-in-a-docker-container/ and
  http://www.steves-internet-guide.com/mqtt-username-password-example/
1. Compile Tasmota with Script supprt. Normal rules will not support color change.
2. Flash Tasmota to Wemos D1 Mini
3. Hook up WS2812s (Only need header on one side Wemos if lazy)
4. Set Tamsmota Module to Generic, Set GPIO Pin for the WS2812
5. Configure MQTT. For Ease of Use Set the Topic of Every Device AliceBob (or whatever your two names are). 
  This should work for any number of lamps if you have lots of friends
```
