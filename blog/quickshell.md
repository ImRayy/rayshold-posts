---
title: "Quickshell"
description: "Quickshell is a widget wrapper for Qt, likely the first of its kind, while most others stick with GTK, specifically GTK3. It's a toolkit for building widgets, primarily targeting Wayland for window manager users."
publishDate: 2025-08-19
draft: false
tags: ["foss", "react", "tanstack", "better-auth", "hono", "bun"]
image:
  {
    src: "https://ik.imagekit.io/rayshold/my-blog/posts/quickshell.webp?updatedAt=1755613062567",
    alt: "tsuika thumbnail",
  }
---

Okay, let's tackle the introduction segment before diving into the main reasoning. Quickshell is a widget wrapper for Qt, likely the first of its kind, while most others stick with GTK, specifically GTK3. It's a toolkit for building widgets, primarily targeting Wayland for window manager users. Those familiar with the ricing ecosystem know that most popular tools, like Waybar and Eww, are based on GTK, as is SwayNC (Sway Notification Center). Does this mean I'm a typical GTK hater? NO! For a solid reason, from GNOME 42 to mid-45, I used GNOME as my desktop environment. Later, I switched to Hyprland and, for a long time, used Waybar and SwayNC before moving to Alyur's GTK Shell (aka AGS). This background should be enough to show I'm not a GTK hater.

## GTK or Qt?

My very first desktop environment was KDE, and I used it maybe longer than GNOME, considering the time span. So, I'm probably the ideal person to offer unbiased opinions about either. Over the years, many people, including me, had a misconception that GTK is minimal, with great UX and especially UI, while KDE comes packed with features and, naturally, some bonus bugs. One thing to note: GNOME is often criticized for being heavy, and KDE is seen as lightweight but bug-prone, so both lose points there. When it comes to UI, GNOME looks better by default—well-designed, with a premium vibe and look. I'm not denying that. Some say GNOME's UI is shit just to piss off (rage bait) users, but let's pretend those people don't exist. From a general perspective, GNOME does deliver a polished appearance. And GNOME being heavy? That's was true when I last used it. On an APU, Qt gave a snappier experience than GNOME, it was a mess until I got a discrete GPU. That was years ago, though. Now, both desktop environments are mostly solid, but KDE's default UI still looks like crap, coming from a web developer with decent design eye. If you think KDE Plasma's default (uncustomized) UI looks better than GNOME's, specifically in terms of UI, sorry to say, my friend, your design taste is terrible.

Considering all these points, it's clear both have their pros and cons. So, which one should you pick? Qt or GTK? That's the wrong question to ask. I shouldn't need to explain why, but if you've read this far, you probably have the common sense to get it. I'll explain anyway. KDE Plasma and GNOME are just showcases of Qt and GTK, not fully showing their potential UI and UX possibilities. Think of them as another rice from r/unixporn, but backed by a big team instead of an individual. GNOME is basically widgets on top of the Mutter window manager, and KDE Plasma is the same, using the KWin window manager. It's like using Hyprland with Waybar, Rofi, Dunst, or whatever the hell else is out there. Back to picking Qt or GTK, well, it depends on the developer experience you want, which mostly comes down to your preferred widget wrapper. If you know JavaScript, try Alyur's AGS. If Python's your thing, go with Fabric. If nothing suits you, Eww is there with its own language, Yuck. Or, if you like QML, Quickshell is your pick. If you still can't decide, stick with me. But let me warn you: by the end of this blog, you'll get my perspective, not some definitive answer on what to choose. This is my fucking blog, not one of those fan-service posts that try not to piss off either side.

## What do we have on the table?

