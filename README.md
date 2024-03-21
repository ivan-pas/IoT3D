

This project focus to concentrate various different ESP projects in one consistent line of "Ready to Use" sensors for Home Assistant.

Every sensor is 3D printed and shipped with a Tasmota custom firmware, Ready to Use.
Additionally, there's a section containing all the different configurations for ESPHome to help end user to compile his custom firmware on his own.
There's a file for every sensor model, at the begin of every file there are variable declaration where you have to modify data to adapt to your network/use case

# ESPHome Installation - Common parameters
First of all we have to chose one configuration and customize the code:

```
substitutions:
  devicename:    Ultrasonic Sensor   
  devicename_id: ultrasonic_sensor

  static_ipaddr: 192.168.1.201    # I use static ip address, to use DHCP, remove this row and manual_ip block
  gateway_ip: 192.168.1.1         # I use static ip address, to use DHCP, remove this row and manual_ip block
  subnet_mask: 255.255.255.0      # I use static ip address, to use DHCP, remove this row and manual_ip block
  dns_ip: 8.8.8.8                 # I use static ip address, to use DHCP, remove this row and manual_ip block

  ap_mode_password: 12345678
```



https://esphome.io/components/api.html#configuration-variables