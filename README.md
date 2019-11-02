# Tasmota-Sensor-Offset
Adjust (Temperature) Values of Tasmota connected Sensors

Rule1 ON Tele-DS18B20#Temperature do backlog var1 %value%; add1 2;  Publish temp/s1 var1 ENDON

Command | Description
------- | -----------
TelePeriod | show publishing interval
TelePeriod  10 | Set to 10 seconds(10...3600sec)
Rule1 ON | creates Rule1
Tele- | sends Data by TelePeriod interval
backlog | allows multiple commands in a row
var1 %value% | stores sensor data in variable1
add1 2 | add 2 to variable1
Publish temp/s1 var1 | publishes variable1 as MQTT payload
//


Rule on ENERGY#power>8 do  RuleTimer1 16 endon on Rules#Timer=1 do power1 off endon
