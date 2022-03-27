# MrTAP
MrTAP - Music Runtime Assembly Protocol

MrTAP is a protocol which allows music sample libraies to be consumed at runtime and outputed as a continuous audio stream.  The MrTap protocol is a single json file which contains meta data and an http pointer the the source for each audio sample.  MrTAP allows the creator to give `hints` to the player regarding assembly or an tonal conformity but ulitmately the each player implementation with decide how the music is assembled.

```
{
    'name': 'library name',
    'authors': [],
    'licence': 'MIT',
    'parts': [
        {
            'id': 'a',
            'type': 'low',
            'chords': ['am','am','dm','g'],
            'bar_count': 4,
            'time_signature': 4,
            'variations': [
                {
                    'midi_name': 'apt4_bm_70_piano-midi_01_fa.mid',
                    'midi_source': 'https://s3.console.aws.amazon.com/s3/object/sas-storage-v1-c53a9aa1cd43270040ea65896164fa25?region=us-west-2&prefix=apt4_bm_70_piano-midi_01_fa.mid',
                    'audio_name': '12-bar-loop.wav',
                    'audio_source': 'https://s3.console.aws.amazon.com/s3/object/sas-storage-v1-5de823ee75641c510e322669b144ffa6?region=us-west-2&prefix=12-bar-loop.wav'
                }
            ]
        },
        {},
    ],
}
```

