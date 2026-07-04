# Cryptography-Ciphers 🔐

A collection of classical ciphers implemented as command-line tools, created as part of my **Introduction to Cryptography** course (Semester 6).  
This repository contains clean, standalone scripts for three fundamental encryption algorithms:

- **Caesar Cipher**
- **Affine Cipher**
- **Vigenère Cipher**

All scripts are designed to be run from the terminal, making them easy to test, integrate, or extend.

---

## 📚 Table of Contents

- [Ciphers Included](#-ciphers-included)
- [Prerequisites](#-prerequisites)
- [Installation](#-installation)
- [Usage](#-usage)
  - [Caesar Cipher](#caesar-cipher)
  - [Affine Cipher](#affine-cipher)
  - [Vigenère Cipher](#vigenère-cipher)
- [How Each Cipher Works](#-how-each-cipher-works)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🔍 Ciphers Included

| Cipher         | Type          | Key Space                                    |
|----------------|---------------|----------------------------------------------|
| Caesar         | Substitution  | Shift value (0–25)                           |
| Affine         | Substitution  | Two integers `a` and `b` (with `gcd(a,26)=1`)|
| Vigenère       | Polyalphabetic| A keyword (repeated to match plaintext)      |

---

## 🧰 Prerequisites

- **Python 3.6+** (all scripts are written in Python)
- No external libraries are required – only the standard library is used.

---

## 📦 Installation

Clone the repository and navigate into the project folder:

```bash
git clone https://github.com/your-username/Cryptography-Ciphers.git
cd Cryptography-Ciphers
```

Make sure the scripts are executable (if on Unix-like systems):

```bash
chmod +x caesar.py affine.py vigenere.py
```

---

## 🖥️ Usage

Each script accepts input either via command-line arguments or interactive prompts (depending on the implementation). Below are typical usage examples.

### Caesar Cipher

**Encrypt** a message with a shift of 3:

```bash
python caesar.py -e "HELLO" -s 3
```

**Decrypt** with the same shift:

```bash
python caesar.py -d "KHOOR" -s 3
```

Alternatively, you can run without flags and follow the interactive prompts.

---

### Affine Cipher

The affine cipher uses two keys: `a` (must be coprime with 26) and `b`.

**Encrypt** with `a=5`, `b=8`:

```bash
python affine.py -e "CRYPTO" -a 5 -b 8
```

**Decrypt** with the same keys:

```bash
python affine.py -d "MZ..." -a 5 -b 8
```

*Note: The script will validate that `a` is coprime with 26; if not, it will raise an error.*

---

### Vigenère Cipher

The Vigenère cipher uses a keyword.

**Encrypt** with key `"KEY"`:

```bash
python vigenere.py -e "ATTACKATDAWN" -k "KEY"
```

**Decrypt** with the same key:

```bash
python vigenere.py -d "KX..." -k "KEY"
```

The key is case-insensitive and non-alphabetic characters (spaces, punctuation) are usually preserved.

---

### 📝 General Notes

- All scripts preserve case by default (you can modify the source to suit your needs).
- Non‑alphabetic characters (spaces, numbers, punctuation) are typically left unchanged.
- Use `-h` or `--help` with any script to see the full list of options:

```bash
python caesar.py -h
```

---

## 📖 How Each Cipher Works

### Caesar Cipher
A substitution cipher where each letter in the plaintext is shifted a fixed number of positions down the alphabet.  
*Example:* Shift of 3: `A → D`, `B → E`, ... `X → A`, etc.

### Affine Cipher
A monoalphabetic substitution that uses a linear function to map letters:  
`E(x) = (a*x + b) mod 26`  
where `a` and `b` are keys, and `a` must be coprime with 26. The decryption uses the modular inverse of `a`.

### Vigenère Cipher
A polyalphabetic cipher that uses a keyword to determine multiple shift values. Each letter of the plaintext is shifted by the corresponding letter of the keyword (repeated as needed), making it more resistant to frequency analysis than simple substitution.

---

## 🤝 Contributing

This is a personal learning project, but suggestions and improvements are welcome!  
Feel free to open an issue or submit a pull request for:

- Bug fixes
- Additional ciphers (e.g., Transposition Ciphers,)
- Better argument parsing or interactive menus
- Unit tests

Please ensure your code is well-documented and follows PEP 8 conventions.

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).  
Feel free to use, modify, and distribute it as you wish.

---

*Happy encrypting!* 🔑
