# RC_TTL_MP
A Version of the RC1 that is not only TTL but also Multi Processor
Its basicly a version of [this]{https://github.com/Syntaxer04/RC1Computer} Computer, but with a few changes.

# THE CHANGES:
1. First thing is that this version has a lot of... featuer creep
....* It was supposed to be a version of the RC1 made in logisim evolution.
....* The Problem that I had was: "I put this much time into the logisim version, might as well improve on it"
2. It, as the name implies, is completly made of TTL logic chips. The Version I uploaded here is *mostly* buildable in real life
....* Some things logisim forbids can __absolutely__ be done in real hardware. It all boils down to the quality of the simulation.
....* The number of chips used in this version is __mental__. It is a completly unoptimized version of this design.
....* The bigger issue at hand would most likely be the power consumption. With some napkin math, the rough aproximation for One(1) CPU would be around, at most, 20 W. *__ONLY__* TTL 74 Series logic chips. Yikes.
Everything else is more or less the same thing. Even the Code should be identical to the Relay version. Only difference is the speed of the computer.
The numerical speed, i.e. the clock frequency is much, much higher than the relay version ever can support. This means that complex tasks suddenly become almost possible.
With the addition of the Arbiter and a second CPU, which can be activted through a command, the efficiency can get even higher. Only real issue is that the CPUs share a memory Bus.
So the Arbiter holds
