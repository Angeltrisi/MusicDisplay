# MusicDisplay
## FAQ
Q: Can you add in compatiblity for (some mod)?

A: Mods add in their own compatibility. So if you want their mod to support this, show them this page!

It's a fairly simple process so hopefully they listen.

Q: Is this on 1.4.4?

A: Yes! The mod works on 1.4.3 and 1.4.4.

## Compatibility
Adding compatibility is simple.
Adding a track is as follows: 

```
//Where display == MusicDisplay's Mod instance
display.Call("AddMusic", short musicId, LocalizedText title, LocalizedText author, LocalizedText subtitle);
//OR
display.Call("AddMusic", short musicId, string titleKey, string authorKey, string subtitleKey);
```

The types of these are interchangeable, so if you really want to, you could do Language.GetText("x"), "y", "z" or whatever.

An example would be

```

display.Call("AddMusic", (short)MusicLoader.GetMusicSlot(Mod, "Sounds/Music/VibrantHorizon"), 
    Language.GetText("Mods.Verdant.TrackNames.VibrantHorizon.Name"), 
    Language.GetText("Mods.Verdant.TrackNames.VibrantHorizon.Author"), 
    Language.GetText("Mods.Verdant.TrackNames.ModName"));
```

This gives the given track a display of

```
Current Music:
Title
Author
Subtitle
```

The overload that skipped the author parameter has been REMOVED. DO NOT use it, and update your code. If you wish to skip the Author, simply write "" or LocalizedText.Empty in its place.


For modders that used the string overloads, the mod still functions the same, though you should replace your old code with either localization keys or LocalizedTexts directly.

This way, other languages have support for your content easily and update properly.

## Issues/Suggestions

Feel free to report issues or ask for API suggestions here on this GitHub, on the Steam page, or wherever I am on Discord (@gabehaswon).
Always more than happy to help!
