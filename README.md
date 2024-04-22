# GHOST IN THE MACHINE
The GHOST IN THE MACHINE is a noise/sound generating Eurorack module with many controls, but not much control.
It is meant to be a kind of black box for creating numerous different sounds with no specific information about how to create them.
All the knobs and switches are not labelled on purpose in order to encourage the user to experiment.

The module is built of several different sections with certain different signal flows (audio and CV), which can be influenced by these knobs and switches.
There are a number of optional inputs (labelled, but not in a traditional way), so the module can be influenced by other modules.
It has two separate outputs, so you can achieve some stereo effect or use each output separately.

You will find some basic information about the inputs, knobs, switches and the mysterious central push button below, sufficient to have fun with the module.
However, if you are interested in the details of the module below the skin, about the signal flow and more information of the given controls, you can find a more detailed user manual in the related folder.
I divided that part on purpose, in case you might not want to know too much, so the surprise in discovering new sounds is not taken away.

This YouTube video shows the module in action:

<img width="500" src="https://github.com/TOILmodular/GHOST_IN_THE_MACHINE/assets/97026614/f641cf4a-e125-4994-ba60-6b1bafa4b1dc">

## How the Module works (Basics)
As I stated in the intro above, you will only find some basic information about the module in this section in order to (hopefully) enjoy it.
More details are given in the folder "User Manual", if you want to know them.

### The Knobs
There are 17 knobs available at the front panel.
Turning each knob has a specific influence on the output.
Explaining the function of each knob is not really helpful, which will only be understandable, as soon as the central push button and the CHAOS input will be explained further below.
At the moment, I will only give two hints:

- The knobs located around the module outputs on both the left and right side are only  influencing the corresponding outputs.
- The lowest knob at the front panel center is controlling the level of both outputs.

## The Switches
There are 7 switches spread accross the front panel, which are influencing the routing of the internal CV and audio signal flows.
Depending on the knob settings, changing a switch can have no, subtle or big influence on the audio outputs.
Just like the knobs, the switches invite to experimenting.

### The Outputs
The audio signals presented at the two outputs are processed the same way, with the exception of those outer knobs mentioned above.
Processing the outputs via a stereo output mixer can provide a stereo effect for the module sound.
On the other hand, the signals can of course also further be processed separately by other modules.

### The Inputs
#### FEED (left and right)
The two FEED inputs provide the option to use external audio sources, instead of the internal ones.
But the signal flow and processing for each of those inputs is not the same.

#### TACT
The TACT input provides the option to add an internal clock signal to the module.
The usage of that clock signal might be recognizable more or less, depending on the setting of some of the controls.
If no cable is plugged in, the module is using an internal clock signal source.

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
The actual reason that no knob is labelled is an internal shuffle function, which allows a change of the assignment of several knobs to different control functions.
Each new assignment is done in a random way, and the trigger of shuffling the knob functions is the central button.
That trigger can also be provided by an external high signal (>1V) into the CHAOS input.

It should be mentioned, that not all knobs are shuffled in that way.
Some knobs keep their function and are not influenced by the shuffling.
However, I decided to keep all of them unlabelled, maybe for design aesthetics reasons.

## Module Build and PCBs

## Additional Information about specific Components
