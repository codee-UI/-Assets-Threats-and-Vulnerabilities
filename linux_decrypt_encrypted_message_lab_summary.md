# Linux Lab: Decrypt an Encrypted Message

## Objective
Use Linux shell commands to inspect files, locate a hidden file, decode a Caesar cipher, and decrypt an AES-encrypted file with OpenSSL.

## Scenario
Files in `/home/analyst` have been encrypted. The task is to follow the instructions in `README.txt`, decode a hidden instruction file, and recover the encrypted message.

## Tasks and Commands

### 1. Inspect the home directory and read instructions

```bash
ls
cat README.txt
```

The directory contains `Q1.encrypted`, `README.txt`, and the `caesar` subdirectory. The README directs the analyst to find a hidden file inside `caesar`.

An explicit-path alternative shown in the exemplar is:

```bash
ls /home/analyst
```

### 2. Find and decode the hidden Caesar-cipher file

```bash
cd caesar
ls -a
cat .leftShift3
cat .leftShift3 | tr "d-za-cD-ZA-C" "a-zA-Z"
cd ~
```

- `ls -a` displays hidden files, whose names begin with a dot (`.`).
- `.leftShift3` contains text encrypted with a Caesar cipher shifted three letters.
- `tr` translates the shifted lowercase and uppercase letters back to their original alphabet positions.
- The decoded message provides the OpenSSL command needed for the next task.

### 3. Decrypt the encrypted file

Run the command revealed by the decoded instructions:

```bash
openssl aes-256-cbc -pbkdf2 -a -d -in Q1.encrypted -out Q1.recovered -k ettubrute
```

Then verify the output file and read the recovered message:

```bash
ls
cat Q1.recovered
```

The exemplar's recovered message confirms that the file was successfully decrypted and that the encryption key was recovered.

## Command Summary

| Command or option | Purpose |
|---|---|
| `ls` | Lists files and directories. |
| `ls -a` | Includes hidden files in the listing. |
| `cat FILE` | Prints a file's contents. |
| `cd caesar` | Changes into the `caesar` directory. |
| `cd ~` | Returns to the user's home directory. |
| `tr SET1 SET2` | Translates characters from one set to another. |
| `openssl aes-256-cbc` | Invokes OpenSSL's AES-256-CBC cipher operation. |
| `-pbkdf2` | Uses PBKDF2 for password-based key derivation. |
| `-a` | Handles Base64-encoded input/output. |
| `-d` | Selects decryption mode. |
| `-in Q1.encrypted` | Specifies the encrypted input file. |
| `-out Q1.recovered` | Specifies the recovered output file. |
| `-k ettubrute` | Supplies the lab's password. |

## Key Concepts

- **Hidden files:** Linux filenames beginning with `.` are hidden from ordinary `ls` listings; use `ls -a` to display them.
- **Caesar cipher:** A simple substitution cipher that shifts letters by a fixed number of alphabet positions. It is suitable for learning, not for protecting real data.
- **Symmetric encryption:** AES uses the same underlying secret key to encrypt and decrypt data; password-based decryption derives the key from a supplied password.
- **Encoding versus encryption:** The `-a` option concerns Base64 encoding, while AES provides encryption. Encoding alone does not make data confidential.
- **Recovery verification:** Confirm that `Q1.recovered` exists and inspect its contents after decryption.

## Security Relevance
This lab demonstrates how analysts can follow recovery instructions, inspect hidden files, identify a simple cipher, and use OpenSSL to recover encrypted data. In real incidents, passwords and keys should be handled securely and should not be embedded in scripts, shell history, or public documentation.

## End the Lab
1. Confirm that all three tasks are complete.
2. Click **End Lab** and confirm submission.
3. Optionally provide feedback.
4. Return to the course tab and refresh it if needed to register completion.

## Core Takeaway
Use basic Linux file commands to locate the recovery instructions, decode the Caesar-cipher text with `tr`, and decrypt the file with OpenSSL. The recovered file should be checked to confirm that decryption succeeded.
