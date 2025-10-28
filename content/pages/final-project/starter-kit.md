---
content_type: page
description: This section provides a kit to help students get started on their final
  project, including example code, exercises, and suggested project ideas.
draft: false
learning_resource_types:
- Projects
ocw_type: CourseSection
parent_title: Final Project
parent_type: CourseSection
parent_uid: 43e815cb-25bc-972c-4ad2-bcd5545036c5
title: Starter Kit
uid: 95373ee7-c310-c36e-3ac2-a00d9b23d8bf
---
Starting a C or C++ project from scratch can be a daunting task. If you're having trouble picking a software library, installing it on your system, and testing that it works, maybe you should try this Starter Kit!

This Starter Kit uses the {{% resource_link "d1b3d602-78c2-4ae4-ae9e-2235534d5367" "libpng" %}} library to render a series of random lines as a PNG image. The images look like this:

{{< resource uuid="16c065ed-11ff-2203-60ba-6190d4a8bc4d" >}}

The example code was written by skimming the section of the {{% resource_link "f0dbd4b2-5651-4ad7-93ba-57b2535d56bb" "libpng manual (PDF)" %}} on how to write PNG files. That manual also has a section on *reading* PNG files that you might find useful.

Use this kit to bootstrap your project and your imagination! The deadline looms, but there's still plenty of time to have fun making silly little PNG files!

### Source Code

{{% resource_link "c9d5adc7-5b85-7df4-4582-fc9ce339dd56" "lines (C)" %}}

### Compiling

`$ gcc -Wall -std=c99 lines.c -lpng -o lines`

The `-lpng` flag is short for `-l png`, which links the `png` library with your project to create the program.

### Running

`$ ./lines`

`./lines` creates a file called `out.png` in the current directory with some crazy graphics inside.

To view your image, you can use the `scp` command to copy it to your computer.

## Understand It

In the spirit of lab exercises, here are a few tasks to direct your focus to the parts of the program that matter:

1. Make the program take the filename as a command-line argument instead of hard-coding "`out.png`".
2. Tweak the values that are assigned to `r`, `g`, `b`, and `a` in the loop labeled "`draw a bunch of vertical lines`". The values range from 0 to 255. You should do this if you don't understand how pixels work. {{% resource_link "0966c70c-ff81-4587-9eb1-b4dc2f569e8e" "Wikipedia has a nice section on pixel colors" %}}.
3. Memory is allocated for storing the image data, but it's never freed. You should free it. You'll definitely need to do this if you use this code as a base for your project!
4. Tweak the program to draw horizontal lines instead of vertical ones.

## What Next?

Here are some concrete project ideas that you can implement and submit, roughly in order of increasing difficulty.

Whatever you do, **start (very) small** and add features as time allows. The secret to success here is to be unambitious at first.

### Plot a Graph

Instead of drawing lines of random height, allow users to plot a bar graph by providing numbers as program arguments or using `stdin`.

### Draw Shapes

Draw shapes of various colors. Start with squares, then move on to lines and circles if you have more time or people.

Optionally, convert the program to C++ and create a `Shape` parent class with sub-classes for each type of shape.

### Draw Text

Read text from `stdin` and draw it on the image by changing pixel colors in the patterns of (very simple) letters. Here's an example of how you might render 'hi':

{{< resource uuid="62024122-c82c-d8dd-dade-4ceb1b4e1f83" >}}

Instead of hard-coding how to draw each letter shape, I recommend storing them as strings or in a separate file, but this is not necessary.

### Invert an Image

Read a PNG image (with libpng), flip it upside-down, and save it as a new image.

### Game of Life

Implement the {{% resource_link "70ec92dc-5164-456c-bc2e-dd8828743f42" "Game of Life" %}} and render each time step as a separate PNG file.