# hwvnc


Shares and existing device in your desktop. This will later be extended to including virtual devices in your desktop.

## Basic usage

This will show you what devices you can connect to

```
$ ./hwvnc --list
eDP-1 connected primary 3840x2160+3340+2160 (normal left inverted right x axis y axis) 346mm x 194mm
DP-2 connected 3840x2160+0+0 (normal left inverted right x axis y axis) 621mm x 341mm
DP-3 connected 3840x2160+3840+0 (normal left inverted right x axis y axis) 621mm x 341mm

```

Now, let's share a couple of them

```
$ ./hwvnc eDP-1 DP-2
```

You can then connect to them from another device. I use this to move between a sitting and standing desk using old tablets as extra displays.

## Longer term usage

Have a look at ~/.vnc/hwvnc . You can change the behavior of the tool using 

## Security considerations

### Setting a password

If you haven't set a password already, it will warn you and give you instructions. You really should have this on to prevent anyone passing by from connecting to your session.

### Clear text and Encryption

Know where you're running it. There are [implications](https://www.reddit.com/r/AskNetsec/comments/3djr8t/could_someone_explain_to_me_what_makes_vnc/) that should be considered.

If you can, it's worth enabling SSL encryption. You can see how to do it by reading the comments in ~/.vnc/hwvnc.

#### Known to work with SSL

* Ubuntu 19.10

#### Known to not work with SSL

* Ubuntu 18.10

### Sharing

By default, sharing (multiple concurrent connections) is not enabled. This is to prevent extra devices from silently connecting, and makes it obvioius if someone is trying to (and succeeding in) taking over your session. You can change this behavior by editing ~/.vnc/hwvnc. Take a look at the cooments in the file to see how.
