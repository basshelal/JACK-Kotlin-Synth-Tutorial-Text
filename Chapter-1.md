# Chapter 1: Setup

In this chapter we setup our project by installing the required packages,
making sure JACK is working, and finally creating and setting up our Kotlin JVM project 
and running Hello World.

# Setting up JACK

**Note: this is only for GNU/Linux based systems,
other systems should consult the JACK website for installation
and setup instructions**

## Install JACK

Using your distribution's package manager, install JACK.

* On Debian based systems:

  `sudo apt install jackd2`

* On Arch based systems:

  `sudo pacman -S jack2`

## Install `qjackctl`

JACK on its own is just a server/backend, while we can control 
JACK using a terminal, it is easier to use a GUI to do so.

`qjackctl` is a commonly used GUI application that allows us to control JACK.

Using your distribution's package manager, install `qjackctl`.

* On Debian based systems:

  `sudo apt install qjackctl`

* On Arch based systems:

  `sudo pacman -S qjackctl`

## Install `a2jmidid`

Hardware MIDI keyboards send their events directly to ALSA and not to JACK,
`a2jmidid` bridges these MIDI events so that they can be usable by 
JACK applications.

Using your distribution's package manager, install `a2jmidid`.

* On Debian based systems:

  `sudo apt install a2jmidid`

* On Arch based systems:

  `a2jmidid` can be found in the AUR

  `sudo yay -S a2jmidid`

## Checking to see if it all works

No more packages are required, however, in order to ensure everything
works as expected, we need to try using a program that uses JACK, for this 
we will use `qsynth`, a sound sampler that uses JACK.

* On Debian based systems:

  `sudo apt install qsynth`

* On Arch based systems:

  `qsynth` can be found in the AUR

  `sudo yay -S qsynth`


**TODO** Explain how to set it all up with pics

### PulseAudio & JACK not cooperating

PulseAudio and JACK do not work nicely together, there are many ways around this
all can be found and explained on the Arch Wiki:

https://wiki.archlinux.org/index.php/PulseAudio/Examples#PulseAudio_through_JACK

In general though, we will only use JACK for our application and stop it when we're
not developing, thus we will not need both to work at the same time.

However, if you really need both to work at the same time,
this can be done with a PulseAudio module.
Read 
[here (Debian/Ubuntu)](https://askubuntu.com/questions/572120/how-to-use-jack-and-pulseaudio-alsa-at-the-same-time-on-the-same-audio-device) and 
[here (Arch)](https://wiki.archlinux.org/index.php/PulseAudio/Examples#PulseAudio_through_JACK) 
for more information.


# Creating our Kotlin JVM project

* Install IntelliJ IDEA if it is not already installed.

* Create a new Kotlin JVM project with "Gradle Kotlin" as our build system and 
  at least Java 11 as our JDK.

* *(Optional Reccomended)* Add Git and GitHub integration into our project using 
  IntelliJ's built in "Share to GitHub" tool.

* In our `build.gradle.kts` add JNAJack into our dependencies as follows:
  ```kotlin
  dependencies {
    implementation("org.jaudiolibs:jnajack:1.4.0")
  }
  ```

# Hello World

To ensure everything has worked, let's write a Hello World function and run it.

* Create a Kotlin file `App.kt`

* Create a `main` function as follows:
  ```kotlin
  fun main() {
    println("Hello World!")
  }
  ```

* Run the program,
  if everything worked correctly we should see "Hello World" in the console.

----

[Previous Chapter](./Chapter-0.md)

[Next Chapter](./Chapter-2.md)