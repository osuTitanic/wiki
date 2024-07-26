# Client Editor Differences

### Written by Digitalfear117

Hi, I'm Digitalfear117 and I like old editors. It is my hope that users of titanic will be able to map and rank songs using any of the available versions of osu! This guide goes over features in chronological order of being added. It also explains how the .osu file format works, and what the values do. Hopefully by the end of this page you can understand how to make modern maps work in older clients, and can choose the best client for making your maps! 

I have omitted some versions from this list if I could not find any significant changes to the editor within them. If I have missed something feel free to reach out to me, or contribute to this so this page!

# Pre-release osu! versions (v1)

Some versions of osu! exist that predate the games official public beta. A lot of the earliest maps in the game were made during this pre-release era and were updated by peppy to .osu v3 and ranked.

## 07-27-2007

This version produces some of the most barebone osu maps. This client lacks the ability to do anything outside of circles, even in the .osu the only information is the hitobjects. 

Here is an example of a circle in this version:

`96,64,8118,5,4`

## 07-29-2007

The top of .osu files from this client now stores the TEMPO and the OFFSET. Below this is hit object data. This version is very similar to the previous one, however sliders now (mostly) work! Something important to note is that slider heads and bodies must start at the exact position, unlike in later editor revisions. The only slider curve type that exists in this version is catmull. Since there are no other slider curve types the slider format is simplified.

Here is an example of a slider in this version:

`224,80,17118,2,0,224:80|336:32|360:153,1`

## 08-26-2007

If you want to create new maps in this version, you must create a folder in the songs directory, and within that folder you must have identically named mp3 files and .osu. Create these before you enter the game. So you could create a folder called `Map` and the files within it should be `Map.mp3` and `Map.osu` 

This version has 2 new tags in the .osu `SPEEDX` and `CUSTOMX`. SPEEDX is for slider velocity, , CUSTOMX is for slider tick rate, but these don't seem to work.

Here is an example of the header of the .osu file from this version:

```
TEMPO 500
OFFSET 126
SPEEDX 1
CUSTOMX 1
```

# Pre-release osu! versions (v2)

This version of the game is significantly more usable then the other pre-release versions. As of right now we only have one client that produces .osu v2's.

## 09-08-2007

This version has far more of the information needed to be a readable map in modern osu!. Headers for splitting up the data have been implemented. SPEEDX and CUSTOMX have been renamed, the audio hash is now included within the .osu file, and you can now place bezier sliders in addition to linear sliders. Notice how there is no way to change difficulty settings. Also there is no way to name a difficulty yet. 

I recommend you continue to use the same folder name and file name structure as the previous version though. This explains why some of the earliest beatmaps are all just "default" settings, users didn't have choice yet. 

There are no ranked .osu v2's, v3's are the first official version.

Here is the .osu format for this version:

```
osu file format v2

[General]
AudioFilename: audio.mp3
AudioHash: a37859a4a0919cd369a1612762cb0c38
SpeedMultiplier: 1
CustomMultiplier: 1

[Metadata]
Title:Dango Daikazoku (TV Size)
Artist:Chata
Creator:Digitalfear117

[Events]

[TimingPoints]
226,600

[HitObjects]
0,0,226,2,0,C|0:0|0:128,1,100
0,192,1426,2,0
```

# b53 to b144 (v3)

Here is the first public release of osu! These are the oldest maps that are fully compatible in modern osu!, so if you want to map in pre-historic versions of the game, this is the most featured, and would require the least amount of additional effort to get working on your part.

Notable changes to .osu v3 include allowing for user adjustable Difficulty Settings. Note that none of these can be decimals, and that OD and AR are combined:

```
[Difficulty]
HPDrainRate:6
CircleSize:4
OverallDifficulty:6 // OD and AR are combined
SliderMultiplier: 1.4
SliderTickRate: 2
```

You can now choose a sampleset for hitsounds in General:

```
[General]
SampleSet: None
```

Images or video can now be added, and they will be at the start of the Events tag:

```
[Events]
0,0,"katamari2.jpg" // Background
2,34350,47100 // Break
```

