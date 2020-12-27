# Chapter 2: Understanding JACK

TODO 27-Dec-20: Need to explain this better and clean it up,
But this is basically just key terms and theory before some exposure and
experimenting in the next chapter.

We explain some key terms of JACK by using qsynth and qjackctl.

Terms such as Ports, Connections and Clients and XRuns

Before proceeding any further I highly reccommend these 2 videos

https://www.youtube.com/watch?v=iaPW5v2ztEQ

https://www.youtube.com/watch?v=fEduGnD6ZKQ


## Key Terms

**The JACK server** is the daemon that manages everything within the JACK system.

JACK handles 2 types of data, MIDI like keyboards and sequencers and audio, like 
speakers and microphones.

The server also keeps and manages the global JACK settings such as sample rate and audio driver.

**A JACK client** is an application that registers itself to JACK, ready to send and receive data.

In order to actually listen for data the client needs to register JACK ports.

**A JACK Port** is a channel for which JACK clients can send or receive data, either MIDI or Audio.

A JACK Port can be either MIDI or Audio, and be either an input port (listening) or output port
(writing).

Still, JACK ports on their own do not do anything, it is only when they are connected will
they actually be useful.

**A JACK Connection** is a connection between ports that allows the flow of data from one 
client to another.

Connections can only be of the same JACK port type (MIDI, Audio) and opposing input or output.

## Example Scenarios

These terms are great but are of no use on their own without concrete examples and use cases

## What We'll be Building

In our case we'll be creating a JACK Client that listens to MIDI data and writes audio data.

That means a client with 2 ports:

* A MIDI Input port that will receive MIDI events from a keyboard
* An Audio Output port that will write audio data that can be played back by the soundcard



----

[Previous Chapter](./Chapter-1.md)

[Next Chapter](./Chapter-3.md)