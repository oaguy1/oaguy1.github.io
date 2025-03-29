---
layout: post
title:  "I Did Two Game Jams, Here's What I Learned"
author: oaguy1
date:   2024-06-03 06:19:16 -0500
categories: gamedev
tags: gamedev lisp
---

I delved into  game dev in January 2024 and since have participated in two game jams. What's a game jam? For the uninitiated, a game jam is a competition where you create a game from scratch within a limited amount of time and often within a set theme or rules. These constraints are an amazing way to stretch the boundaries of what you think is possible and really encourages creativity.

For the curious, below are links to the two games I created so far:

<iframe frameborder="0" src="https://itch.io/embed/2544698?dark=true" width="552" height="167"><a href="https://oaguy1.itch.io/coming-out-story">Coming Out Story by oaguy1</a></iframe>

<iframe frameborder="0" src="https://itch.io/embed/2722800?dark=true" width="552" height="167"><a href="https://oaguy1.itch.io/stols">Stols by oaguy1</a></iframe>

For those who haven't read my [previous post](/posts/build-a-stupid-game/) on starting game dev, I've been using game dev as an excuse to continue my journey with LISP. As such, I've been writing all the game code in a language called [fennel](https://fennel-lang.org) which is a LISP which compiles down to Lua and have utilized the [LÖVE](https://www.love2d.org) game framework for all the game functions. I mention this because these technology choices influenced what game jams I chose to participate in. Specifically, I choose the [LÖVE Jam 2024](https://itch.io/jam/love2d-jam-2024) and the [Spring Lisp Game Jam 2024](https://itch.io/jam/spring-lisp-game-jam-2024), both run on [itch.io](https://itch.io).