## b70 linear sliders
In between b53 and b70 linear sliders got added! You can now produce sliders that have the modern day effect of red lines. However in this version, you must choose if you want the entire slider to be linear, entire slider to be bezier, or entire slider to be catmull.

# b162 to b222 (v4)

This update to the .osu format offers some new features which are quite useful.

You can now set a audio lead in time, and enable or disable the countdown feature in General:

```
AudioLeadIn: 0
Countdown: 1
```

Timing points have 3 new additions that can be added:

```
[TimingPoints]
118,500.004999999999,4,0,1
``` 

 - 4 refers to timing signature. Nearly all maps will be 4/4
 - 0 here refers to the sampleset. 0 is legacy and will default to Normal. 1 is the correct way to set the Normal sampleset, 2 is for Soft. Remember that the Drum sampleset does not exist yet
 - 1 refers to whether or not custom sampleset has been checked. In this version of the game there can only be 1 custom sampleset.

## b196 storyboarding

This is the earliest version of osu! that supports the storyboarding scripting language. The design tab won't be done for many more versions, but if you don't mind doing it in a text editor, most of the simple functions work in this version.

## b222 hitsound volume adjustment

This update let's you customize the hitsound volume of any given timing point. That means that the hitsound volume tag in Timing Points can be between 0 and 100. The modern game only let's you go down to 5%, and will force any values lower back to 5% when played.

