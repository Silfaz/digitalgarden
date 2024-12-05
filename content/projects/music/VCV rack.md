---
title: VCV rack
---
# What is modular synthesis? 
The routing and manipulation of signals to create sound and music.
[Modular synthesis](projects/music/Modular%20synthesis.md)

# VCV-specific
https://vcvrack.com/manual/GettingStarted
All signals in VCV rack are virtual voltages, but they can be classified roughly into a few categories:
- **Audio** signals are audible if played through your speakers. They contain audio-rate frequencies typically between 20 Hz and 20 000 Hz. 
- **CV** (control voltage) signals can modulate parameters of other modules. For example, and LFO (low frequency oscillator) can oscillate the pitch of a VCO (voltage-controlled oscillator) or the volume level of a VCA (voltage-controlled amplifier). 
- **1V/oct** (1 volt per octave) signals are CV signals that represent a pitch or a note. In this standard, and increase of 1V increases the pitch by 1 octave. Since there are 12 semitones in an octave, an increase of 1/12 V increases the pitch by one semitone. 
- **Gate** signals carry an on/off signal. 0V represents off, and a positive voltage (typically 10V) represents on. For example a gate signal can turn on when a key is pressed, and off when a key is released. 
- **Trigger** signals are short gates (usually around 1 millisecond) that cause an event to occur, such as a percussion hit. 
- **Clock** signals are triggers played at a steady tempo, in order to set the musical timing of your patch. 



# Modules

## Audio
https://vcvrack.com/manual/Core#audio
The VCV Audio module is the portal between the physical and the virtual world. It sends audio from the VCV rack to your speakers. It can also receive audio from microphones and your audio device's inputs. 

![150](projects/attachments/Pasted%20image%2020241110111702.png)


## MIDI > CV
https://vcvrack.com/manual/Core#MIDI-CV
**Converts MIDI notes from an external MIDI device to CV and gate signals.** _That CV information then goes into e.g. a VCO._
MIDI input can be from laptop keyboard, electric piano keyboard, game controller, etc. 

![150](projects/attachments/Pasted%20image%2020241110103436.png)


**V/OCT** generates 1V/oct pitch signal of the last held MIDI note. Takes MIDI pitch information and converts it to pitch information (voltages) that Eurorack modules can understand. E.g. C1 = 0 volts, C2 (one octave up) = 1 volts, C3 = 2 volts. Notes in between have fractions of volts, e.g. 1.25 volts. 
_Connect **V/OCT** output to V/OCT input on a VCO --> VCO receives pitch information from the MIDI input._

**Gate** output = on/off switch. Either 0V (key not pressed) or 10V (key pressed) signal. Can be turned into something a bit more nuanced with an envelope generator. 
_Gate signals can be shaped by an envelope generator. By connecting an ADSR to the gate output, we're saying: "Turn the ADSR on when a note is pressed, and turn it off when it isn't."_

Righ-click the module to enable **polyphony**, and select the number of polyphonic channels. Makes it possible to overlay several notes at once. Polyphony mode selects the order in which those newly pressed notes appear in the selection . 




## VCO - Oscillator
https://vcvrack.com/Free#VCO
_= voltage controlled oscillator_
**Generates raw tones at a particular frequency (pitch). Creates constant oscillations. Creates the sound.**

Can make sine, triangle, saw and square wave. 
- Sine wave = sounds clean and round.
- Triangle wave = sounds clean but less warm than sine. 
- Square wave = piercing sound
- Saw wave = sharp sound

![200](projects/attachments/Pasted%20image%2020241110102332.png)

**Frequency** knob controls the pitch. Default = 261.63 Hz, i.e. C (C4, middle C). 

**Pulse width** can be controlled by the Pulse Width knob and modulated by the PWM (pulse width modulation) CV input and attenuverter. By default it's 50% of the total wavefrom. Higher and lower pulse widths give reduced harmonics for a thinner sound. 

To control the pitch with another module, path a CV signal into the V/OCT input or the FM input. 
**V/OCT** multiplies the frequency value using the 1V/octave standard, i.e. each volt of CV increases the pitch by 1 octave, meaning each 1/12 V increment increases the pitch by 1 semitone. 

**FM** input applies an additional pitch adjustment with the attenuverter knob. At 100%, the FM input functions like the V/OCT input. Press the LFM button to enable linear frequency mode; the oscillator's frequency is adjusted proportionally to the FM voltage, rather than exponentially. 


## LFO
https://vcvrack.com/Free#LFO
_=low frequency oscillator_
**Creates continuous oscillations below human hearing.**
Like invisible hands that can turn knobs for you. 

Very similar to VCO. LFO is more suitable for generating CV for modulation (while VCO is more suitable for generating audible waveforms). 
LFO is handy when you want to create continuous motion whether or not pressing keys on a keyboard.
Can be connected well with envelope generators. 
 ![200](projects/attachments/Pasted%20image%2020241110103035.png)
Range of the **FREQ** know is much lower than for VCO, ranging from one osciallation every 4 min to about 1000 Hz. 

