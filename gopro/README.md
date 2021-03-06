# GoPro Metadata

## GoPro 360 Cameras

1. [GoPro Fusion (discontinued)](https://gopro.com/en/us/fusion)
2. [GoPro MAX](https://gopro.com/en/us/shop/cameras/max/CHDHZ-201-master.html)

### Metadata DB

_Note: camera firmware update might alter the metadata produced by the camera. The latest firmware was used on when the sample file was taken and date uploaded (`data_added`)._

#### gp01

* Make/model: GoPro MAX
* Type: Video
	- mp4
* Telemetry track: GPMF
* Is geotagged by cam: TRUE
* filename: GS012804.mp4
* Date updated: 2020-06-21

**Video level data**

```
exiftool -ee -G -s -b -j -a -T GS012804.mp4 > gopro_max_GS012804_metadata_overview.json
```

**Track level data (more verbose -- includes telemetry)**

```
exiftool -ee -G3 -s -b -j -a -T GS012804.mp4 > gopro_max_GS012804_metadata_track.json
```

#### gp02

* Make/model: GoPro MAX
* Type: Photo
	- jpg
* Reports pitch / heading / roll XMP: False
* Reports pitch / heading EXIF: False
* Is geotagged by cam: TRUE
* filename: GSAG2002.jpg
* Date updated: 2020-06-21

```
exiftool -G -s -b -j -a -T GSAG2002.jpg > gopro_max_GSAG2002_timelapse_metadata.json
```

#### gp03

* Make/model: GoPro Fusion
* Type: Video
	- mp4
* Telemetry track: GPMF
* Is geotagged by cam: TRUE
* filename: VIDEO_7152.mp4
* Date updated: 2020-06-21

**Video level data**

```
exiftool -ee -G -s -b -j -a -T VIDEO_7152.mp4 > gopro_fusion_VIDEO_7152_metadata_overview.json
```

**Track level data (more verbose -- includes telemetry)**

```
exiftool -ee -G3 -s -b -j -a -T VIDEO_7152.mp4 > gopro_fusion_VIDEO_7152_metadata_track.json
```

#### gp04

* Make/model: GoPro Fusion
* Type: Photo
	- jpg
* Reports pitch / heading / roll XMP: False
* Reports pitch / heading EXIF: False
* Is geotagged by cam: TRUE
* filename: MULTISHOT_0611_000000.jpg
* Date updated: 2020-06-21

```
exiftool -G -s -b -j -a -T MULTISHOT_0611_000000.jpg > gopro_fusion_MULTISHOT_0611_000000_timelapse_metadata.json
```