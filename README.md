# Open-Fortress-Tools
 Basic tools for Open Fortress Sourcemod development.

 This also comes with gamedata for a proper SourceMod base install. However...

# LINUX ONLY #
I can't be bothered to use Windows. So, sorry. Linux bins are stripped anyways so it's already a pain to get signatures and offsets. PRs are welcome but Windows gamedata responsibility will be yours until the end of time.

# THIS IS GOING TO BREAK. A LOT #
Open Fortress gets updated every 20 seconds so gamedata will break like there's no tomorrow. If/when they do break, you'll have to either live without, wait for me to actually update new gamedata, or get the signatures/offsets yourself.

# REQUIRES #
- SM 1.10+
- DHooks with Detours
- A lot of patience

# DETAILS #
As you've probably realized, the TF2 extension does not load in Open Fortress. It probably never ever will. To account for this, I've remapped a majority of the supported natives and forwards into openfortress.inc. Open fortress also has a bunch of silly quirks (like RegeneratePlayer not accounting for class-based weapons and there not being a player_spawn event, to name a few), so there are a few OF_* natives/forwards included to account for these as well.

Porting plugins from TF2 to OF isn't a cakewalk, either. There are a bunch of silly things you'll have to detour and work around, similar to what I've mentioned above. To get yourself started, open up the plugin(s) you want to import and replace

```cpp
#include <tf2>
```
With
```cpp
#include <openfortress>
```

This remaps the natives to the plugin so there's no more reliance on the TF2 ext. After that you get to trial-and-error until your server stops crashing. Enjoy.