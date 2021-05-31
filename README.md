# VSEC

A Real-world Dataset for Vietnamese Spell Correction

## Introduction

VSEC is a dataset of Vietnamsese misspellings errors along with their corrections fixed manually. It contains 9341 sentences and 11202 errors in more than 4500 different types, making it the largest public dataset of misspellings for the Vietnamese language.

## Dataset

The dataset is formatted in JSONL, one object per line. Here's sample of a object in the dataset:

```
{
  "annotations": [
   {
    "alternative_syllables": [],
    "current_syllable": "Chiến",
    "id": 1,
    "is_correct": true
   },
   {
    "alternative_syllables": [],
    "current_syllable": "lược",
    "id": 2,
    "is_correct": true
   },
   {
    "alternative_syllables": [
     "điều"
    ],
    "current_syllable": "đều",
    "id": 3,
    "is_correct": false
   },
   {
    "alternative_syllables": [],
    "current_syllable": "chỉnh",
    "id": 4,
    "is_correct": true
   },
   {
    "alternative_syllables": [],
    "current_syllable": "giá:",
    "id": 5,
    "is_correct": true
   }
  ],
  "text": "Chiến lược đều chỉnh giá:"
 }
```

The object contains the following keys:

* `text`: source sentence
* `annotations`: list of syllables in the source sentence. An syllable object contains the following keys:
    * `id`: index of the syllable in the sentence
    * `is_correct`: true/false indicating if this syllable is correct or not
    * `current_syllable`: current source syllable
    * `alternative_syllables`: list of suggestion syllables for the source syllable if it is a misspelling
    
    * Note: The `alternative_syllables` length usually is 0 or 1, rarely greater than or equal to 2. 

