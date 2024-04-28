# GHOST IN THE MACHINE
GHOST IN THE MACHINE is a noise/sound generating Eurorack module providing many controls, but not much control.
It is meant to be a kind of black box for creating numerous different sounds with no specific information about how to create them.
All the knobs and switches are not labelled on purpose in order to encourage the user to experiment.

The module is built of several different sections with certain different signal flows (audio and CV), which can be influenced by these knobs and switches.
There are a number of optional inputs (labelled, but not in a traditional way), so the module can be influenced by other modules.
It has two separate outputs, so you can achieve some stereo effect or use each output separately.

You will find some basic information about the inputs, knobs, switches and the mysterious central push button below, sufficient to have fun with the module.
However, if you are interested in the details of the module below the skin, about the signal flow and more information of the given controls, you can find more in the folder "Module Details".
I divided that part on purpose, in case you might not want to know too much, so the surprise in discovering new sounds is not taken away.

This YouTube video shows the module in action:

<img width="500" src="https://github.com/TOILmodular/GHOST_IN_THE_MACHINE/assets/97026614/f641cf4a-e125-4994-ba60-6b1bafa4b1dc">

## How the Module works (Basics)
### The Knobs
There are 17 knobs available at the front panel.
Turning each knob has a specific influence on the output.
Explaining the function of each knob is not really helpful, which will only be understandable, as soon as the central push button and the CHAOS input will be explained further below.
At the moment, I will only give two hints:

- The knobs located around the module outputs on both the left and right side are related to internal delay units and only influencing the corresponding outputs.
- The lowest knob at the front panel center is controlling the level of both outputs.

### The Switches
There are 7 switches spread accross the front panel, which are influencing the routing of the internal CV and audio signal flows.
Depending on the knob settings, changing a switch can have no, subtle or big influence on the audio outputs.
Just like the knobs, the switches invite to experimenting.

### The Outputs
The audio signals presented at the 2 outputs are processed the same way, with the exception of those delay related knobs mentioned above, influencing each output separately.
Processing the outputs via a stereo output mixer can provide a stereo effect for the module sound.
On the other hand, the signals can of course also further be processed separately by other modules.

### The Inputs
#### FEED (left and right)
The 2 FEED inputs provide the option to use external audio sources, instead of the internal ones.
But the signal flow and processing for each of those inputs is not the same.

#### TACT
The TACT input provides the option to add an external clock signal to the module.
The usage of that clock signal might be recognizable more or less, depending on the setting of some of the controls.
If no cable is plugged in, the module is using an internal clock signal source, which can also vay, depending on the control settings.

#### RANDOM
The module is using an internal random CV source in different signal flows.
The RANDOM input provides the option to use any external signal as source for the random CV.

#### TUNE
The TUNE input can be used to send a pitch signal to one of the internal audio sources.
The internal audio sources do not strictly follow the 1volt/octave standard, and the module is not meant to output any harmonic melody.
But if required, this input can be used for attempts to get some melody out of the module.
However, it cannot be guaranteed that the result is as desired.

#### SWEEP
The SWEEP input can be used for an external CV signal to influence the cutoff of the internal filter section of the module.

### The central Push Button and the CHAOS Input
The actual reason why no knob is labelled is an internal shuffle function, which allows a change of the assignment of several knobs to different control functions.
Each new assignment is done in a random way, and the trigger of shuffling the knob functions is the central button.
That trigger can also be provided by an external high signal (>1V) into the CHAOS input.

It should be mentioned, that not all knobs are shuffled in that way.
Some knobs keep their function and are not influenced by the shuffling.
However, I decided to keep all of them unlabelled.

## Module Build and PCBs
I added two different versions for the control board in the folder GerberFiles, an "Original", and a "Thonk" version. Reason is that for my own module, I am using specific potentiometers - 16K4 series from Supertech Electronics - and 3.5mm jack sockets - MJ-355 from Marushin - available at my local electronics shop.

<img width="500" alt="CtrlPCB_Orig" src="https://github.com/TOILmodular/GHOST_IN_THE_MACHINE/assets/97026614/1a8eb5f8-ef41-4a7d-83ed-d276df13eec9">

However, since most DIY projects for Eurorack modules out there are using potentiometers from ALPHA and so-called THONKICONN jacks, as they are provided by Thonk in the UK, I also created another control board PCB for the "Thonk" version with footprints for those components.

<img width="500" alt="CtrlPCB_Thonk" src="https://github.com/TOILmodular/GHOST_IN_THE_MACHINE/assets/97026614/11e89a37-6327-445a-8af4-69d1aa8cbfa4">

The main PCB is the same for both versions.

<img width="500" alt="MainPCB" src="https://github.com/TOILmodular/GHOST_IN_THE_MACHINE/assets/97026614/b58380e9-6774-411c-816d-efc6c38ffd27">

I created the Gerber files with the online tool EasyEDA and ordered the PCBs at JLCPCB.

## Panel Layout
I added the information about hole coordinates for the front panel in the folder "Panel Layout", referring to the component layout in the PCB Gerber files.

In addition, there is another Gerber file for the panel, following the HP standard.
My own modules do not follow that width standard, as I am only using sliding nuts in my racks.

You can use the panel Gerber file to have the panel built out of PCB material.

## Additional Information about specific Components
The module build is mainly THT, including all ICs.
However, there are a number SMD capacitors with the package size 1608 (imperial 0603), several transistors (package SOT-23-3) and a voltage regulator (package SOT-89-3).

Concerning the resistor size, I am usually using small-size resistors, about half the length of the usual size, so they need less space on the PCB. If you want to use my Gerber files, you have to consider that fact. You might still use normal size resistors and put them in a standing position on the boards. Should also work fine. Footprints for a few resistors with values larger than 1M have the standard size.
