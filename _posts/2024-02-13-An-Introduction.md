---
layout: post
title: An introduction
---

Hi! This is the development blog for [Acheron](https://acheron.atropos.se) where I, [Sebastian](mailto:acheron@atropos.se), will document the process of the making of the MISCON systems we will use at Acheron. This is mostly for our own benefit, but there might be someone out there in the wider larp community that might find this stuff interesting down the line, so here we go! Please note that everything on this blog is in various stages of conceptualization or testing, and may not reflect the actual look, feel and mechanics once we reach actual larp time.

Let's start with **SENSOR**, the first system in the normal "game loop" that initiates work for everyone else. I need to very briefly explain the some lore before we dive into how the system works.

## SURNET
![SURNET and sensors](/images/surnet.gif "SURNET and sensors")

The surface of the Earth is a hostile place, as there are countless alien machines roaming there - some of which are actively searching for threats to neutralize. The alien machines not only emit their own radio signals (which are often routine check-ins or coordination messages), some of them also listen to and react to unknown electromagnetic activity (such as radio transmissions) and quite easily triangulate and attack those foolish enough to transmit on the surface.

In order to minimize the risk of detection and triangulation while still retaining the possibility of communicating with the surface operators Haven has built the *Surface Net* (**SURNET**) - a network of small, solar cell powered devices that receives and transmits radio signals in a very narrow cone to the next relay in the net. This greatly reduces the amount of electromagnetic radiation being emitted on the surface, and the alien machines must in effect happen to be positioned exactly between two relays as a signal is being transmitted in order to catch it. A signal being transmitted from point A might be routed randomly through a dozen or more of these small surface relays before reaching the receiver at point B.

SURNET is used not only for communication between SURFOPS teams and Haven or the Outposts, but also to constantly forward signals from the sensors that feed into the SENSOR station at MISCON.

## Sensors and enemy signals

Here and there, surface teams have placed omnidirectional sensors, that pick up enemy radio transmissions and relay it, using SURNET, back to the SENSOR station in MISCON. This is called an *intercept*, and every signal contains the following information:

- Primary sensor (the sensor that had the strongest signal intercepted, often meaning it was closest to the source of the transmission)
- Secondary sensor (the sensor with the next strongest signal intercept)
- Bearing to source. The direction (using 360 degrees) from the sensors to the source of the signal. If one draws a line from both the primary and the secondary sensor using their respective bearings, one can find the position of the signal emitter (where the two bearing lines intersect).
- Velocity. A doppler shift analysis of the received signal will be translated into a rough estimation of the velocity of the machine emitting a signal (with 0 being "stationary").
- Heading. Also by analysing the drift of signal strength during a transmission we can roughly approximate the direction the emitting machine was heading (if any).
- The raw signal itself. This is a recording of the actual signal sent, and can be presented both visually (using a spectrogram) or aurally (by listening to the sound through speakers or headphones). This is used to find specific "fingerprints" in the signal to help the operator determine what type of machine sent the message.
- Parsed signal message. Each signal is essentially a message being transmitted. The scientists at Haven have only just begun to be able to decipher the alien language model, enough to pick out a few "words" in the messages here and there. This part of the game mechanics is also a pattern-matching exercise where players will be looking at chunks of random characters in order to find the few sequences that we have a translation for.

## The SENSOR station
![image](/images/sensor.jpg)

So, this is the computer interface that the SENSOR operators will be spending most of their time in (remember, this is a work in progress). The main view has two windows - one contains the list of surface sensors this station is connected to (and their current status - if one is inactive it might mean it has been destroyed or is out of power, often requiring a SURFOPS team to go out and inspect or replace it), and the other window containing a list of all intercepted alien transmissions within range of the sensors.

Most actions in MISCON start at this station, as new (unidentified) signals are intercepted and displayed here. The SENSOR operators will, upon a new signal, notify the commander, then start filling out the contact slip: time of interception, designation, the primary and secondary sensor bearings, velocity and heading, and then pass that slip to SIGINT for classification (they will then pass the slip over to GEOLOC who will do the positional fix, and after that CRYPT works on deciphering the message).

This is the routine - there might be the rare occasion when something out of the ordinary happens, but that will hopefully be self-explanatory if and when it happens :)

![image](/images/contact_slip.jpg)
