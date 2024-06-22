---
title: VCV rack
---
What is modular synthesis? The routing and manipulation of signals to create sound and music.

# Modules
## MIDI > CV
Converts MIDI from an external device to CV and gates.
MIDI input can be from laptop keyboard, electric piano keyboard, etc.
Connect **V/OCT** output to V/OCT input on a VCO --> VCO receives pitch information from the MIDI input. 
**V/OCT** takes MIDI pitch information and converts it to pitch information (voltages) that Eurorack modules can understand. E.g. C1 = 0 volts, C2 (one octave up) = 1 volts, C3 = 2 volts. Notes in between have fractions of volts, e.g. 1.25 volts. 

**Gate** output = on/off switch. Either 0V or 10V signal. Can be turned into something a bit more nuanced with an envelope generator. Gate signals can be shaped by an envelope generator. 

## VCO - Oscillator
Creates constant oscillations.
Can create sine, triangle, saw and square wave. 
Frequency knob controls the pitch. Default = 261.63 Hz, i.e. C. 

FM input: 

## LFO
low frequency oscillator
Creates continuous oscillations below human hearing. 
Are handy when you want to create continuous motion whether or not pressing keys on a keyboard.
Can be connected well with envelope generators. 

## VCA - Amplifier (like a volume knob or fader)
Think of it as a volume switch. Can be turned up or down, either by hand or by voltage.  
How much of the input signal is going through to the output.
Hast two inputs: one that controls the level (can be dynamic) = **CV in**, and one that just feeds through and takes the level that is (manually) set = **channel input** . 

## ADSR - Envelope
Shapes the timbre over time
Envelopes put out SHAPES. They can shape volume, or pitch (frequency) or filter cutoff, or wherever else you plug the cable into. 
Takes the crude on/off information from the MIDI gate input, and creates a more nuanced sound: Connect the **gate** output from MIDI input to the **gate** input on the ADSR. 

Attack time can be elongated or shortened
Decay
Sustain
Release

E.g. for a more plucked sound: Short attack, medium decay, no sustain and release. 



## VCF - Filter
LPF = low pass filter. Let's the lowest pass through as the cutoff goes down. 
HPF = high pass filter. Cutoff dial to the right. 
Brighten up or dull down the timbre of a tone. Takes away (subtracts) energy from the input signal. 

Cutoff input slot: Lets us control the filter cutoff using other voltages. 


## SCOPE
Makes the waves and signals visible

## AUDIO 8
Audio output

## Notes
- V/OCT = volt per octave. One volt up is double the frequency, i.e. one octave up. 

## Sequencer


# Patches
## 2024-06-10 
### Patch 1
_Followed https://www.youtube.com/watch?v=TB-7vRnc5nw from 343 Labs Youtube channel._

MIDI from keyboard: 
- V/OCT into V/OCT on oscillator. _Takes signal from keyboard and converts it to pitch information for the oscillator._
- Gate into Gate on envelope generator. _Works as on/off switch for the MIDI input. By patching it to envelope, we can make a more nuanced on/off switch._
VCO: 
- Sawtooth wave into IN on filter. _Generates a continuous sawtooth wave. By patching it into the filter we can modulate the timbre of the tone (brighten or dull)._
- FM into ENV on envelope generator. _To modulate the envelope. FM makes it more squawky._
VCF: 
- CUT into ENV on envelope generator. _To modulate the cutoff of the envelope._ 
- LPF into channel in on amplifier. _Filtered signal goes into the channel input of the amplifier._
ADSR: 
- ENV into CV input on amplifier. _Total output from the envelope directs the signal intensity on the amplifier._

![](projects/attachments/Screenshot%202024-06-10%20at%2020.46.02.png)


### Patch 2: Modulation
Changing parameters over time
_Followed https://www.youtube.com/watch?v=z_rZKodSQPc from 343 Labs Youtube channel._

MIDI: 
- Gate output to Gate input on ADSR. _Our on/off switch_
- V/OCT output to V/OCT input on oscillator.

Oscillator: 
- OUT to IN on filter. 

Filter:
- Lowpass output to amplifier channel input. 

ADSR: 
- Envelope output to CV in on amplifier. _Envelope output is modulating, i.e. moving the loudness of the sound._
- Envelope output to Frequency input of filter. _Envelope output is modulating, i.e. moving  filter cutoff and therefore the brightness of the sound._
- 

Amplifier:
- OUT to IN of audio. 



