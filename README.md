## ESP8266 SDK 2.0.0 ARM support
  
Espressif has written a `wifi_send_pkt_freedom()` function that just sends out whatever packet you’d like to the network. 
It also turns out that the ESP8266 will enter monitor mode, where it listens to all WiFi traffic regardless of the MAC address that it’s directed toward.  

The communication between the victim and access point (AP) is traced by `wifi_set_promiscuous_rx_cb` while packet injection is performed by `wifi_send_pkt_freedom`
Future versions of the esp_iot_sdk removed the ability to send wifi control frames with wifi_send_pkt_freedom. Using this bug, ESP8266 is able to send deauthentication packets to any AP nearby. 

https://github.com/spacehuhn/esp8266_deauther uses deauthentication attack and other exploits using an ESP8266.      
__This package is compiled for ARM architecture.__
  
## Installation:  
Add `https://raw.githubusercontent.com/anudeepND/esp8266_2.0.0/master/package_esp8266_index.json` to Additional board manager URLs.    
Go to `Tools` > `Board` > `Boards Manager` and install.
