---
inFeed: true
description: >-
  There are a few situations where as a computer expert, I might have to suggest
  to one of my customers that the method of fixing their computer problem will
  be a back door hack or exploit of their system.
dateModified: '2017-05-03T11:53:00.339Z'
datePublished: '2017-05-03T11:53:15.063Z'
title: When is hacking “ethical?”
author: []
publisher: {}
via: {}
hasPage: true
starred: false
datePublishedOriginal: '2017-05-03T11:53:15.063Z'
sourcePath: _posts/2017-05-03-when-is-hacking-ethical.md
url: when-is-hacking-ethical/index.html
_type: Article

---
# When is hacking "ethical?"

There are a few situations where as a computer expert, I might have to suggest to one of my customers that the method of fixing their computer problem will be a back door hack or exploit of their system.

The idea of an ethical hack is that you are helping the owner of a device gain access to it after they have been locked out for some reason or another. The hack needs to be done in such a way that the changes made to the device can be undone, returning the device to it's normal operation after you have unlocked your customers device for them.

Other reasons to employ an ethical hack would be to test the capabilities of a security system that you have installed or plan to install, so that weaknesses can be found and fixed before someone malicious finds those weaknesses.

An example of an ethical hack was one I recently did for a customer who had been shut out of their computer. The problem became a somewhat well known one, where after a windows 10 update, users passwords suddenly stopped working. No changes to the password had been made, but the password was no longer accepted as correct.

Had the customer made a password reset disk, things may have been simpler. But, here we were, locked out of the user account.

If you are going to hack a device for someone, make sure to verify that they are the owner. Hacking a stolen device on the request of a thief can land you in hot water, and really is not good for the owner of the stolen device.

I happen to know this customer personally and actually consulted with them to the point of purchase, so I know that this system belongs to them.

The method I decided to use was a back door exploit that you can create on a windows installation, with the right tools.   
I pulled out my windows 10 bootable usb key, and forced the system BIOS to boot from usb key.

I was then able to run the cmd shell on the system, completely bypassing the system's main windows installation.

I navigated to the system drives system32 folder and swapped around a few files:
![](https://the-grid-user-content.s3-us-west-2.amazonaws.com/7e46cbde-1f14-4aef-95b6-f82f7d73b772.jpg)

Now I could shut down the computer, remove my bootable usb key, and start the computer again as normal.

When reaching the login screen, all I had to do was load the on screen keyboard from the accessibility options. Because I had renamed the command line program to the same as the on screen keyboard name, clicking on screen keyboard actually loaded the command line:
![](https://the-grid-user-content.s3-us-west-2.amazonaws.com/25bd86ab-fbab-494c-aed0-bb6d375b2cb3.jpg)

As you may have guessed, having command line access to the system means that you can do many, many things. This wouldn't normally be possible before you had even logged in to your computer.

So, all I needed to do was bring up the password reset options for the user account:
![](https://the-grid-user-content.s3-us-west-2.amazonaws.com/070fe262-beb8-4016-a8a7-72a5099c1eb7.png)
![](https://the-grid-user-content.s3-us-west-2.amazonaws.com/bab9db2a-4727-426a-bd80-bb33175df3fb.jpg)

Bingo, the user can log in immediately upon using the password reset.

I restarted the computer again and booted my usb key so that I could return the computer to it's normal operation (osk.exe loads the on screen keyboard and cmd.exe loads the command as it did before I made the changes.)

Job done!

Always ask a trusted expert if you are not sure what you are doing, or need help with your computer. The fix may be easier than you think!  
This is not a tutorial, so some step by step instructions are missing. Please get in touch if you would like to know more or if you are having issues with your windows device. Help is out there!