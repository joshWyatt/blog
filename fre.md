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

#shine through your tech interview
*2014/07/21* - interview, psychology

Nervous yet? No worries!! We're going to dig into some really easy to learn strategies for presenting your best and most capable self during the technical interview.

##Not Your Parents

Humans tend to operate on memory. This is well-established scientifically, and has major implications (believe or not) for the interview process. Answer me this:

<i>What kind of person has to go out of their way to gain someone else's approval, immediately, in order to get the resources they need to feed and shelter themselves?</i>

If you said children, I agree. If you said someone who is interviewing for a job, I agree.

In fact the situation is so closely aligned to us on an unconscious level that we bring any and all anxiety that we might have felt as a helpless and utterly dependent child.

Recognize that all the anxiety you feel going into an interview is in fact just a memory and then breath deeply, look around the room at some of the details of the environment, and remind yourself of your actual age. Like anything, you will have to practice this, so find situations where you can trigger yourself to feel that familiar anxiety so that you can practice bringing yourself down over time.

You will get better at keeping yourself calm.


##Enter Like You Were Meant To Be Here

There will come a time to defend your position during the technical part of the interview. When you first meet your interviewer, be like an award winning actor, playing the role of knowing that they are exactly where they need to be. Everyone is happy that you've arrived.

##It's Just Your Friend

Think about that time on the train, or in the bar with a colleague when you were delighted to talk about an exciting new coding challenge. This is all you're doing in the interview.

##Draw

As soon as you start talking code you should start drawing on the white board. Assume your interviewer is going to take a picture and show it to someone else in expectation that they would be able to take some really good guesses at what you're talking about just by what is on the board. Put squares or circles around your writing, it's easier to read, and make sure if you're using data structures that you draw them in a cannonical way.

##Be Concise and Technical

Try to reduce the amount of time you spend speaking about something by using the correct and precise technical jargon. Stay on topic and don't get distracted. An interviewer will ask you to defend yourself or go deeper into a topic if the need arises.

##Make Eye Contact

And slow your voice down while you're at it. Remember you're just hanging out with your friend. Work on the feeling between you and your interviewer. Remember, they want to see your technical chops and find out if they want to spend most days hanging out with you.

##Don't Go Silent

If you don't know what to do next talk out load through your thought process and be gracious and clear when you recognize you've started to consider a wrong answer. Don't be afraid to ask for clarification and always move towards simulating your thought process on the white board. Sometimes the answer will occur to you after you've started drawing.

##Say Thanks
The interviewer's time is valuable, show appreciation.

##Practice
The more you practice the better you'll get.
Best!

#what, me complain?
*2014/06/29* - hack reactor

