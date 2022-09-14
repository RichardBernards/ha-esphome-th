# ha-esphome-th
Configuration for esphome in home assistant to disclose temperature and humidity sensor data

## Hardware Used
* ESP-01S (ESP8266EX)
* DHT-11
* 3.3V Power Supply (for ESP-01S)
* 3.5V+ Power Supply (for sensor)

## Connection Diagram
```
                       +-----------------+
                       |                 |
                       |                 |
                       |                 |
                       |      DHT-11     |
                       |                 |
                       +-----------------+
                         [1] [2] [ ] [4]                            
                          |   |       |
5V (+) -------------------+   |       |
                              |       |
GND  -------------------------|-------+---------+
                              +-------------+   |
3.3V (+) -----------------+                 |   |
                       +--|--------------+  |   |
                       | [8] [ ] [ ] [ ] |  |   |
                       | [ ] [ ] [2] [1]----|---+
                       |          +---------+
                       |    ESP-01S      |
                       |                 |
                       |                 |
                       |                 |
                       |                 |
                       +-----------------+
                        

ESP-01S GND (1) ----------------------------------- GND
ESP-01S GPIO2 (2) --------------------- DHT-11 DATA (2)
ESP-01S VCC (8) ------------------------------ 3.3V (+)
DHT-11 VCC (1) --------------------------------- 5V (+)
DHT-11 GND (4) ------------------------------------ GND

```

## Installing using esphome cli
Installing esphome:
```
pip3 install wheel
pip3 install esphome
```

Flashing ESP-01S through USB:
```
esphome run ./th.yaml
```
When asked, choose the desired COM-port to start flashing.
