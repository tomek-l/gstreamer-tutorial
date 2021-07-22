# Gstreamer Tutorial

My notes trying to make sense of `gstreamer`  🙂

## Install

```
apt-get install gstreamer1.0-tools libgstreamer1.0-dev gstreamer1.0-plugins-\* gstreamer1.0-libav libgstrtspserver-1.0-0 libgstrtspserver-1.0-dev
```

## Underlying Data Model

- __Pipeline__ is a video (or audio) processing application. Pipeline consists of _elements_.
- __Elements__ are self-contained processing unit such as `h264 encoder`, `filesink`, or `xvimagesink`. Because they're self-contained, they are agnostic to what's happening upstream or downstrem the pipeline. As long as the elements have compatible _pads_, you can connect them like lego blocks.
- Individual elements connect using __pads__. This anaglogy comes from pads on an electronic circuit board (and imo is a bit unfortunate).
More formaly, a __pad__ is an interface that elements adopt to exchange data. "Producer" pads are called __sources__, and "consumer" pads are called __sinks__.
- One element can contain multiple pads with:
    + different data formats (e.g. RGB, or YUV images),
    + different media types (e.g. demuxer typically outputs audio and video stream)

tl;dr
`Pad ∈ Element ∈ Pipeline`


## 
