# VOICE CONTROLLED WHEELCHAIR FOR THE QUADRIPLEGIC


Voice controlled wheelchairs extend the capabilities of a conventional wheelchair by providing a facility to control the movement of it by voice commands. This is helpful for those with severe physical impairments, particularly those who are quadriplegic.
A voice controlled wheelchair is under development. The aim of the project is to develop a wheelchair that is driven by voice commands. A speaker dependent voice recognition module is used for this purpose. The ongoing work towards attaining the goal of a fully functional and efficient wheelchair is described in this report.

1.Introduction

A wheelchair is a mechanical device that assists in transportation to those who are unable to walk on their own. A traditional wheelchair demands them to manually control its movement or use the assistance of someone else available. This sets a barrier to those who have lost control over their upper body also.

Advancements in technologies have the potential to cater to the needs of people with different degrees of incapacities. For instance, a joystick controlled wheelchair controls the direction effectively with slight finger movements. However, this requires persons to have control over their upper body.
 
One of the many solutions to aid the quadriplegic, who are paralyzed in both arms and legs, is to provide them with a support system that they can control using their voice. A voice controlled wheelchair takes specific words as input commands to drive it. 


 1.1 The voice controlled wheelchair project

The aim of the project is to develop a fully functional wheelchair that uses a seat, 4 wheels, battery and the control system mounted on a metal chassis. It is controlled by speaker dependent voice commands. The control system consists of EasyVR, a voice recognition module and Arduino Uno, a microcontroller board based on ATmega328. The movement of the wheelchair is influenced by two motors taking care of linear and directional movements respectively.






2.Theory
2.1 Voice signals
Voice consists of the sound made by a human being using vocal folds for talking, laughing, crying etc.
When a person speaks, his or her voice changes in power and utterance. Voice authentication refers to the accepting or rejecting of an identity claim of a speaker based on the individual information present in the waveform. The different characteristics of an analog voice input are amplitude, frequency, period etc.
The first step of voice recognition is that the user has to speak into the microphone. The electrical signals from this microphone are then digitized  using an analog-to-digital converter (A/D Converter) and is stored in the memory. 

2.2  Analog to digital conversion
The voice input sent via  microphone is an analog waveform which has to be converted into digital signal and then sent for processing. This analog-to-digital conversion can be done using the following techniques: Pulse Code Modulation (PCM) and Delta Modulation.

2.3 Pulse Code Modulation
A PCM encoder has three processes
•	Sampling
•	Quantization 
•	Encoding
2.3.1 Sampling

This process is also known as Pulse Amplitude Modulation (PAM).  
The analog signal is sampled every Ts seconds where Ts is the sample interval or period. The sampling frequency is given as fs=1/Ts. The sampling rate depends on the Nyquist theorem. 
There are three sampling techniques- ideal, natural and flat top sampling.
 In ideal sampling, pulses from the analog signal are sampled but cannot be easily implemented.
In natural sampling, a high speed switch is turned on for a small period when the sampling occurs. As a result we get a sequence of samples that still retains the shape of the analog signal.
In flat top sampling, we use circuits to create flat top samples.

