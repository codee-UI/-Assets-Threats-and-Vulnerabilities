# Linux Lab Summary: Decrypt an Encrypted Message

## Objective
Use Linux shell commands to inspect a home directory, locate and decode a hidden Caesar-cipher instruction file, and decrypt an encrypted file with OpenSSL.

## Scenario
The files in `/home/analyst` have been encrypted. The `README.txt` file directs the analyst to find a hidden file inside the `caesar` directory. That hidden file reveals the command needed to decrypt `Q1.encrypted`.

## Task 1 — Inspect the home directory

```bash
ls /home/analyst
cat README.txt
```

The directory contains `Q1.encrypted`, `README.txt`, and the `caesar` subdirectory. The README explains that a hidden file in `caesar` contains the recovery instructions.

## Task 2 — Find and decode the hidden file

```bash
cd caesar
ls -a
cat .leftShift3
cat .leftShift3 | tr "d-za-cD-ZA-C" "a-zA-Z"
cd ~
```

- `cd caesar` changes to the subdirectory.
- `ls -a` lists all entries, including hidden files. Linux filenames beginning with `.` are hidden by convention.
- `.leftShift3` contains text encoded with a Caesar cipher shifted by three letters.
- `tr` translates each character in the first character set to its corresponding character in the second set. The mapping reverses the three-letter shift and reveals the recovery command.
- `cd ~` returns to the analyst's home directory.

The decoded instruction provides this command:

```bash
openssl aes-256-cbc -pbkdf2 -a -d -in Q1.encrypted -out Q1.recovered -k ettubrute
```

## Task 3 — Decrypt the encrypted file

```bash
openssl aes-256-cbc -pbkdf2 -a -d -in Q1.encrypted -out Q1.recovered -k ettubrute
ls
cat Q1.recovered
```

The OpenSSL command decrypts `Q1.encrypted` and writes the recovered plaintext to `Q1.recovered`.

| Option or component | Meaning in this command |
|---|---|
| `openssl` | Runs the OpenSSL command-line toolkit. |
| `aes-256-cbc` | Selects AES with a 256-bit key in CBC mode. |
| `-pbkdf2` | Uses PBKDF2 for password-based key derivation. |
| `-a` | Uses Base64 encoding/decoding for the encrypted data representation. |
| `-d` | Decrypts rather than encrypts. |
| `-in Q1.encrypted` | Specifies the encrypted input file. |
| `-out Q1.recovered` | Specifies the output file for recovered plaintext. |
| `-k ettubrute` | Supplies the lab's password. Do not reuse this example password in real systems. |

**Source limitation:** The exemplar explains that `cat Q1.recovered` displays a message, but the pasted source does not show the actual recovered message. Therefore, this summary does not infer or invent its contents.

## Command summary

| Command | Purpose |
|---|---|
| `ls` | Lists directory contents. |
| `cat FILE` | Prints a file's contents. |
| `cd DIR` | Changes the current directory. |
| `ls -a` | Includes hidden entries in the listing. |
| `tr SET1 SET2` | Translates characters according to corresponding character sets. |
| `openssl ... -d` | Decrypts the specified encrypted file. |

## Key concepts

- **Caesar cipher:** A simple substitution cipher that shifts letters by a fixed number of positions. It is educational, not suitable for protecting real data.
- **Hidden files:** On Linux, names beginning with a period are omitted from ordinary `ls` output unless hidden entries are requested.
- **Encoding vs. encryption:** Base64 is an encoding representation, not encryption by itself. AES provides the cryptographic transformation; the password-based key derivation option helps derive key material from a password.
- **File recovery:** Decryption writes the recovered content to a separate output file, leaving the encrypted input file in place.

## Security relevance
Security analysts may need to inspect hidden files, recognize simple obfuscation, and use approved tools to recover data. In real incidents, only decrypt files when authorized, protect passwords and recovered plaintext, and use modern, properly configured cryptography rather than Caesar ciphers or hard-coded passwords.

## Core takeaway
The lab combines Linux file navigation, hidden-file discovery, character translation with `tr`, and file decryption with OpenSSL. The Caesar cipher reveals the command; OpenSSL performs the actual decryption.
