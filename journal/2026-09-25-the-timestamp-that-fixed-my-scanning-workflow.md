# September 25, 2026 — The Little Timestamp Program

## A Very Small Problem

I scan documents using Simple Scan and send them into Paperless.

The workflow works.

But I wanted the scanned files to have a predictable filename containing
the date and time.

Something like:

    20260925_032419

I didn't want to type that every time.

That seemed like a good excuse to write a tiny program.

## What We Built

We created a small Python program called `timestamp.py`.

When I run:

    python3 ~/timestamp.py

it generates the current date and time in this format:

    YYYYMMDD_HHMMSS

and puts the result directly into the clipboard.

For example:

    20260925_032419

The program reports:

    Timestamp copied to clipboard: 20260925_032419

## Why I Like This One

There isn't anything particularly sophisticated about the program.

That's exactly why I like it.

It solves a problem I actually have.

I scan something, run the little program, and the timestamp is sitting
in the clipboard ready to use.

No web service.

No account.

No subscription.

No complicated application.

Just a tiny program that does one thing.

## The Larger Workflow

The little program is part of a much larger document workflow:

    Document
        ↓
    Simple Scan
        ↓
    Timestamp filename
        ↓
    Paperless
        ↓
    OCR
        ↓
    Searchable document

The timestamp program is only one small piece, but it removes one of
those annoying repetitive steps.

## The Lesson

I've discovered that some of the most satisfying things I've built
aren't necessarily the biggest programs.

Sometimes the best use of an afternoon is eliminating something that
annoys me every time I do it.

This is one of those projects.

### Project

**Timestamp filename helper**

### Status

**Working**

### Used with

- Simple Scan
- Paperless-ngx
- Linux Mint