I recently replied to a Quora post, ["What are the biggest complaints from students in Hack Reactor?"](http://www.quora.com/Hack-Reactor/What-are-the-biggest-complaints-from-students-in-Hack-Reactor). To check out Marcus Phillip's (as always) eloquent and thorough persepective, and other takes as well, click on the link above. In the meantime, here's my response: Enjoy!

I just finished my 4th week at Hack Reactor and am excited to chime in on this discussion. It’s Sunday morning and in spite of my intention to sleep in, I seem to have started waking up early  as uncontrollably as I’m having trouble going to sleep. I’m so happy I get more time today to hack. Thanks for starting this conversation. Hack Reactor is brutal: safely and intelligently, and intentionally brutal, but if you’re considering attending you would do well to know about where your idealism is going to throw a temper tantrum. Full disclosure: I’m in love with this place. I’ll try to voice the part of me that complains because it hates leaving what it believes to be the safety of certitude.

I’m catching my second wind this week. So many of the strategies I’m used to employing to do something effectively have, with fatigue, become unsustainable, either because I don’t have the energy to virtualize what I’m about to do before I do it, or, because the curriculum is more challenging than the situations where I’ve used these strategies in the past. Now I’m starting to experience a quiet inner process where I don’t spend too much time expecting that I know what I’m doing and instead, proceed, and watch as I pull effectiveness spontaneously out of thin-air (a skill that is developing from all the work I've been doing). This transforming serves as the grounds for a very deep and primal complaint:

"What do you mean I don’t get to keep doing what I’m already the best at?!?!?!”

Everyone knows we only needed, all the generations of being human, to make it to 20 or so to have kids in order to keep the (species) train on track. It has proven evolutionarily effective to figure out what works nice and early and prioritize acting in such a way, over, and in spite of, a competing human urge, that is also seeming to prove effective, to play and experience novelty. We have more like 3 brains and they’re pair programming, and you tell me who’s driving and who’s navigating.

We get a lecture during the first week and one of the first slides reads “Bigger, Faster, Stronger…..than you.” If you come to Hack Reactor you will be exhausted (which is not the magical feeling you are imagining it is if you’re not exhausted right now), and you will be too exhausted to pretend you’re the smartest person amongst all your friends (which even if you’re a small exception to thinking this, I bet you wouldn’t even consider Hack Reactor if you didn’t have some latent dialoguing to yourself about this being true.) So there’s a complaint: even though the environment and staff is incredibly supportive at Hack Reactor, I’ve had to face the fact that I’m actually not the smartest person in my generation (or even close) and no one has been able to realize that for me, and it’s liberating and it sucks.

That brings me to pair programming. Pair programming is incredible, and incredibly challenging. I spent 3 months going from 0 code experience to passing the Hack Reactor technical interview, and all that time I didn’t do a lick of collaborating, except to (gladly) steal from all the kind people who have taken it upon themselves to teach by way of posting material on the internet. You have to give up control when you pair program. You might think you know what this means, but I bet you don’t. Depending, you might just act out or plow your way though it by doing what you’re used to doing, but hopefully you’ll find yourself in the deeply transformative (aka tumultuous and therefore self-complaining) position of attempting to reframe how you go about pursuing intellectual/creative projects with others. You might even undergo the task (as recommended to us by the staff) of taking responsibility for your own experience. This will mean it is never your partner’s fault. Again, the part of me that has already found a safe way of doing things, continues to throw a fit as I face the reality of using a computer that is not fully under my governance, with another human who as it turns out, is just as sophisticated, wily, creative, and unpredictable as me.

Unfortunately, the coffee at Hack Reactor sucks. I’ll admit I’m kind of a snob, but if you drink the coffee there it will not contribute towards your doing well in the curriculum. They do provide hot water however, and Sight Glass is just a few blocks away. (And of course they don’t owe us good coffee, I’m just complaining is all.)

Lastly, and this one is actually very disconcerting to me, is how highly under represented women are in our cohorts. There are not zero women, but close to zero women. Now, let me be clear, this is not Hack Reactor’s fault in my opinion. In fact, I see Hack Reactor, by way of their Mission Bits intern program, at least equally representing women at an age, and stage of the game where it really matters (and I hope that they will continue). That said, coding is rad, and this school is mind-blowingly incredible (which I’ll have to write about under a different post) and I’m probably about to go out in a few months and make a bunch of money building really cool stuff that might make the world a much better place, and it just sucks to me that the demographic of others doing the same is so disproportionately skewed. Who do I complain to about this?

Okay enough complaining, I should be coding.

Oh yeah, one more thing, if you come you will not have another life for 3 months. If you say to yourself under the breath that you’re still going to hang out or do anything but Hack Reactor, then you’re going to be complaining about that. Talk to everyone about this before you come. I only did this 75% of the way, in spite of our instructor’s urgings, and now I have loved ones complaining to me.

Good Day!

#a coffeeScript event system
*2014/06/25* javascript, events, code, coffeescript

I had the pleasure of attending a lecture at [Hack Reactor](http://www.hackreactor.com) given by [Phillip Alexander](http://phillipalexander.io) on the topic of Event Systems. During the lecture he demonstrated the implementation of an event system by way of an object mixin, using only native JavaScript.

Phillip has also been excitedly encouraging us to learn and practice CoffeeScript. In his honor, here is an event system implementation inspired by his lecture, written in CoffeeScript.

In the code below we create a mixin that receives an object and returns that same object with event system functionality. After passing through the mixin the object will be able to trigger events, and register event listeners which declare how other objects will behave when a particular event is triggered. In the example we create a dog, an owner and a kid. When the dog triggers a bark event, the owner will feed it and the kid will play with it.

```
mixInEventSystem = (obj)->

  obj.repliesTo = {}
  
  obj.on = (event, callback)->
    @repliesTo[event] = @repliesTo[event] or []
    @repliesTo[event].push callback

  obj.trigger = (event)->
    do callback for callback in @repliesTo[event]

dog = {}

mixInEventSystem dog

owner =
  feed: ->
    alert 'I just fed the dog!'

kid = 
  play: ->
    alert 'I just played with the dog!'

dog.on 'bark', owner.feed
dog.on 'bark', kid.play

dog.trigger 'bark'

```

#why don't hackers ever go outside?
*2014/06/21* code debugging

Because they already get plenty of vitamin debug.

#the biginning
*2014/06/14* - code, memory

...Over the next two days I am going to learn how to use jQuery and AJAX so that my web apps can actually store and remember data.

Everything I've programmed so far has the memory of a fish. Now all my apps will go fishing.

> "...And I will make you fishers of Mem-ory"

