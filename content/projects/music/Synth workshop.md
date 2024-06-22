---
title: Synth workshop
---

## Introduction


Standard synth: No patch cables. E.g. miniMoog
Modular synth: No coupling directly to any interface

What is modular synthesis? The routing and manipulation of signals to create sound and music. 
It's also analog computing. We can perform mathematical operations. 

Ring modulator

Guitar pedal is also a modular synth, making an effect.

High & low perspective
High level programming example of today: Using a sequencer
Low level programming example for today: 

Today's modules
- voltage controlled amplifier (VCA)
- Mixer
- Comparator
- Control voltage source
- Clock divider
- Sequential switch
- Quantizer
- Voltage controlled oscillator (VCO)
- Low frequency oscillator (LFO) --> there's no such thing as an LFO

Control voltage and frequency
Lots of different standards
- MIDI - digital
- CV/Gate - analog
- OSC - digital

How voltage is interpreted depends on the module. 
Voltage = electronic "pressure"
MIDI goes from 0-127V. 
Everything in modular synthesis is done through voltage. How voltage is interpreted depends on the module. 

VCV rack modules today:
LFO, VCO, Man CV, Scope, VCA, Audio
VCA: voltage-controlled volume knob

Quantizer (QNT): gets the signal and outputs the closest note --> turns a continuous signal into defined notes. 

Mixer: Matrix81. Adding two things together, e.g. a constant value to a square wave.

Comparator: CMP

Sequential switch, Clock (gate): Switch 8-1. Goes sequentially through different inputs.





CV-addressable sequencer


Bias


## Part 2

Analyzer

Additator
Overtone series


If you want to emulate a flute or clarinet-like instrument, use square waves.

Comparator: do something when it's above 0 and something else if it's below 0. 

Pulse with modulation
LFO > Comparator > VCO sawtooth wave > Audio

PW = pulse width. 

Sawtooth to triangle converter
Frequencer divider

Ring modulator Befaco "A * B+C"

Slew Limiter
Changes how fast a signal can change. Sounds a bit "drunk" or wobbly.

Filter



LFO > VCA > VCF, VCO > VCF


Wave folder
Inverts wave


VCO > VCF > Folding 
LFO > Folding, LFO > VCF

Envelope


MIDI > CV can have polyphony. Right click and select.

Drone with Envelope


Homework: 
- Design a base drum. E.g. with some white noise and quick thump.
- Optional, from Duncan: make a drone (that you can listen to for more than 10 min)



## Base drum
Version 1
Noise generator, white noise > VCA, envelope generator > VCA CV input with short attack, bit of decay, no sustain, short release. To trigger, connect LFO square wave with gate on envelope. 

## Bubbly water
Noise generator, red noise > VCF input, LPF > VCO v/oct input, sine wave output > 2nd VCO v/oct input, sine wave output > VCA channel input, output into Audio; ADSR env into VCA CV input.
Push trigger on ADSR to activate.

## Part 3
Attack-Release: not the whole ADSR module

G-T: Gate-to-trigger, trigger converteer. Has gate-in and turns it into a trigger or impulse

Instruo filter: V/OCT

Filters can generate self-oscillations, so can be used as "sound sources". 

Kickall Befaco: bassdrumm module. Put LFO square into the trigger input. Can also make a snare drum if tuned high up. Put in triangle wave into tune input. 

Clock divider: gives fractions

BPM Clock: 

Boolean modulator: Connect inputs with AND or OR or XOR. 

Low pass gate LLPG: opens up sound nicely

Maths module Rampage: Man.CV > Rampage

Sequencer: put Clock output into clk input to synch them up.

Wave folder: To make wave shapes more interesting. Feed into VCA, controlled by VCO sine wave to make it sound less shrill. 

Some modules that are not available in real life: e.g. NES --> load Mario ROM into it and make Mario run with signals

