---
layout: default
title: The Blood Glucose Meter
permalink: /journal/the-blood-glucose-meter/
---

# September 25, 2026 — The Blood Glucose Meter

## The Problem

I wanted to get the readings from my Accu-Chek Guide Me blood glucose
meter into my computer.

The meter already knows how to communicate electronically. The problem
is that the normal software ecosystem is not particularly interested in
Linux.

My main computer is an old iMac with **Linux Mint** installed. I call it **Minty**.

So naturally, the first question became:

> Can we get the meter talking directly to Minty?

## The Experiment

The answer turned out to be yes.

We found an existing open-source program called `accuchek` and got it
working with the Guide Me's USB connection.

The meter appeared as USB device:

    173a:21d6

The program uses libusb and the Roche meter protocol to communicate with
the device.

It was able to connect to the meter, retrieve its stored data, decode
the glucose reading, acknowledge the data, and release the device.

## The Moment It Worked

The program returned JSON containing an actual glucose reading:

```json
{
  "id": 0,
  "epoch": 1790350560,
  "timestamp": "2026/09/25 10:36",
  "mg/dL": 105,
  "mmol/L": 5.833333
}
