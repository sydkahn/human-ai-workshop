---
layout: default
title: The Medical Gateway I Didn't Build
permalink: /journal/the-medical-gateway-i-didnt-build/
---

# The Medical Gateway That I Decided Not to Build

I had a plan.

It was a perfectly reasonable plan, which should have been my first warning.

I have several Bluetooth medical devices around the house — a blood glucose meter, a blood-pressure monitor, a scale, a thermometer, a pulse oximeter and probably a few other things I've forgotten about.

My thought was: why not build a little ESP32 device that sits between all of them and my computers?

The ESP32 would talk Bluetooth LE to the medical devices, collect the readings, and then send the results to my medical-vitals application. One little gateway. Any computer could talk to it. No need to write Bluetooth code for Linux, Windows and everything else separately.

It sounded elegant.

So I started with the Zewa UAM-880 blood-pressure monitor.

And we actually got surprisingly far.

The ESP32-C6 could see the monitor advertising over Bluetooth. We eventually identified the device as:

```text
UAM-880E05AE417
```

We found its Bluetooth address. We watched it appear when the monitor finished taking a blood-pressure reading. We could see the Bluetooth activity.

But getting from *"I can see the device"* to *"I can reliably retrieve the blood-pressure reading"* turned into a completely different problem.

The monitor apparently has a very short window after taking a measurement when it attempts to send its data. That meant discovering the right GATT services and characteristics, figuring out how the device expects to communicate, and then figuring out how to reproduce what its phone application already does.

In other words, I was beginning to reverse-engineer a proprietary medical-device Bluetooth protocol.

That's when I had what may be the most important engineering realization of the entire project.

**My phone already does this.**

There is an app on my phone that has been happily collecting the readings from the Zewa. It can retain the recent measurements and export them, including CSV.

And, as I started thinking about it, I realized that every medical device I was considering already has a phone application.

So I have a choice.

I can spend the next several days reverse-engineering Bluetooth protocols, chasing undocumented GATT characteristics, figuring out why a device disconnects after 300 milliseconds, and generally making my life considerably more complicated...

Or I can open the app.

Sometimes engineering means knowing when to stop engineering.

### So the gateway is going on the shelf.

At least for now.

I'm still interested in the ESP32 medical gateway idea. There may be devices that don't have useful applications, or situations where a generic local gateway would be genuinely useful.

And the work wasn't wasted.

I learned how the ESP32-C6 handles BLE scanning. I got MicroPython running on it. I learned how BLE advertisements are structured. I found the Zewa and watched it announce itself. I learned a little more about the difference between discovering a Bluetooth device and actually communicating with it.

But the immediate goal — getting my blood-pressure readings into my computer — already has a solution.

It's called a phone.

Sometimes the best piece of code you can write is the piece you decide not to write.

**Today's lesson from the home lab:**

> Just because you can build it doesn't mean you should.

And tomorrow I'll probably find something else that needs building anyway.
