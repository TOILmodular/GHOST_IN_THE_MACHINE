# GHOST IN THE MACHINE
GHOST IN THE MACHINE is a noise/sound generating Eurorack module providing many controls, but not much control.
It is meant to be a kind of black box for creating numerous different sounds with no specific information about how to create them.
None of the knobs and switches are labelled on purpose in order to encourage to experiment.

<img height="500" src="https://github.com/TOILmodular/GHOST_IN_THE_MACHINE/assets/97026614/3267466e-8458-4e35-b397-e47aecb191f6">
<img height="500" src="https://github.com/TOILmodular/GHOST_IN_THE_MACHINE/assets/97026614/69268a0a-fc85-415c-8a68-d5b05628b578">
<img height="500" src="https://github.com/TOILmodular/GHOST_IN_THE_MACHINE/assets/97026614/c5759ef7-6633-4786-beb4-f305428482b0">

The module is built of several different sections with certain different signal flows (audio and CV), which can be influenced by these knobs and switches.
There are a number of optional inputs (labelled, but not in a traditional way), so the module can be influenced by other modules.
It has two separate outputs, so you can achieve some stereo effect or use each output separately.

You will find some basic information about the inputs, knobs, switches and the mysterious central push button below, sufficient to have fun with the module.
However, if you are interested in the details of the module below the skin, about the signal flow and more information of the given controls, you can find more in the folder "Module Details".
I divided that part on purpose, in case you might not want to know too much, so the surprise in discovering new sounds is not taken away.

This YouTube video shows the module in action:

[<img width="500" src="https://github.com/TOILmodular/GHOST_IN_THE_MACHINE/assets/97026614/42def195-1964-4781-99b4-90af90b23f52">](https://youtu.be/bmia9UFnqQ8)

## How the Module works (Basics)
### The Knobs
There are 17 knobs available at the front panel.
Turning each knob has a specific influence on the output.
Explaining the function of each knob is not really helpful, which will only be understandable, as soon as the central push button and the CHAOS input will be explained further below.
At the moment, I will only give two hints:

- The knobs located around the module outputs on both the left and right side are related to internal delay units and only influencing the corresponding outputs.
- The lowest knob at the front panel center is controlling the level of both outputs.

### The Switches
There are 7 switches spread across the front panel, which are influencing the routing of the internal CV and audio signal flows.
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
It should also be mentioned, that using external sound sources will cut off some of the internal modulation options.

#### TACT
The TACT input provides the option to add an external clock signal to the module.
The usage of that clock signal might be recognizable more or less, depending on the setting of some of the controls.
If no cable is plugged in, the module is using an internal clock signal source, which can also vary, depending on the control settings.

#### RANDOM
The module is using an internal random CV source in different signal flows.
The RANDOM input provides the option to use any external signal as source for the random CV.

#### TUNE
The TUNE input can be used to send a pitch signal to one of the internal audio sources.
The internal audio sources do not strictly follow the 1volt/octave standard, and the module is not meant to output any harmonic melody.
But if desired, this input can be used for attempts to somehow influence the pitch of the module.
However, it cannot be guaranteed that the result is as expected.

#### SWEEP
The SWEEP input can be used for an external CV signal to influence the cutoff of the internal filter section of the module.
The module does not contain any envelope generator.
The SWEEP input is great for e.g. creating interesting pluck sounds by sending CV from an ADSR.

### The central Push Button and the CHAOS Input
The actual reason why no knob is labelled is an internal shuffle function, which allows a change of the assignment of several knobs to different control functions.
Each new assignment is done in a random way, and the trigger of shuffling the knob functions is the central button.
That trigger can also be provided by an external high signal (>1V) into the CHAOS input.

If you are tired or stuck with the sound from the module, then just push the button, as often as you like to immediately create some different sounds, until you find something interesting to continue working with that one.
Sometimes the change might be very tiny or not recognizable at all.
Then just try again.
It is all about getting surprised and finding new and strange tunes.

It should be mentioned, that not all knobs are getting shuffled.
Some knobs keep their function and are not influenced by the shuffling.
However, I decided to keep all of them unlabelled.
You might find out some fixed points for orientation, as you play along with the module.

## Module Build and PCBs
I added two different versions for the control board in the folder GerberFiles, an "Original", and a "Thonk" version. Reason is that for my own module, I am using specific potentiometers - 16K4 series from Supertech Electronics - and 3.5mm jack sockets - MJ-355 from Marushin - available at my local electronics shop.

<img width="500" alt="CtrlPCB_Orig" src="https://github.com/TOILmodular/GHOST_IN_THE_MACHINE/assets/97026614/d7795712-9d43-4c20-a772-2e5bc55c6953">

However, since most DIY projects for Eurorack modules out there are using potentiometers from ALPHA and so-called THONKICONN jacks, as they are provided by Thonk in the UK, I also created another control board PCB for the "Thonk" version with footprints for those components.

<img width="500" alt="CtrlPCB_Thonk" src="https://github.com/TOILmodular/GHOST_IN_THE_MACHINE/assets/97026614/0ddded87-ad4e-457d-9258-b7f5fc965c0d">

The main PCB is the same for both versions.

<img width="500" alt="MainPCB" src="https://github.com/TOILmodular/GHOST_IN_THE_MACHINE/assets/97026614/58fe27d1-5f04-411f-8417-e86c8ac5d92c">

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

<img width="432" alt="LFO Caps" src="https://github.com/TOILmodular/GHOST_IN_THE_MACHINE/assets/97026614/bb9ccacb-d89d-4794-9aa7-bef4f79a8560">

The rates of the 2 internal LFOs can be changed to some degree via two 100K potentiometers.
But the main range of the rate is determined by a capacitor for each of the LFOs.
The location of those caps is given on the control PCB with the label "CAP FOR LFO RATE" (see picture above).

The values for those caps are not specified in the BOM and can be selected, depending on the desired oscillation range.
I prefer slow movements, so I used 47uF caps for both LFOs (check the YouTube video linked above for hearing the result).
If you choose a small value around 1000pF, the rate will be in the audio range.
You can try out any vallue and check if the modulation is as you like it.
The values do not have to be the same.

One electrolytic capacitor on the control board (47uF) is located very close to the edge of the main board on top of the control board. Due to that, the capacitor cannot be mounted in the usual standing position. Instead, bend the legs and mount it in a horizontal way, as shown in the picture below. The rectangle on the PCB shows the position of the horizontal capacitor.

<img width="432" src="https://github.com/TOILmodular/GHOST_IN_THE_MACHINE/assets/97026614/57125876-ce0b-4a9b-8371-872ae6278f89">
