# <div  style="font-family:'arial blACK', sans-serif,monospace; text-align: left; min-height: 100px; vertical-align:bottom;" >  <span style="position:absolute; left: 0; bottom: 0; padding-right: 120px; padding-bottom: 10px"> <b> ScientISST - Arduino IDE Tutorial</b></span> <img src="https://raw.githubusercontent.com/scientisst/scientisst-sense-api-python/main/docs/img/logo.png" style=" background:#FDC86E;border-radius:10px;height:100px;top:0; position:relative" width=100 align="right" /> </div>

## Keywords:

`Sense`, `Arduino`, `IDE`

In this tutorial, we will describe how to program the ScientISST - Sense development board through the Arduino's Integrated Development Environment (IDE), whether you’re using Windows, Mac OS X or Linux.

<br>

## I. Prerequisites - Installing the Arduino IDE
<br>
<div class="title"style="width:100%; background:#FDC86E;font-family:'arial black',monospace; text-align: center; padding: 7px 0; border-radius: 5px 50px;margin-top:-15px" >
</div>
<br>

Before starting this tutorial, you need to download and install the latest version of the Arduino IDE from: https://www.arduino.cc/en/software [[1]](#reference_1). If you don’t have the latest version installed, uninstall Arduino IDE and install it again. Otherwise, it may not work.

After you have the latest Arduino IDE software installed in your computer, open the software to confirm that it is working. 

Hovering with the mouse pointer on each button shows a brief description of its function. The following figure 
summarizes these functionalities:

<table title="Overview of the Arduino IDE Graphical User Interface (GUI)">
    <caption>Overview of the Arduino IDE Graphical User Interface (GUI)</caption>
    <tr>
<td> <img src="https://raw.githubusercontent.com/LeoPereira89817/scientisst-sense-arduino-ide-tutorial/main/images/ArduinoIDE.png" width="500"/> </td>
<td> <img src="https://raw.githubusercontent.com/LeoPereira89817/scientisst-sense-arduino-ide-tutorial/main/images/ArduinoIDEexplained.png" width="600"/> </td>
</tr></table>

> **Note:**
To get a better understanding on the Arduino Software (IDE) and its functionalities, a more comprehensive guide on this topic is available at: https://www.arduino.cc/en/Guide/Environment [[2]](#reference_2).

<br>

## II. Installing the ESP32 Add-on in Arduino IDE
<br>
<div class="title"style="width:100%; background:#FDC86E;font-family:'arial black',monospace; text-align: center; padding: 7px 0; border-radius: 5px 50px;margin-top:-15px" >  </div>
<br>

The ScientISST - Sense development board is built upon the ESP32-WROOM-32, a powerful, generic Wi-Fi+BT+BLE MCU module, which has at its core the ESP32-D0WDQ6 chip. This is why you first need to install the ESP32 add-on in the Arduino IDE in order to program the ScientISST - Sense development board from the Arduino IDE using its programming language (C/C++). To install this add-on, follow these next instructions:

1. In the Arduino IDE, go to *File > Preferences*:<br>

<img src="https://raw.githubusercontent.com/LeoPereira89817/scientisst-sense-arduino-ide-tutorial/main/images/file_preference_marked.png" width="200" style="display:block; margin:auto"/>

