# person.json

This repository contains the formal specification for `person.json` files.

## What's a `person.json` file?

`person.json` files are small JSON files that contain a person's schedule of events for a given week. They associate a number of events with a given name. 

## What can I do with a `person.json` file?

Anything you like!

The original intent of `person.json` files was to be an input to [Schedule Lynx](https://schedule-lynx.streamlit.app) tool, though. Schedule Lynx allows the user to upload multiple `person.json` files and recieve a .png containing all of the uploaded schedules, side by side, in different (and customizeable!) colors.

## How can I make a `person.json` file?

1. Open a text editor and start typing, being careful to follow the specification. Save your file with the extension ".json". 

2. I made a nice GUI for any non-technical users out there. It's available [here](https://schedule-lynx-assistant.streamlit.app).

## How can I parse a `person.json` file?

The `person.json` specification is a strict subset of JSON, which is itself a strict subset of YAML. Any library that can read JSON or YAML files will happily read `person.json` files too! (Python has a really nice `json` library that works quite well)

## Can I use this specification in my own applications?

Yes! Please! This is a completely free, open-source tool for all the world to use if anyone finds it useful.

## I have a super technical question about what's allowed and what isn't!

My answer is: does it work in JSON? If so, you're fine. If not, your file will likely break in Schedule Lynx. 

## Can I help extend this specification?

Yes! Open an issue and I'll get back to you asap :)
