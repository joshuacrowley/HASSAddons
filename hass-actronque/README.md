# hass-actronque
Actron Que/Neo Air Conditioner Add-On for Home Assistant (https://blog.mikejmcguire.com/2021/02/11/actron-neo-and-home-assistant/)

This add-on for Home Assistant enables you to control an Actron Air Conditioner equipped with the Actron Que or Actron Neo modules. 

The add-on requires you to use the Mosquitto MQTT broker on your Home Assistant device, with authentication enabled and a valid credential supplied. You'll also need to ensure that MQTT discovery is enabled with the default prefix 'homeassistant' for HA to discover the climate device and zone switches.

## Configuration
### MQTTBroker: string
Set this field to core-mosquitto to use the HA Mosquitto MQTT add-on. Otherwise, specify a host or host:port for an alternative MQTT server.

### MQTTTLS: true/false
Setting this option to true will force the MQTT client to attempt a TLS connection to the MQTT broker.

### PerZoneControls: true/false
If you Actron has controllers in each zone, setting this option to true will create an air conditioner controller in HA for each zone.

### PollInterval: integer
By default, the add-on will poll the Que API system every 30 seconds for updates. This can be set to between 10 and 300 seconds inclusive.

### QueSerial: string
If you have multiple Que units on your account, you can add this optional configuration to specify the serial number you want the add-on to use. You can find the discovered serial numbers in the log for the add-on when the add-on is starting.

### SystemType: string
This option specifies if you have a "que" or "neo" control system. If not specified, this defaults to "que". 