<br>
2. Enter `https://dl.espressif.com/dl/package_esp32_index.json`
[[3]](#reference_3) into the “Additional Board Manager URLs” field (1) in the “Preferences” window as shown in the figure below. Then, click the “OK” button (2):<br>

<img src="https://raw.githubusercontent.com/LeoPereira89817/scientisst-sense-arduino-ide-tutorial/main/images/preferences_marked.png" width="600" style="display:block; margin:auto"/>

<br>

> **Note:** 
If you already have the URL of another board in the “Additional Board Manager URLs” field, you can separate the URLs with a comma as displayed in the figure above.

3. Open the Boards Manager. Go to *Tools > Board > Boards Manager*<br>

<img src="https://raw.githubusercontent.com/LeoPereira89817/scientisst-sense-arduino-ide-tutorial/main/images/tools_boards_marked.png" width="600" style="display:block; margin:auto"/>

<br>
4. Search for ESP32 and press the “Install” button for the “**esp32** by **Espressif Systems**”:<br>

<img src="https://raw.githubusercontent.com/LeoPereira89817/scientisst-sense-arduino-ide-tutorial/main/images/esp32_install_marked.png" width="600" style="display:block; margin:auto"/>

<br>
5. The add-on should be installed after a few seconds, as shown in the following figure:<br>

<img src="https://raw.githubusercontent.com/LeoPereira89817/scientisst-sense-arduino-ide-tutorial/main/images/esp32_installed.png" width="600" style="display:block; margin:auto"/>

<br>

## III. Setting up your ScientISST board to upload code from the Arduino IDE
<br>
<div class="title"style="width:100%; background:#FDC86E;font-family:'arial black',monospace; text-align: center; padding: 7px 0; border-radius: 5px 50px;margin-top:-15px" >  </div>
<br>

1. Connect the USB-C cable to your computer and to the corresponding socket on the ScientISST - Sense development board:<br>

   1.1 Connect the standard USB-A connector to your computer:<br>
   
<img src="https://raw.githubusercontent.com/LeoPereira89817/scientisst-sense-arduino-ide-tutorial/main/images/usb_pc.png" width="600" style="display:block; margin:auto"/>
   
   1.2 Connect the other end to your ScientISST - Sense development board:<br>
   
<img src="https://raw.githubusercontent.com/LeoPereira89817/scientisst-sense-arduino-ide-tutorial/main/images/usb_board.png" width="400" style="display:block; margin:auto"/>

<br>
At this point, the built-in blue LED on the back of the ScientISST - Sense development board should be on, and the built-in white LED on the front should be flashing repeatedly, if the board still carries the original firmware for the ScientISST - Sense development board.


2. In the Arduino IDE, go to `Tools > Board > ESP32 Arduino` and select your board model, i.e. ESP32 Dev Module:<br>

<img src="https://raw.githubusercontent.com/LeoPereira89817/scientisst-sense-arduino-ide-tutorial/main/images/select_board_marked.png" width="600" style="display:block; margin:auto"/>



3. Go to `Tools > Port` and select the port that your ScientISST - Sense development board is using. On Windows it should have the prefix COM, followed by an integer number (as is the case in the figure below), and on Mac OS it should have the prefix /dev/cu.usb or /dev/tty.usb. Usually the port of your newly added device appears at the end of the list:

<img src="https://raw.githubusercontent.com/LeoPereira89817/scientisst-sense-arduino-ide-tutorial/main/images/port_marked.png" width="600" style="display:block; margin:auto"/>

<br>

> **Note:** 
If you don’t see the COM Port in your Arduino IDE, you need to install the CP210x USB to UART Bridge VCP Drivers from: https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers [[4]](#reference_4).


4. To upload a sketch with your code written on the Arduino IDE, you must first put your ScientISST - Sense development board on **BOOT mode**. To do so, you will need to use the RESET and MODE buttons on the ScientISST - Sense development board, shown in the following figure:

<img src="https://raw.githubusercontent.com/LeoPereira89817/scientisst-sense-arduino-ide-tutorial/main/images/reset_mode.png" width="300" style="display:block; margin:auto"/>


Before uploading the sketch:

1. Hold down the MODE button.
2. Press the RESET button. 
3. Release the MODE button.

If the previous steps were done correctly, the white LED should have stopped blinking.

At this point, the ScientISST - Sense development board is now on BOOT mode and is ready to have the sketch uploaded to it.


5. Upload the sketch to your board by clicking the “Upload” button in the Arduino IDE:

<img src="https://raw.githubusercontent.com/LeoPereira89817/scientisst-sense-arduino-ide-tutorial/main/images/upload.png" width="300" style="display:block; margin:auto"/>

<br>
Wait a few seconds while the code compiles and uploads to your board. If everything went as expected, the MESSAGES section of the Arduino IDE should show a notification indicating that the code has been uploaded, and list general information regarding the device and memory use:

<img src="https://raw.githubusercontent.com/LeoPereira89817/ScientISST_Tutorial/main/images/done_uploading.png" width="600" style="display:block; margin:auto"/>

<br>

> **Note:**
In case you obtain an error during the upload, read the output in the MESSAGES section carefully and you will likely be able to have a rough idea of what went wrong. The most common causes of problems are syntax errors in your code, a mismatching board version on the Arduino IDE, or a wrongly selected port, so please review your code and try to identify any typos or mismatching
characters.


6. Finally, press the RESET button to put your ScientISST - Sense development board on Execution mode and have it run the uploaded code.

<br>

## IV. Testing your Setup 
<br>
<div class="title"style="width:100%; background:#FDC86E;font-family:'arial black',monospace; text-align: center; padding: 7px 0; border-radius: 5px 50px;margin-top:-15px" >  </div>
<br>

To test your setup, follow the steps from Section III and upload the Blink sketch, one of the built-in examples of the Arduino IDE that can be loaded from `File > Examples > 01.Basics > Blink`:

<img src="https://raw.githubusercontent.com/LeoPereira89817/scientisst-sense-arduino-ide-tutorial/main/images/blink.png" width="600" style="display:block; margin:auto"/>

<br>

> **Note:**
Don't forget to replace the ```LED_BUILTIN``` in the Blink sketch with the number of the pin connected to the white LED (GPIO 22).

Upon successful completion of the process, the white LED on the front of the board should be on for one second, then off for one second, repeatedly.


<br>

## V. References
<br>
<div class="title"style="width:100%; background:#FDC86E;font-family:'arial black',monospace; text-align: center; padding: 7px 0; border-radius: 5px 50px;margin-top:-15px" >  </div>
<br>

<a id='reference_1'></a> 1\. https://www.arduino.cc/en/software

<a id='reference_2'></a> 2\. https://www.arduino.cc/en/Guide/Environment

<a id='reference_3'></a> 3\. https://dl.espressif.com/dl/package_esp32_index.json

<a id='reference_4'></a> 4\. https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers


<div style="height:100px; border-radius:10px;text-align:center"> 
    <img src="https://raw.githubusercontent.com/LeoPereira89817/scientisst-sense-arduino-ide-tutorial/main/images/IT.png" alt="it" width=250/> 
    <img src="https://raw.githubusercontent.com/LeoPereira89817/scientisst-sense-arduino-ide-tutorial/main/images/IST.png" alt="alternate text" width=250/>
</div> 

```Contributors: Prof. Hugo Silva; Leonor Pereira; Francisco Melo; Afonso Raposo```