# tl5592_arduino
Arduino code for an Arduino DUE that controls an Opel/Vauxhall Corsa OPC/VXR Instrument Panel Cluster via a CAN-Bus interface. The entire system is managed by a separate PCB, which connects to the Arduino DUE and incorporates illuminated push-button switches and rotary encoders.  

This Arduino code, tested in Arduino IDE 2.0.3, uses libraries:  
SPI library and variant library are Arduino IDE included libraries.  
MCP23S17 library is associated to https://github.com/wollewald/MCP23017_WE .  
DueTimer library is associated to https://github.com/ivanseidel/DueTimer .  
due_can library is associated to https://github.com/collin80/due_can .  
LedController library is associated to https://github.com/noah1510/LedController with the adition of the following code in the file LedController_template.hpp :  

void setDecode(unsigned int segment, byte data) noexcept{  
  spiTransfer(segment, 0x09, data);  
}  
  
void setNum(unsigned int segment, byte position, byte data) noexcept{  
  spiTransfer(segment, position+1, data);  
}  



Opel and Vauxhall Corsa OPC/VXR are registered trademarks of Opel Automobile GmbH and Vauxhall Motors Limited, respectively.  
Arduino and Arduino IDE is registered trademark of Arduino AG and Arduino SA.  
Arduino libraries are property of their respective owners.  

All other trademarks mentioned in this project are the property of their respective owners.  
