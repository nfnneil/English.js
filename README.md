#How to use it.

Installation is simple:

```
<script src=”mostCommonWords.js”></script>
```

#Built in functions

##mostCommonWords.get(part_of_speech)

It will fetch an array list of the top x most popular words inside the
argument's part of speech.

For example:
```
console.log(mostCommonWords.get("noun"));
```
Will print the top 1,524 most common nouns in the english language. If you're
curious about the size of each valid part of speech here's a table:

| Part of Speech | Number of Most Common Words |
| ------ | ------ |
| Noun | 1,524 |
| Verb | 1,010 |
| Adjective | 252 |
| Adverb | 58 |
| Pronoun | 46 |

###Potential uses

```
console.log(mostCommonWords.get("noun"));
console.log(mostCommonWords.get("verb"));
console.log(mostCommonWords.get("adjective"));
console.log(mostCommonWords.get("adverb"));
console.log(mostCommonWords.get("pronoun"));
console.log(mostCommonWords.get("preposition"));
```

##mostCommonWords.get(array_of_parts_of_speech)

This function will return a combined array of all the parts of speech you want.

###Example:

```
console.log(mostCommonWords.get(["noun", "verb"]));
```

It will print the most common nouns with the most common verbs into console.

##mostCommonWords.getAll()

This function will return an array of all parts of speech: nouns, verbs, adjectives,
adverbs, and pronouns.

###Example:

```
console.log(mostCommonWords.getAll());
```
This code snippet will print all the most common parts of speech.
