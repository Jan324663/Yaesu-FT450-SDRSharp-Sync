# SDRSharp.YaesuFT450Sync

## SDR# Plugin for 2-Way CAT synchronization with Yaesu FT-450D.

This plugin enables real-time frequency, mode, and bandwidth
synchronization between SDR# Studio and a Yaesu FT-450 / FT-450D
transceiver via CAT (Serial).

In addition, the transmitter output power can be controlled directly from the SDR# plugin interface.

### Features

2-Way Sync

-   SDR# → TRX
    -   Frequency
    -   Mode
    -   DSP Bandwidth (IF Width)
    -   Transmit Power
-   TRX → SDR#
    -   Frequency
    -   Mode

### Hardware Setup

TBC

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
