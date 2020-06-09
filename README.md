# 360 Camera Metadata

## In one sentence

This repository exists to accumulate and understand file formats and metadata standards generated by 360 cameras.

## Why we built this

We build software that processes 360 video and image files. In many cases these files contain telemetry data (e.g are geotagged).

Before processing them, we need to understand the format (or standard) of files each camera produces to process it correctly.

This repository contains our research to aid others building similar tools.

## Cameras

* [GoPro](/gopro/README.md)
	- MAX
	- Fusion
* [Ricoh](/ricoh/README.md)
	- Theta V
	- Theta Z1
* [Labpano](/labpano/README.md)
	- Pilot One
	- Pilot Era
	- Pilot Lock
* [Insta360](/insta360/README.md)
	- ONE
	- ONE X
	- ONE R
	- Pro
	- Pro2
	- Titan
* [Samsung](/samsung/README.md)
	- Gear 360
* [Xphase](/xphase/README.md)
	- Xphase
* [Kandao](/kandao/README.md)
	- QooCam
	- QooCam 8k
	- Obsidian GO
	- Obsidian S & R
* [Manufacturer (example structure)](/maufacturer/README.md)
	- Model
	- Model

## Accessing sample files

All sample files used to extract metadata are offered free of charge for the benefit of other developers. You will find links to download under each cameras README.md file.

## Telemetry Standards

Generally camera manufacturers write metadata standards in a few formats.

One's we've researched are linked:

1. [gmpf](/0-telemetry-standards/gpmf.md)
2. [camm](/0-telemetry-standards/camm.md)

## Data wanted

We are seeking geotagged files from the following cameras:

### Timelapses

* Insta360
	- Pro
	- Pro2
	- Titan
	- One R
	- One
	- One X
* Labpano
	- Pilot One
	- Pilot Lock
* Garmin
	- VIRB360
* Kandao
	- QooCam
	- QooCam 8k
	- Obsidian GO
	- Obsidian S & R
* XPhase
	- Pro

### Videos

* Labpano
	- Pilot One
	- Pilot Lock
* Insta360
	- Pro
	- Titan
	- One R
	- One
	- One X
* Garmin
	- VIRB360
* Kandao
	- QooCam
	- QooCam 8k
	- Obsidian GO
	- Obsidian S & R
* Samsung
	- Gear360
* XPhase
	- Pro


## Extracting metadata from images

You can use the open-source [Exiftool](https://exiftool.org/) to extract and normalise metadata.

_Consider supporting exiftool: Exiftool is a free and very well supported bit of software we use to extract metadata. Let’s make sure it stays that way. [You should consider a small donation to support it if this repository has been useful to you](https://exiftool.org/#donate)_.

Heres a quick introduction on how to use it:

### Exiftool Images

_[Read more about image file metadata](https://www.trekview.org/blog/2020/metadata-exif-xmp-360-photo-files/)_

Some useful exiftool commands:

```
exiftool -G -s -b -j -a -T MULTISHOT_0611_000000.jpg > MULTISHOT_0611_000000_timelapse_metadata.json
```

[This command includes the following arguments](https://exiftool.org/exiftool_pod.html):

-a: Allow duplicate tags to be extracted
-G: Print group name for each tag
-s: Descriptions, not tag names, are shown by default when extracting information. Use the -s option to see the tag names instead.

### Exiftool Videos

_[Read more about video file metadata](https://www.trekview.org/blog/2020/metadata-exif-xmp-360-video-files/)_

Some useful exiftool commands:

**Video level data**

```
exiftool -ee -G -s -b -j -a -T VIDEO_7152.mp4 > gopro_fusion_VIDEO_7152_metadata_overview.json
```

**Track level data (more verbose -- includes telemetry)**

```
exiftool -ee -G3 -s -b -j -a -T VIDEO_7152.mp4 > gopro_fusion_VIDEO_7152_metadata_track.json
```

[These commands includes the following arguments](https://exiftool.org/exiftool_pod.html):

* -ee: Extract embedded data from mp0 files (and others).
* -a: Allow duplicate tags to be extracted
* -G3: Identify the originating document for extracted information. Embedded documents containing sub-documents are indicated with dashes in the family 3 group name. (eg. Doc2-3 is the 3rd sub-document of the 2nd embedded document.)
* -s: Descriptions, not tag names, are shown by default when extracting information. Use the -s option to see the tag names instead.
* -b: Output metadata in binary format (useful because often telemetry data is binary e.g gyroscopes)
* -j: Use JSON (JavaScript Object Notation) formatting for console output

Note, for larger files you might encounter the error:

```
Warning: End of processing at large atom (LargeFileSupport not enabled)
```

I got this error when processing this 4GB video.

In which case you need to enable `largefilesupport` using an [exiftool `.config` file](https://exiftool.org/config.html). [Read this topic on the exiftool forum for more information](https://exiftool.org/forum/index.php?topic=3916.0).

## Help us build better software

Unfortunately we don’t have the budget to buy every single 360 camera to test the photos and videos they produce with our software.

Whilst having standards like EXIF and XMP is very helpful, many manufacturers do things slightly differently (especially given the flexibility of fields in XMP data).

In order to make sure our [free, open-source software works for everyone](https://github.com/trek-view/), we need to test it using 360 image and video files produced by a range of cameras and manufacturers.

And that’s why we need your help.

If you have a 360 camera and want to support our work, [please share more information about your camera with us using this form](https://docs.google.com/forms/d/e/1FAIpQLScgOk1W5jpyrQuDF5FuKqUpKK0EIpSlokckZd3OB-r_ZOjZmQ/viewform). Thank you!

## License

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>.