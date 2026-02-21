# 🎰SHA-256 Hash Generator
<img src = https://github.com/user-attachments/assets/fbcc5de4-3af6-4719-b72c-67c6a60ced49 width = 800 height = 170/>

# 🔍Description
SHA-256 (Secure Hash Algorithm 256) is a cryptographic hash function from the SHA-2 family, designed by the NSA. It takes an input of any size and produces a fixed 256-bit (32-byte) output, represented as a 64-character hexadecimal string. It's a one-way function, meaning it's computationally infeasible to reverse-engineer the original input from the hash, making it ideal for security purposes. SHA-256 is collision-resistant (hard to find two inputs with the same hash) and avalanche-effect sensitive (small input changes yield vastly different outputs).
Other similar hashes include:

>***SHA-1***: An older 160-bit hash, now considered insecure due to collision vulnerabilities.

>***SHA-224***, ***SHA-384***, ***SHA-512***: Fellow SHA-2 family members with varying output sizes (224, 384, and 512 bits) for different security needs.

>***MD5***: A 128-bit hash, fast but broken for security due to easy collisions.

>***BLAKE2***: A modern, faster alternative to SHA-2 with similar security for hashing.

## 🔗Usages of SHA-256 hashes include:

***Password storage***: Hashing passwords in databases to protect against breaches (often with salting).

***Data integrity verification***: Ensuring files or messages haven't been tampered with (e.g., checksums in downloads).

***Digital signatures and certificates***: In SSL/TLS for secure web communications.

***Blockchain and cryptocurrencies***: Bitcoin uses SHA-256 for mining and transaction verification.

***General security***: Fingerprinting data, like in version control systems (e.g., Git) or forensic analysis.

## 🐍Python's Hashlib Library
Python's hashlib is a standard library module that provides a common interface to many secure hash and message digest algorithms. It allows developers to generate hashes efficiently without implementing algorithms from scratch, supporting both cryptographic and non-cryptographic uses. It's built on OpenSSL for performance and security.
Capabilities and usages:

>***Supports a wide range of algorithms***: Including MD5, SHA-1, SHA-224, SHA-256, SHA-384, SHA-512, BLAKE2b, BLAKE2s, and others via hashlib.algorithms_guaranteed and hashlib.algorithms_available.

>***Incremental hashing***: Update hashes in chunks for large data (e.g., files) using update() method, avoiding memory overload.

>***Hex and binary outputs***: Get results as hexadecimal strings (hexdigest()) or bytes (digest()).

>***Usages***: Password hashing/verification, file integrity checks (e.g., comparing hashes of downloads), digital signatures, token generation in web apps, and building custom security tools like the hash cracker in the provided code. It's often combined with salting or key derivation (e.g., via PBKDF2) for enhanced security.

# 💻Software + Modules Used
- Windows 11 Host
- Python v3.13.1
- PyCharm
- PyFiglet Module(apt install Pyfiglet or pip install Pyfiglet)
- Hashlib Module(hashlib.sha256)
- 

# 🎰SHA-256 Generator 
>The code is a simple command-line tool for generating or cracking SHA-256 hashes, using a banner for aesthetics and basic error handling. Here's a step-by-step breakdown:
>Import necessary modules: ***hashlib*** for hashing, ***pyfiglet*** for ASCII art, and ***time*** for delays.
- Generate and print an ASCII banner using pyfiglet.figlet_format with "SHA-256 Hash Generator" in slant font, followed by a note that it's for SHA-256 only.
  
- Enter an infinite loop to handle user choices until an invalid input breaks it.
  
- Prompt the user to choose 'E' (Encode) or 'D' (Decode/Crack) and convert input to uppercase.

### If 'D' is chosen
- Ask for the wordlist file path and the target SHA-256 hash.
- Add timed delays with print statements to simulate "cracking" progress (e.g., "Cracking...", "Wordlist: [path]", etc.).
- Try to open the wordlist file with UTF-8 encoding (ignoring errors).
- For each line in the file: Strip whitespace, encode to bytes, compute SHA-256 hash, get hex digest, and compare to the target hash.
- If a match is found, print the cleartext password and break.
- If no match after all lines, print "Password not found" and continue the loop.
- Handle exceptions: FileNotFoundError (suggest checking path/hash) and PermissionError (note permission denied).

### If 'E' is chosen
- Ask for text input.
- Compute SHA-256 hash of the encoded input.
- Print the hexadecimal digest.

### If neither 'E' nor 'D'
- print "Invalid Choice" and break the loop.
