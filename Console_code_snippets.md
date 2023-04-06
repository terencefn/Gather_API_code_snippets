Notes from API Chat sessions (from Pedro, Kilian and Terence)

Useful console commands:

  // returns all the players in a gather space
  
    game.players
  
  //returns your own player object, can be useful when you want to find information about where you are standing, etc, without having to look for yourself in a list of players

    game.getMyPlayer()
 
 //one thing I will often do is go:
 
     const {x,y,map} = game.getMyPlayer()
     
  //to have access to the properties I might need in a teleport or to maybe spawn an object beneath yourself at once...  

  //just like the above, but for the current map
  
    gameSpace.getMyPlayerMap()

  //⭐ teleporting is fun
  
    game.teleport(mapId,x,y,[targetPlayerId])

  //this property possibly lists all event names available, I used to like looking into that a lot to see what I could try to use
  
    game.eventSubscriptions 

  //⭐ useful for checking the event payload or just trying to see when/how often an event actually fires, this will log both arguments in the event payload (data and context)
    
    game.subscribeToEvent('eventName',console.log)
