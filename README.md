# Tasmota-Sensor-Offset
Adjudt (Temperature) Values of Tasmota connected Sensors

Command | Description
------- | -----------
TelePeriod | show publishing interval

TelePeriod  10 | Set to 10 seconds(10...3600sec)

Rule1 ON Tele-DS18B20#Temperature do backlog var1 %value%; add1 2;  Publish temp/s1 var1 ENDON
// creates Rule1

//Tele- on Teleperiod sends Data

//
