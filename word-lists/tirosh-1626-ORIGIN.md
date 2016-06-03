Source: http://web.archive.org/web/20101031205747/http://www.tothink.com/mnemonic/

http://web.archive.org/web/20090918202746/http://tothink.com/mnemonic/wordlist.html

https://github.com/singpolyma/mnemonicode

Size: 1626

Sort: ranked by word quality

Word selection criteria

1. The wordlist contains 1626 words.
2. All words are between 4 and 7 letters long.
3. No word in the list is a prefix of another word (e.g. visit, visitor).
4. Five letter prefixes of words are sufficient to be unique.

The rest of the criteria are less strict. You may find exceptions to all of them because it is difficult to satisfy them all at the same time.

1. The words should be usable by people all over the world. The list is far from perfect in that respect. It is heavily biased towards western culture and English in particular. The international vocabulary is simply not big enough. One can argue that even words like "hotel" or "radio" are not truly international. You will find many English words in the list but I have tried to limit them to words that are part of a beginner's vocabulary or words that have close relatives in other european languages. In some cases a word has a different meaning in another language or is pronounced very differently but for the purpose of the encoding it is still ok - I assume that when the encoding is used for spoken communication both sides speak the same language.
2. The words should have more than one syllable. This makes them easier to recognize when spoken, especially over a phone line. Again, you will find many exceptions. For one syllable words I have tried to use words with 3 or more consonants or words with diphthongs, making for a longer and more distinct pronounciation. As a result of this requirement the average word length has increased. I do not consider this to be a problem since my goal in limiting the word length was not to reduce the average length of encoded data but to limit the maximum length to fit in fixed-size fields or a terminal line width.
3. No two words on the list should sound too much alike. Soundalikes such as "sweet" and "suite" are ruled out. One of the two is chosen and the other should be accepted by the decoder's soundalike matching code or using explicit aliases for some words.
4. No offensive words. The rule was to avoid words that I would not like to be printed on my business card. I have extended this to words that by themselves are not offensive but are too likely to create combinations that someone may find embarrassing or offensive. This includes words dealing with religion such as "church" or "jewish" and some words with negative meanings like "problem" or "fiasco". I am sure that a creative mind (or a random number generator) can find plenty of embarrasing or offensive word combinations using only words in the list but I have tried to avoid the more obvious ones. One of my tools for this was simply a generator of random word combinations - the problematic ones stick out like a sore thumb.
5. Avoid words with tricky spelling or pronounciation. Even if the receiver of the message can probably spell the word close enough for the soundalike matcher to recognize it correctly I prefer avoiding such words. I believe this will help users feel more comfortable using the system, increase the level of confidence and decrease the overall error rate. Most words in the list can be spelled more or less correctly from hearing, even without knowing the word.
6. The word should feel right for the job. I know, this one is very subjective but some words would meet all the criteria and still not feel right for the purpose of mnemonic encoding. The word should feel like one of the words in the radio phonetic alphabets (alpha, bravo, charlie, delta etc).

Notes:

When checking for soundalikes I have found that the standard soundex algorithms are far too liberal and find too many words that supposedly sound similar. It may be true that all vowels are pronounced as schwa in certain cases, but completely eliminating vowels from the soundex comparison is going a little too far . The consonant groups in the soundex algorithm are too general while at the same time ignoring consonants that sound alike over a limited bandwidth channel such as "F" and "S".

If you need a shorter wordlist for any purpose please use words from the beginning of the list. It is sorted according to my ranking for word quality.

The phonetic pronunciation database in the Moby wordlist has been particularly useful in finding soundalikes by comparing the distance between the phonetic representations rather than the standard spelling.

Actually, not all words are 4 to 7 letters long. 7 extra words with 3 letters each are used for encoding 24 bit remainders i.e. when the encoded data length is 3 modulu 4.
