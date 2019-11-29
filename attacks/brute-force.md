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

A popular program for brute forcing passwords is [John The Ripper](https://github.com/magnumripper/JohnTheRipper). Modern versions of John the Ripper have several modes which are complex variations of the methods explained above.

### Brute Force on the Web

Brute forcing on the web has more constraints than normally exist locally, for example rate limiting and locking of accounts after a certain amount of failed attempts per account. Despite widespread of anti brute force systems in place there are still some websites which are vulnerable to this attack vector.

Tools for brute force on the web include:

- [Hatch](https://github.com/metachar/Hatch) - Hatch is a brute force tool that is used to brute force most websites
- [BruteSpray](https://github.com/x90skysn3k/brutespray) - Brute-Forcing from Nmap output - Automatically attempts default creds on found services.

### Case of Bitcoin Brain Wallet

A great example of a good brute force attack is the case of Bitcoin Brain Wallets. A Bitcoin Brain Wallet is a Bitcoin wallet generated from an english phrase using a specific algorithm. The brain wallet was popularized because it makes remembering the private key to a wallet easier. Instead of having to remember a long key, a person could simply remember a word or phrase.

However the amount of possibilities for brain wallets is much smaller than all possible bitcoin keys. A brute force to look for bitcoin ballances would be as follows:

- Generate a private key
- Check balance of wallet
- Withdraw balance if greater than 0

This process would simply be unfruitful if every possible key was attempted as the vast majority of wallets are empty and unused. However when we reduce all possible wallets to the sub-set of all possible wallets that can be generated from a phrase.

At [DEF CON 23 Ryan Castellucci](https://www.youtube.com/watch?v=foil0hzl4Pg&feature=emb_title) did a talk about how he was able to obtain the private keys to several Bitcoin wallets with balances by using brute force to generate a list of all possible brain wallets using english words from the English dictionary.


### Brute Force for Cracking

We've talked about Brute Force for password cracking but it also a valuable tool in the cracking world. Brute forcing and dictionary attacks are also great tools for those crack. Targets for cracking include but are not limited to:

- Serial codes for Software
- Serial codes for hardware or physical engineering *(see social engineering section for more on why)*
- Coupon codes *(free food, gifts, ect.)*
- Gift cards

When it comes to the above items there are varying degrees of difficulty. This comes down to the method by which numbers are assigned, also if there is additional piece of data to verify the main number *(card number and pin combination)*.

The worst codes use a variation of incrimenting numbers, thus by obtaining a legitimate code by normal means, others can be deduced simply by adding 1.

Another crucial aspect for cracking is being able to confirm if a value is valid or not. Online giftcard balance checkers are often used for this. A balance checker without rate-limiting or some form of captcha can be a major security hole allowing crackers to find valid values. Companies with the worst designed giftcards have found themselves to be continual targets.

A popular example in the USA in the restraunt P. F. Chang whose giftcards are regularly sold on black markets for 10% of face value or less. Since these giftcards a gained by cracking methods, their use implies the loss of funds for a valid giftcard owner.

Ways to prevent cracking include:

- Using a good algorithm to create numbers.
- Limit crackers ability to check if a guess is correct.
- Have a pin attached to a giftcard which is seperate from the main number, created using a seperate algorithm.

### Preventing Brute Force Attacks


