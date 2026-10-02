---
date: 2026-09-09
categories:
    - AGE-VERIFICATION
    - privacy
tags:
    - AGE-VERIFICATION
    - privacy
    - Open For Contribution
comments: true
---
# How Age Verification SHOULD Be
## How the current way is wrong

The current way age verification is done is unsafe or flat out doesnt work.
Right now, the main options that there are either you record your face and it *might* work(if you look close enough to what companies deem an "average" person) or you upload a picture of your ID.

Because the recording of your face isnt reliable, companies may also just decide that you dont act lke their "average person" that you must not be, and force you to use other methods to prove that you are.

ID verification is far worse, with the major risk of a dahabeah ending up putting you ID online for anyone to see or use, and putting you at risk for identity theft.

All other methods have the problem of being inaccessible for many people

## My idea for a solution

Instead of relying on random companies to (un)"safely" verify your age in a way that can be used to track you across platforms, instead it should be done as a easily verifiable but untraceable data blob

```txt title="example 1"
-----BEGIN PGP SIGNED MESSAGE-----
Hash: SHA256

<TODAY'S DATE>
<HASH OF DATE AND ID BLOB>
-----BEGIN PGP SIGNATURE-----

<SIGNATURE GO HERE>
-----END PGP SIGNATURE-----
```

for a user to get the data blob, a user could get one from an official website or app

for a site to verify it, it would be as simple as verifying the PGP signature using a publicly available public key

By having the data blob be the date and then a hash of the date and an ID blob, it makes the verification blob unique to the user and day it was generated