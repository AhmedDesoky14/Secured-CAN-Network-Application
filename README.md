# Secured-CAN-Network-Application

`# Secured-CAN-Network-Application` is application for CAN network communications to enable real-time communication over CAN bus between different microcontrollers, designed and developed for 2 targets
First, **Raspberry Pi with MCP2515 CAN controller**. 
Second, **STM32F1x with MCP2551 CAN transceiver**

This application is part of the **Secured V2X Enabled Autoparking System Graduation Project**, mentored by **Valeo**.

## Features
- Real-time communications between different micrcontrollers via CAN bus.
- Support messages up to size of 116 bytes.
- Support high level of security by using AES cryptosystem and SHA256 hash algorithm for the exchanged messages.
- Handle all exchanged messages asynchronously.

---

## Components
*1- For STM32F1x*
	- CAN handler, based on STM HAL libraries, acts as a wrapper for CAN STM sHAL library.
 	- CAN Tansport Protocol. Implementation of CAN TP (ISO 15765-2) for CAN segmentation and assembly. **Tareget independent.**
  	- CAN Service Manager. CAN application APIs with the ability and option to encrypt the messages using the implemented Cryptography stack. **Tareget independent.**
  
*2- For Raspberry Pi*
	- CAN handler, based on can-utils library, acts as a wrapper for it.
 	- CAN Tansport Protocol. Implementation of CAN TP (ISO 15765-2) for CAN segmentation and assembly. **Tareget independent.**
  	- CAN Service Manager. CAN application APIs with the ability and option to encrypt the messages using the implemented Cryptography stack. **Tareget independent.**

## External Dependencies
- WolfSSL open-source crypto library
- STM HAL libraries
- can-utils library

---

**All communications and data exchange are handled asynchronously using:**
- pthread library for Linux on Raspberry Pi
- Interrupts by NVIC on STM32F1x microcontrollers

**NOTE:** cryptography keys need to be configured. 

---

**Authors:**
	Ahmed Desoky,
  	Ziad Emad
	
**Emails:**
	ahmed0201150@gmail.com,
	ziademadh7@gmail.com