Why these two jams and not one of the literally hundred+ jams that ran during that same time frame? The truth is I have a soft spot in my heart for both LISP and LÖVE, especially together. I know I could most likely achieve more impressive results using other technology, but I enjoy writing much of my personal code in LISP, which brings a somewhat more limited list of game engines/frameworks to work in. LÖVE gives me much of what I need while largely staying out of my way or forcing me to solve problems in a specific way. The two together feel like a perfect match for LISP fun while still having access to many essential game functions and [minimal setup](https://sr.ht/~benthor/absolutely-minimal-love2d-fennel/). Add in the excellent platform/export support for LÖVE and I can bring my games almost anywhere.

The first jam I did was LÖVE Jam 2024, which took place in February of 2024. I had only really done some simple prototypes by the time this jam rolled around with its theme of "interface." As such, I went with a game concept that I knew I could execute on: I created a visual novel that attempted to look like AOL Instance Messenger (AIM) circa 2004. The game was called "Coming Out Story" and was, well, a coming out story between two boys in 2004. While the game is short, I finished it on time and truly learned so much about writing interactive fiction. I plan on returning to this genre in the future there is so much one can do with it.

The second jam I did was the Spring LISP Game Jam 2024. This jam had no theme, but instead required that the games written be written in a LISP dialect of the authors choice. For this jam, I wanted to do something more gameplay driven. I was inspired by Balatro, I wanted to see what I could do by playing with the rules of slots. This brought to a slots game named "Stols" (slots backwards) that allowed the user to either spin for a bet or upgrade the machine to increase their chances. I thought of the game as something of a puzzle game because there were definitive strategies to make it to the final goal of making a million dollars. Despite being a betting game, I found the game fun to program and a definite experiment in gameplay and balancing an in-game economy.

### The Most Important Feature is to Finish the Game

Let’s go over the most important piece of learning I gained from these two competitions: finishing a game. Finishing a game is hard. It requires so much more than programming: it requires final art and audio assets, basic marketing materials, menus and state navigation, balancing all the different systems in the game, and polish. What’s more, you only have a limited amount of time to execute on all these tasks.

I found that after the first jam, completing the second jam was slightly easier. I had significant technical knowledge I gained between the two jams, but I also had experience with things such as making builds of the game, creating marketing assets for [itch.io](https://itch.io) pages, and actually uploading the build and ensuring they worked as expected. All of this took days in my first game jam, but was only an afternoon's worth of work the second time around.

There is also the bizarrely difficult decision of when to finish working on the game. Game jams have time limits, but I have a demanding family schedule that requires me to schedule time even more carefully. As such, one of the most important things I did to finish the games was keep the scope small and add stretch goals as I went. In the first jam, this meant writing the story over only a day or two before focusing on the games visuals and learning how to make game builds for LÖVE games. This last part was somewhat complicated by my initial use of a game template which had some extra features that were amazing for development but broke building the game for several days until I figured out which specific piece was causing the problem. For the second jam, I wised up and chose a pre-made build tool called [makelove](https://github.com/pfirsich/makelove) which took care of creating builds for Mac, Windows, Linux, and Web. This, along with using my first jam game as a template, allowed me to ship quickly and update the builds on my submission page.

### Feedback is Key

One of the most exciting pieces of a game jam is that people actually play your game! If you are lucky, people will comment on your game either on the game jam submission page or on your game's store page. I was lucky enough to get some essential feedback from this portion of both game jams.

For the first jam, I was told the game was too short and that it *really* needed some sound effects to sell the illusion of being an instant messenger from the early 2000s. This was important. I ended up spending much more time on sound in my next game and even wrote an original music loop for the background music.

In terms of narrative length, I chalked it up to being difficult to write interactive fiction with branching paths. It was the first time I had written such an interactive story. I learned quite a bit about what types of branching structures there are and some of the tooling out there for writing interactive story. I ended up using the [ink language](https://www.inklestudios.com/ink/), which had a Lua library written to integrate it right into my game. Plus the tooling around ink was superb and something I definitely plan on continuing to use in the future.

In the second jam, I got somewhat more mixed feedback. I got some positive praise which was wonderful! I also didn't get anybody commenting on the audio, which meant I had sufficiently improved from the previous jam. What negative feedback I did receive was around how hard it was to start the game. One person spin the slots over 50 times and didn't win. I certainly knew this was a possibility and had tried to balance for it by setting the odds in the player's favor by limiting the number of symbols in the slot game at the beginning so there was increased changes of winning. One play tester suggested adding a cheat if the player was near the end of their money so that the game lets the player win. I honestly wish I had implemented this feedback before the jam ended. I think it would have played into the power fantasy I wanted the player to feel.

Of course, one of the biggest piece of feedback was the score/placement in the jam. In my first jam, I placed in the 72 percentile, ranked 37 out of 51 entries with an overall score of 2.029. In my second jam, I placed in the 50 percentile, ranked 24 our of 48 submissions with an overall score of 2.821. While neither of these scores will knock the pants off of anyone, I was pleased to have improved so much between the two jams. Perhaps with more practice I may even win a jam one day.

### Technical Learnings

One example of something that was deceptively hard for me was UI buttons. Replicating a simplified AIM interface for my first game required copying the Windows XP style interface down to the window decoration and button style. LÖVE doesn't have any built in UI libraries, so I had to implement buttons and a text box using the built-in drawing and input primitives. This was a lot of work, but I feel the result was reasonably convincing! As this was my first complete game, all the logic for buttons was mixed in with game logic. That wasn't going to fly for my future endeavours.

In my second game, buttons had many actions and styles. I ended up utilizing a factory pattern to create a button factory that returned a Lua table containing all the button state, including lambda functions for when the button was active and its effect when clicked. This allowed me to have a parent table containing all the buttons and iterate through as necessary to check for things like clicks. 

Another design pattern I was able to implement in the second game was the strategy pattern. Essentially, there are multiple winning selections in a slot game, the most basic being three-or-more of the same symbols in a row. In order to capture all the different ways of winning, I created a strategy for each, each strategy returning its winnings of $0 or more. This structure also meant I could control how much a player won based on each strategy, making some types of winning more lucrative.

Getting to implement these design patterns in my game made me feel like I had graduated from simply trying to get by to thinking strategically about how to code each portion of of the game. I plan on continuing to explore ways to bring more design patterns in so each game feels more maintainable and sustainable in the future..

### What's Next?

I definitely want to participate in more jams! I had a blast working on these two jams and learned an incredible amount about game dev in the process. I haven't picked my next jam, although I believe there will be a Fall LISP Game Jam in 2024. Itch.io has a plethora of game jams going on at any time, so I plan to take advantage of this when the figurative itch arises to make a complete game in a short period of time.

I also plan on continuing to work on the game I started in the [previous post](/posts/build-a-stupid-game/). I've added so much since I last wrote, from a player who moves to rocks to break and gems to collect. I feel like I am getting close to releasing that game soon. Once I do, I will blog about what I learned.
