SDRSharp.YaesuFT450Sync

SDR# Plugin for 2-Way CAT synchronization with Yaesu FT-450D.

This plugin enables real-time frequency, mode, and bandwidth
synchronization between SDR# Studio and a Yaesu FT-450 / FT-450D
transceiver via CAT (Serial).

In addition, the transmitter output power can be controlled directly from the SDR# plugin interface.

------------------------------------------------------------------------

Features

2-Way Sync

-   SDR# → TRX
    -   Frequency
    -   Mode
    -   DSP Bandwidth (IF Width)
-   TRX → SDR#
    -   Frequency
    -   Mode

CAT Communication

-   Stable CAT backend
-   Debounced CAT transmission
-   Echo suppression / holdoff logic
-   Loop guards to prevent feedback oscillation
-   Duplicate command filtering

DSP Bandwidth Sync

-   Maps SDR# filter bandwidth to FT-450 SH0xx width index
-   Special handling for AM modes (00 / 16 / 31 Narrow / Normal / Wide)
-   Hysteresis to prevent slider jitter

------------------------------------------------------------------------

Hardware Setup

IFace (Panadapter Integration)

The FT-450D can be connected to an external SDR receiver using an IFace
interface board, which taps the intermediate frequency (IF) signal
inside the radio and routes it to an SDR device.

More information:
https://www.tspelettronica.com/en/2019/01/29/installazione-iface-su-ft-450d/

Installing such hardware requires opening the radio and modifying
internal circuitry. Perform any hardware modification at your own risk.

CAT Interface (Development Setup)

During development, the FT-450 was connected via a Yaesu SCU-17 USB
Interface.

The SCU-17 provides: - USB-to-CAT serial interface - Audio interface for
digital modes - Reliable isolation and stable CAT communication

Any compatible USB-Serial CAT interface should work, provided the
correct COM port and baud rate are configured.

------------------------------------------------------------------------

Architecture Overview

SDR# Studio ↓ ControlPanel (UI) ↓ ControlPanelController ↓ SyncEngine ↓
YaesuCatClientAdapter ↓ YaesuCatClient (SerialPort) ↓ FT-450 (CAT)

------------------------------------------------------------------------

Installation

1.  Build the project in Release mode.
2.  Copy the compiled .dll into your SDR# Plugins directory.
3.  Add the plugin entry to Plugins.xml.
4.  Restart SDR#.

------------------------------------------------------------------------

Configuration

Settings file: YaesuFT450Control.settings.json

Example:

{ “ComPort”: “COM3”, “BaudRate”: 9600 }

Make sure the baud rate matches the CAT configuration in the FT-450.


License: MIT

Author: DO8DX
