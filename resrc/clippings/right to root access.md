---
title: "right to root access"
source: "https://medhir.com/blog/right-to-root-access"
author:
published: 2001-01-13
created: 2026-03-14
description: "right to repair laws should include provisions requiring manufacturers to unlock a device's bootloader (to provide root access) upon consumer request."
tags:
  - "clippings"
  - "right to root"
---
I believe consumers, as a right, should be able to install software of their choosing to any computing device that is owned outright.

![iTerm2 running the nano text editor on my MacBook with the text “I should be able to do this on my iPad”](https://storage.googleapis.com/download/storage/v1/b/medhir-com/o/blog%2Fassets%2Fe40fc0c3-b60e-4045-981f-b3cd986d6d0d%2Fb29c3905-c530-4c47-9e31-2736e34e5dbe.jpg?generation=1736722307372807&alt=media)

This should apply regardless of the computer’s form factor. In addition to traditional computing devices like PCs and laptops, this right should apply to devices like mobile phones, “smart home” appliances, and even industrial equipment like tractors.

In 2025, we’re ultra-connected via a network of devices we do not have full control over. Much of this has to do with how companies lock their devices’ bootloaders, prevent root access, and prohibit installation of software that is not explicitly sanctioned through approval in their own distribution channels.

We should really work on changing that.

## what's the big deal?

A **bootloader** is the computer program responsible for the process of booting up a computer. **Root access** refers to the highest level of privileges a user can be granted to a computer system.

Having access to the bootloader and root gives you full control of your device. You must have access to these if you want to do things like:

- inspect the processes a device is running
- install new operating systems
- interact with the entire file system

The average user does not need access to root, which is why you need to “Run as Administrator” on Windows or use `sudo` on Linux and MacOS to use these greater privileges. It is easy for a system to be compromised if root access falls into the wrong hands.

Despite the risk inherent with a greater set of privileges, this elevated access is useful when a user wants to delve into the lower layers of a computing system and make modifications.

Citing this security risk, most smartphones' bootloaders are locked by default, with the ability to unlock [varying from easy to impossible](https://en.wikipedia.org/wiki/Bootloader_unlocking). The main issue I see with this being the current paradigm – devices that are locked down at the hardware level, *without the option to unlock*, are **inherently anti-consumer**.

As a result of the lack of regulation around hardware-level locks, companies are all too willing to sell electronic devices with restrictions on what software is allowed to run. These locks are justified through the lens of safety — essentially, the average consumer is at too high of a cyberattack risk if arbitrary software is allowed to run.

This "security" justification provides cover for many anti-competitive practices:

- Requiring third-party software to be vetted by the manufacturer, with the ability to revoke distribution at any time through [inconsistent](https://www.cnet.com/tech/mobile/apple-app-store-is-unfair-to-spotify-netflix-former-app-reviews-head-shoemaker-says/) [policies](https://blog.pushbullet.com/2022/10/27/how-we-became-the-worlds-foremost-expert-on-google-play-store-policy-violations/).
- Requiring third-parties to [revenue share](https://www.statista.com/statistics/975776/revenue-split-leading-digital-content-store-worldwide/) with the hardware vendor's platform.
- [Voiding a device's warranty](https://support.apple.com/guide/iphone/unauthorized-modification-of-ios-iph9385bb26a/ios#:~:text=Apple%20strongly%20cautions%20against%20installing,has%20any%20unauthorized%20software%20installed.) if a consumer elects to install alternative software, despite the legal ambiguities of restricting warranties in this manner.
- Restricting access to certain system APIs to create an advantage against competitors on the hardware vendor's platform.

This norm of locking devices and preventing loading of 3rd party software is misrepresented as the only way to keep users secure. But there’s ample evidence to suggest this isn’t true — consumers have already had the ability to install software on desktop operating systems for decades.

This double standard on "security" becomes abundantly clear when we consider two devices currently on the market: MacBooks and iPads. Both use the same M-series processors, however iPads ship with a locked bootloader.

Macs that use M-series chips do not have such locks, which means I can [install Linux](https://asahilinux.org/) if I so choose. I can also do work as a developer by compiling programs from source and being able to touch all aspects of my system through `sudo`.

Those who purchase iPads, often at great expense, do not have any such privilege despite having an equally capable device. This has evolved into new heights of maddening with the [latest iPad Pro release that launched the M4 chip](https://www.apple.com/ipad-pro/). One of the most [state-of-the-art silicon manufacturing processes](https://www.techinsights.com/blog/introducing-tsmc-n3e-power-behind-apples-m4-soc) of 2024 went into a device that you cannot write code on, a reality forced upon consumers through onerous hardware locks.

As an owner of the original iPad Pro, which no longer receives active iPad OS updates, I have no option to load an alternative operating system that could potentially lengthen the life of the device. Some may balk at this being practical. But that's why it's *my* device and *not yours*. However impractical, I should be able to modify a device *that I own* as I see fit.

## balancing safety with consumer choice

Locked down devices have been around long enough that many growing up no longer even know what a filesystem is. While I attribute much of this to the choices made by Apple and the like to hide the filesystem from users, I agree with the premise that consumer devices, such as mobile phones, should be as secure as they can by default. This can even go so far as shipping new devices with locked bootloaders and blocking access to root.

But this shouldn’t come at the expense of being able to **make an informed choice** to unlock these privileges to install any software you want, even if that means adopting a higher level of risk. This is fundamentally about defining what rights you, as the consumer, have when purchasing computing hardware.

*On balance*, I do not believe the security benefit provided by locking devices justifies the many negative impacts to consumers that come through these same restrictions. These impacts include:

### sustainability

Devices that are locked become e-waste once a manufacturer stops supporting them. This keeps happening like clockwork:

- Spotify’s [Car Thing](https://support.spotify.com/us/article/car-thing-discontinued/)
- Nest [Secure](https://support.google.com/googlenest/answer/10191961?hl=en) and [Dropcam](https://support.google.com/googlenest/answer/9257288?hl=en&sjid=8920885882621522457-NC)
- Many fitness devices once [Google shuts down the APIs](https://arstechnica.com/gadgets/2024/05/google-fit-apis-get-shut-down-in-2025-might-break-fitness-devices/)

Locked devices also allow companies to restrict who is and is not allowed to repair hardware. This is particularly acute in the case of farming equipment – John Deere, which accounts for [over 25% of global marketshare](https://www.nasdaq.com/articles/plowing-ahead:-john-deeres-crop-of-success-in-turbulent-markets) for agricultural equipment, notoriously restricts access to data their equipment generates to only their certified dealers. Restricting this data [creates an effective monopoly on repair services](https://nationalaglawcenter.org/update-on-right-to-repair/), harming both farmers that are limited in repairing their equipment and 3rd party repair shops that cannot properly compete with John Deere dealers.

Consumers shouldn't have to be at the whim of manufacturers that have little incentive to maintain hardware longevity. Ensuring devices can be unlocked to inspect / modify any software process would go a long way in removing these artificial monopolies.

### free speech

Disabling the right to load software and forcing consumers through a sanctioned corporate distribution channel makes it easier for nation states to silence speech. Nation states can impose requirements, [such as banning apps from distribution](https://www.washingtonpost.com/technology/2024/04/19/apple-whatsapp-threads-china/), in order to operate in their markets.

It remains to be seen if we'll witness a similar dynamic take hold in the United States if [TikTok does not go forward with a sale to a US-based entity](https://www.bbc.com/news/articles/c289n8m4j19o).

Being able to run your own software, regardless of whether the source is considered "good" or "bad" in the eyes of our governments, makes platforms less brittle against geopolitical conflicts. The main loser of these types of locks is the average person.

### competition

Locking devices and preventing distribution of 3rd-party software restricts competition, as barriers to entry prevent developers from providing the full range of services that consumers want. These restrictions are obvious when looking at Apple's iDevice ecosystem.

Apple restricts many APIs in favor their own hardware and service products. Some examples:

- [Restricting apps from using NFC communication](https://ec.europa.eu/commission/presscorner/detail/en/ip_22_2764) to provide an unfair advantage to Apple Pay in the mobile wallet product space.
- [Limiting APIs that allow iPhones and 3rd-party smartwatches to communicate](https://www.theverge.com/2024/3/22/24107984/apple-watch-smartwatch-ecosystems) to push iPhone consumers to buy Apple Watches vs other brands.
- [Banning alternative browser engines](https://infrequently.org/2022/06/apple-is-not-defending-browser-engine-choice/), as they could offer potentially better native web experiences that could compete with the App Store.

## (rough) thoughts on legal solutions

The de-facto norm of allowing large corporations to dictate how customers can use their own hardware is insidious. It should be considered unreasonable to not have any ability to modify the software for a piece of hardware you own.

The main exception to this, I believe, would be for *critical* systems where compromising operation through software modification presents too high a risk. Examples I'm thinking of include:

- certain medical devices, such as implants and insulin pumps
- subsets of electronic control units for cars

The standard for such restrictions should be extremely high. The burden should be on a manufacturer to demonstrate what material risks exist that justify a hardware lock.

Even in the cases where a device is locked down, there should be some ability to audit the processes the device is running. The large majority of consumer products **should** be covered by “right to root access” protections.

## tl;dr

If you own a computing device outright, you should be able to make any level of software modification you desire. hardware manufacturers should not be allowed to absolutely restrict distribution of software to their own channels under the guise of safety.

In the broader conversation of right to repair regulations, we also need to be thinking about a "right to root access" for computing devices.