#[fremd](http://en.wiktionary.org/wiki/fremd)

*adj*

    Strange; foreign; alien; outlandish; far off or away; distant.

*noun*

    stranger; guest
    the only word output from `cat dict/words | grep md$`

#on this blog
*2015/05/07* - meta, first, explain

More like a log really, just write as I go.

Everything will be in this one file and it will be searchable.

#on bugs
*2014/10/03* - code, bugs

Just in case you haven't heard what a bug is, here's the low down: whenever our code doesn't behave the way we are expecting it to, it's a bug. If we try to run our code and it doesn't run at all, it's a bug. If we run it and we get some errors either before during or after our code has run, it's a bug. If it runs but doesn't give us what we want, it's a bug.

We might say our code has a bug, and it turns out that it has lots of bugs. We might run into bugs quite frequently and then we would say that our code is buggy. Or, we might use someone else's program and it's slow or does some unexpected things, then we will say it's buggy too.

'Bug', in my mind, is just about the perfect thing we could call it when our code doesn't behave in the way that we expect. Usually (although certainly not always), it's just the tiniest little thing in our code that needs changing to make it work again...just a tiny little bug we need to find. There are so many different kinds of bugs. Oftentimes when you go looking for a bug, you end up finding a whole lot of them. People also tend to be quite annoyed by bugs, but...

##Don't bug out on bugs

Here's a few facts:

  - For a long time at least in your life as a hacker, you're going to spend more time hunting bugs than writing code.
  - Everyone I know who writes code spends more time hunting bugs than writing code.
  - When you're hunting bugs, you're learning about how your code works in ways that you would have glossed over had it just worked right away.
  - Bug hunting will make your logical and problem-solving powers incredibly strong.
  - When you build something that no one has ever built before, there are no instructions, and you are going to have to play with all kinds of bugs before you get to be the first person who ever made it work.
  - The only thing you have to lose when hunting bugs, is your mind.

Considering these statements logically leads me to the following conclusion: we should love hunting bugs, and every time we get a bug, we should get excited about the process of hunting it down. (By the way, the formal term for hunting bugs, or tracking down a bug, is 'debugging').

Becoming an incredible debugger goes hand in hand with being an incredible coder. Debugging will teach you how to look at code and quickly learn what is going on. Debugging will teach you how to how to ask the right questions. Debugging will help you build kinship with all your other coder friends who get to debug all the time too. Debugging will make you a better debugger, and did I mention, you'll always be debugging.

##The mystical truth about bugs

There are no bugs in your code...the bug is always in your understanding of the code.

Don't get me wrong, you have to find the part of the code that needs some changing, to be sure, but I've seen so many intrepid coders get angry with their code, get angry with their computers, blame this thing and that thing and talk about how stupid this or that part of the language they're working with is, or how dumb a certain rule is. Well, computers and programs and all that might be very fast, but they are very stupid indeed. So stupid that all they ever do is exactly what you tell them to. Therefore, when debugging, realize that you have all the power, all the responsibility, and all the control. And besides, since debugging is going to make you such a better coder, you might as well learn to love it.

##"The Debugger's Question"

There's actually nothing mystical about debugging, all you have to do is ask, and answer, the "debugger's question", which is more like a statement and a question:

*I have certain assumptions about how my program should behave: as precisely as possible, how can I prove (or disprove) that those assumptions are true?*

Let's put the debugger's question into practice with a very simple, non-coding based example.

##A fable for the debugger

###The program

You have 4 friends: Avon, Brian, Carl, Donnel. You've made plans with them that you're going to meet Avon alone and and tell him something. Then he's going to go find Brian and tell him what you said, and then Brian's going to tell it to Carl, and then Carl's going to tell it to Donnel, and then Donnel is going to write it down and mail it to you. The plan is that you should have a letter arriving within 2 weeks, from Donnel, that has what you originally told Avon. So, you tell Avon "My favorite month is May" and get to waiting.

###Result #1

2 weeks later, you still haven't received a letter in the mail. Your program is not behaving in the way you expected...you've got a bug.

