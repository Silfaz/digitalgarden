---
title: Modular synthesis
---
From the book **Patch & Tweak - Exploring modular synthesis** by Kim Björn and Chris Meyer.

## Voltage control
Allows you (or your module) to remotely reach out and turn a knob on another module. The CV (voltage control) inputs are usually summed together internally with that parameter's knob to change how a module behaves. 
E.g. Sending CV to oscillator (VCO) instructs it to play a sound at a particular pitch (e.g. middle C). Sending CV to filter (VCF) input will tell it at what "corner" frequency it should start alterting the sound going through. Sending CV to amplifier (VCA) tells it how much to boost the sound. 
Most modules with CV inputs also have attenuators to reduce the strength of effect the incoming voltage has. 

Generating CVs: Keyboard, sequencer, module. 
### Gates, triggers
Special kind of CV that is most often used to indicate the timing and length of note events. Gate = starts and sustains note (5V) and then drops back to 0V. Trigger = quick positive voltage pulse. 

### Audio source oscillator
Outputs a voltage that fluctuates between positive and negative values at a speed in the audible range (20-20000 Hz). 
Classic oscillator waveforms contain a specific mixture of harmonics, giving them a distinctive timbre or sonic signature: 
- Sawtooth - most full sounding, both even and odd harmonics, well suited for recreating brass and string sounds.
- Square - perfect square contains only odd harmonics, sounds slightly more hollow than sawtooth. Pulse is a variation of square wave where the positive and negative portions have ratios different to 50%. 
- Triangle - contains just odd harmonics but compared to square wave, the strength of its higher harmonics fall away more quickly. 
- Sine - contains only one harmonic resulting in a very pure tone with no overtones. 

### Noise
Random signal that contains a wide array of unrelated frequencies. Used for sound effects like wind, surf, to add breath noise to recreations of real instruments, or as a random source for modulation. 

## Audio modifiers

