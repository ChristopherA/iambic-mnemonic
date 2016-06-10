# iambic-mnemonic
Experimental techniques for private keys to be expressed as iambic metered rhymed verse, to aid in their memorization.

# How to make a password into a poem
BIP39 introduces the concept of expressing a private key entropy by mapping the data directly to a word list. The goal of this project is to extend this idea to create significantly more memorable passphrases without reducing entropy.

We do this mostly by utilizing 2 techniques. The first is to break up the word lists into parts of speach such that you can select the right type of word at a given time without reducing the number of options available (this reducing entropy expressed). The second is to fill in the gaps between these entropy derrived words with `filler words` which represent nothing and are strictly selected for the memorability of the surrounding words.

Finally, lets bring this to it's logical conclusion and create poems from the system. A rhythmic symantically sane sentence with little to no meaning is still rather easy to remember.


Ideally, it should look something like this:
```
the hazards of bliss are pleasing the lounge
unfair was cinnamon to search and scrounge
the stained vibrant lasers give us lectures
prayer saves the valley from conjectures
....
```

### What makes a poem?
 * Iammbic rhythm
 * Reasonable sentences
 * predetermined syllable counts
 * Optional rhyming

#### Iambic
This is the easiest part. We can easily map a given word to it's `s/u` syllable stress levels. It's just a matter of mapping the missing syllable types in between the entropy words and passing these "missing sounds" into the selection engine for the filler words.

#### Reasonable setences
The normal approach to word selection is simply grab 11 bits at a time from the entropy and grab the word from the 2048 list at the corrosponding index. If the words you select truly randomly are in a bizarre order then there is simply nothing that can be done. This requires a specific technique.

First thins is first, sentence structure. When you have a predertermined structure, you instead just need to fill in each of the word slots with a word based on the upcoming bits of entropy. To function exactly like BIP39, this means we would need 2048 words of each basic type that will be used for the entropy derrived words (as opposed to filler words).

If we reduce the word lists to 1024, it gets a bit more reasonable to curate, however it drops 1 bit of entropy for every word. If a sentence contains 4 entropy derrived words then it has 4 bits less entropy than BIP39. We can make up those 4 bits by having the sentence structure itself be derrived from entropy. If there are 16 total sentence structure possibilities then this makes up the missing 4 bits, allowing proper structured sentences to contain all 44 bits of entropy BIP39 would express.

Example:
```
0x0: Noun Verb Adjective Noun
0x1: Adjective Noun Adverb Verb
0x2: Noun Adverb Verb Noun
```
