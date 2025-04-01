# pdf-ext-slide-video-sync
Documentation for pdf 2.0 extension conforming to ISO32000-2:2020 Annex E. The main purpose of this extension is to annotate appearance intervals in videos of lectures showing slides on projector screen.

## Purpose
Created for application at https://github.com/DanValnicek/slide-video-sync for creating a list of intervals in video where a slide is being shown. 
This can be helpful to students trying to study wanting to know what was said about topic being shown on a given slide.

# Format
The extension entry iin the `/Extensions` dictionary looks something like this:
```
/Extensions <<
  /Type /DeveloperExtensions
  DANV <<
    /BaseVersion /2.0
    /ExtensionLevel 1
    /URL (https\072\057\057github\056com\057DanValnicek\057pdf\055ext\055slide\055video\055sync)
    >>
>>
```
Every page dictionary gets extended with `/DANV_SlideVideoSync` which is a key for a dictionary containing info produced by this extension.

An array with the key `/SlideAppearanceIntervals` which contains an array of arrays with 2 values.
The values in the the subarrays are in the form `[ start end ]` - start and end time in miliseconds at which the slide appears in the video.
```
<<
/Type /Page
/DANV_SlideVideoSync <<
/SlideAppearanceIntervals [ [ 119000 121000 ] [ 124000 124000 ] [ 127000 128000 ] ]
>>
>>
```
The slide in this example appeared 3 times in total in the video in non overlapping intervals.

## Planned features
- video information that these intervals were made for (e.g. video hash, video name, link for download)
  
