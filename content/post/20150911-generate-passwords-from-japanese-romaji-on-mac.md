---
title: Generate Passwords from Japanese Romaji Words on Mac
subtitle: Great for nihongo-learning Mac users
slug: generate-passwords-from-japanese-romaji-words-on-mac
banner: /img/Cogley-Banner-PapaBubble-Candy-2.jpg
date: 2015-09-11T15:20:15+09:00
publishdate: 2015-09-11T15:20:15+09:00
description: 'Mac users, easily generate passwords using Japanese romaji, a post by Rick Cogley.'
draft: 'false'
images:
  - /img/Cogley-Post-Genpass.png
  - /img/Cogley-Banner-PapaBubble-Candy-2.jpg
  - /img/rick-cogley-avatar-240x240.png
tags:
  - password
  - generate
  - clipboard
  - shell
  - script
  - genpass
  - security
topics:
  - Software
  - Tips
  - Productivity
  - SysAdmin
postsummary: I wanted an easy way to generate passwords at the Mac command line, and found a relatively simple solution which lets you type ``genpass`` and then simply copy-paste the password from your clipboard, to whatever password box is requesting one.
postsvg: icon-origami-fish
---

I wanted an easy way to generate passwords at the Mac command line, and found a relatively simple solution which lets you type ``genpass`` and then simply copy-paste the password from your clipboard, to whatever password box is requesting one.

<!--more-->

## Background

Searching for a password generator that I could run from Terminal in Mac, and also generate password strings from a dictionary file in which I had collected Japanese _romaji_ words, Japanese slang, and English, I tried several scripts and apps.

In the end I found [genpass](https://github.com/sh4t/genpass), a shell script coded by Justin Shattuck, to be closest to my needs.

## Development

I made some quick changes to the original script, which can be seen in my [jpassgen](https://github.com/RickCogley/jpassgen) repository at Github:

* Added a dictionary file which I had been creating, collecting some standard Japanese words and slang, and referenced the file in the code.
* Added the dictionary file to the existing ``makefile`` (noting you have to be careful to use tabs not spaces in a makefile), for easy installation.
* Increased the maximum default length of words to be selected from the dictionary file.
* Changed the pattern of the generated passwords.

## Installation

Here are the steps to install the script, if you are not familiar with ``git``.

1. Download the [latest zip](https://github.com/RickCogley/jpassgen/archive/master.zip), move it from your ``~/Downloads`` to a more permanent location, and unzip it. I have mine in ``~/dev/jpassgen``.
1. Install links to the scripts, in Terminal (assuming you installed in ``~/dev/jpassgen``):

{{< prism bash command-line >}}
cd ~/dev/jpassgen
ln -s ~/dev/jpassgen/genpass /usr/local/bin/genpass
sudo ln -s ~/dev/jpassgen/genpass-dict-jp.txt /usr/share/dict/genpass-dict-jp
Password: *****
{{< /prism >}}

You need to use ``sudo`` for the second ``ln`` command, because ``/usr/share/dict`` is a protected folder.

## Usage

{{< figure1 link="/img/Cogley-Post-Genpass.png" src="/img/Cogley-Post-Genpass.png" type="Screenshot" title="genpass being run in the OS X terminal" >}}

Since ``genpass`` is static linked into a folder that's in the system path, you can run it from whereever. Just type ``genpass`` in the Terminal and press enter:

{{< prism bash command-line >}}
genpass
95+Roten-MOKUREI-Tsukiyo#77
{{< /prism >}}

In addition to displaying it on the command line, the script will copy the password to the clipboard using ``pbcopy``, so you can then paste the password where you need to after running ``genpass``.

## Uninstall

To uninstall, just use ``rm`` on the links from Terminal:

{{< prism bash command-line >}}
rm /usr/local/bin/genpass
sudo rm /usr/share/dict/genpass-dict-jp.txt
{{< /prism >}}

## Tweaks

There are a few things you can do to tweak the script:

* Edit the pattern of the password, by editing the ``TEMPPASS=$(random_word)...`` line.
* Add words to the dictionary file, one per line.

## For Developers

If you have a development environment set up, you can use ``git clone`` to pull a copy of this repository, and then ``make install`` and ``make uninstall`` as well.

## Are These Passwords Secure?

You should note that passwords comprised of a couple of common words are _very_ strong & secure, and the passwords generated by this script are comparatively easy to remember.

As mentioned, you can edit the password pattern in the script, to make the generated passwords a bit more simple as well, if you prefer.

Enjoy!
