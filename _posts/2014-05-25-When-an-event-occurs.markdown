---
layout: post
title:  "When an event occurs"
date:   2014-05-25 20:27:40
---

No problem. It's a very common misconception (which is why it drives me nuts, haha). You can sort of see why; if your electronic gizmo is still working you're hardly going to assume it's suffered any ESD events.

There are entire companies who won't take it seriously. They buy some of the equipment such as mats and wrist straps (two of the best things you can use), but then nobody on the assembly floor will use them. Then they complain to us when 10% of their product has failed a soak test.

As you likely know, an ESD event is generally a problem for semiconductor ICs above all else, and places where similar conditions exist (such as the wafer-thin ITO conductive meshes inside TFT display panels).

When an event occurs, the charge surges into the IC. The amount of energy transferred is tiny, but the voltage is sufficiently high (generally in hundreds of volts, if not thousands) that there is almost no impediment to its path through the chip. To us, the discharge might not even be felt, but on the scale of a modern day IC, it's basically a lightening strike. The filament thin circuitry etched into the IC will for the briefest instant light up like a blowing fuse, as the material is vaporised by the passing energy. But the damage won't necessarily be complete (this is the part people struggle with). Bits of it may be spattered about the vicinity of the affected circuit, or vaporised altogether, but the circuit may still be complete.

![It might look a bit like this](http://i.imgur.com/zTrr63p.jpg)
[It might look a bit like this](http://i.imgur.com/zTrr63p.jpg) if you were to peel open the chip (and had a scanning electron microscope attached to your face). Nice and melty.

If that circuit is still complete, then its performance has changed; firstly, it is very likely of slightly higher resistance due to there being less conductive material along the signal path. This can be enough to cause stability issues if the affected chip is, say, part of a stick of RAM performing high-speed communication, because the parameters of the carefully balanced circuit are no longer as expected. Problems like this can affect signalling and timing between ICs. In this scenario, the circuit may operate but will be forever underperforming or unstable.

Secondly, its current-carrying capability has therefore reduced. If that capability is important for the circuit's performance, you can now expect the kind of problems that follow underpowered electronics; browning out under stress, for instance. In this scenario it is also quite likely that the chip will eventually fail, because the current-carrying pathway is being pushed beyond its new, reduced capability.

Many ICs these days come with some rudimentary level of protection (clamping diodes which dump residual charge to ground before the rest of the chip can be exposed) but it often isn't enough as is more useful for softer voltage spikes associated with things like connecting and disconnecting cables and peripherals (wouldn't be any good if your computer/tablet/phone broke every time you went to plug it into something).

The above information leads to some interesting conclusions. For example, the static problem *is getting worse*. Chips are getting smaller, so their ability to survive an ESD event is reduced, much like how thinner fuse wire will pop under less current. It's actually bad enough that our newer equipment must monitor workstations using lower voltages than the older stuff, because the old stuff is actually beyond the minimum threshold for some of the electronics on the market today.

Another example: we've had customers damaging displays a lot, these last few years. Displays contain wafer thin conductive traces (they must be transparent, of course!) in order to drive the crystals. Our customers were popping these ITO traces on the displays during soak tests and winding up with white or coloured lines (sometimes up to a week or more after first powering up), because they were damaged by ESD during assembly.


EDIT: some common questions/issues answered:

*1) "It's never happened to me/I've handled loads of electronic without ESD protection and had no problems."*

You don't know that. You might have been lucky in a favourable environment - this involves the air around you (humidity), the work surfaces, your choice of clothing and even what your own skin is like. Maybe everything was perfect and you were constantly lucky.
 
Alternatively, you might well have been doing damage and simply not noticed. Either because you didn't associate future misbehaviour of your gadgetry with that one time you took it apart, or because you don't use it in a way which exposes the damage (temps not too high, not pushing it too hard, not using that port or socket, etc etc).

At least if you take precautions against ESD, you can eliminate that variable entirely. If you don't, it might be OK... but you'll never be sure.

*2) Regarding ESD protection.* Think of your entire environment as a circuit. You want to ensure everything is at the same potential to stop charge from flowing anywhere. If you only ground one thing (like your PC), you are if anything making the ESD situation worse as now it has a place to go. This means you, your work surface, your tools, your electronics... everything must be at zero potential. A good start is an ESD wrist band and an antistatic mat. That's enough to ensure good coverage of you and your environment, so long as your tools can sit on the mat with your computer and any parts which you're about to install. 

*3) Regarding grounding.* You CAN'T USE DIRECT CONNECTION TO GROUND. That's NOT protecting you. That's making it WORSE. You just provided a low-resistance path for a violent discharge. Antistatic equipment uses very high resistances to pull charge away briskly, but *gently*, typically in the megaohm and above range. Plugging in your PC to a grounded wall socket and holding the case with your hand is BAD.

*4) So what makes a good set up for home? (already posted this, put here for visibility)*

Officially, the simplest solution is a proper antistatic wristband and antistatic mat big enough for your computer and any new/old bits and bobs and tools to sit on while working.

Bonus if it's somewhat humid and not too dry (dry air = bad, it raises the resistance of all the surfaces in your environment and can lead to bigger ESD events from greater static buildup).

Cotton clothes are advised. Avoid plasticy, synthetic fabrics.

Be mindful of the static potential differences between separate objects in your work environment. You're grounded through a proper strap and so is your computer on the mat, but that graphics card you just unpacked... maybe it needs to sit on the antistatic mat for a moment just to bring it in line with the rest of the environment. Also, did you stand your computer upright on the mat? If you have rubber or plastic case feet, your computer isn't actually grounding on the mat properly.

To hook it all up: Both your wristband and your mat should be connected to ground. Do not connect the wristband to ground through the mat. The mat is a resistor in and of itself, and the wristband will have suitable resistance built into its cable - if you connect them in series, the wristband will no longer work (resistance too high). You can use extension cords/leads/wires if you need to reach a ground point for your wrist strap.

There's more to it in that (so much more) but for a home user, that will do, and the tools you need are really cheap.

