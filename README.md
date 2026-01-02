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


#Rule on ENERGY#power>8 do  RuleTimer1 16 endon on Rules#Timer=1 do power1 off endon


on tele-ENERGY#Current do publish ingoiot/f/4 %value% endon
//only publish on teleperiod / tele- in front of sensor



#empfänger:{"Rule1":"ON","Once":"OFF","StopOnError":"OFF","Free":475,"Rules":"on Rules#Timer=1 do power1 off endon"}

rule1 on Rules#Timer=1 do power1 off endon




#sender: {"Rule1":"ON","Once":"OFF","StopOnError":"OFF","Free":403,"Rules":"on switch1#state=1 do backlog websend [192.168.43.127] #RuleTimer 80; websend [192.168.43.127] power on endon"}

rule1 on switch1#state=1 do backlog websend [192.168.43.127] RuleTimer 8; websend [192.168.43.127] power on endon



1. automatisch einschalten
2. strommessen
3. wenn strom unter 8 watt fällt, nach 10 sekunden  ausschalten (mit verzögerung)


Rule1
  ON System#Boot DO Power1 ON ENDON
  ON Energy#Power<8 DO RuleTimer1 10 ENDON
  ON Energy#Power>=10 DO RuleTimer1 0 ENDON
  ON Rules#Timer=1 DO Power1 OFF ENDON
ENDON
Rule1 1

Hier die bereinigte und lesbare Darstellung von Rule1 (wie sie aktuell auf deinem Gerät steht):

