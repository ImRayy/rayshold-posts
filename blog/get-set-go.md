---
draft: false
title: "Get set Go!"
description: "I wanted a simple language to build CLI applications, anything but Bash. Why not Bash? Because it's only good for small, maintainable scripts with minimal external dependencies beyond what GNU/Linux offers by default. Managing anything more complex than that is a real pain. The real struggle begins when you have to handle arrays, JSON data, and similar tasks. Bash is great for automation scripts, but not ideal for building full CLI applications. Sure, no one is stopping you from making a CLI or TUI app with Bash, but good luck mate, I'll pass on that!"
publishDate: 2024-04-08
tags: ["cli", "bash", "go", "python" ]
image: {
	src: "https://ik.imagekit.io/rayshold/my-blog/posts/gopher.jpg?updatedAt=1726417090682",
	alt: "Gopher",
}
---

I wanted a simple language to build CLI applications, anything but Bash. Why not Bash? Because it's only good for small, maintainable scripts with minimal external dependencies beyond what GNU/Linux offers by default. Managing anything more complex than that is a real pain. The real struggle begins when you have to handle arrays, JSON data, and similar tasks. Bash is great for automation scripts, but not ideal for building full CLI applications. Sure, no one is stopping you from making a CLI or TUI app with Bash, but good luck mate, I'll pass on that!

So after Bash, I considered Python, which is a nice language. People say it's slow, and while that's not wrong, it's still fast enough for non-system-critical tasks. Python is easy to learn, and I picked up the basics long ago, so it seemed like a good option. But nope. When it comes to local development, Python can be a hassle. First, you have to set up a virtual environment (venv), then install packages, and it’s not even version-controlled unless you create a requirements.txt file. What if I forget to do that? The next time something breaks, I might not even have the requirements.txt file to fix it.

If that’s not a little inconvenient enough, you also have to manually activate or source the venv from the root directory to access the packages installed by pip for that specific project. I mean from a JS dev perspective, what the fuck? At first, it might not seem like a big deal, but when you’re working on a large project, constantly navigating to the directory and repeating those steps gets boring and pita fast.

I'm a JavaScript developer, and I write TypeScript more often than JavaScript. So, considering that, if I break my requirements into two major parts, the programming language I needed had to be simple to set up, and it also had to have a type system similar to TypeScript. The only valid answer was Go. I knew Python has third-party tools like `mypy`, `pytype`, and `pylint`, but based on my requirements at the time, Python just wasn't a good fit.

Well those were good excuses to get started with `go`, but one more reason why I chose go is [_charm.sh](https://charm.sh), and easy & insanely fast compilation, all you have to do `go build` & then `go install` and done. You don't have to deal with something like `pyinstaller`, why would you? heh. No hate against python but GO meets all my requirements.  

## What was my goal? Learn another language? 


Absolutely not. I wanted to build a CLI app that fetches subtitles from certain sites and saves them. Not bulk scraping—just an easy way to do it from the terminal. Why? Because there are some movies that aren't available on any OTT platform, and when you download them, subtitles aren’t always included. Sure, you can visit websites and click the download button, but no thanks—I love my terminal. So I built [subcli](https://github.com/ImRayy/subcli), it only downloads subtitles, not movies, and I don't endorse piracy unless absolutely necessary.

**Features** 
- Search Movies, uses search engine, so accurate results
- Filter by language
- List multiple subtitles, uploaded and rating also visible 

My second project was/is a ToDo application I call [toodles](https://github.com/ImRayy/toodles), a name inspired by a clock in Micky mouse cartoon series. It's quite feature rich unlike average ToDo applications, though many of my planned features are upcoming since it's a new project, but I plan to add them at some point. When I build any application let it be a any reinventing the wheel project, I try to make sure to add some values and good looks to it, here 2 screenshots...

**Features**
- CRUD operations odiously
- Set priority
- Do, Undo or Remove a task
- Filter by pending, and done
- More features are coming....

![1](https://ik.imagekit.io/rayshold/projects/toodles/1.png)

I'm satisfied with how they turned out, though I'm pretty sure I'll be disappointed with the design after some time, I may or may not update later on, but I think that's a good thing, it means I'm improving my skills and recognizing areas for growth. That's the whole fucking point.


## Conclusion

I love Go and will definitely use it to build more apps. The overall developer experience, from setup to build and install, is fantastic. I believe there should always be a clear target when learning something new. In this case, I wanted to build something, and I chose Go. Sure, I could’ve used JavaScript, but I didn't, because my goal is to improve to be good, or even the best if possible, and gain as much experience as I can.

Everyone roasts JS for being bad, and as someone who was limited to the JS environment, I never understood those criticisms. But after trying Go, I now see the difference. I've learned more about best practices, how to handle errors properly, and how to use functions more efficiently.
