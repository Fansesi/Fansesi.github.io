---
title: List of Small Utilities that I Wrote
description: We all like utilities.
slug: utilities
date: 2024-10-08 00:00:00+0000
categories:
    - Project
tags:
    - Utilities
weight: 1       # You can add weight to some posts to override the default sorting (date descending)
---

# tiq
*t*erminal *i*mage *q*uote. A cli tool for displaying a quote associated with an image. I wanted to make it easier for an external displayer function to be used easily. Currently `viu` and `asci-image-converter` is supported. 

Looks cool:

TODO: add picture.

Link to [github](https://github.com/Fansesi/tiq).


# chillbg
There were cool posters and album pictures in our archive, suitable to use as a desktop background. The problem is, it looks a lot better if we add noise and border to the image. This is a small script that implements different noise patterns. 

An example:

![Beautiful Ghibli production](chillbg.webp)

Link to [github](https://github.com/Fansesi/chillbg).

# eargparse
*E*nhanced *argparse* experience. 

I hate handling file paths and naming files. Python has a good OOP flavored path module called `pathlib` that exposes such functionalities. I use it in almost every script (that does some IO). As a well known fact, `json` is extremely easy to use file format to hold structured data; especially in the context for research environment where we need to pass small datasets and experiment results quickly. Therefore, usually I read some kind of dataset with `--input`/`--dataset` flag and output single or multiple `.json` files which I get its name/path with `--output` flag. The thing is, there are many checks such as if the directory exists, if the full path is given or just the name, null check and set a default directory/file name etc. Moreover, while saving the data, we need to check if it is serializable (I have so many long runs failed, just because I forgot to serialize a numpy array...). I believe these can be done with an enhanced argument parsing.

Moreover, I would like to make python arguments savable to a special file/folder automatically and select amongst them via a tui. This can easily be done via python tui libraries such as `rich` but I don't want to use heavy external library. Maybe, I can write it with a compiled language and publish it that way. We'll see.

Link to [github](https://github.com/Fansesi/eargparse).

# wspace
A cool script to write text inside text with empty spaces. Much easier to show than tell:

![Darkest Dungeon logo, written with quotes from Darkest Dungeon.](wspace.webp)

Link to [github](https://github.com/Fansesi/wspace).
