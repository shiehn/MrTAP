# MrTAP
MrTAP - Music Runtime Assembly Protocol

MrTAP is a protocol which allows music sample libraies to be consumed at runtime and outputed as a continuous audio stream.  The MrTap protocol is a single json file which contains meta data and an http pointer the the source for each audio sample.  MrTAP allows the creator to give `hints` to the player regarding assembly or an tonal conformity but ulitmately the each player implementation with decide how the music is assembled.

```{"a": {
}}
