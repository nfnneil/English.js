
Installation is simple:
```
<script src=”mostCommonWords.js”></script>
```

#It’s purpose.
The purpose of this library is to generate pseudo-random groupings of words.  It’s great for password and URL generators.

#How to use it.
```
array<str> mostCommonWords.get (mixed wordType)
```
##MostCommonWords.get – Returns the most common words that comply to the wordType provided.

#Parameters

The mixed argument wordType could be either be:

String
    Takes in a part of speech: noun, verb, adjective, pronoun, or preposition.
Array of String
    Takes in an array of parts of speech.

#Return Values

Returns an array of words that comply with wordType, ordered by type then popularity.

#Example

```
console.log(mostCommonWords.get("noun")[0]); //length: 1524
console.log(mostCommonWords.get("verb")[0]); //length: 1010
console.log(mostCommonWords.get("adjective")[0]); //length: 528
console.log(mostCommonWords.get("adverb")[0]); //length: 252
console.log(mostCommonWords.get("pronoun")[0]); //length: 58
console.log(mostCommonWords.get("preposition")[0]); //length: 46
console.log(mostCommonWords.get(["noun", "verb"])[0]); //length is noun length + verb length
array<str> mostCommonWords.getAll ()
MostCommonWords.getAll – Returns the most common words in every type.  It is the exact equivalent to calling mostCommonWords.get([“noun”, “verb”, “adverb”, “pronoun”, “preposition”])
```
