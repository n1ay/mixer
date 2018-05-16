# Mixer

## Formal methods project: Mixer implementation in LOTOS

Specifications (informal):

 > A (blocking) Mixer is a handshake component with three 2-phase handshake ports, two passive and one active. The handshakes on the passive ports are "multiplexed" over the active port. That is, whenever the environment requests on a passive port and the Mixer is not "busy", the Mixer requests on the active port (becoming "busy"), and when the active port receives an acknowledge, the passive port that received the original request is also acknowledged (becoming "idle").
In contrast to a Non-Receptive Mixer, the environment of a Mixer need not guarantee mutual exclusion of the passive requests. A request on a passive port while the Mixer is "busy" (processing a request on the other passive port) is not lost but is handled when the Mixer becomes `idle' again.

 > When a Mixer receives requests on both passive ports, it will process exactly one of them (and delay the other). The specification leaves the choice open. Often there is a fairness requirement on this choice: if a choice situation arises "infinitely often" then both outputs are chosen "infinitely often".

![Mixer XDI graph](https://raw.githubusercontent.com/n1ay/mixer/master/mixer.jpg)

Specification source:[ http://edis.win.tue.nl/sys/mixer/index.html](http://edis.win.tue.nl/sys/mixer/index.html)
