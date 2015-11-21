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
![untitled123](https://cloud.githubusercontent.com/assets/8260656/11318150/1a158774-906c-11e5-8879-5a667f3e693e.png)

2.3.2  Quantization
The result of sampling is a series of pulses with amplitude values between the maximum and minimum values of the signal. But then the set of amplitudes within this range can take infinite non integral values. Hence the sampled wave has to be quantized.
Quantization basically deals with mapping a large set of inputs values to a smaller set of outputs – similar to rounding off. And the error caused due to this rounding off is called quantization error.
![image](https://cloud.githubusercontent.com/assets/8260656/11318153/36154a90-906c-11e5-8c25-bc0a3b64890b.png)

2.3.3 Encoding 
Encoding is the process of assigning binary values to the quantization code.

![untitled123](https://cloud.githubusercontent.com/assets/8260656/11318156/5bdbaf80-906c-11e5-9669-a9f69f269a7c.png)
2.4 Voice recognition
The two common approaches for voice recognition are template matching and feature analysis.
 To determine the "meaning" of this voice input, the computer attempts to match the input with a digitized voice sample, or template, that has a known meaning.
 Since each user’s voice is different the program cannot possibly contain a template for each potential user. Hence the program has to be first “trained” to the new voice before it can be recognized. The user is made to speak a printed word or phrase and the program computes a set of statistical sample values and the average sample value is selected. Such a system is said to be speaker dependent.
Another general way is to use feature analysis which leads to speaker independent voice recognition. Instead of matching the actual voice input and previously stored voice template, this method processes the voice input string using Fourier Transforms and linear predictive coding and find similarities between the input and stored template. These similarities exist for a range of speakers and hence the program doesn’t have to be trained separately for each speaker.
 Recognition accuracy for speaker independent systems is less compared to speaker dependent ones.
2.5 Analysis
 
![untitled123](https://cloud.githubusercontent.com/assets/8260656/11318160/84eb4bce-906c-11e5-98a3-e7a86b799f45.png)

# 3. Voice Controlled Wheelchair

![untitled123](https://cloud.githubusercontent.com/assets/8260656/11318166/ab23cd3e-906c-11e5-9d9c-5083b11f8877.png)
3.1 Control System
The control system makes use of EasyVR,  a voice recognition module and Arduino Uno, a microcontroller board based on ATmega328. It is powered by a 9V battery. It is programmed to drive two motors depending on the voice command.
  
Command				Action
1.  Chair Go	   			          Drives the wheelchair in set direction                                                                   2.  Chair Left				           Directs the wheelchair towards left                                                       
2.  3. Chair Right				       Directs the wheelchair towards right                                                           
3.  4. Chair Stop				        Stops all the above actions 


The control system takes these four commands as input and accordingly drives 2 motors. The first motor sets the directionality while the second drives the wheelchair in the set direction.  

## 3.2 Implementation of the control system
 The implementation of the control system is done using Arduino Uno, EasyVR, Motor drive and two stepper motors.
## 3.3 Components
(i)	Arduino Uno
(ii)	EasyVR
(iii)	Motor Driver
(iv)	Jumper wires
(v)	9V Battery


Microphone specifications
Load Impedance 2.2K
Operating Voltage 3V
Sensitivity -38dB (0dB=1V/Pa  at 1KHz)
If you use a microphone with different specifications the recognition accuracy may be adversely  affected. No other kind of microphone is supported by the EasyVR.

Speech Recognition using EasyVR
The recognition function of the EasyVR works on a single group at a time, so that users need to group together all the commands that they want to be able to use at the same time. 
When EasyVR Commander connects to the module, it reads back all the user-defined commands and groups, which are stored into the EasyVR module non-volatile memory.

3.3.3 Motor Driver
L298	(Dual Full Bridge Driver)

The L298 is an integrated monolithic circuit in a 15-lead Multiwatt and PowerSO20 packages. It is a high voltage, high current dual full-bridge driver designed to accept standard TTL logic levels and drive inductive loads such as relays, solenoids, DC and stepping motors. Two enable inputs are provided to enable or disable the device independently of the input signals. The emitters of the lower transistors of each bridge are connected together and the corresponding external terminal can be used for the connection of an external sensing resistor. An additional supply input is provided so that the logic works at a lower voltage.




