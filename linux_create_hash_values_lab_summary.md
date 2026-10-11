# Linux Security Lab: Create Hash Values

## Objective
Use Linux commands to generate SHA-256 hashes for two files, save the hash outputs, and compare them to check file integrity.

## Task 1 — Generate hashes

### 1. List and inspect the files
```bash
ls
cat file1.txt
cat file2.txt
```

Both files display the same visible EICAR antivirus test-string text. However, identical-looking output does not prove that the files are byte-for-byte identical.

### 2. Generate SHA-256 hashes
```bash
sha256sum file1.txt
sha256sum file2.txt
```

Hashes shown in the exemplar:

| File | SHA-256 hash |
|---|---|
| `file1.txt` | `131f95c51cc819465fa1797f6ccacf9d494aaaff46fa3eac73ae63ffbdfd8267` |
| `file2.txt` | `2558ba9a4cad1e69804ce03aa2a029526179a91a5e38cb723320e83af9ca017b` |

**Task 1 answers**
- Do the contents appear identical when displayed with `cat`? **Yes.**
- Do both files produce the same hash? **No.**

The different hashes indicate that the files' underlying contents differ, even though the displayed text looks the same. The exemplar does not identify the exact byte-level difference.

## Task 2 — Save and compare the hashes

### 1. Save each hash output to a separate file
```bash
sha256sum file1.txt >> file1hash
sha256sum file2.txt >> file2hash
```

The `>>` operator appends command output to a file, creating the file if it does not exist.

### 2. Display the saved hashes
```bash
cat file1hash
cat file2hash
```

### 3. Compare the hash-output files byte by byte
```bash
cmp file1hash file2hash
```

Expected exemplar output:
```text
file1hash file2hash differ: char 1, line 1
```

`cmp` reports the first difference in the two saved hash-output files. Here, the first character differs because the hash values differ.

**Task 2 answer:** **Yes**, `file1.txt` and `file2.txt` are different according to their SHA-256 hashes.

> Note: `cmp` compares `file1hash` with `file2hash`—the files containing the hash outputs—not the original text files directly.

## Command summary

| Command | Purpose |
|---|---|
| `ls` | List directory contents |
| `cat FILE` | Display a file's contents |
| `sha256sum FILE` | Calculate and display a file's SHA-256 digest |
| `>> FILE` | Append command output to a file |
| `cmp FILE1 FILE2` | Compare two files byte by byte and report the first difference |

## Key concepts

- **Hash/digest:** A fixed-length value calculated from input data by a hash function.
- **Integrity checking:** Comparing a calculated hash with a trusted reference hash can help detect unexpected changes.
- **Different hashes:** The two different SHA-256 values in this lab indicate that the files are not identical.
- **Hashing is not encryption:** A cryptographic hash is not intended to be decrypted to recover the original content.
- **Context matters:** A hash comparison is useful only when the reference hash is trustworthy. A matching hash is strong evidence of identical content, but a hash alone does not establish that a file is safe or authentic.

## Security relevance
Security analysts can use hashes to identify known files, check whether evidence or downloads have changed, and support malware triage. The EICAR string used in this lab is a standard antivirus test string, not a real malware sample; handle it according to the lab's instructions.

## Core takeaway
Files that look identical when printed may still contain different underlying bytes. Use `sha256sum` to calculate digests and compare them, and use `cmp` when you need to identify whether two files differ byte by byte.
