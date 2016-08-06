# iambic-mnemonic

Experimental techniques for expressing random private keys as memorable phrases.

Our initial approach is to create phases that are iambic metered, ideally rhymed verse, and then reverse the process to reliably restore the private key against minor inaccuracies, all while being at least as secure as other approaches.

## How to turn a random binary number into a poem and reverse it

One of the challenges in internet security is the dichotomy between passphrases that are random vs passphrases that are memorable. Human selected passphrases are clearly not very secure, as we have learned from decades of experience. We can address this by beginning with a random number selected by a computer or dice, and deriving words from it. This is is the technique that is used by Diceware and BIP39.

In the Diceware technique, 5 dice are rolled, and words are loooked up from a table of 7,776 words. The best version of this is Jospeph's Bonneau's [EFF Diceware](https://www.eff.org/deeplinks/2016/07/new-wordlists-random-passphrases) word list, which has selected words that are common, learned early in life, concrete, distinct, etc. while removing problematic words.

In the bitcoin ecosystem, the [BIP39 standard](https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki) introduced the concept of expressing a random private key to a word list that includes a checksum to validate the conversion back to from the word list to the binary private key.

The goal of this project is to extend this idea to create significantly more memorable passphrases, with checkshum, without reducing entropy.

## Approach

We do this mostly by utilizing 2 techniques. The first is to break up the word lists into parts of speech such that you can select the right type of word at a given time without reducing the number of options available (this reducing entropy expressed). The second is to fill in the gaps between these entropy derrived words with `filler words` which represent nothing and are strictly selected for the memorability of the surrounding words.

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

The normal approach to BIP39 word selection is simply grab 11 bits at a time from the entropy and grab the word from the 2048 list at the corrosponding index. If the words you select truly randomly are in a bizarre order then there is simply nothing that can be done. This requires a specific technique.

First thing is first, sentence structure. When you have a predertermined structure, you instead just need to fill in each of the word slots with a word based on the upcoming bits of entropy. To function exactly like BIP39, this means we would need 2048 words of each basic type that will be used for the entropy derrived words (as opposed to filler words).

If we reduce the word lists to 1024, it gets a bit more reasonable to curate, however it drops 1 bit of entropy for every word. If a sentence contains 4 entropy derrived words then it has 4 bits less entropy than BIP39. We can make up those 4 bits by having the sentence structure itself be derrived from entropy. If there are 16 total sentence structure possibilities then this makes up the missing 4 bits, allowing proper structured sentences to contain all 44 bits of entropy BIP39 would express.

Example:
```
0x0: Noun Verb Adjective Noun
0x1: Adjective Noun Adverb Verb
0x2: Noun Adverb Verb Noun
```
