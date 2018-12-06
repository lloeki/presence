---
layout: default
title:  Pulling the plug on ArchMac
---

Dissatisfied with the then status of macOS package managers, 12 years ago [I kicked off a stupid idea][0].

[0]: https://bbs.archlinux.org/viewtopic.php?pid=410679#p410679 

> Hello again, fellow archers! I've not posted nor monitored arch-related stuff for quite some time, because I moved to MacOSX...
>
> *-snip roundup of status-*
>
> so I went on a journey to see what I can do about it.
>
> *-snip technical details-*
>
> on to test the thing:
>
> ```
> $ /opt/arch/usr/bin/pacman -V
> 
>  .--.                  Pacman v3.2.0 - libalpm v3.0.0
> / _.-' .-.  .-.  .-.   Copyright (C) 2006-2008 Dan McGee <dan@archlinux.org>
> \  '-. '-'  '-'  '-'   Copyright (C) 2002-2006 Judd Vinet <jvinet@zeroflux.org>
>  '--'
>                        This program may be freely redistributed under
>                        the terms of the GNU General Public License.
> ```
>
> woohoo.

A little bit of digging showed my first efforts predate Homebrew’s first commit by a couple of months!

There were ups and downs across the years, especially as the ecosystem evolved, binary hosting went from pricey to cheap, technical hurdles, and outside constraints, up to ultimately getting official approval to use the Arch brand. But mostly I’ve been maintaining it by myself, for my own use. Honestly the biggest project-to-user-base ratio I’ve had to handle.

I learned so much about using simple, boring solutions, automating as much as possible, and using lever effects to decuple developer impact. Computers truly are the bicycle of the mind.

Last March at ParisRB 2020, I had the opportunity to chat with Yurihiko Matsumoto, about the approach to keep the momentum on projects of this size, which boils down to one’s own satisfaction, a.k.a scratch your own itch. As long as it brings you joy, you have no reason to stop.

But maintaining ArchMac has been painful since macOS Catalina. Pacman started having strange hard-to-debug failures. Packages updates fell by the wayside. After a happy time of free CI, things became more difficult on that front, with increasingly limited minutes, pricey bills for overuse, and limited macOS version range for testing. Even going the handmade virtualisation path with custom runners became hard (GitLab Runner itself is still a breeze but VirtualBox is now officially dead on macOS as they will not switch from their virtualisation engine).

Even with outdated packages, ArchMac still was the only one that worked right away on Big Sur, somewhat proving that the model is sound. But now there’s Apple M1 and while I’m confident I could make pacman work there, there’s no CI yet. The time and money cost to me also seems higher than ever. Part of it is my own failing at marketing the thing to potential users, contributors, and sponsors, as the project failed to get traction overall.

Still, I’m happy to see the macOS package manager ecosystem thriving. Now there’s still MacPorts, but also Homebrew, pkgsrc, and Nix. So many alternatives with solid communities! On the flip side it made it really hard to get any mindshare.

Ah, Nix. It has some limitations in my mind, and is quite a bit more complex to build for (ABS is still so dead simple, even compared to Homebrew formulas). Their hydra CI is stellar, and package support is wide, although there can be corner cases where it’s lacking. It solves some limitations of ArchMac, and it’s now my go-to choice.

Recently I also had the opportunity to join a great company and enjoy what I work on a lot, and I also have other fish to fry, like contributing to the Ruby ecosystem. These are areas I want to focus more on, and I realised ArchMac became dead weight onto my mind and wallet. Fighting the urge of sunk cost fallacy, I decided it’s time to pull the plug.

Goodbye [ArchMac][1], we had a good time, I will long for you but I have to move on.

[1]: https://archmac.org
