# MDC_transcoding
A Multiple Description Transcoder for OGG streams

[Multiple Description Coding(MDC)](https://en.wikipedia.org/wiki/Multiple_description_coding) is a coding technique that can improve real-time communications in variable-bandwidth transmission contexts. On the other hand, the [Multi-Channel Set (MCS)](https://p2psp.github.io/#x1-240009) can be used to receive more than one stream simultaneously.

In this scenario, an forward MDC transcoder would input an OGG stream and output so many OGG streams as descriptions. A good starting point can subsample the images using a simple pattern:
```
+---+---+
| a | b |
+---+---+
| c | d |
+---+---+
```
if `a`, `b`, `c` and `d` are neighbor pixels of an image, description (images) A would be formed only by the pixels `a`, description B only by `b` pixels and so on.

The inverse MDC transcoder would compose the original resolution of the video using one or more descriptions (missing descriptions should be interpolated).
