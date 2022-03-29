# MrTAP
MrTAP - Music Runtime Assembly Protocol

MrTAP is a protocol which allows music sample libraies to be consumed at runtime and outputed as a continuous audio stream.  The MrTap protocol is a single json file which contains meta data and an http pointer the the source for each audio sample.  MrTAP allows the creator to give `hints` to the player regarding assembly or an tonal conformity but ulitmately the each player implementation with decide how the music is assembled.

```
{
    'name': 'my_mrtap_sample_library',
    'authors': ['jane doe'],
    'meta-info-link': "",
    /* any aribitray field intended for an http link to meta data or relevant info */
    'licence': 'MIT',
    'bpm': 120,
    'section': [
        {
            'id': 'verse', 
            /* Id is user defined.  Must be unique. */
            'bar_count': 4, 
            'key': 'c', 
            /* Keys are diatonic major.  Minor keys must use the relative major.  Possible values: [a, a#, b, c, c#, d, d#, e, f, f#, g, g#] */
            'time_signature': 4,
            /* One chord per bar.  The count must match the bar_count defined */
            'chords': ['am','am','dm','g'], 
            'layers': [{
                /* a minimum of one layer and one variation are required per section */
                'type': 'low', 
                /* possible values: [low, mid, hi, melody, ambience, drum_bottom, drum_tops, drum_full, drum_perc, drum_fill] */
                'variations': [
                    {
                        'id': '1',
                        /* Id is user defined.  Must be unique in the current section. */
                        'midi_name': 'apt4_bm_70_piano-midi_01_fa.mid', 
                        'midi_source': 'https://s3.console.aws.amazon.com/s3/object/sas-storage-v1-c53a9aa1cd43270040ea65896164fa25?region=us-west-2&prefix=apt4_bm_70_piano-midi_01_fa.mid',  
                        /* public http location (i.e S3 url)*/
                        'audio_name': '12-bar-loop.wav', 
                        'audio_source': 'https://s3.console.aws.amazon.com/s3/object/sas-storage-v1-5de823ee75641c510e322669b144ffa6?region=us-west-2&prefix=12-bar-loop.wav'
                        /* public http location (i.e S3 url)*/
                    }
                ]
            }],
        },
        {},
    ],
}
```

