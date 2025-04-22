# Fine-tuning Gemma to understand Dutch numerals


#Introduction

Here I demonstrate fine-tuning the Gemma Large Language Model using Low Rank Adaptation (LoRA) along the lines decribed in this article:Fine-tune Gemma models in Keras using LoRA.

I use an example in Dutch language understanding: understand Dutch numerals written in words. This is a fairly complex problem on which Gemma performs poorly, as not only are the words in Dutch, but Dutch numerals are written in a different order than English ones and several words can be strung together in various ways.

For example the number 34 is written as vierendertig (vier = 4 , en = and, dertig = 30). 483 is written as vierhonderddrieentachtig (vier = 4 , honderd = 100 , drie = 3 , en = and, tachtig = 80 - but no 'en' between 'vierhonderd' and 'drieentachtig').
