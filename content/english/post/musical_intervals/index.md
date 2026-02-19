---
title: Understanding Western Music by Its Intervals
description: Large musical data processing, jit-compilation and multiprocessing and lots of hours. 
slug: musical_intervals
date: 2024-09-16 00:00:00+0000
categories:
    - Project
tags:
    - Python
    - Music
weight: 1       # You can add weight to some posts to override the default sorting (date descending)
---

# Description
Ever since I curated my classical guitar dataset, I was curios about the note and interval distribution of it. How many instances of a particular note and interval sequence of N elements there exist?

The idea is fairly simple: I have bunch of MIDI files that I can easily load with [PrettyMIDI](https://craffel.github.io/pretty-midi/) (or [symusic](https://github.com/Yikai-Liao/symusic) as a much faster alternative) and count the occurrences of a set of numbers (intervals) using a sliding window. The thing is, doing this in python, with single core, length of the interval sequence N=5, with 10k MIDI samples with varying lengths takes a long time.

I initially thought it would be better to write this in C++ but because of some time constraints, I went for a jit+multiprocessing python implementation. This project helped me learn quite a lot of multiprocessing, jit compilation with numba and numpy's internals (like how to subclass a numpy array for additional functionalities).

# Some Results
For the following graphs, x axis is the index of the interval group while y axis is the number of occurrences. "Intervals of (-4.0, 4.0)" means, every interval from the list "-4.0, -3.5, -3.0, ..., 3.5, 4.0" is considered while creating interval groups. "n=3" means the length of the group is "3". All graphs are in *logarithmic scale*.

![(-4.0, 4.0) with n=3](-4.0_4.0_n=3_distribution_LOG.webp)

![(-4.0, 4.0) with n=4](-4.0_4.0_n=4_distribution_LOG.webp)

![(-12.0, 9.0) with n=2](-12.0_9.0_n=2_distribution_LOG.webp)

![(-12.0, 9.0) with n=3](-12.0_9.0_n=3_distribution_LOG.webp)

# Code
The code can be found [here](https://github.com/Fansesi/intervalic). Since then, I have became better at structuring my repositories, so excuse my past self :).
