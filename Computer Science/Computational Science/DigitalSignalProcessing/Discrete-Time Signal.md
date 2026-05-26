---
date: 2026-05-25
aliases:
  - DT Signal
  - DT
  - Discrete-Time
---

A **discrete-time signal** is the result of [[Sampling]] a subset of the domain of an [[#Analog Signal]], creating a new signal where the [[Domain]] is discrete, while the [[Codomain]] remains [[Continuity|Continuous]]. It is typically denoted as $x[n]$, where $x$ is the function of the signal, and $n$ is the index.

![[Pasted image 20260521160335.png|300]]

An example of a discrete-time signal is within the process of digitally recording a guitar. While a microphone can hear any pitch, it can not convey every instant of a sound to a computer. Therefore, a broker responsible for converting the analog signal of the microphone into something the computer can understand is required. A [[Analog-to-Digital Converter]] decides on a certain sampling rate at which to note what the microphone hears at that moment so that it can eventually send a finite amount of information to the computer. At a certain stage within the converter, the signal is represented with discrete time, but the codomain is still continuous.