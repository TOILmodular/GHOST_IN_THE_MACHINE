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

<img width="600" src="https://github.com/TOILmodular/GHOST_IN_THE_MACHINE/assets/97026614/2c9872de-066e-4f44-a3c1-7a8c8fcf474d">

The signal of one of the VCOs is sent to the VCF, while the other one is influencing the cutoff frequency.
Pitching the two VCOs in a certain way can even lead to vowel sounds, like when using a formant filter.
The signal is then sent via 2 separate delay units to the outputs.

There are a number of modulation options via the LFOs, which combine their triangle signals, a S&H unit fed by a noise unit or optionally by an external source, and the other optional external inputs, explained in the module introduction README file.

<img width="600" src="https://github.com/TOILmodular/GHOST_IN_THE_MACHINE/assets/97026614/c3ed3ab8-df07-4aa6-83b9-92007e638b6a">

## Fixed and Variable Knobs
One central aspect of the module to be more experimental and less controllable is the function of knob assignment shuffling.
So the front panel gets messed up in some way.
As stated already, that is the main reason why I decided not to label the knobs for their functions.

However, this module is entirely analog, including the logic behind this shuffle function.
That limits the possibilities of such a function.
As can be seen in the flow chart, not all of the 17 knobs are being shuffled around.
Infact, there are only 8 such knobs.

Those knobs are separated into 2 groups, each with 4 knobs.
Even that restriction already led to the need of 8 multiplexer ICs (CD4052), as described in the next section.
I guess, there is a more clever way to achieve that.
Anyway, this is what I could come up with.

The functions in group 1 (red) are
- An attenuator for the noise or external RANDOM source fed into the S&H section 
- The frequency control for the VCO going into the VCF cutoff frequency control
- The frequency rate of one of the 2 LFOs
- The feedback control of one of the 2 delay units

The functions in group 2 (yellow) are
- An attenuator for the combined triangle signal of both LFOs
- The frequency control for the VCO going into the VCF input
- The frequency rate of the second LFO
- The feedback control of the second delay unit

The fixed knobs are
- (1) The VCF cutoff frequency control
- (2) The VCF resonance control
- (3, 4) The glide controls for 2 identical separate CV outputs from the S&H unit
- (5, 6) The delay times for both delay units
- (7, 8) The wet/dry mix controls for both delay units
- (9) An attenuator for the VCF output signal before the delay units, which can be used as a kind of one volume control for both outputs. However, this will not necessarily always reduce the volume to zero, as it is located before the delay units, so that existing echoes and feedback signals might continue.

## Knob Assignment Shuffle Logic
As mentioned above, the shuffle logic core consists of 8 CD4052 multiplexer ICs.
Each of the 2 groups with knobs to be shuffled make use of 4 of these ICs.

The logic how the shuffling works with the CD4052 chips might be a bit difficult to follow by just looking at the schematics.
In a nutshell, with each change, the potentiometer connections for all knobs in one group are swapped (turned on at one connection point and off at others) in a way, that connections for one potentiometer always stay together during the change.

The group size of 4 knobs each is chosen, because this limits the need of ICs.
An extension e.g. to all 8 knobs combined in one group would significantly increase the number of needed multiplexers, let alone the attempt to add all 17 knobs on the front panel.
Therefore, the randomness of knobs assigned to functions is actually quite limited.
But I hope it is still enough to cause some fun or even confusion.

The decision about how to shuffle the knob assignments, i.e. the way the multiplexers are determining connections, is done via 2 control bits in each IC.
Those control bits are provided by a CD4094 shift register.
The data to be moved into the shift register is derived from the internal noise source sent via a comparator op amp, deciding for a high or low bit.
In order to ensure the simultaneous shuffling of all knobs in one group, all multiplexers for that group receive the same control bits.

Triggering a shuffle event is done either via the central push button, or with a high signal (>1V) sent into the CHAOS input.
That trigger is sent to the shift register clock input.
So keeping the button pressed or keeping the CHAOS input high does not cause a permanent shuffling, but trigers the process only once.
Re-shuffling requires another separate trigger pulse.

## Switch Functions
The 7 switches on the front panel are all fixed, i.e. there is no shuffling for them.

The switch functions are
- (A) Waveform selection (sawtooth or square) in the VCO, which is sending the signal into the VCF input
- (B) Sending the CV from the S&H unit to the frequency control of the VCO, which is connected to the VCF input (on or off)
- (C) Switching between the S&H output and the combined CV from both internal LFOs to be sent to the VCF cutoff frequency control
- (D) Soft sync switch from the VCO, which is connected to the VCF input, to the other VCO (on or off)
- (E) Sending combined CV from both internal LFOs to the frequency control of the VCO, which is connected to the VCF cutoff frequency control (on or off)
- (F) Sending CV from the S&H unit to the frequency control of the VCO, which is connected to the VCF cutoff frequency control (on or off)
- (G) Waveform selection (triangle or square) in the VCO, which is sending the signal into the VCF cutoff frequency control
