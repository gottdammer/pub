PUB! Programmable USB Button
============================
Program a button to send keystrokes to your computer


PUB! is a Programmable USB Button on which you can program with a sequence of keystrokes. When you press the button those keystrokes are "replayed" over a USB connection.



Features
--------
- One-button design (a rotary encoder with a builtin switch)
- Programmed by using an ordinary text editor as a display (for example, gedit on Linux, or Notepad on Windows)
- Supports a GOTO function, so you can program loops
- Can send USB System Control codes (Power off, sleep, wake) to your PC
- Can send USB Consumer Device functions (e.g. Mute, Play, Pause, Stop, etc.)
- Requires NO drivers for Windows/Linux etc


Futures
-------
The possibilities are fairly broad including:
- Using a Bluetooth module to detect proximity of the button owner's mobile phone so that the USB button is only enabled when its owner is near.
- Support for a number of "registers" to record state. For example, R0 to R15.
- Support for basic arithmetic. Add, subtract, etc.
- Support for conditional logic. For example, Compare to value, Jump on zero, etc.


Construction
------------

TODO

How To Use
----------
### You want to program your password onto the PUB! button
  - Open a text editing program (for example, gedit or Notepad) and make sure it has keyboard focus
  - Plug PUB! into a host USB port
  - By default it is in RUN mode, so press and hold the rotary encoder knob for more than 1 second to switch to PROGRAM mode. It will display in your text editor:

          PUB! 0.90
          Main:   Turn=Select, Press=OK, Press+Turn=Set At, Press+Hold=Exit
             0    Set Keystroke at 00
          At Code Action

  - Press the rotary knob to set a keystroke. It will display:

          PUB! 0.90
          Key:    Turn=Select, Press+Turn=Modify, Press=OK, Press+Hold=Return
          00 0004 a
          At Code Action

  - Turn the rotary knob to choose the first letter of your password (say c) and then press the knob to add it to the list of actions:

          PUB! 0.90
          Key:    Turn=Select, Press+Turn=Modify, Press=OK, Press+Hold=Return
          01 0006 c
          At Code Action
          00 0006 c

  - Continue choosing and adding the remaining letters (say, a and t):

          PUB! 0.90
          Key:    Turn=Select, Press+Turn=Modify, Press=OK, Press+Hold=Return
          03 0017 t
          At Code Action
          00 0006 c
          01 0004 a
          02 0017 t

  - Press and hold the rotary knob to Return to the main menu:

          PUB! 0.90
          Main:   Turn=Select, Press=OK, Press+Turn=Set At, Press+Hold=Exit
             0    Set Keystroke 03
          At Code Action
          00 0006 c
          01 0004 a
          02 0017 t

  - Rotate the knob until "Save to EEPROM" is displayed:

          PUB! 0.90
          Main:   Turn=Select, Press+Turn=Set At, Press=OK, Press+Hold=Exit
             E    Save to EEPROM
          At Code Action
          00 0006 c
          01 0004 a
          02 0017 t

  - Press the knob to save "cat" to the EEPROM

          Saved in EEPROM

  - The device is now in RUN mode. Press the knob to "play" the recorded sequence:

          cat

