# Chapter 0: Introduction

In this chapter we introduce the tutorial series by explaining the expected end result, what this even is
and why you should care, and the tools that we will use.

## Expected End Result

By the end we should have a program that plays back sine waves in response to key presses from a MIDI keyboard.

## What is this and why?

This is a programming tutorial series about basic audio programming aimed to help those who are interested 
in audio programming, specifically those who want to use the tools below rather than the commonly used ones (
C/C++, JUCE).

I made this series because I want to learn audio programming but found it annoying that all tutorials use C++
and JUCE with those written for the JVM being very few and of much lower quality.

C/C++ and JUCE are industry standard tools for audio programming and if you want use those, then there are 
excellent resources for that much better than this such as The Audio Programmer and the JUCE documentation.

However, the JVM is more than capable of handling the strict requirements of audio programming such as 
performance and latency while offering a much more pleasant programmer experience as well as a wider range 
of tools and libraries.

## Tools to Use

### Kotlin

Kotlin is a modern functional and object oriented language designed by JetBrains to run on the Java Virtual 
Machine (and other runtimes). It has full compatibility with Java APIs and libraries while adding many more 
features an improvements to the Java language.

This makes Kotlin an excellent alternative language for the modern Java developer since they can use the Java
APIs with a modern and more powerful language.

This is why we will be using Kotlin, however, the code and explanations keeps Java developers as the core 
audience and thus is still equally relevant to Java developers with no Kotlin experience.

### JACK

JACK is a cross-platform sound server API used by audio professionals and professional audio software for
its low latency performance with audio and MIDI data. JACK is cross platfrom but is more well known and used
in the UNIX world, however, instructions can be found online for installing it on other operating systems 
such as Windows.

The JACK server allows applications to communicate audio and MIDI data between one another in a manner similar
to a mixer across the computer. JACK compliant applications can send and receive this data through the server
and users can connect and disconnect applications and hardware to suit their desires.

We will use JACK for its high performance, extreme versatility and for the fact that it implements some key 
features for us very well (hardware communication).

However, in order to interact with JACK we need to have a way to communicate with it in the JVM realm, as JACK
is fundamentally a C library.

### JNAJack

JNAJack is a library written by Neil C Smith that binds the JACK C APIs into Java, allowing us to interact with 
JACK as if we were making the C calls ourselves.

This library translates the JACK C API into Java and will be a key part of this tutorial series, though most audio 
programming concepts are universal across APIs and languages.

We will use JNAJack to interact with JACK so that we can receive MIDI events from a keyboard and send audio data
to a speaker or sound card.

### Others

This tutorial is aimed more more towards using a GNU/Linux based operating system as I was learning this knowledge
with the intent of creating a sound sampler on a Raspberry Pi. Users running other operating systems should still 
be able to run and benefit from the code but some instructions may be slightly different on those systems, specifically
instructions related to JACK.

----

[Next Chapter](./Chapter-1.md)
