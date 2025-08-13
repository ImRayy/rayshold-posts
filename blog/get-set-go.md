---
draft: false
title: "Get set Go!"
description: "I wanted a simple language to build CLI applications, anything but Bash. Why not Bash? Because it's only good for small, maintainable scripts with minimal external dependencies beyond what GNU/Linux offers by default. Managing anything more complex than that is a real pain. The real struggle begins when you have to handle arrays, JSON data, and similar tasks. Bash is great for automation scripts, but not ideal for building full CLI applications. Sure, no one is stopping you from making a CLI or TUI app with Bash, but good luck mate, I'll pass on that!"
publishDate: 2024-09-15
tags: ["cli", "bash", "go", "python" ]
image: {
	src: "https://ik.imagekit.io/rayshold/my-blog/posts/gopher.webp?updatedAt=1755117733352",
	alt: "Gopher",
}
---

I wanted a simple language to build CLI applications, anything but Bash. Why not bash? Because it was only good for small, maintainable scripts with minimal external dependencies beyond that GNU/Linux offered by default. But try scaling up to something complex, and it's a mess, managing packages across different managers is a headache. Arrays, JSON, or anything remotely data-heavy? Bash laughs in your face. Bash is perfect for automation scripts, but full CLI or TUI apps? I’m out.

## What about python?

I was this close to sticking with Python, But, honestly, I was itching to try something new, and Python’s got a few quirks that nudged me toward Go. For one, Python’s interpreted nature makes it slower than compiled languages like Rust or Go, particularly for performance-critical tasks, and Go’s compiled speed is just snappier. Then there’s the Global Interpreter Lock—Python’s GIL can choke concurrency, while Go’s goroutines make concurrent programming a breeze. Also, Python’s package management, even with `uv`, still feels like wrangling a spaceship to brew tea compared to Go’s dead-simple `go mod`.

I wanted to learn more about compiled and low-level languages without jumping in too deep, Go's a sweet spot for that. It’s lean, fast, modern, and gets out of the way so you can build. I still love Python’s flexibility and expressiveness, and I’ll probably bounce back to it for the next quick script that pops into my head—but for now, Go’s got my attention.

## Enter Go

I'm hooked for a few reasons, like [Charm.sh](https://charm.sh/) and it's ridiculously fast compilation. Run `go build`, then `go install`, and you're done, no wrestling with `pyinstaller` or similar tools. Go's setup isn't as simple as Bash's "create a `main.sh` and start bashing keyboard," but the tradeoff feels right.

## What was my goal? Learn another language?

Absolutely not. I wanted to build a CLI app that fetches subtitles from certain sites and saves them. Not bulk scraping—just an easy way to do it from the terminal. Why? Because there are some movies that aren't available on any OTT platform, and when you download them, subtitles aren’t always included. Sure, you can visit websites and click the download button, but no thanks—I love my terminal. So I built [subcli](https://github.com/ImRayy/subcli), it only downloads subtitles, not movies, and I don't endorse piracy unless absolutely necessary.

**Features**

- Search Movies, uses search engine, so accurate results
- Filter by language
- List multiple subtitles, uploaded and rating also visible

**Irony**

My second project was/is a ToDo application I call [toodles](https://github.com/ImRayy/toodles), a name inspired by a clock in Micky mouse cartoon series. It's quite feature rich unlike average ToDo applications, though many of my planned features are upcoming since it's a new project, but I plan to add them at some point. When I build any application let it be a any reinventing the wheel project, I try to make sure to add some values and good looks to it, here 2 screenshots...

**Features**

- CRUD operations odiously
- Set priority
- Do, Undo or Remove a task
- Filter by pending, and done
- More features are coming....

![1](https://ik.imagekit.io/rayshold/projects/toodles/1.png)

I'm happy with how they turned out, though I suspect I’ll grow dissatisfied with the design over time. I might update it later, or I might not, but I see that as a positive sign. It means I’m improving and learning to recognize areas where I can grow, which is exactly the goal.

## Trust the Vibe, Not the Forums

I could deep-dive into research, dissecting every language’s pain points until I’m paralyzed by choice. Or I could ask a senior dev, “Yo, I’m feeling Go,” and they’d probably roast it because they’re married to JavaScript, Rust or whatever. That’s a one-way ticket to second-guessing myself and missing out on a dope experience. So, I skipped the overthinking and dived into what felt exciting. There’s that saying, “Don’t jump to a new language until you’re cashing checks with it,” and yeah, it’s solid advice. But who says you can’t flirt with a new language on the weekends? Every language has its own flavor and solves problems in its own way. Trying them out feels like test-driving a new framework, it’s not about ditching your main squeeze; it’s about seeing what else is out there and what problems it solves.

## Conclusion

I’ve fallen in love with Go, and I’m excited to build more apps with it. The developer experience is top-notch. Setting up, building, and deploying feels seamless and intuitive. When I learn something new, I always set a clear goal to stay focused. This time, I wanted to create a project, and Go was my choice. JavaScript was an option, but I chose Go to push my skills further, aiming to grow as a developer and gain hands-on experience with a powerful language.

Coming from a JavaScript-heavy background, I never quite understood the criticism JS gets in the dev community. But after diving into Go, the contrast is striking. Go has opened my eyes to cleaner coding practices, robust error handling, and more effective ways to structure functions. It’s been a game-changer, helping me write code that’s not just functional but thoughtfully designed.
