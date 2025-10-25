# Meshtastic-Heltec3-ESP8266-IO

## Description

Implements a remote Meshtastic node that allows for the control of outputs 
and reports back the status of the outputs and inputs. The inputs and 
outputs can be digital or analog and are easily configured my editing
the input and output array. Each remote Meshtastic node can have a node 
name, defined by the NODENAME string. This allows multiple remote nodes
to share the same Meshtastic serial/data channel and respond to controls
for each node.

Below is a picture of remote node, which is constructed using a Heltec v3 
as the Meshtastic radio and an Adafruit Huzzah ESP8266 Module as the 
controller. The Huzzah module is connected to two LEDs, a push button, and
a trim pot to demonstrate a digital output (red LED), analog (PWM) output 
(green LED), digital input (pushbutton), and analog input (trimpot) being
controlled and reported from another Meshtastic node thru the Meshtastic 
network.

![Picture](https://github.com/user-attachments/assets/df19c8f3-f684-4076-9212-d02de885dfca)

Picture available at https://github.com/jonw0224/Meshtastic-Heltec3-ESP8266-IO/blob/main/Pictures/Picture.jpeg

Schematic available at https://github.com/jonw0224/Meshtastic-Heltec3-ESP8266-IO/blob/main/Schematic/Meshtastic-ESP8266/Meshtastic-ESP8266.pdf

## Setting Up the Meshtastic Nodes

Get the [Heltec v3 radios](https://www.amazon.com/Meshnology-V3-Development-4000mAh-Battery/dp/B0F1FZ2LGS/ref=sr_1_1_sspa?dib=eyJ2IjoiMSJ9.9x1tLwZkEi5HQ-7S_Vy8Y3a0-KlkQFvbSTyApyhdfcU1ntypt2dXqHgRQTmZfmPeyqz0GV-VyHA9TM3PSvTeb6xvpuMiaZFyot7O_QlPsRSfhPJlic409QmAZFQtE5ZMkmKXUb9eyGUlKPzmYCPg_Vj1uO29EroceBRy3UOofj2Ov2ootNVPTWvCvmRj6iNhY1kLSb2voHHukSxlVVb3kF0UYO8ltH84v1Ltc0StzO4.uEQxOZplHiWz4xN0w0xoCSSdG3ZzLuqRqsxvDoNUUr0&dib_tag=se&hvadid=557504008769&hvdev=c&hvexpln=0&hvlocphy=9018702&hvnetw=g&hvocijid=10464675869868019842--&hvqmt=b&hvrand=10464675869868019842&hvtargid=kwd-1898806290948&hydadcr=24359_13517651&keywords=heltec%2Bwifi%2Blora%2B32%2Bv3&mcid=d49bb74e3f093007a121896930289a90&qid=1761431059&sr=8-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1)

Set up the a serial/data radio channel on each node. This channel must be
the set up on the PRIMARY channel, because the serial module sends messages
on the PRIMARY channel. It is recommended that you don't use the default 
public Meshtastic channel as the PRIMARY channel and instead use your own
private channel to (1) limit who can control your device, (2) avoid spamming
the public channel with telemetry control and status messages.

## Programming the Adafruit Huzzah ESP8266

