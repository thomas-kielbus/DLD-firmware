# DLD firmware v5 with send/return before loop

DLD firmware v5 with send/return before loop is a modest alternative firmware for the [Dual Looping Delay (DLD) eurorack module by 4ms](http://www.4mscompany.com/dld.php), based on the [original open-source firmware](http://github.com/4ms/DLD).

This firmware is identical to the official v5 firmware provided by 4ms, with the exception that each channel's send->return insert can be positioned right before the looping delay memory. (Instead of being a parallel feedback path only.) This behavior can be turned on or off for each channel using the DLD's system settings mode.

Turning on this behavior means that audio sent to the input of a given channel goes through the send->return path once before being delayed, and then again on each subsequent feedback loop of the delay. For example, if you patch a low-pass filter in the send->return path, the dry sound will not go through the filter, the first echo will go through the filter once, the second echo will go through the filter twice, and so on.

# Caveats

- To use the new send/return behavior, you must turn it on in the DLD's system settings mode (see manual). This firmware adds a new system settings page which is accessed using (time A switch = center, time B switch = up). Press on the "reverse" button of a given channel to turn on or off the new send/return behavior for that channel. Light off = original behavior. Light on = send->return before loop is enabled.

- __Important:__ you must always patch something from send to return for a given channel for it to work as expected when the send/return before loop mode is enabled. If send->return is left unpatched, no wet sound will be output. This is because all incoming audio and feedback is sent to the send output, and that the return input is used directly to write to the looping delay memory. If you do not want any effect inserted in the delay audio and feedback path, simply patch a cable directly from send to return.

- Having the send->return path before the looping delay memory modifies the audio topology of that channel. Some patches that are possible with the original firmware are not possible anymore, for example patches with two feedback loops using send/return across both channels.

# Installation

- Download and save [DLD-firmware-v5-send-return-before-loop.wav](http://github.com/thomas-kielbus/DLD-firmware/raw/master/DLD-firmware-v5-send-return-before-loop.wav)
- Follow manual instructions to update the DLD firmware using the audio bootloader

# Uninstallation

- Simply install the official firmware again
