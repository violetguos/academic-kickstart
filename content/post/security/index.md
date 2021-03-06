+++
title = "Security Project: Exploiting OS using C and Assembly"
date = 2017-11-12T16:10:39-05:00
draft = false

# Authors. Comma separated list, e.g. `["Bob Smith", "David Jones"]`.
authors = []

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["os", "C", "assembly", "security"]
categories = ["os", "C", "assembly", "security", "systems"]

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["deep-learning"]` references
#   `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
# projects = ["internal-project"]

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
```
"\xeb\x2a\x5e\x89\x76\x08\xc6\x46\x07\x00\xc7\x46\x0c\x00\x00\x00"
"\x00\xb8\x0b\x00\x00\x00\x89\xf3\x8d\x4e\x08\x8d\x56\x0c\xcd\x80"
"\xb8\x01\x00\x00\x00\xbb\x00\x00\x00\x00\xcd\x80\xe8\xd1\xff\xff"
"\xff\x2f\x62\x69\x6e\x2f\x73\x68\x00\x89\xec\x5d\xc3"
```
Don't worry, as you are reading this post, your device is not compromised by this code. It has to be loaded into operating system kernel memory address in order to be exploited.

However, if it is loaded into operating system [https//en.wikipedia.org/wiki/Kernel_(operating_system)]kernel memory address, this assembly code (Ron's Code, the author Ron is the R in CLRS algorithm book) can get administrator access to everything on your OS!


## What is cryptography?

Cryptography allows users to apply a non-linear transformation on their data. User can encrypt their data with an 128-bit key. Unlike conventional passwords, which is generated by users, is short, and is simple to crack. Many passwords contain birthday, user's initials, important dates and places, etc. The key is random.

If you are interested in math, skip this note.

Note: random here is strictly defined as pseudo-random within a space of infinite dimension. In this case, the dimension is defined by how many bits the encryption key has.

Because cryptography is non-linear and is based on discrete log operations, it take 2^128 trials to crack a key, which is equivalent to 5.4 *10^18 years. For more math about cryptography, please refer to http://www-inst.eecs.berkeley.edu/~cs161/sp18/notes/3.4.signatures.pdf


## My Result
For objective 1:
- Implemented C language memory exploit to inject code in vulnerable program
- Implement HTML, Javascript, and SQL attack to program "phishing" on vulnerable  webpages

For objective 2:
- Implemented an encrypted communication network socket in OpenSSL in C
- Verified encryption using a cryptographic hash (HMAC and SHA1) in C
