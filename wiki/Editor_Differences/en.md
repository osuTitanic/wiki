# Client Editor Differences - Written by Digitalfear117

This is a simple run down of what each version of the game expects for osu! beatmaps, and how they are generated. This will document any major changes between versions to the best of our ability. You can use the site to understand how to make existing maps work in older versions, or for choosing the best version for the map you want to make! 

I have omitted some versions from this list if I could not find any significant changes to the editor within them. If I have missed something feel free to reach out to me so this wiki page can be updated!


# Pre-release osu! versions (v1)

Some versions of osu! exist that predate the games official public beta. 

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

`TEMPO 500`
`OFFSET 126`
`SPEEDX 1`
`CUSTOMX 1`

# Pre-release osu! versions (v2)

This version is significantly more usable then the other pre-release versions. As of right now we only have one version that produces .osu v2's.

## 09-08-2007

This is the first version that can make actual maps. This version has far more of the information needed to be a readable map in modern osu! Headers for splitting up the data have been implemented. SPEEDX and CUSTOMX have been renamed, the audio hash is now included within the .osu file, and you can now place bezier sliders in addition to linear sliders. Notice how there is no way to change difficulty settings. Also there is no way to name a difficulty yet. 

I recommend you continue to use the same folder name and file name structure as the previous version though. This explains why some of the earliest beatmaps are all just "default" settings, users didn't have choice yet. 

It's possible some .osu v2's got updated by peppy to .osu v3 and ranked. There are no ranked .osu v2's, v3's are the first official version.

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

`SampleSet: None`

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

You can see what hitsound a circle has applied to it by looking at the last flag on in the .osu:

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

**This is the first client does not have broken sliders if kiai has been applied to a timing point!**
