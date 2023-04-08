# String identification (SID) - Work in progress 
String identification is a debugging tool that is commonly used in game development to look up game assets. A game contains a very large number of assets. Meshes, textures, animations, skeletons, scripts, sounds, effects, triggers, events, NPCs, and various other miscellaneous resources, objects and entities. These objects in any virtual game world needs to be uniquely identified in some way. The unique object identifiers allow Game Designers to keep track of object count to make up their game worlds. The Unreal Engine employs a similar technique  to wrap the string id and a pointer to the corresponding C-style character array in a tiny class, in the Unreal Engine this class is called FName.



## Advantages of using SIDs over string
* SIDs take up smaller amount of memory compared to strings.
* SID comparisons are compiled time constants, vastly improving performance time.  
* The SID macro can be applied on switch cases, which is not possible with strings.


## Example usage

```cpp
// expand macro to generate a StringID
#define SID(x) hash::fnv1a<uint32_t>::hash(x)

  const char* game_state = "player-seen";
    uint32_t event = SID(game_state);
    
    switch (event) {
        case SID("player-seen"):
            // Play a line of dialog...
            // Play a line of dialogue from a file called "dialogue1.wav"
             playDialogue("dialogue1.wav");
            break;
            
        default:
            break;
}
    
``` 




