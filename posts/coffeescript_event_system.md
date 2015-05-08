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
