# MrTAP
MrTAP - Music Runtime Assembly Protocol

MrTAP is an HTTP Rest API exposing AI & procedurally generated Audio Loops.  All audio loops are royalty free and can be used in any commercial or non-commercial project.  For more details please visit: https://signalsandsorcery.ai

```
swagger: '2.0'
info:
  title: MrTAP API
  description: MrTAP (music runtime assembly protocol) is an API for accessing and
    arranging a database of procedural an AI generated audio loops.
  contact:
    email: stevehiehn@gmail.com
  version: v1
host: signalsandsorcery.ai
schemes:
  - https
basePath: /mrtap/v1
consumes:
  - application/json
produces:
  - application/json
paths:
  /loops:
    get:
      operationId: loops_list
      description: ''
      parameters:
        - name: api-token
          in: header
          description: 'MrTap API_TOKEN can be generated here: https://signalsandsorcery.ai/sas/profile'
          type: header
        - name: bpm
          in: query
          description: Filter loops by BPM (beats per minute)
          type: integer
          default: 120
        - name: key
          in: query
          description: Filter loops by Key
          type: string
          default: C
        - name: chords
          in: query
          description: Filter loops by colon seperated Chords.  e.g. 'CM7:Dm7:G7:CM7'
          type: string
        - name: limit
          in: query
          description: Limit the number of results returned. Max 100.
          type: integer
          default: 10
        - name: offset
          in: query
          description: Start index of the limit result subset
          type: integer
          default: 0
      responses:
        '200':
          description: ''
      tags:
        - loops
    parameters: []
  /loops/{id}:
    get:
      operationId: loops_read
      description: ''
      parameters:
        - name: api-token
          in: header
          description: 'MrTap API_TOKEN can be generated here: https://signalsandsorcery.ai/sas/profile'
          type: header
      responses:
        '200':
          description: ''
      tags:
        - loops
    parameters:
      - name: id
        in: path
        required: true
        type: string
  /options/bpms:
    get:
      operationId: options_bpms_list
      description: ''
      parameters:
        - name: api-token
          in: header
          description: 'MrTap API_TOKEN can be generated here: https://signalsandsorcery.ai/sas/profile'
          type: header
      responses:
        '200':
          description: ''
      tags:
        - options
    parameters: []
  /options/chords:
    get:
      operationId: options_chords_list
      description: ''
      parameters:
        - name: api-token
          in: header
          description: 'MrTap API_TOKEN can be generated here: https://signalsandsorcery.ai/sas/profile'
          type: header
        - name: bpm
          in: query
          description: Filter chords by BPM (beats per minute)
          type: integer
        - name: key
          in: query
          description: Filter chords by Key
          type: string
      responses:
        '200':
          description: ''
      tags:
        - options
    parameters: []
  /options/keys:
    get:
      operationId: options_keys_list
      description: ''
      parameters:
        - name: api-token
          in: header
          description: 'MrTap API_TOKEN can be generated here: https://signalsandsorcery.ai/sas/profile'
          type: header
      responses:
        '200':
          description: ''
      tags:
        - options
    parameters: []
  /options/roles:
    get:
      operationId: options_roles_list
      description: ''
      parameters:
        - name: api-token
          in: header
          description: 'MrTap API_TOKEN can be generated here: https://signalsandsorcery.ai/sas/profile'
          type: header
      responses:
        '200':
          description: ''
      tags:
        - options
    parameters: []
definitions: {}

```

