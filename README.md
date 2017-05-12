# DLD firmware v5 with send/return pre-delay

DLD firmware v5 with send/return pre-delay is a modest alternative firmware for the [Dual Looping Delay (DLD) eurorack module by 4ms](http://www.4mscompany.com/dld.php).

This firmware is identical to the official v5 firmware provided by 4ms, with the exception that each channel's audio is forced through its correponding send->return path before being written to the looping delay memory. This means that audio sent to the input of a given channel goes through the send->return path once before being delayed, and then again on each subsequent loop of the delay.

For example, if there is a low-pass filter in the send->return path, the dry sound will not go through the filter, the first echo will go through the filter once, the second echo will go through the filter twice, and so on.

Note that you must patch something from send to return for a given channel to work as expected. If send->return is left unpatched, nothing will be output. This is because all incoming audio and feedback is sent to the send output, and that the return input is used directly to write to the looping delay memory. If you do not want any effect in the delay feedback path, simply patch a cable straight from send to return.

# Installation

- Download and save [DLD-firmware-v5-send-return-pre-delay.wav](https://github.com/thomas-kielbus/DLD-firmware/raw/master/DLD-firmware-v5-send-return-pre-delay.wav)
- Follow manual instructions to update the DLD firmware using the audio bootloader

# Uninstallation

- Simply install the official firmware again
