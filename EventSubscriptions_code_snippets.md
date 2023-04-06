From API Chat session 
by Terence
Useful snippets for event subscriptions with "playerInteracts"
To setup a simple interactive object

In VSCode, using gt-helper, in subscriptions.ts:

        game.subscribeToEvent("playerInteracts",({playerInteracts},context)=>{
        if(playerInteracts.objId === "movingGingerbread"){

          const map = context.player?.map!
          const objId = playerInteracts.objId
          const locationX = context.player!.x!
          const locationY = context.player!.y!
          game.moveMapObject(map, objId, {x: locationX +2, y: locationY +2 }, 300, "Linear")
          //when someone presses x near the object, this moveMapObject fn moves the object 2 tiles right and 2 tiles down in 0.3 seconds
        }
    })

Using the console in Developer Tools:

    game.setObject(gameSpace.mapId, "moving", {
    "_name": "movingGingerbread",
            "x": game.getMyPlayer().x,
            "y": game.getMyPlayer().y,
    "offsetX": 0,
    "offsetY": 0,
    "normal": "https://cdn.gather.town/storage.googleapis.com/gather-town.appspot.com/internal-dashboard/images/MQ3EZfL-8WYwKO4dJZjPm",
    "type": 5,
    "width": 1,
    "height": 1,
    "previewMessage": "Press x for gingerbread",
    "distThreshold": 1,
    "id": "movingGingerbread"
    });
