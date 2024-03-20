# About

This repo contains helper scripts for use with my [UNIX Socket Control patch](https://tools.suckless.org/tabbed/patches/unix-socket-control/) to Suckless's [tabbed](https://tools.suckless.org/tabbed/).

When I switched from i3 to bspwm, I really missed the tabbing feature, but I loved the way bspwm used a UNIX socket to control its windows and another tool specifically for binding keys too much to go back to i3. When I discovered tabbed, I was excited at the prospect of having tabs again, but dismayed when I had to use different keys to control tabbed than I did the rest of my windows. Finally, I found the time to write a patch which let tabbed use a UNIX socket for control like bspwm and subsequently wrote these scripts that allow me to maintain use of my standard keys no matter if I was in a tabbed window or not.

The way tabs work with these scripts is about how I remember them working in i3, but it may not be exact as its been some time since I used it. Either way it works quite well for what I was looking for!

I hope you like it as much as I do!

# BSPWM Usage

For use in BSPWM, simply adjust your sxhkd config as follows below. Obviously feel free to implement it however you like, this is just an example of how I did it.

```
# close and kill
super + {_,shift + }q
	bspctab node -{c,k}

# focus/move the node in the given direction
super + {_,shift + }{h,j,k,l}
	bspctab node -{f,s} {west,south,north,east}

#
# Tabbing
#
# make two windows into tabs, or if they're already tabs, pop a tab out in the given direction
super + shift + t; {h,j,k,l}
	bspctab inorout {west,south,north,east}
```
