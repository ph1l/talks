---

# REDACTED - Public Key Encryption Intro with GnuPG - 🔐

a talk by `"Philip Freeman" <freeman@endlessm.com>`
aka...    `"Philip J Freeman" <elektron@halo.nu>`















---

## PGP - Pretty Good Privacy - 🔒

* written and released in 1991 by Phil Zimmerman

* strong cryptography software that provides:

  * data privacy and

  * data authentication

* via features:

  * asymmetric cryptographic key management and

  * a "trust" mechanism for validating public keys




---

## PGP - Cryptographic software is a Munition - 💣 🚀☢

* In February 1993, Zimmerman became the target of a criminal investigation
  by the US government for "munitions export without a license."

* Encryption software using keys larger than 40 bits were then considered
  munitions according to the US export regulations.

* Zimmerman published the source code of PGP in book form, via MIT Press.

* The export of *books* being protected by the First Amendment provided a
  loophole to allow the legal export of PGP software outside of the U.S.

* Charges against Zimmerman were dropped without ever making it to court

* Later cases established software source code was speech protected by the
  First Amendment. (Bernstein v. United States)


---

## PGP - Concepts - Asymetric Cryptography - ☯

* asymmetric cryptography (or Public-key cryptography)

  * keys are generated in two parts:

    * The Public Part

      This key is distributed widely and not sensitive. It is used to encrypt
      data that only the holder of the private part of the key can decrypt and
      to verify digital signatures made by the holder of the private part.

    * The Private (or Secret) Part

      This key is known only to the owner. It is needed for decrypting data
      encrypted to the user and generating signatures for data that can be
      verified by others.


---

## PGP - Concepts - Encryption / Decryption - 🔒 / 🔓

* Encryption

  * a random symetric key (the session key) is generated

  * payload is enrypted with the session key

  * the session key is encrypted for each recipient using her public key

  * the encrypted data and sesion key are bundles into a single message

* Decryption

  * the session key is decrypted by the recipient using her private key

  * the data is decrypted with the session key


---

## PGP - Concepts - Signing / Verifying - 🔏

* Signing

  * a hash (or digest) of the payload is calculated

  * this is used to create a digital signature with the private key of the
    sender.

* Verification

  * recipient computes a digest of the payload

  * using the senders public key and the digital signature, the digest is
    compared to the digest in the digital signature




---

## Gnu Privacy Guard - 🔐

* RFC4880 Compliant Implementation of OpenPGP Message Format

* GPLv3 License

* Pre-installed on Endless OS

* CLI Command$ gpg --help










---

## GPG - Demo - Alice Gets Started - ✒

* Generate a new key-pair:

      alice@endless:~$ gpg --gen-key

* Choose key-type, size, and expiration (defaults are okay)

* Choose a key-id:

      Real name: Alice Albatross
      Email address: alice@endless
      Comment: 

* Generate Entropy

* Generate a revocation certificate and make a backup


---

## GPG - Demo - Alice Gets Started - 😋

* public and secret key created and signed.

* sending an encrypted message to Bob

  * get bob's public key

  * encrypt a love note

* verifying bob's fingerprint and signing his key

* sharing your signature with bob or the world

* assigning a trust level in bob's key signing




---

## GPG - Demo - More about key signing and trust - 🙊

* Signing a Key?

  * You sign a key when you verify it's authenticity

  * Compare the Fingerprint.

  * Check a Government issued ID (Driver's license, Passport, etc...)

  * Signatures should be shared to establish the web of trust








---

## GPG - Demo - More about key signing and trust - 🙈

* Assigning trust to a key

  * trust is private, it's not shared.

  * trust level defines how much you trust another user to sign keys

  * GnuPG uses trust levels and sigs to calculate the confidence in a key










---

## GPG - Demo - Alice's Cheat Sheet - Working with Keys - 🔑

* Generate a new public/private keypair:

      gpg --gen-key

* Generate a revocation certificate:

      gpg --gen-revoke alice@endless > revoke.asc
      chmod 400 revoke.asc

* Import a key from a local file:

      gpg --import bob-public_key.asc

* Search for and import a key from a keyserver:

      gpg --search-keys freeman@endlessm.com

---

## GPG - Demo - Alice's Cheat Sheet - Working with Keys #2 - 🔑🔑

* List keys in your public keyring:

      gpg --list-keys

* Edit a key (to sign or assign trust to other people's keys):

      gpg --edit-key 95C7423D

* Export a public key to a local file:

      gpg --armor --export 95C7423D > 95C7423D.asc

* Export a public key directly to a keyserver:

      gpg --send-key 95C7423D


---

## GPG - Demo - Alice's Cheat Sheet - Encrypting/Signing - 🔏

* Encrypt a file for user (generates secret.txt.gpg):

      gpg --encrypt --recipient freeman@endlessm.com secret.txt

* Create a detached signature for a file (generates a .sig):

      gpg --detach-sign package_0.0.1.deb

* Sign and Encrypt a message, generate acsii output suitable for copy/paste:

      echo "hi" | gpg --armor --sign --encrypt --recipient freeman@endlessm.com

* Encrypt a message with a hidden recipient (to hide recipient info):

      echo "hi" | gpg --armor --encrypt --hidden-recipient freeman@endlessm.com


---

## GPG - Demo - Alice's Cheat Sheet - Decrypting/Verifying - 🔓

* Decrypt a file:

      gpg --decrypt secret.txt.gpg

* verify a detached signature for a file:

      gpg --verify package_0.0.1.deb.sig

* Decrypt and verify a message (copy ascii armor text to stdin, then ^D):

      gpg --decrypt

* Decrypt a message with a hidden recipient:

      gpg --decrypt


---

# REDACTED - Public Key Encryption Intro with GnuPG - 🔐

a talk by `"Philip Freeman" <freeman@endlessm.com>`
aka...    `"Philip J Freeman" <elektron@halo.nu>`


## Questions?







## Slides:

https://github.com/ph1l/talks/blob/master/gnupg.md


---
