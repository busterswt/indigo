---
title: "Sapient Technologies Quad-Port Serial Expansion Card for the Apple Lisa"
layout: post
image: /assets/images/2018-08-14-sapient-qpb/lisalogo.png
headerImage: true
tag:
- apple
- lisa
- vintage
- serial
- xenix
- uniplus
- unix
category: blog
blog: true
published: true
author: jamesdenton
description: Hands-on with the Sapient Technologies quad-port serial expansion card for the Apple Lisa

---

The Lisa computer holds a special place in Apple lore and in the hearts of enthusiasts and collectors around the world. My interest in the Apple Lisa has led me to people and communities looking to breath new life into the vintage system. This is nothing new, of course. The platform saw CPU and software upgrades introduced years after it was discontinued, and folks brought out hard disk replacements in the early 2000's to replace aging Apple ProFile and Widget drives. 
<!--more-->

So, when I found out that a quad-port serial expansion card was in the works I had to know more. John Woodall from VintageMicros explained that the new quad-port board, or QPB, was "part of a two-year effort to build a modernized version of a serial card for the Apple Lisa that was manufactured and sold by Tecmar[^1]." Todd Meyer, vintage Apple hardware enthusiast and Founder of Sapient Technologies, funded the endeavor as part of the [**Lisa Hardware Preservation Project**](https://www.callapple.org/hardware/the-apple-lisa-hardware-conservation-project/) with help from the following Lisa experts and devotees:

- James MacPhail -- Design Engineering
- Rick Ragnini -- Quality Engineering and Testing
- John Woodall -- Parts Procurement, Assembly and Testing

The original quad-port serial expansion card was to be used with the Microsoft/SCO XENIX operating system and later, UniSoft's UniPlus+ UNIX, rather than the Lisa Office System. At the time of its release, UNIX had been around for over a decade and was mostly used on large mainframes and minicomputers like the PDP and VAX series of machines. In the early 80's, as microcomputers became more powerful, you could find vendors porting UNIX and UNIX-based operating systems like XENIX to less-expensive systems like the Apple Lisa and other 68000 or 8086-based systems, among others. Needless to say, I was intrigued.

After talking with John, I received a pre-production sample of the card and spent a few months putting together a guide. This exercise involved installing both Microsoft XENIX 3.0 and UniSoft UniPlus+ UNIX V and working out the post-installation kinks. The guide quickly balooned to over 100 pages and includes information on basic administrative tasks, printing, and more, within the XENIX and UNIX operating systems. It even includes information on interfacing with terminal emulators running on new and vintage Macs and PCs running Windows. Instructions for configuring UUCP on High Sierra are included for those willing to walk on the wild side. 

![Hub](/assets/images/2018-08-14-sapient-qpb/hub.png)

Thanks to Sapient Technologies, this fresh look on a unique and difficult-to-obtain expansion card has been made available to the Lisa community.

[^1]: Tecmar was a computer peripheral company that created products for many different systems and platforms in the 1980s and early 1990s. 


# The card

The process of building a new card based on the Tecmar card began in 2016. The original PCB was duplicated and tested with modern components, then optimized for function, form factor, and performance by a design engineer who knows a thing or two about Lisa hardware. A new PCB was fabricated and a prototype built. Many hours of development, testing, building and writing resulted in a final product two years later.  

Within a supported operating system like UNIX or XENIX, the Quad-Port Serial Expansion Board, or QPB, offers a total of four serial interfaces that can be used to connect the Lisa to different terminals or terminal emulators as well as serial printers and modems.

![Serial Card](/assets/images/2018-08-14-sapient-qpb/serialcard.png) 

Two external RS232 DB25 serial interfaces can be connected to other computers and peripherals using cables and adapters. The card also includes two internal headers that can be exposed using DB25-to-ribbon cable adapters that are provided with the card.

Using a USB-to-serial adapter, users can connect modern systems to the Lisa as terminal emulators, which allows them to login and interface with the operating system running on the Lisa as if they were seated at the console:

![Z-Term MacOS](/assets/images/2018-08-14-sapient-qpb/ztermmac.png)

Or, users can adopt a fully-retro setup and connect using vintage systems, like the Macintosh 128k, using adapters provided by VintageMicros or ImageWriter I or II cables depending on the system:

![MacTerminal](/assets/images/2018-08-14-sapient-qpb/macterminal.png)

# Installation

The Quad-Port Serial Expansion Board comes with a guide that walks the reader through the process of installing the card in an Apple Lisa 2. Like most expansion cards, the installation process is very straightforward and can be accomplished with the following steps:

- Remove the rear panel of the Lisa
- Locate slot number 3 (closest to the I/O board)
- Slide out the silver spreader pin and turn the pin clockwise to spread the ZIF (zero insertion force) socket
- Insert the card until it hits the bumpstop
- Turn the pin counter-clockwise to close the socket and push the spreader pin back into the socket
- Reinstall the rear panel

![Case Pic](/assets/images/2018-08-14-sapient-qpb/serialcase.jpg)

In addition to installing the serial card, a compatible operating system must be installed for the card to be functional. VintageMicros provides a kit that includes Microsoft/SCO XENIX and UniSoft UniPlus+ UNIX on compact flash cards that are compatible with the [X/ProFile](http://vintagemicros.com/catalog/lisa-xprofile-hard-drive-emulator-p-282.html) hard disk system. These pre-installed distributions offer a working operating system right out of the box, and are accompanied by a guide that walks the user through basic administrative tasks, connectivity instructions, and more. Instructions for installing the compact flash card(s) and adjustments to the X/ProFile are also provided. Users are also free to install the operating systems themselves on original Apple ProFile or Widget drives using original guides and software available on Bitsavers and other areas of the Internet.


# UNIX on the Lisa

Many modern operating systems are based on UNIX, and macOS and iOS are no exceptions. Anyone familiar with using the Terminal application on a Mac, and especially those fluent in Linux, should feel right at home within Microsoft XENIX or UniPlus+ UNIX. That said, there are some notable differences between older UNIXes and today's operating systems. 

XENIX for the Lisa is based on AT&T's UNIX System III released in 1982, while UniPlus+ UNIX is a little newer and based on AT&T UNIX System V first released in 1983. Neither include a TCP/IP network stack - the workhorse of the modern Internet - though it was available at the time on certain UNIX distributions. Neither distribution offers a GUI - the crown achievement of the Lisa Office System at the time - though XENIX does offer a 'visual shell' that removes the burden of learning (some) CLI commands.

In their day, machines were connected to networks using modems, and to some extent, direct serial connections. UNIX offered the UUCP suite of tools to provide file and mail operations between hosts. Users could copy files between machines and exchange mail messages with users on other systems. In fact, MacOS releases as recent as High Sierra include UUCP software that can be configured to communicate with the Lisa running UNIX or XENIX, allowing the Lisa to send files and even electronic mail! Connections to bulletin-board systems were likely possible as well, though none of the BBSes are around to allow one to recreate that magic. XENIX provides a service known as 'micnet' that allows users to quickly setup a network between other XENIX systems. High-level instructions for UUCP and Micnet are included in the guide.

Microsoft offered a spreadsheet and word processor for XENIX systems, and both were available for the Apple Lisa. The spreadsheet, known as Multiplan, is included with the XENIX distribution provided by VintageMicros:

![Multiplan](/assets/images/2018-08-14-sapient-qpb/multiplan.png)

The word processor, Microsoft Lyrix, is not included but can be found at [bitsavers.org](http://www.bitsavers.org).

The UniPlus+ UNIX distribution includes two UNIX games, Mastermind and Wump, that I'm sure provided countless hours of entertainment to users of the day:

![Wump](/assets/images/2018-08-14-sapient-qpb/wump.png)

Other original games from BSD UNIX can be found on the Internet, including [here](https://github.com/weiss/original-bsd), that can be directly compiled or ported using the included C compiler and associated tools.

# Summary

Using UNIX-based operating systems on the Apple Lisa is a real treat, and further demonstrates the Lisa's flexibility and the backwards compatibility of modern UNIX-based operating systems. The Quad-Port Serial Expansion Board enables the Lisa to act as a communications hub for up to four directly-connected hosts, and users can interact many more using an intermediate device like a Raspberry Pi to route UUCP over the Internet.

Both operating systems are available on Bitsavers, but the installation process is a bit nuanced. The pre-installed operating systems allow users to immediately enjoy a peek into the past. The pre-POSIX C compiler included with UniPlus+ UNIX even allows ambitious users to develop applications. The UniPlus+ Development Guide provides information on included libraries. XENIX development tools are not included but can be installed.

Without the diligence of the software and hardware experts in the Lisa community, both XENIX and UNIX for the Apple Lisa as well as the quad-port serial expansion board would have been lost to time. Thank you!

For more information on the Sapient Technologies Quad-Port Serial Expansion board and the accompanying kit, check out the product page at [http://vintagemicros.com/catalog/apple-lisa-quadport-serial-board-unix-xenix-with-software-p-303.html](http://vintagemicros.com/catalog/apple-lisa-quadport-serial-board-unix-xenix-with-software-p-303.html) or contact John Woodall of [VintageMicros](http://vintagemicros.com/). Kits and cards are expected to be available in November 2018. 