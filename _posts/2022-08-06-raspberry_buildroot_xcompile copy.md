---
layout: post
title: Raspberry Pi cross-compile using Buildroot 
description: RPi x-compile
#image: assets/images/pic06.jpg
date: 2022-08-05 20:30:00
---

This article provides a simple but robust workflow to develop embedded applications using cross-compilation.
These notes are tailored to applications based on OpenCV and Qt5, that will run on a Raspberry Pi 4.  
Setting up the packages for computer vision and UI, as well as their dependencies, already make a compelling case for building an automated workflow that is simple and repeatable.

## Introduction

Developing applications for embedded systems means having to deal with hardware constraints that seriously hinder the possibility of local development (local here refers to the development done onto the embedded device itself).
A smarter alternative is instead to setup a development machine, where all the phases of the coding happen, that connects to the embedded device only to deploy and run the application after it has been built. 

This workflow is referred to as **cross-compilation** and to work properly it relies on two key aspects:

- cross-compilation **toolchain**, the set of tools (compiler, linker, etc.) available on the development machine (i.e. host) and needed to build the source code into binary files for the embedded device (target). Since the CPU architecture of the host and the target might not be the same, the standard toolchain of the host, which is designed to produce binaries for its own architecture, doesn't work for cross-compilation. Instead, for example, a development x86 machine used to develop for Raspberry will use a toolchain that runs on x86 but compiles for ARM.

- **target filesystem**, the set of libraries and other relevant resources representing the target environment of the embedded device in which the cross-compiled application will run. For example,

As described above, and when compared to local development, cross-compiling might seems more convoluted to set up and it might end up being more difficult to maintain.

## Goal

The overarching goal is to have a (mostly) automated and consistent way of generating

![My helpful screenshot](/assets/)

## State of the art

Current

## Buildroot

### Configuration

![My helpful screenshot](/assets/images/img1.jpeg)

### Generate SDK

``` bash
Target packages -> Network -> 
```

## Host computer

adfgervbejhrbjtvhberjt

## Heading 2c

rejktbvyejr  ecrhtnwer  rnckuer ucwntke
