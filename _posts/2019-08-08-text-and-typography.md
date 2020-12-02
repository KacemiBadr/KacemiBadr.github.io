---
title: Maintaining the real time concept while designing the software application

author: Cotes Chung
date: 2019-08-08 11:33:00 +0800
categories: [Blogging, Demo]
tags: [typography]
---

# Maintaining the real time concept while designing the software application

![GitHub Logo]({{"/assets/img/sample/front.jfif"}})

## The real-time concept

The real-time concept in brief can be defined as 2 essential conditions:

- First, the results should be “Correct”, means acceptable in the sense of the reliability of outputs, this condition is necessary but not sufficient.

- If and only if the first condition is verified, we can discuss the accuracy of our system in terms of time “constraints=deadlines”

	"Output Y desired in the deadline T well-defined”

If the two conditions are verified, then the system can be called a Real-time system.

A real-time system is not necessarily a fast system, it should react just in time.

Remember that **providing the right answer is not enough, but rather providing it at the right time.**

![GitHub Logo]({{"/assets/img/sample/Embedded-System-and-Its-Real-Time-Applications-Image-4.jpg"}})

## Types of Real-Time Embedded Systems

We can’t mention the second condition without taking a look at the real-time systems types:

![GitHub Logo]({{"/assets/img/sample/218206_1_En_1_Fig3_HTML.png"}})

The main two types are:
- Soft: Tolerable but occasionally more flexible.
Soft RT constraints may occasionally be missed without troubling the integrity of the system.

- Hard: exceeding a deadline is categorically not accepted.
Hard RT timing constraints must be met absolutely, on penalty of catastrophic results include maximum interrupt latency and input-to-output delay.

![GitHub Logo]({{"/assets/img/sample/461004_1_De_8_Fig3_HTML.gif"}})

## ES restrictions

The developer has to be adapted to different situations, **knowing the constraints to which an ES is subjected.**

The software developed by the manufacturer is dedicated to well-known tasks.
The user doesn’t have to step in this software, that's what’s called **firmware** namely MP3, camera, scanner, and so on, whereas a computer is an open hardware platform it's up to you to do whatever you would like to do with.

In short, we have to differentiate between IT development and onboard development.
As we all know IT development doesn't care about the hardware side (Computer with 8GB Ram-large ROM, high battery performance.)

Rather in Embedded programming generally the memory spaces are very low, so it crucial to optimize the code and instructions, in the side of overheating risks that must be taken seriously, it means that frequencies in the GHz range or similar cannot be used, it’s better to choose frequencies of the order of a few hundred MHz.
To guarantee battery autonomy, losses must be decreased as much as possible.

There is another category of embedded systems which require more memory space because they host Linux OS, the widely used OS in several industries (automotive, aeronautics ...) of course with some adaptations "adding the Xenomai extension ", to add the real-time aspect to the OS, because at the base Linux doesn’t have this aspect (we’ll talk about this later), but Linux provides the concept of multitasking.

### Importance of multitasking

Keeping in mind that multitasking does not guarantee the RT condition of the application, its main purpose is to simplify the creation of our Real-time application.

Make it concrete for designing software based on ES we’re not going to dedicate a processor for each task (cost increased, further than that the problem of synchronizing processors one another comes up, so what we have to do is to implement a maximum of features in one calculator regarding the constraints of the system, nevertheless by sharing its calculation time between its several tasks, hence the interest of **multitasking**

## The real-time concept and the constraints of the entire system

The complexity is somehow increasing, we are dealing with 2 issues:
How to design a real-time system responding to the RT exigences such as deadlines and so on, and the hardware constraints.

![GitHub Logo](/images/Embedded-System.png)

### Ensuring the real-time aspect of your system

In critical cases, to be correct we must use a hardware clock either using a timer this one can be less accurate, or we simply could use an external entity RTC which maintains the exact time without any uncertainties.
As well as, we are allowed to use the mechanism of interruptions to know when to trigger priority actions.

Working with multitasking allows the facility of developing a professional application that's supposed to do several tasks (displaying, managing, internal communication between tasks, scheduling).

### Constraints especially for the small ES

Generally, these are linked with the frequency of the processor which wouldn’t be high for several reasons as we’ve mentioned before like overheating, weight, the autonomy of the battery, small memory space.

In this sense, the impact of these constraints can go further till the code concretely some compilers provide suggestions to optimize instructions in your code.

### What’s the process?

The software developer starts to develop the application (several software components) for realizing the services which will provide this system, after choosing the architecture of the material (microcontroller, processor, frequency, memory size) by the hardware engineers.
Of course, the software developer should optimize the code according to the chosen architecture.
Generally, the application is not easily portable to other hardware.

What is the component which helps to deal with this issue?
What is the OS? What are its approaches? 
What are the advantages and disadvantages of integrating it into your project?How to choose the suitable OS for your project? 

All these questions will be well detailed in the next blog.



*"the fundamentals aspects of real-time embedded software are often not well understood by designers in a design community which is traditionally hardware oriented …"*

																			[anonymous]

Thank you for your attention.
I am open to learning more from your questions.
