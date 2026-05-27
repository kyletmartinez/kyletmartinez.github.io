---
layout: default
title: Open Source
permalink: /cyclops/support/open-source/
nav_order: 3
parent: Support
---

# Open Source

This software uses code of [FFmpeg](https://ffmpeg.org/) licensed under the [GPLv2](https://www.gnu.org/licenses/old-licenses/gpl-2.0.html) and the [x264](https://www.videolan.org/developers/x264.html) library licensed under the [GPLv2](https://www.gnu.org/licenses/old-licenses/gpl-2.0.html). Source for both is available on this page.

## Components

| Component | Version | License | Source |
|---|---|---|---|
| FFmpeg | `n8.1.1` ("Hoare", released 2026-05-04) | [GPLv2](https://www.gnu.org/licenses/old-licenses/gpl-2.0.html) | [ffmpeg-8.1.1.tar.xz](https://github.com/kyletmartinez/kyletmartinez.github.io/releases/download/ffmpeg-8.1.1/ffmpeg-8.1.1.tar.xz) |
| x264 | `stable` at commit [`b35605ac`](https://code.videolan.org/videolan/x264/-/commit/b35605ace3ddf7c1a5d67a2eb553f034aef41d55) | [GPLv2](https://www.gnu.org/licenses/old-licenses/gpl-2.0.html) | [x264-b35605ac.tar.gz](https://github.com/kyletmartinez/kyletmartinez.github.io/releases/download/ffmpeg-8.1.1/x264-b35605ace3ddf7c1a5d67a2eb553f034aef41d55.tar.gz) |

The binaries shipped inside Cyclops are compiled from the exact source tarballs linked above. SHA-256 checksums:

- `ffmpeg-8.1.1.tar.xz` → `b6863adde98898f42602017462871b5f6333e65aec803fdd7a6308639c52edf3`
- `x264-b35605ac.tar.gz` → `cd71a7515b0e9a012e1ac9b1f8415bebcaf6fc97d4db32286642ac4c0fbe24f9`

## Modifications

No modifications were made to the upstream source code. The tarballs published above are the unmodified upstream releases. A [changes.diff](https://github.com/kyletmartinez/kyletmartinez.github.io/releases/download/ffmpeg-8.1.1/changes.diff) is published alongside them per the FFmpeg project's compliance request — the diff is empty because no modifications were made.

## Compilation

Both the macOS and Windows binaries are compiled with the following minimal FFmpeg configuration — only the codecs, demuxers, muxers, and filters Cyclops actually invokes are enabled:

```sh
./configure \
  --enable-gpl \
  --enable-libx264 \
  --disable-everything \
  --enable-decoder=png \
  --enable-encoder=libx264 \
  --enable-demuxer=image2 \
  --enable-muxer=mp4 \
  --enable-parser=png \
  --enable-parser=h264 \
  --enable-protocol=file \
  --enable-filter=scale \
  --enable-filter=format \
  --disable-doc \
  --disable-ffplay \
  --disable-ffprobe \
  --disable-network \
  --disable-debug
```

## Usage

Cyclops invokes the bundled FFmpeg binary once per render with the following command shape:

```sh
ffmpeg
  -r FPS \
  -start_number START_FRAME \
  -i INPUT_%05d.png \
  -vf "scale=iw/N:ih/N,scale=trunc(iw/2)*2:trunc(ih/2)*2:out_color_matrix=bt709:out_range=tv" \
  -vcodec libx264 \
  -crf 17 \
  -pix_fmt yuv420p \
  -color_range 1 \
  -colorspace 1 \
  -color_primaries 1 \
  -y OUT_PATH
```

## Location

The FFmpeg binaries are located at the following paths within the Cyclops extension:

```
Cyclops/utility/mac/ffmpeg
Cyclops/utility/win/ffmpeg.exe
```
