---
layout: post
title:  "MakerWeekend with ESPresso Lite"
date:   2016-01-24 16:34:00
categories: maker arduino iot
language: en
---
Yesterday, I attend MakerWeekend in [Makedonia][makedonia-home] about Affordable IOT Solution with ESPresso Lite. The speaker was William Hooi from Espert. The workshop was awesome and we did some quick demos with ESPresso Lite.

![William Hooi][william]

### What is ESPresso Lite?
According to the [website][espert-home], ESPresso Lite is **"Arduino-compatible ESP8266 Wi-Fi development board for makers and novice learners to build their very own Internet-of-Things (IoT) projects"**. So it is basically an ESP8266 Wi-Fi module, but you can code it using Arduino software, which is really great because it is as easy as coding the Arduino Uno or Nano with extra wireless communication.

ESPresso Lite is very cheap. It costs $9.95 USD. It is about the same cost with cloned Arduino Uno or $20 cheaper than Arduino Uno. Here is comparison between ESPresso Lite and Arduino Uno  

![Comparsion Table][espert-comparison]

ESPresso Lite comes with complete IoT solution. It comes with [ESPert MQTT Websocket Client][espert-client] and [Freeboard][espert-freeboard] for visualizing data. Espert also provide [Mobile App][espert-mobileapp] and [Espert.io Dashboard][espert-dashboard] to manage connected smartphones, geofencing and freeboards.

### Making 'Things' with ESPresso Lite
At the workshop, William guide us to make a weather monitoring device. We were provided an ESPresso Lite module, DHT22 Temperature and Humidity digital sensor, OLED LCD Display module, FTDI Module and a [Workshop Guide][espert-guide]. ESPresso Lite module has been uploaded with a weather monitoring program.

Before building the hardware, we need to create account in Espert.io. Then, we connect our smartphone by installing Espert.io Mobile App. My smartphone will be shown in the dashboard after logged in to mobile app. I noticed no feature is working yet except push notification. Notification also won't show if the app is not running.

After creating account, we assemble the hardware. it was very easy because the sensor and display module just fit into the pins. To power up ESPresso Lite, we use power source from notebook. The FTDI module is used to bridge ESPresso Lite to notebook. Then, we switch ESPresso Lite mode to AP (Access Point) mode and set-up Wi-Fi for Internet connection source. The module will connect automatically after Wi-Fi is set.

![ESPresso Lite][espert-image1]

When ESPresso Lite connected to internet, it will periodically publish data gathered from sensors to Espert MQTT Broker. To see data, we use MQTT Websocket client. This client can subscribe messages (receive) and publish (send) data from/to ESPresso Lite. All MQTT messages is formatted in JSON, so it would be easy to read and write. The JSON data can be visualized with Freeboard by subscribing to sensor data.

### Review
ESPresso Lite is great alternative for Particle boards, which is very hard to find in Indonesia. Hardware is still work in progress and there will be another revision. William said, there will be more features such as auto-reset after flashing, better button placement and more pins (this one is important!). I haven't program ESPresso Lite using Arduino yet, so I am looking forward to borrow a module and do some experiment. Checkout the website for tutorials on how to make things with ESPresso Lite. Besides Hardware, Epsert also offers complete IoT solution besides Hardware such as MQTT Broker for Middleware, MQTT Websocket Client and Freeboard for Presentation (visualizing data).

I think this workshop give participants more insight about the Espert IoT environment rather than the hardware (ESPresso Lite) itself, but it's still great for beginners to understand IoT.

Last, I would love to see a library/dependency for mobile and web apps, so makers can easily integrate their own apps to Espert IoT environment.

[makedonia-home]: http://www.makedonia.co/
[espert-home]: http://www.espert.co/
[espert-mobileapp]: http://thaigw.com/apps/espert/
[espert-client]: http://www.espert.io/mqtt/
[espert-freeboard]: http://www.espert.io/freeboard/index.html
[espert-dashboard]: http://www.espert.io/
[espert-guide]: https://www.dropbox.com/s/2iua0zr1peis6ka/IoT%20Workshop%20Guide%20Rev%202.pdf?dl=0
[espert-comparison]: https://raw.githubusercontent.com/saggafarsyad/saggafarsyad.github.io/master/images/espert-comparison.PNG
[espert-image1]: https://raw.githubusercontent.com/saggafarsyad/saggafarsyad.github.io/master/images/espresso_lite.jpg
[william]: https://raw.githubusercontent.com/saggafarsyad/saggafarsyad.github.io/master/images/william_hooi.jpg
