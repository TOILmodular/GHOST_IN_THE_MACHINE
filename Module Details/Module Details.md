# GHOST IN THE MACHINE - Module Details
This document is a more in-depth description of the setup, functions and controls of the GHOST IN THE MACHINE.

## Module Sections
The module consists of a number of different sections for creating and modulating audio signals.

- 2 VCOs, based on the AS3340 VCO chip (CEM3340 clone)
- A state variable lowpass VCF
- A noise generator
- A sample&hold unit
- 2 LFOs
- 2 delays, based on the PT2399 delay chip
- A knob function shuffle logic section, based on a shift register (CD4094) and a number of multiplexer chips (CD4052)

## Signal Flow Chart
The following graph shows the signal flow chart for audio and CV between the different module sections.
<img width="500" src="https://github.com/TOILmodular/GHOST_IN_THE_MACHINE/assets/97026614/ab3ed9ac-1f92-44cd-8025-82404f6bc720">

In a nutshell, one of the VCOs' signal is sent to the VCF, while the other one is influencing the cutoff frequency.
Setting the two VCOs' pitched in a certain way can even lead to vowel sounds, like when using a formant filter.
The signal is then sent via two separate delay units to the outputs.

There are a number of modulation optionsvia the LFOs, which combine their triangle signals, a sample & hold unit fed by a noise unit or optionally by an external source, and the other optional external inputs, explained in the module introduction README file.

## Fixed and Variable Knobs
One central aspect of the module to be more experimental and less controllable is the function of knob assignment shuffling.
So the front panel get messed up in some way.
As stated already, that is the main reason why I decided not to label the knobs for their functions.

However, this module is entirely analog, including the logic behind this shuffle function.
That limits the possibilities of such a function.
As can be seen in the flow chart, not all of the 17 knobs are being shuffled around.
Infact, there are only eight such knobs.

Those knobs are separated into two groups, each with four knobs.
Even that restriction already led to the need of eight multiplexer IC (CD4052), as described in the next section.
I guess, there is a more clever way to achieve that.
Anyway, this is what I could come up with.

The functions in group 1 (red knobs in the graph above) are
- An attenuator for the noise or external RANDOM source fed into the sample & hold section
- The frequency control for the VCO going into the VCF cutoff frequency control
- The frequency rate of one of the two LFOs
- The feedback control of one of the two delay units

The functions in group 2 (yellow knobs in the graph above) are
- An attenuator for the combined triangle signal of both LFOs
- The frequency control for the VCO going into the VCF input
- The frequency rate of the second LFO
- The feedback control of the second delay unit

The fixed knobs (black knobs in the graph above) are
- The VCF cutoff frequency control
- The VCF resonance control
- The glide controls for two identicat separate CV outputs from the sample & hold unit
- The delay times for both delay units
- The wet/dry mix controls for both delay units
- An attenuator for the VCF output signal before the delay units, which can be used as one volume control for both outputs

## Knob Assignment Shuffle Logic
As mentioned above, the shuffle logic core are eight CD4052 multiplexer ICs.
Each of the two groups with knobs to be shuffled make use of four of these ICs.

The logic how the shuffling works with the CD4052 chips might be a bit difficult to follow by just looking at the schematics.
In a nutshell, with each change, the potentiometer connections for all knobs in one group are swapped in a way, that connections for one potentiometer always stay together during the change.
The group size of four knobs each is chosen, because this limits the need of ICs.
An extension e.g. to all knobs in one group would significantly increase the number of needed multiplexers, let alone the attempt to add all 17 knobs on the front panel.

The randomness of knobs assigned to functions is actually quite limited.
But I hope it is still enough to cause some fun or even confusion.

## Switch Functions
