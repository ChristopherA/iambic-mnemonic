Source: https://github.com/bitcoin/bips/blob/master/bip-0039/english.txt

Size: 2048 words

Sort: alphabetic

An ideal wordlist has the following characteristics:

a) smart selection of words

- the wordlist is created in such way that it's enough to type the first four
  letters to unambiguously identify the word

b) similar words avoided

- word pairs like "build" and "built", "woman" and "women", or "quick" and "quickly" not only make remembering the sentence difficult, but are also more error prone and more difficult to guess

c) sorted wordlists

- the wordlist is sorted which allows for more efficient lookup of the code words
  (i.e. implementations can use binary search instead of linear search)
- this also allows trie (a prefix tree) to be used, e.g. for better compression