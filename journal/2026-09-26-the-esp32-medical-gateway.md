---
layout: default
title: The ESP32 Medical Gateway
permalink: /journal/the-esp32-medical-gateway/
---

# September 26, 2026 — The ESP32 Medical Gateway

## The Problem Got Bigger

Yesterday we got a small program working that could communicate with a
blood glucose meter.

That was satisfying.

But it also exposed a larger problem.

I have several computers I might want to use for recording medical
information. They don't all run the same operating system, and I have
several different kinds of medical devices.

I don't really want to build a Bluetooth application for every computer
and every medical device.

That seems backwards.

## A Different Approach

The idea that came to me was:

> What if the computers didn't have to talk to the medical devices at all?

Instead, put a small device in the middle.

Something like an ESP32 could act as a **medical-device gateway**.

The medical equipment would communicate with the gateway.

The gateway would deal with the device-specific communication.

The computers would communicate with the gateway using one consistent
interface.

Conceptually:

    Medical Devices
          |
          | Bluetooth LE
          |
        ESP32
       Gateway
          |
          | Wi-Fi / network
          |
    -----------------
    |       |       |
  Minty   Lucy   Other
  Linux  Windows Computers

## Why I Like the Idea

It separates two problems that don't really need to be coupled.

### The device side

The gateway knows how to communicate with:

- a blood glucose meter
- a blood pressure monitor
- a scale
- a thermometer
- a pulse oximeter
- other devices we may add later

### The computer side

The computer doesn't need to know how any of those devices work.

It simply asks the gateway for data.

That could make the Medical Vitals Tracker much easier to use on
different computers and operating systems.

## The Larger Goal

The eventual goal would be something like:

    Blood glucose meter
             |
    Blood pressure monitor
             |
          Scale
             |
       Pulse oximeter
             |
       Thermometer
             |
             v
          ESP32
          Gateway
             |
             v
       Standard data
             |
       ----------------
       |       |      |
      Linux  Windows  Other

The gateway becomes the common meeting point.

## But This Is Still an Idea

We haven't built this yet.

That's important.

Yesterday's blood glucose experiment was a working experiment.

The ESP32 gateway is a design idea that came out of that experiment.

The next step is to find out what the ESP32 can actually do with the
medical devices I have.

There will probably be some surprises.

There usually are.

## What Happens Next

The first experiment will be deliberately small.

Rather than trying to build the entire gateway at once, we'll see if an
ESP32 can discover and communicate with one of the medical devices.

If that works, we'll figure out what the data looks like.

Then we'll worry about how a computer should receive it.

Then, eventually, we'll connect it to the Medical Vitals Tracker.

One experiment at a time.

---

### Status

**Idea / early design**

### Related Projects

- Blood Glucose Meter
- Medical Vitals Tracker
- ESP32 experiments

### The Question

**Can one inexpensive little computer become the translator between my
medical devices and all the computers I want to use?**

That's what we're going to find out.
