How to install it.
Simply include this following line in any page you would like to use mostCommonWords.js

<script src=”http://gugenja.com/lib/mostCommonWords.js”></script>
Or DOWNLOAD.

It’s purpose.
The purpose of this library is to generate pseudo-random groupings of words.  It’s great for password and URL generators.

How to use it.
array<str> mostCommonWords.get (mixed wordType)
MostCommonWords.get – Returns the most common words that comply to the wordType provided.

Parameters

The mixed argument wordType could be either be:

String
Takes in a part of speech: noun, verb, adjective, pronoun, or preposition.
Array of String
Takes in an array of parts of speech.
Return Values

Returns an array of words that comply with wordType, ordered by type then popularity.

Example

console.log(mostCommonWords.get("noun")[0]); //length: 1524
console.log(mostCommonWords.get("verb")[0]); //length: 1010
console.log(mostCommonWords.get("adjective")[0]); //length: 528
console.log(mostCommonWords.get("adverb")[0]); //length: 252
console.log(mostCommonWords.get("pronoun")[0]); //length: 58
console.log(mostCommonWords.get("preposition")[0]); //length: 46
console.log(mostCommonWords.get(["noun", "verb"])[0]); //length is noun length + verb length
array<str> mostCommonWords.getAll ()
MostCommonWords.getAll – Returns the most common words in every type.  It is the exact equivalent to calling mostCommonWords.get([“noun”, “verb”, “adverb”, “pronoun”, “preposition”])

Parameters

No parameters.

Return Values

Returns an array of the most common words in the English language.

Example

commonWords = mostCommonWords.getAll();
for (var i = 0, len = commonWords.length; i < len; i++) {
    console.log(commonWords[i]);
}
How I made it.
I created it by scraping an English vocab website.  I used the following function to print all of the applicable data to the console and then copy and pasted it into my mostCommonWords.js file.

keep = "";
$("#GridView3 a").each(function() {
    keep += "\"" + $(this).html() + "\",";
});
keep;
From there, I added a small JavaScript wrapping.

mostCommonWords = {
    getAll : function () {
        return this.get(Object.keys(this.data));
    },
    get : function (input) {
        if (typeof input === "object") {
            arr = input;
            returnArr = [];
            for (var i = 0, len = arr.length; i < len; i++) {
                returnArr = returnArr.concat(this.get(arr[i]));
            }
            return returnArr;
        } else if (typeof input === "string") {
            str = input.trim().toLowerCase();
            if (typeof mostCommonWords['data'][str] === "undefined") {
                throw("The part of speech requested does not exist in our library.");
            }
            return mostCommonWords['data'][str];
        } else {
            throw("Please pass a string or an array to the mostCommonWords get function.");
        }
    },
    data : {}
};

// Normally, all the array definitions for the most common words are defined in this document.
//   But, they were removed in this example for readability sake.
If you’re wondering, the scrape and creation of this library is perfectly legal.  The most common words in the English language is a fact, and, thus, can’t be copyrighted.