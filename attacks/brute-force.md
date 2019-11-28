---
layout: default
title: Brute Force
nav: brute-force
---

## Brute Force Attacks

A brute force attack involves trying every possible combination to a password or key. On a key pad which has numbers 0-9 and a pass number of 4 digits long we can calculate all possible pass numbers with:

    10^4

That is:

    10*10*10*10 = 10000

So we know that the maximum amount of combinations we need to try to crack the keypad is 10,000. Of course on average the amount of tries will be less than this.

Of course on a physical keypad entering 10,000 combinations is quite time consuming, but doing so with a computer it could be done in a few seconds.


### Dictionary Attacks

A dictionary attack is a specific brute force attack where the attempts are limited to a number of likely possibilities. For example consider the example above in which all 10,000 possible combinations on a keypad. Instead of trying all the combinations sequentially, we could instead create a list *(or "dictionary")* which lists codes in order of popularity. For example:

    0000
    1234
    1111
    2222
    ...

Often a dictionary will be words which are commonly used in passwords for example:

    password
    apple
    dog
    qwert
    unlock
    ...

Hence the name "dictionary".

More advanced dictionary attacks will add rules to each word. For example after using all common words are used, another loop might try those same words with numbers at the end:

    password1
    apple1
    dog1
    qwert1
    unlock1
    ...

If the correct combination isn't found on that run another loop is done switching 1 for 2. Another loop may try combinations of words:

    passwordApple
    passwordDog
    passwordQwerty
    passwordUnlock
    ...

Or another run might try combinations which switch letters for numbers:

    p455w0rd
    4ppl3
    d06
    qw3r7
    unl0ck
    ...



### Case of Bitcoin Brain Wallet

A great example of a good brute force attack is the case of Bitcoin Brain Wallets. A Bitcoin Brain Wallet is a Bitcoin wallet generated from an english phrase using a specific algorithm. The brain wallet was popularized because it makes remembering the private key to a wallet easier. Instead of having to remember a long key, a person could simply remember a word or phrase.

However the amount of possibilities for brain wallets is much smaller than all possible bitcoin keys. A brute force to look for bitcoin ballances would be as follows:

- Generate a private key
- Check balance of wallet
- Withdraw balance if greater than 0

This process would simply be unfruitful if every possible key was attempted as the vast majority of wallets are empty and unused. However when we reduce all possible wallets to the sub-set of all possible wallets that can be generated from a phrase.

At [DEF CON 23 Ryan Castellucci](https://www.youtube.com/watch?v=foil0hzl4Pg&feature=emb_title) did a talk about how he was able to obtain the private keys to several Bitcoin wallets with balances by using brute force to generate a list of all possible brain wallets using english words from the English dictionary.


### Brute Force for Cracking

### Preventing Brute Force Attacks
