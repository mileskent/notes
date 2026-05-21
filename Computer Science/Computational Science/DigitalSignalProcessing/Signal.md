---
date: 2026-05-20
---
A signal is a way of carrying information from one place to another.

The [[Domain]] of a signal is almost always time. The [[Codomain]] is usually some kind of measure of amplitude, whether it be decibels, voltage, etc. An exception to the rule of thumb are inputs involving both space and time, such as sensor data from a satellite or a waymo or something, where the domain is spatiotemporal rather than just temporal, consisting of coordinates and time, and the codomain is some kind of multidimensional representation of color, usually RGBA, rather than a single scalar.

# Analog Signal
An **analog signal** is a [[Continuity|Continuous]] wave.

An example of an analog signal is sound; imagine a guitar string vibrating at an 440 Hz A. Not only is the string a continuous wave, but the compression waves it imparts onto the air, the sound, are also continuous waves.

# Discrete-Time Signal
A **discrete-time signal** is the result of [[Sampling]] a subset of the domain of an [[#Analog Signal]], creating a new signal where the [[Domain]] is discrete, while the [[Codomain]] remains [[Continuity|Continuous]]. 

An example of a discrete-time signal is within the process of digitally recording a guitar. While a microphone can hear any pitch, it can not convey every instant of a sound to a computer. Therefore, a broker responsible for converting the analog signal of the microphone into something the computer can understand is required. A [[Analog-to-Digital Converter]] decides on a certain sampling rate at which to note what the microphone hears at that moment so that it can eventually send a finite amount of information to the computer. At a certain stage within the converter, the signal is represented with discrete time, but the codomain is still continuous.

# Digital Signal
A **digital signal** is the result of [[Quantization|Quantizing]] the values of the codomain of a [[#Discrete-Time Signal]], creating a new signal where both the [[Domain]] and [[Codomain]] are discrete. 

An example of a digital signal would be the final steps of the [[Analog-to-Digital Converter]] before it sends the final digital signal to the computer; it has to represent that signal in binary. Any means of representing all continuous values with finite digits of precision will lead to loss, so regardless of if you choose [[IEEE 754 Double]]s, or some kind of integer, you will be performing some level [[Quantization]] to the signal. The result is a signal with both discrete time and amplitude.