Time to ask the debugger's question: You assumed you would get a letter with what you said to Avon on it, what are all the things that need to be true for that to actually happen, and how can you prove whether or not they are actually true? One trick to keep in mind while you're debugging is to ask all the obvious questions, and break them down to the most basic and smallest parts. Remember, bugs are usually tiny, and easy to miss. Here we go.

- I'm assuming the mail actually got delivered: You look into this and in fact the mail has been delivered every day (this of course could be broken down into even smaller parts).
- I'm assuming Donnel put the letter into the mail: You ask him and he says that he did.
- I'm assuming Donnel sent the letter to the right address: You ask him and it turns out he didn't send it to the right address. Bug caught!

So you make sure Donnel knows where to mail the letter to, and you try the whole thing again, starting off by meeting Avon and telling him "My favorite month is May".

###Result #2

10 days later a letter arrives in the mail from Donnel! You open the envelope and it's empty!

- You assume that Donnel actually put the letter in the envelope he mailed and to test your assumption you ask him if he did. Turns out he didn't. You carefully explain to him that he has to actually put the letter in the envelope before he mails it. He understands and you try it again. Another bug caught!

You meet up with Avon and tell him again "My favorite month is May".

###Result #3

12 days later a letter arrives in the mail from Donnel! You open the envelope to find a folded piece of paper that reads "Ya moms got giant ears!"

Wow, what are you going to do about this bug?

First you go to Donnel and ask him why he wrote that. He says that's what Carl told him to write. You go to Carl and ask him why he told Donnel to write that. He says that's what Brian told him to say. You go to Brian and say, why did you tell Carl that and he says, "Because it's true!".

Okay, well, at least you figured out this bug. You cut off Brian from saying anything else and get his word that he will only tell Carl what he hears from from Avon. Then you meet with Avon and tell him "My favorite month is May."

###Result #4

10 days later a letter arrives in the mail from Donnel! You open the envelope to find a folded piece of paper that reads "Ya moms got giant ears!"

What a bug!! This time you go straight to Brian and ask if he told Carl to say that. He says yes. You ask him why and he says "Because it's true!"

You say, "You gave me your word you would only tell Carl what Avon told you," and he replies, "Wait let me finish. Because it's true... that Avon told me to say that!"

You of course go straight to Avon and ask if he told Brian to say "Ya moms got giant ears?" He says yes. You ask why. "Because that's what you told me to say." You insist that it is not what you told him to say and he continues to insist that it is.

You can hardly believe it, and you're not sure what to do about it, so you don't change anything. Avon is right here, so you decide to kick off the program once again and you tell him, "My favorite month is May."

###Result #5

13 days later you get a letter in the mail from Donnel! You open the envelope to find a folded piece of paper that reads "Ya moms got giant ears!"

What did you expect? You didn't change anything?

You go to Avon and ask him the same questions as last time and he gives you the same answers. You find it hard to believe so you really start thinking out of the box. You ask him to repeat back what you say to him and you tell him, "My favorite month is may." He says back to you "My favorite month is May." You tell him, remember that and I'll see you tomorrow.

When you see him the next day you ask him what you said to him yesterday and he says, "Ya moms got giant ears!" What is going on? Is his memory broken? Is he insane? Is he just playing a prank?

You're not sure, and he insists that you told him to say that. You can't think of anyone to talk to like a doctor or psychologist who might be able to tell you more about Avon, and you're also not able to talk to anyone from his childhood or look up any of his medical records. You decide you don't know what to do and leave. Later that day you see Brian and tell him "I just don't get that guy Avon."

12 days later you get a letter in the mail from Donnel! You open the envelope to find a folded piece of paper that reads "I just don't get that guy Avon."

Happy debugging.

#git bisect
*2014/08/19* - code, debugging, git

I had a nasty bug to track that, as it turned out, spawned its ugly head over 2 months and 300 commits ago!

I had the pleasure of learning a new tool in my epic quest to hunt it: [git bisect](http://git-scm.com/docs/git-bisect).

[git bisect](http://git-scm.com/docs/git-bisect) is a command that allows you to use binary search to track down when your code stopped acting the way you expected it to. Check out the docs, it's very easy to use.