![Audio section of the Timing Setup panel in b222](https://i.imgur.com/JpWPlyo.png)

.osu example for hitsound volume:

```
[TimingPoints]
118,500.004999999999,4,0,1,42
```
- 42 refers to the hitsound volume %

# b282 to b904 (v5)

The switch to .osu v5 seemed to happen on 2008-03-24, but we have no builds in between b222 and b282. .osu v5 evolved a significant amount during it's time, so much so, that .osu v5's made in the last version that created this file format won't even work correctly in the first version that made this format!

The first versions that use .osu v5 are not majorly different from what came before, it seems that the major change is that 25ms of offset was removed from new maps going forward due to a change peppy made on March 23rd of 2008. This from his official changelog:

`Realised my silence finding function WASN'T RUNNING! Fixed, and adjusted previous beatmaps to earn themselves a free 25ms offset.`

As of me writing this, this is the oldest possible version that works with osu!titanic, however only testers are allowed to use it due to bugs that exist with the client. I think this is a shame but maybe one day this can be changed.

## b294 remove redundant slider anchor on slider head

Up until this point, the first point of all slider bodies copied the coordinate of the slider head, creating a hardcoded link between the start of the slider body and the head. Starting with this version however, this linking is done automatically by the game, and no longer written explicitely to the .osu file. This means that all sliders made on this version of osu! and later will be broken on older clients, so beware!

|       |.osu Slider Definition                                        |
|-------|--------------------------------------------------------------|
|Before:|<code>224,80,17142,2,0,B\|224:80\|336:32\|360:153,1,140</code>|
|After: |<code>224,80,17142,2,0,B\|336:32\|360:153,1,140</code>        |

## b337 red anchors

Starting with this version you can now create red anchors on all 3 available slider types! 

![Red anchor examples on all 3 slider curve types](https://i.imgur.com/wgxg5w7.png)

Adding a red anchor to a Bezier allows you to have sharp straight turns, this could be useful in situations where you want one part of the slider to have a straight turn, but you want another part to have a curved turn. Catmull sliders produce a loop bulb effect on red anchors, where the player is forced to hold on the red anchor. This could be useful on some more gimmicky maps, or to really emphasize a sound on a slider. As a consequence of the bulb though, the slider will end up appearing shorter than the other curve types when the slider anchors are identical. Adding a red anchor to a Linear slider does not do anything noticeable to it. 

Red anchors work in the .osu by copying the same slider anchor point twice. If the game sees two identical slider points it will treat it as a red anchor.

|             |.osu Slider Red Anchor vs White Anchor                       |
|-------------|-------------------------------------------------------------|
|Red Anchor:  |<code>32,32,85207,6,0,L\|128:32\|128:32\|128:160,1,210</code>|
|White Anchor:|<code>32,32,85207,6,0,L\|128:32\|128:160,1,210</code>        |

## b337 toggled options are remembered during session

If you press on the Distance Snap, or Grid Snap toggle buttons, the client will now remember your selection till you close the game.

## b370 change slider curve type on the fly

In this build you can easily try out the different slider curve types by pressing **A** **S** or **D**.

|Key|Action |
|---|-------|
|A  |Linear |
|S  |Catmull|
|D  |Bezier |

![Example of the on screen popup for swapping between slider curve types](https://i.imgur.com/5QB6ucb.gif)

This allows you to experiment more easily with different slider curves on a single object if you want to try some other way to emphasize a sound without having to go up to *Options > Slider Curve Type* every time you want to change types.

## b370 taiko specifics

This is the first build we have available that can make taiko maps! You can enable this by going to *Song Setup (F4)  -> Advanced* and check off **Made for Taiko Mod**

You can tell if a map was made for osu! or taiko by looking at the new flag under the General section of the .osu

```
[General]
Mode: 0
```
-  0 osu! standard
- 1 taiko
- 2 catch the beat (won't be added till b504)
- 3 mania (won't be added till around osu! 2012 b20121030)

## b370 editor selection links can be clicked in chat

An absolute must have feature for those who mod over IRC

![An example of clickable editor selection links over in-game chat](https://i.imgur.com/zto4ZS9.png)
## b370 seek via time display

![GoTo Time popup for jumping to a specific time stamp](https://i.imgur.com/ksnash7.png)

Clicking on the time stamp at the bottom left allows you to go to any time in the map easily.

## b394a tags

In this version you can now add tags directly to the .osu within Song Setup. This will show up under the Metadata section:

```
[Metadata]
Tags:Digitalfear117
```

## b394a red lines and breaks on scrollbar

With this version you can easily see red lines and breaks on the scroll bar. These did show up on the timeline at the top where the notes are, but not on the scrollbar till this version

![Example of a red line and break on the timeline](https://i.imgur.com/h23JnKZ.png%5B)

This makes seeing aspects of the map a bit easier, as you can see all the maps sections more easily at the bottom

## b420 inherited lines

Starting with this version new timing points can inherit the bpm of the previous one. This is what will eventually turn into green lines, but for now they are still red.

![b420 Timing Setup popup, showing off an interited timing point](https://i.imgur.com/tIfXTdJ.png)

You can tell if a timing point is inherited in the .osu based on if the last flag in the timing point is a 1 or a 0.

```
[TimingPoints]
2055,600,4,2,0,65,0
2555,600,4,2,0,65,1
```

The last flag being 0 means non inherited, and 1 means inherited in this version, and for a decent amount of versions after this.

## b452 clap hitsound

This is the very first version that you can use the clap hitsound! This version has a clap for both available samplesets (Normal and Soft).

![A screenshot of the clap hitsound button from b452](https://i.imgur.com/vEJpCYx.png)

You can see what hitsound a circle has applied to it by looking at the last flag in the .osu:

`96,128,45555,1,2` 

- The value of 2 at the end is the hitsound

|Flag|Hitsound |
|----|---------|
|0   |None     |
|2   |Whistle  |
|4   |Finish   |
|8   |Clap     |

These numbers are combined when you add multiple to one object. So for example 6 would be Whistle and Finish.

This is also true of the sliders, if the entire sliderbody has a hitsound applied to it you will see it on the last digit before the slider curve type.

`96,128,52155,2,6,B|96:256,1,100`

- Here it is 6, so that means Whistle + Finish.

## b452 slider head, tail, and reverse arrow hitsounding

This version brings another major milestone for hitsounding, you can now hitsound the head, tail, and reverse arrow of a slider individually. Prior to this build you could only hitsound the entire slider body. You can do this by clicking on the body part in the timeline at the top, or the object on the play field until the segment gets highlighted in black.

![An example of me selecting a reverse slider for hitsounding](https://i.imgur.com/JCtv4lf.png)

Here is a .osu example of a slider with a reverse arrow, where the entire slider body has hitsounds, and each part of the slider has individual hitsounds:

`96,160,61755,2,2,B|224:160,2,100,4|6|10`

Compared with the slider example before, there is now an additional comma after the 100, the 4 being a hitsound on the slider head. Then after the pipe character there is a hitsound value of 6 on the reverse arrow, and after the next pipe a hitsound value of 10 has been applied to the slider tail. That means the entire slider body has a whistle applied to it, the slider head has a finish applied to it, the reverse arrow has a whistle and finish applied to it, and the slider tail has whistle and clap applied to it.

### b452 is the first client does not have broken sliders if kiai has been applied to a timing point!

## b497 storyboarding changes

Storyboarding in b497 got a big overhaul, this is the format that would later be supported by the first versions of the in game design tab like in b595b. This format isn't hugely different from what modern stable expects, but there are few things to keep in mind. You may not have a design tab yet in this version, but storyboards are visible within the editor. If you want to reload your SB after changes do `CONTROL + L`. Annoyingly, this version of osu! will delete any lines it does not understand. So make sure you keep your text editor open or have backups.

Here are some important rules to know about manual storyboarding in this format:

- X & Y coordinates can never contain decimals `320,227.5` would be invalid, unlike in the modern game.
- Scale commands must have a start and end command. `S,0,11892,15594,0.4` is valid in modern stable, but it must be adapted to have an end scaling transformation, even if it's just the same value. `S,0,11892,15594,0.4,0.4` is valid in this format
- Modern stable uses the easy to read Name format for all objects such as `Sprite,Foreground,Centre,` for the start of any object in the storyboard. This version expects you to use numerical values to represent these things. So for my example Sprite is considered type `4`, Foreground is considered type `3`, Centre is considered value `1`. `4,3,1,"Storyboard\Lyrics\A1.png",320,200` would be the valid format for this version.

![Any example of a storyboard loaded in b497](https://i.imgur.com/OUMv1dS.png)
Here is a valid storyboard tag example for within a .osb:

```
4,3,1,"Storyboard\Lyrics\A4.png",320,200
 F,0,232715,232905,0,1
 S,0,232715,235563,0.4,0.4
 F,0,235373,235563,1,0
```

Here is a valid storyboard tag example for within a .osu:

```
4,3,1,"Storyboard\Lyrics\A4.png",320,200
 F,0,232715,232905,0,1
 S,0,232715,232715,235563,0.4,0.4
 F,0,235373,235563,1,0
```
For some reason the start time for the size transition must be there twice.

### b504 is the last build to allow CS 0-10 without .osu editing

## b595b design tab (in game storyboard editor)

![A screenshot of the in game storyboard design tab](https://i.imgur.com/SH47KiN.png)
You can now make storyboards within the game itself!

## b595b green lines

Timing points that only change things with hitsounds are now assigned as green lines! Only timing points with BPM changes (or uninherited points) will receive red lines. Rejoice as you can finally tell what each line's function is!

If you try to import a modern map with slider velocities in it, the game will read the slider velocity change as a BPM multiplier instead, so this version cannot support true slider velocity right now. 

## b595b BPM adjustment

![A screenshot of the Timing section within Timing and Control Points popup menu](https://i.imgur.com/F76WPSr.png)

BPM Adjustment options are now available in the Timing and Control Points popup! This allows you to change the BPM by 0.5x or 2.0 in order to better emphasize more intense or less intense parts of the song! Everything about the editor relates to BPM though, for example, doubling the BPM means your slider velocity is now doubled, your distance snap is now doubled. Even if the value the game displays is the same, this is the actual result. This is the same in the modern game as well.

## b595b additional sample set custom override

![A screenshot of the Audio section within Timing and Control Points popup menu](https://i.imgur.com/AYawU5v.png)

You can now use up to two custom sampleset overrides! Think about the possibilities! 

You can tell within the .osu which sampleset override has been applied to a timing section by looking at the 5th flag

`500,-100,4,2,1,75,0`

- the `1` in the 5th section here denotes that this section is using custom sampleset 1. This is the version version of the game that lets you use up to 2, if the number is higher it will read as if there is no override, so no cheating! osu! won't override any of these when saving at least.

## b699 support for mode specific maps

Now when you upload a map it should correctly identify the mode. I can't test this since titanic BSS isn't ready yet, but that means that maps from this client should properly show up as taiko maps, not just taiko maps that were forced to be playable in standard too lol. CtB is not supported yet.

## b699 kiai time

Kiai time can now be added! This adds some visual flare to the game during the timing sections that utilize it. For some reason it also has gameplay modifications as well, such as making some objects worth more points in taiko, changes the HD fade distance to be lower. In addition, there are glow effects for notes. In standard this shows up under notes, and in CtB the glow effect is where the fruit will land.


## b699 rotate by...

![Rotate by... popup as seen in b699](https://i.imgur.com/4hWEfOB.png)

You can finally rotate objects by arbitrary amounts, rejoice! Annoyingly you have to type an amount in this version, so it's not all sunshine and rainbows, and no preview, type a number, hit OK and see what horrors you have unleashed I guess lol.

## b753a grid snap and beat snap divisors saved to .osu

Quality of life change, these are now saved to the .osu, so you can see what settings the mapper used, rather than your last used settings.

# b1077a to b1218 (v6)

.osu v6 fixed an issue with stacking objects over spinners and animation speeds in storyboards that existed in .osu v5's. Bugs like this are maintained for compatibility in gameplay, but are not visible in the editor. The editor updates the map to the most recent format when you open it (this is why you get prompted to update old maps if you simply just open them and do nothing, and then exit)

# b1533 (v7)

This is the only build that we have the creates .osu v7's. This fixed a calculation issue with multipart bezier sliders.

# b1652 to b1672 (v8)

According to documentation, 3 changes were made with v8. 

## mm additions

Constant sliderticks-per-beat are now generated

## HP drain near breaks

I don't know if it was made harder or easier. No one cares exactly how HP works, so this kind of stuff never gets fully documented.

## taiko triple drumrolls

It's not clear if they were added, or fixed in this version.

# b1700 to b20120916 (v9)

## b1700 only bezier sliders

Peppy decided to wage war on all the older slider curve types. .osu v9's contain only bezier sliders. Linear sliders are recreated through red anchors or 2 point beziers, catmulls and linears are no longer selectable using the slider curve type hotkeys. Any slider curves your map has when you open them in these clients will be maintained, but if you try adding any new points to any old slider it becomes a bezier.

## b1700 spinner new combos are no longer enforced

This is a change that peppy has flip flopped on many times. In modern stable this is actually enforced again, but on modern lazer it isn't. Older versions had it not enforced, then it became enforced.

# b20121003shine.test to b20121203 (v10)

Compared to previous .osu firmat updates, this brings many new features to the format!

## b20121003shine.test mania editor

This is the very first version that supports mania! It has some differences compared to modern. This veraion of the game uses a very basic column grid with normal hitobjects. This gives a great view of how mania maps are acrually stored in the .osu file. The playfield is divided into how many columns the map has (based on circle size). Sliders are used for LN's, the modern "Hold Note" button does not exist yet.

Mania was so experimental during the time of this format, that maps were not allowed to be ranked during this .osu version on Bancho. All Mania maps that weremade during this time were updated alongside the editor improving.

## b20121003shine.test sampleset additions

This greatly expands hitsounding, you can add the soft, normal, drum versions of any hitsound on top of the original sampleset's hitsound, creating much more depth. 

## b20121003shine.test romanized artist and song fields 

Finally you use the original language for the artist and song name and English as well. This is an important feature on Bancho, if the artist's name is written in another language on Bancho, you must use both fields as per the ranking criteria. Take the Japanese artist monet, her name is always written in English, so only the normal field is needed. This is not an enforced rule of titanic though.

## b20121003shine.test BeatmapID and BeatmapsetID saved directly to the .osu file. 

This is important, as tools such as Mapset Verifier check to make sure these tags are there, and therefore are an unspoken requirement to the Ranking Criteria on Bancho. Titanic does jot force this though.

## b20121003shine.test fixed each bezier sliders part being 1/50 second too short

This is the actual reason for peppy incrementing the format to v10. This is the second time a .osu incrememnt happened due to issues with Bezier sliders lol

## b20121008 osz2

This is the very first release version of osu! that uploads maps as osz2's. The important part about this feature, is only clients with osz2 support can currently upload maps on titanic. So if you want to upload your maps, this is the first version you can use!

# b20121223 (v11)

This is the only build we have that creates .osu v11's. 

## "only" perfect curve sliders

There are a few version of osu! that saves every slider as perfect curve sliders, you can see this in maps like this one: https://osu.ppy.sh/beatmapsets/66346#osu/193641. This is very similar to what .osu v9 and v10 did with bezier sliders. 

## linear, perfect curve, bezier slider saving in .osu file

At some point it got switched to the way we all know today. Honestly I'm not even sure if this is a v12 change or a v11 change yet. 

2 point sliders are always saved linear, 3 points as perfect curves, 4 points or more as bezier. This is how osu! reads the maps that claim every slider is a perfect curve, so may as well just save it like this so it's easier to parse the .osu file.

# b20130303 to mid 2014 (v12)

I have no idea what this added

# mid 2014 to mid 2015 (v13)

This build adds the ability to add decimal difficulty values to maps! At the time this got added you could only do .5 increments, but this would later be changed to support .1 increments. However, do note that decimal difficulty settings are against the ranking criteria on titanic! Do not upload maps with AR 9.5 for example.

# mid 2015 to now (v14)

This versions adds per node sampleset changes to sliders (or juice streams) for Catch the Beat. I'm a CtB and I don't even know what this means, and I have no idea if anyone uses this to be honest.

# Late 2018 to now (v128)

This is the .osu version for all maps made on lazer. Inside lazer you can export maps in compatiblity mode (osz) for editing on stable, or you can save in the lazer format (olz) for editing on lazer. As of the time of me writing this (7-25-2024), there has never been a 100% pure .osu v128 ranked, as all lazer maps ranked on Bancho, or Titanic have been updated on stable during the ranking process, bringing the .osu version back to v14. However, using my modded client you can actually upload the map as a pure .osu v128, so if you are feeling adventurous you could be the very first one to do so!

# b20130303 Digital Client++

This a modded mapping client made by Digitalfear117, with help from Nikku, Tree, and Levi! This offers many legacy and stable features for mappers to use, and a few extra new ones as well.

## slider curve type swapping

Just like older clients, you can press A, S, or D to change slider curve types. Unlike old clients you can also press F to change to perfect curves too! This is the first client that you can easily choose any slider curve type.

## expanded beat snap divisor and distance snap

Using the Unhinged Slider Curve Type, and Unhinged Beat Snap Divisor options in the editor, you can use DS from 0.1x to 16x, and you can map from any beat snap 1/1 to 1/32. These features do also fully work when exported to stable or lazer, so get crazy with it!

## fixed sv decimal rounding

For some reason this version of osu! would round sv's like 0.95 to 1.00. This has been fixed in my client

## decimal difficulty settings

You cannot use AR's such as 9.5 when uploading maps to titanic. They must be whole numbers. However, if you wish to map for stable or lazer, you can enable this in Compose. Using decimal difficulty settings will save the map as a .osu v13 instead of a v12.

## taiko and catch the beat editors

Although modern stable doesn't seem to offer much for Taiko and CtB mapping, they do actually have a few more features. For CtB distance calculation only changes when you move something in the X coordinate, and for Taiko you can actually see the color of the don and kats based on NC's.

## uploading older .osu formats

All other osu clients force update your .osu file to the version they are built around, however my client is different. You can import your map from another client, and go directly to the upload button. It will ask you if you want to force save, and you can hit No. Doing this will skip the saving process, allowing you to upload any map from any client in a pure fashion! Try this for uploading .osu v9's and earlier, and .osu v128's!
