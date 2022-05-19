---
layout: post
title: Hyper CapsLock Unified
category: [Productivity]
tags: [keyboard, productivity]
description: Make CapsLock Consistently Great on MacOS and Windows!
unsplash: Z6SXt1v5tP8
---

## Hyper CapsLock Unified

[https://github.com/darkato42/Capslock](https://github.com/darkato42/Capslock)

I'm an user switching between my work PC and my personal Mac for different coding projects. My goal is to create configurations so I can have almost identical experiences when on MacOS and Windows, with or without my small external ANSI 60 keyboard.

### Highlights

Based on [Vonng/Capslock](https://github.com/Vonng/Capslock), some extra features are introduced:

* Consistent shortcut combinations between MacOS and Windows with different keyboard layouts.
* Duplicated key combos for a greater redundancy, less typo and ease of use.
* Simplified to have only one extra modifier, the left `Cmd` key, when `Hyper` is used.
* Removed hard to reach and less used key combinations for better ergonomics.
* Remapped the app launch keys accoding to their initials.
* Remapped frequent IDE functions to keys with close semantic meanings, such as `-` and `+` for **Fold** and **Unfold**.
* Remapped `#`, `£`, `` ` `` and `~`, so they are typed in consistent fashions across keyboard and OS.

### ANSI 60 Key and Keycap change

My external keyboard has a small ANSI 60 keys layout that is different from both my Mac and Windows laptop's UK ISO keyboards. It's reprogrammed with firmware to have the left modifier keys (`Ctrl`/`Win`/`Alt`) swapped to (`Ctrl_L`/`Alt`/`Ctrl_R`) to allow the same finger positions for the same Hyper shortcuts defined in both MacOS and Windows.

![ansi-60](/assets/images/posts/hyper-capslock/ansi-60-remapped.png)

------------------------

## CapsLock Enhancement Windows

The additional `Ctrl_R` key gives a close `⌘` experience when in Windows, While the original `Ctrl_L` key on the left makes Windows users feel at home by keeping Windows `Ctrl+` shortcuts unchanged.

Only the top `Hyper+` layer are kept for the middle `T`, `G`, `V` and `B` keys because they are difficult to reach for the `Hyper+Ctrl+` layer.

![hyper-win](/assets/images/posts/hyper-capslock/hyper-caps-lock-win.png)

------------------------

## CapsLock Enhancement Mac

Mac keyboard layout is designed slightly different than normal ANSI/ISO layouts. Its wider and slighly left moved `⌘` key is more ergonomics for usual `⌘`+`C` or `⌘`+`V`. And it allows slighly easier reach for `T`, `Y`, `G`, `V` and `B` keys when `CapsLock` and `⌘` are both pressed.

Use **Karabiner-Elements**'s simple rule to change `Ctrl_R` to `Cmd_L` for the external ANSI keyboard only. All other complex rules defined in the JSON file can then be loaded for consistent Hyper features.

![hyper-mac](/assets/images/posts/hyper-capslock/hyper-caps-lock-mac.png)

### Installation

It only takes two steps to enable Capslock on your Mac: Download & Enable

1. Download

   Download & Install [**Karabiner-Elements**](https://karabiner-elements.pqrs.org/).

   Following the wizard and grant required permissions (Settings - Security - Privacy)

2. Enable

   Open this [link](karabiner://karabiner/assets/complex_modifications/import?url=https://raw.githubusercontent.com/darkato42/Capslock/master/mac/capslock.json) with Safari. It will launch Karabiner-Elements and import the configuration.

   `karabiner://karabiner/assets/complex_modifications/import?url=https://raw.githubusercontent.com/darkato42/Capslock/master/mac/capslock.json`

   Click **Enable All** on pop-up dialog. It will affect immediately.

   You can now try moving cursor with `⇪ + h,j,k,l`.