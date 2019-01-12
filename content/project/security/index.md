+++
title = "Security Project: Exploiting OS using C and Assembly"
date = 2019-01-12T15:47:52-05:00
draft = false

# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = ["os", "C", "assembly", "security"]

# Project summary to display on homepage.
summary = ""

# Slides (optional).
#   Associate this page with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references
#   `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides = ""

# Optional external URL for project (replaces project detail page).
external_link = ""

# Links (optional).
url_pdf = ""
url_code = ""
url_dataset = ""
url_slides = ""
url_video = ""
url_poster = ""

# Custom links (optional).
#   Uncomment line below to enable. For multiple links, use the form `[{...}, {...}, {...}]`.
# url_custom = [{icon_pack = "fab", icon="twitter", name="Follow", url = "https://twitter.com"}]

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
[image]
  # Caption (optional)
  caption = ""

  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = ""  
+++

## Introduction

Cybersecurity is a branch of study in computer system and algorithm that aims to provide security to data and programs. The two types of work done are
1. Improve computer system to shield users from attackers
2. Encrypt data so that when the device is compromised, the attacker cannot decrypt user data

The course project is also designed to address these two objective
1. Given a vulnerable system, implement code to attack the system
2. Program effective encryption
I will provide a detailed explanation for both techniques

## What is code injection?

Think about how many times a webpage has asked for your input: username, password, your comment on your friend's profile picture. Your input will go into the webpage's server. When your friend's friend read your comment, it will be retrieved from the server, and loaded on their devices. What if your comment is not written in human language? What if it is
"\xeb\x2a\x5e\x89\x76\x08\xc6\x46\x07\x00\xc7\x46\x0c\x00\x00\x00" "\x00\xb8\x0b\x00\x00\x00\x89\xf3\x8d\x4e\x08\x8d\x56\x0c\xcd\x80" "\xb8\x01\x00\x00\x00\xbb\x00\x00\x00\x00\xcd\x80\xe8\xd1\xff\xff" "\xff\x2f\x62\x69\x6e\x2f\x73\x68\x00\x89\xec\x5d\xc3"

Don't worry, as you are reading this post, your device is not compromised by this code. It has to be loaded into operating system kernel memory address in order to be exploited.

However, if it is loaded into operating system [https//en.wikipedia.org/wiki/Kernel_(operating_system)]kernel memory address   

This is the computer code (Ron's Code, the author Ron is the R in CLRS algorithm book) to get administrator access to everything on your device!
