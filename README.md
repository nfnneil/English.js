#How to use it.

Installation is simple:

```
<script src=”mostCommonWords.js”></script>
```

The functionality of this library is also very simple.  You can use mostCommonWords.get(part_of_speech) 
to fetch the most common words inside a particular part of speech.  Or you can use mostCommonWords.getAll()
to fetch the most common words for all parts of speech.  You can use this in combination with a
random number generator to create great passwords or memorable URL's.

#Example

```
console.log(mostCommonWords.get("noun")); //length: 1524
console.log(mostCommonWords.get("verb")); //length: 1010
console.log(mostCommonWords.get("adjective")); //length: 528
console.log(mostCommonWords.get("adverb")); //length: 252
console.log(mostCommonWords.get("pronoun")); //length: 58
console.log(mostCommonWords.get("preposition")); //length: 46
console.log(mostCommonWords.get(["noun", "verb"])); //length is noun length + verb length
console.log(mostCommonWords.getAll()); //fetches all valid parts of speech
```
