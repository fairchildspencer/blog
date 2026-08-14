---
title: The Perfect Prompt
description: Finding an actual use case for AI in my personal coding workflow
date: 2024-08-20 14:30
---

# The Perfect Prompt

I have finally found an actual use case for LLM assistance in programming. 

### Background
Before I get into it, let me start by saying that I have used AI assistance for programming on and off since 2021. I was on the Copilot beta, I remember turning it on for the first time and saying "Huh this is sort of interesting". Then I turned it off for the next couple of years until all of the AI hype began. 

I have found AI assistance to range from mildly helpful to obnoxiously useless. It has gotten better over the years, I remember all of my coworkers crowding around my computer and laughing at the comments and variable names generated in Chinese and Russian that Copilot would spit out in its earlier phases. It is more context-aware these days, but I still find myself scratching my head at all the people on X claiming that they don't even code anymore. My personal experience has been very far from that, most of the time I find that it gets in the way more than anything.

This past weekend I found myself once again tackling a problem I have been working on for a month or two. I am writing a program to interface with an E-paper display that will sit on my desk and display a bunch of fun widgets and images. All of the driver code provided by the company that manufactures the display is written in either C or Python. I wrote the first proof of concept for my little desktop display in Python and it worked pretty well, but I just don't enjoy writing Python that much. As this is a passion project I decided that I would give it a shot in Go. It seemed pretty straightforward, all I had to do was re-write one of the provided drivers in Go and then I was of to the races.

### Depression and Regret
After four or five complete rewrites of the Go driver, I was baffled. I had burned through almost every available GPIO and SPI library I could find on GitHub. There were even a couple of people who had attempted to write drivers for my exact display in Go but not a single one worked. All of the libraries I tried had been written 5-6 years ago and seemed to not work with the newer generation of Raspberry Pis. I even tried writing everything from scratch as well as I could but to no avail. At this point, I was either going to just give up and use Python, or try and use cgo to wrap the C driver code (which I was not very excited about doing). On a whim, I decided to crack open Claude and see if I could get any help sorting out these libraries.

I loaded the Python driver file into Claude and gave it some basic context as to what I was trying to do. I asked it if it could help me convert that Python driver and voila! It spat out a whole file of (what appeared to be) pretty dang good driver code. It ended up having a few minor syntax errors and a logical issue, but overall it was close! I was impressed at how it actually found a usable GPIO library for Go and implemented it cleanly. I chatted back and forth with it a couple more times and came out with a fully functioning driver written in Go.

### Life Reflection
At this point, I began to question everything. Up until this point I had been unimpressed if not skeptical of AI. Are all of the AI hype bros right? Has this just been a skill issue? After a few days of thinking I finally came to a conclusion as to why I think it worked so well in this instance.

I believe that the reason I got such effective results from my chat with Claude mostly had to do with the type of problem I had. 

My problem was:
- Well defined
- Small in scope
- Had an actual example to work from

### Conclusion
My problem was very straightforward, take this functioning Python code and convert it into Go. The LLM had a very specific set of requirements, it had to write less than 100 lines of code and could use a working example to start from. With all of these pieces in place, it was pretty trivial for it to just spit out a driver that pretty closely resembled what I was looking for. I don't think I will be using AI in my daily workflow anytime soon, but at least I finally found some semblance of use for it.

This experience has opened my eyes to an actual use of AI in my personal workflow. Next time I have a small, well-defined problem that could be a little tricky, I'll throw it in Claude's direction and see what he thinks.