- [Alyur ags](https://aylur.github.io/ags/): GTK based widget wrapper for GNOME, if you're familiar with JavaScript there's literally no other options and so for the others. It also have TypeScript support, you can pick CSS framework like SASS.
- [Astal](https://github.com/Aylur/astal): GTK3 & GTK4 based, same as ags infect AGS is scaffolding tool around it, also, Astal supports multiple languages besides JavaScript, languages that support GObject introspection according to the docs.
- [Fabric](https://github.com/Fabric-Development/fabric): It's also GTK based, but for python users. And supports both X11 & Wayland
- [ElKowars wacky widgets (EWW)](https://github.com/elkowar/eww): GTK3 based, it's written in rust but you don't have to write rust. It has it's own configurable language known as yuck. Like fabric it also supports both X11 & Wayland
- And there comes [Quickshell](https://quickshell.org/): Finally a QT based widget wrapper, supports QtQuick components, configurable in QML (Qt Modeling Language) language.

With all cards on the table, you can see only one with Qt support. I personally used AGS for the longest time. I haven't tried Astal on its own, nor Fabric, but I did try Eww, and I didn't like it much. Eww was mostly okay; Yuck didn't bother me as much as others complained, but polling values with Bash scripts annoyed me a lot. As a developer, not just a dotfiles ricer, the whole timeout and timer thing bugs me; like maybe it shouldn't, but it does. Another reason is that polling isn't superior to services in terms of performance, which AGS provided. Also, Bash isn't intuitive for parsing, formatting, arrays, and a few other things. Naturally, at the time, I didn't go beyond creating a simple top bar—basically following a tutorial and adding a few extra things with Eww.

## Before Quickshell

I was using Ags before switching to Quickshell, and there were valid reasons why. I liked Ags as it was, Ags V1 was more like how widget echo system works, lemme give an example:

**This is how it used to look before V2**

```js
 Box {
  child: Button {
    child: Text("Hello World!")
  }
}
```

**Now how it is**

```js
<box>
  <button>
    <text>Hello World!</text>
  </button>
</box>
```

Many people liked AGS, and many still do, even though I migrated away and wasn't fucking thrilled. For those who know HTML + JS = JSX, shit can get ugly when it's too complex or big, which is exactly what I hate. I'm a sucker for clean code. I'm not great at it, but I prefer it and I'm still learning, hoping to get good someday—but that's not the point here. As a web dev, this shouldn't be an issue, right? Fuck no! I don't want to deal with the same bullshit everywhere. I want something different, not the same behavior in everything, because there's no fun in that.

The second issue is with the developer. I don't follow him closely, but he seems like a decent guy based on his replies to issues. His character doesn't change my complaint, though. AGS is open source and free (FOSS), and his AGS dotfiles were too. Then, after launching, he made his AGS dotfiles paid, which I respected—it's a smart way to make money, and there's nothing wrong with that. [Hyprland](https://hypr.land/) is planning something similar. But then he launched another widget wrapper called [Marble](https://marble-shell.pages.dev/), which is closed source and exclusive to GitHub Sponsors. Naturally, the first thing you think is: what the fuck happens to AGS? Nothing yet, but it might fade if [Marble](https://marble-shell.pages.dev/) takes off. I didn't want to deal with that uncertainty, so I switched beforehand when I had the chance.

## To Quickshell

I knew about Quickshell long before Alyur launched [Marble](https://marble-shell.pages.dev/), maybe even before AGS V2, but I was busy, and Quickshell's docs weren't ready. I gave it a shot, no doubt, and loved the hot-reloading, but QML and Qt were new to me, so I didn't dig deeper. I didn't mention earlier, but I had to write a `hotreload.sh` script using `watch` and `inotify` for AGS because it didn't support built-in hot reloading for obvious reasons. In the middle of the Tsuika project I'm still working on, I got fed up with the whole JavaScript ecosystem. So, I decided to give Quickshell another go. I spent a solid 2-3 days learning QML and the basics of how Quickshell works by diving into the docs and reviewing other people's code. It was a wild ride—full of joy, pain, but ultimately success and rewarding. It wasn't easy by any stretch, but it was enjoyable. And holy shit, it can look clean as hell, giving me a dopamine rush like no other. See for yourself.

```qml
RowLayout {
  id: rightModules
  anchors.right: parent.right
  anchors.verticalCenter: parent.verticalCenter
  spacing: Theme.margin.sm

  Button {
    id: network
    text: "Network"
  }
}
```

These few lines of code prove jack shit at best, but you've got to check out my dotfiles (not yet released); they're damn close to how AGS V1 used to look. QML as a language is super intuitive, well-structured, and just plain fun to work with. By the way, Quickshell supports JavaScript, no TypeScript, which is a lil sad, but it gets the job done.

When I was on AGS, pulling off fancy animations was a fucking pipe dream. I'd see those slick [r/unixporn](https://www.reddit.com/r/unixporn/) rices with subtle, badass animations, and I wanted to create them too, but I crashed and burned. There was no native, intuitive way to add transitions except relying on Hyprland's built-in layer animations. For starters, I made a custom wallpaper picker, and adding animations with custom cubic Bezier curves was a pain like I'd never felt before. It worked, but barely basic transitions with CSS were fine but, well, basic. Couldn't use keyframes. With Quickshell, getting started with transitions was a simple. I'm no animation expert, but I pulled off some sick tricks on my own and copied a few from others' dotfiles. I still need to properly learn animations beyond simple opacity 0 to opacity 1, XD.

## Widgets that I've created so far

All the basic stuff, nothing fancy. A good looking bar replicating my Ags, notifications (not a panel this time), app launcher, clipboard launcher, wallpaper picker, mpris player and that's about it for now. And I had to finish all of em in one week which I did under less than a week.

#### What's missing from my previous dots

1. **Notification panel:** Quickshell doesn't support persistent notification storage right now, [end-4/hyprland-dots](https://github.com/end-4/dots-hyprland) found a way but since I was still learning Quickshell I didn't bother with it cause blindly copying not my style.
2. **Control Panel:** Yeah, I made this happen while I was on Ags but turned out to be pretty useless.
3. **Flatpak Widget:** I made this to track latest updates from Flatpak, important to keep apps like browser, telegram to keep updated, but since I don't use Flatpak for most apps anymore hence it was not worth it.

#### What's new

1. **Wallpaper Picker** with dynamic theme like Android's, why keep it bland? I could change wallpapers from the terminal faster.
2. **App Launcher** , **Clipboard Launcher** , **Power Menu**, I was using Rofi for all three, but no more.
3. Better animations and UI improvements. You know my taste changes over time.

I've got a ton of improvements to make, which is why I haven't posted on [r/unixporn](https://www.reddit.com/r/unixporn/) yet or made my source code public. I'll add missing features like notification popup timeouts, a notification panel, and fix issues like animation delays and such. But by the time I'm done, the Quickshell hype might fade too, I hope not. It's a badass project, thanks to [outfoxxed](https://git.outfoxxed.me/outfoxxed).

## Conclusion

Overall, I'd say the switch was totally worth it. Qt is a killer framework for building powerful computer applications. Official site claims 1+ billion companies use it, and I buy that. Plus, QML is a dope language to learn. Every ecosystem has its pros and cons for instance, QML needs a better, updated linter because the current one on qmlls is half-baked. The JavaScript ecosystem spoiled me with auto-imports, auto-sorting, and all that good stuff. But the question is, should you pick Qt or GTK? I'd say Qt 100%, it's better, more flexible, faster, smoother, easy to dive into animations, and has an awesome language like QML, which isn't a full-on programming language, so it's easy (subjective) to pick up. Still, it's your call. I'm biased toward Quickshell until something better comes along.
