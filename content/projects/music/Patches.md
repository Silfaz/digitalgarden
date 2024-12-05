---
title: Patches
---


## 2024-11-10
### Red Means Recording Tutorial 1/4
https://www.youtube.com/watch?v=BTcP3DofZLY
_Shape sound with ADSR and VCF._

- MIDI > CV: generate CV from keyboard input.
- VCO: Feed the V/OCT output from MIDI > CV module into the V/OCT input on VCO. Generate wave with SIN. 
- SCOPE: Make waves visible.
- VCA: IN = sine wave from VCO. OUT = going into audio module.
- AUDIO: set to output audio device to hear the sounds. 

Now, to **shape the sine wave's volume with an LFO**:
1. Sine wave output from VCO into IN on VCA.
2. OUT on VCA into AUDIO.
3. To modulate the volume of the sine wave coming from the VCA, an LFO sine wave output is patched to the CV input of the VCA. 

_The volume of the tone goes up and down periodically with a speed that depends on the LFO's set frequency._

To instead **shape the sine wave's volume with an envelope**:
1. ADSR needs input signal, coming from a gate. 
2. GATE output on MIDI > CV module into GATE input on ADSR. So with every push on the keyboard, both a CV with information for the pitch of the note is generated (going into the VCO, that generates a sine wave at that pitch), as well as a gate signal (on/off) going into the ADSR, that controls the volume on the VCA. 

_The volume of the tone is shaped by the envelope, so it might build up and then fade slowly, depending how ADSR parameters are set._

Now we will include a filter to remove either the higher or lower notes. 
1. Change wave form from sine to saw wave, since VCFs don't really have anything to grab on to with a sine wave. 
2. Makes really fun sound when the tone is held and the cutoff knob is turned very much between low and high. A kind of spacey digeridoo sound. 



## 2024-10-23
### Most minimal
_Makes a constant sound_
MOST minimal setup
**VCO, AUDIO**

- VCO: Selected wave output (e.g. sine) --> input into AUDIO
- AUDIO: Turns the signals into audio output. Select the desired audio channel to hear it. 
### Minimal setup with keyboard input
_Change pitch of constant tone with keyboard and visualise what happens._
**MIDI>CV, VCO, SCOPE, AUDIO**

- MIDI>CV: Input is computer keyboard. Connect V/OCT to V/OCT on VCO.
- VCO: Creates a constant oscillation (sin, tri, saw or sqr). By connecting V/OCT from MIDI input to V/OCT on VCO, I can control the frequency (pitch) of the generated oscillation by pressing different keys on the keyboard.
- SCOPE: Connect the wave output to the input to see it visualised.
- AUDIO: Turns the signals into audio output. Select the desired audio channel to hear it. 

![](projects/attachments/Pasted%20image%2020241110100701.png)

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
