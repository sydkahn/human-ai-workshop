---
layout: post
title: "Photo Explorer: Teaching AI to Find the People in My Photographs"
permalink: /journal/photo-explorer/
---

# Photo Explorer: Teaching AI to Find the People in My Photographs

I've accumulated photographs for decades. They're scattered across hard drives, stored in folders, and mixed together with all the other digital debris that accumulates when you keep computers running for a long time.

Finding a particular photograph can be surprisingly difficult.

I might remember the person in a picture, approximately when it was taken, or the occasion it came from. But I don't necessarily remember which drive holds it, what I called the file, or which folder I put it in.

That got me thinking: what if I could search my collection by the people in the pictures?

## Let the computer do the tedious work

Modern face-recognition models can detect faces in photographs and compare them mathematically. With the right combination of tools, it's possible to group similar faces together without sending the pictures to a cloud service.

The idea is straightforward.

A computer scans the photographs, detects faces, and generates a numerical representation of each one. It then compares those representations and suggests which faces might belong to the same person.

I would review the suggested groups and supply the names.

The interesting challenge is making this work with a real family archive, not just a collection of recent digital photographs. Faces change over time. Older photographs may be scanned prints, faded, blurry, or full of people standing at a distance.

I want to find out how well a compact, locally running model can handle those conditions.

## A home-server project

I'm considering building Photo Explorer as a Python application running on my Proxmox home server.

The server would catalog the photographs and perform the AI processing. Computers throughout the house could access the resulting library through a web browser.

A Smart TV interface would be a natural extension: browse by person, select a year, and put family photographs on the big screen.

I'd also like to combine face recognition with duplicate detection, making it easier to find both the people and the pictures buried in a large archive.

The original photographs would remain untouched. The application would maintain its own database of file locations, metadata, face groupings, and thumbnails.

## Working with AI

This project is an experiment in **human-AI collaboration**.

I'm using **ChatGPT** to help explore the architecture, evaluate technical options, develop the software specification, and plan the implementation.

I plan to use **OpenCode** as my coding assistant when implementation begins.

I'm directing the project, making the design decisions, reviewing the results, and learning along the way.

The goal isn't to pretend that AI can build perfect software on its own. It's to discover what a person working alongside AI can accomplish, where the tools help, and where human judgment remains essential.

I'll document the process, including mistakes, discoveries, and changes of direction, as the project develops.

## Designing before coding

Rather than asking an AI coding assistant to generate an entire application in one go, I'm starting with a software specification.

The proposed design uses Python, FastAPI, OpenCV, lightweight face-recognition models, and SQLite. Those are starting choices, not sacred commitments. I'd rather discover a better approach now than build the wrong thing efficiently.

I've published the initial specification on GitHub and would welcome comments from people with experience in computer vision, Python, self-hosted applications, or photo management.

**Read the specification and join the discussion:**

- [Photo Explorer project on GitHub](https://github.com/sydkahn/photo-explorer)
- [Read the software specification](https://github.com/sydkahn/photo-explorer/blob/main/SPECIFICATION.md)
- [Discuss the design](https://github.com/sydkahn/photo-explorer/discussions)

I'm especially interested in whether the proposed face-recognition models are a good fit, how to handle photographs spanning several decades, and what pitfalls I should anticipate.

This is an experiment in building something useful with local AI, a home lab, and a little help from an AI coding assistant.

The first goal isn't to build the perfect photo application. It's to find out whether the idea works well enough to be worth building.

More to come.
