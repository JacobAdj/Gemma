# Fine-tuning Gemma to understand Dutch numerals



## Introduction

Here I demonstrate fine-tuning the Gemma Large Language Model using Low Rank Adaptation (LoRA) along the lines decribed in this article:Fine-tune Gemma models in Keras using LoRA.

I use an example in Dutch language understanding: understand Dutch numerals written in words. This is a fairly complex problem on which Gemma performs poorly, as not only are the words in Dutch, but Dutch numerals are written in a different order than English ones and several words can be strung together in various ways.

For example the number 34 is written as vierendertig (vier = 4 , en = and, dertig = 30). 483 is written as vierhonderddrieentachtig (vier = 4 , honderd = 100 , drie = 3 , en = and, tachtig = 80 - but no 'en' between 'vierhonderd' and 'drieentachtig').


## Training data

Training data were pairs of instruction and response as follows:

```json
{"response": "607", "instruction": "zeshonderdzeven"}
{"response": "920", "instruction": "negenhonderdtwintig"}
{"response": "17", "instruction": "zeventien"}
{"response": "476", "instruction": "vierhonderdzesenzeventig"}
{"response": "626", "instruction": "zeshonderdzesentwintig"}
{"response": "303", "instruction": "driehonderddrie"}
{"response": "442", "instruction": "vierhonderdtweeenveertig"}
{"response": "800", "instruction": "achthonderd"}
{"response": "148", "instruction": "eenhonderdachtenveertig"}
{"response": "39", "instruction": "negenendertig"}
{"response": "483", "instruction": "vierhonderddrieentachtig"}
{"response": "779", "instruction": "zevenhonderdnegenenzeventig"}
...
```