Square wave on an LFO can also be used as a gate signal input for e.g. an envelope generator.

## VCA - Amplifier (like a volume knob or fader)
https://vcvrack.com/Free#VCA-1
_= voltage controlled amplifier_
**Think of it as a volume switch. Can be turned up or down, either by hand or by voltage.**

How much of the input signal is going through to the output.

The VCA applies gain/attenuation to an audio signal or CV signal according to _another_ CV signal. E.g. you can control the volume level of a synth voice with an envelope generator or sequencer. 

Hast two inputs: one that controls the level (can be dynamic) = **CV in**, and one that just feeds through and takes the level that is (manually) set = **channel input**. 
E.g. the output of an ADSR goes into the upper input so that the ADSR modulates the amplifier. 


![50](projects/attachments/Pasted%20image%2020241110102429.png)
_E.g. Output from an ADSR envelope is going into CV input. The volume on the VCA is now controlled by the ADSR and reacts according to where in the envelope we are at any point in time._

## ADSR - Envelope generator
https://vcvrack.com/Free#ADSR
**Shapes the timbre over time.**
Allows you to shape the timing of the synth, e.g. to fade the sound in gradually.
Envelopes put out SHAPES. They can shape volume, or pitch (frequency) or filter cutoff, or wherever else you plug the cable into. 
Takes the crude on/off information from the MIDI gate input, and creates a more nuanced sound: _Connect the **gate** output from MIDI input to the **gate** input on the ADSR._

![200](projects/attachments/Pasted%20image%2020241110104822.png)

The envelope generator converts a gate (on/off state) into a CV signal with a musically useful shape. Often used to control VCAs. Also, often there's one dedicated envelope for the volume, and one for the cutoff on a filter (e.g. VCF --> ENV output on envelope into CUT input on VCF).



The ADSR envelope generator was developed in the 1960s as an attempt to emulate the behaviour of physical instruments, such as the piano. 

![](projects/attachments/Pasted%20image%2020241021205840.png)
_(From https://mastering.com/modular-synthesis/)_

**Attack**: How long it takes for the synth to reach full volume. Rising time while the gate is HIGH.
**Decay**: How long it takes for the synth to fade to its secondary volume. Falling time while the gate is HIGH.
**Sustain**: How loud the synth is after reaching secondary volume. Target CV level while decaying.
**Release**: How long it takes for the synth to completely fade out. Falling time when gate is LOW.

### Examples of sounds from ADSR
_(From https://mastering.com/modular-synthesis/)_

Plucked sound: Short attack, medium decay, no sustain and release. 
![|500](projects/attachments/Pasted%20image%2020241021210046.png)


Others:
![|500](projects/attachments/Pasted%20image%2020241021210136.png)



## VCF - Filter
https://vcvrack.com/Free#VCF
_= voltage controlled filter_
**Removes a range of frequencies from an audio signal, with its cutoff frequency controlled by an external voltage.**

Brighten up or dull down the timbre of a tone. Takes away (subtracts) energy from the input signal. Filters are used in many types of synthesiser patches to control the intensity or harmonic richness of audio signals. 

Works best with wave forms _other than_ sine wave, e.g. a saw wave.

**LPF** = low pass filter. Let's the lowest pass through as the cutoff goes down. 
**HPF** = high pass filter. Cutoff dial to the right. 


![200](projects/attachments/Pasted%20image%2020241110105957.png)

**CUTOFF** knob sets the characteristic frequency of the filter, the point where it begins to attenuate frequencies. Set to where the cutoff frequency should start from (8-8000 Hz). If set to 100%, the cutoff modulation input controls the frequency with the 1V/octave standard.

**RES** knob controls the filter resonance, which emphasises the signal near the cutoff frequency.

**DRIVE** knob adds gain to input signal. Creates a dirtier, grungier filter sound.

**CUT** cutoff input slot: Lets us control the filter cutoff using other voltages. CUT attenuverter: Set to amount that the big CUTOFF dial should react to. If it's set to 100%, the big cutoff dial will, with every signal, turn all the way to maximum. If it starts at 8 Hz, it would go all the way up to 8000 Hz. If set to 50%, the big cutoff dial would go a half circle. 
Patch for example the ENV output of an envelope generator into the CUT input on the VCF. Turn attenuverter high (100%) and the cutoff knob low to get the most effect. 

## SCOPE
_oscilloscope_
https://vcvrack.com/Free#Scope
**Makes the waves and signals visible.**

An oscilloscope visualises voltage signals over time. Good for understanding CV and audio signals.

![200](projects/attachments/Pasted%20image%2020241110110856.png)

Patch any cable into **IN1** or **IN2** to see its voltage over time. Outputs **OUT1** and **OUT2** are provided to pass the signal through to other modules. 

**TIME** knob zooms the screen horizontally (5 ms - 50 sec). 
**GAIN** knobs zoom the screen vertically. 
**OFST** knobs pan the screen vertically. 


## AUDIO 8
Audio output

## Notes
- V/OCT = volt per octave. One volt up is double the frequency, i.e. one octave up. 

## Sequencer





