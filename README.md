## AES_256kryptkeeper (Encryption/Decryption Tool)

## overview
implements AES-256 bit encryption and decryption for files or messages using the pycryptodome library, featuring secure key derivation, random salt and IV generation, error handling, and a command-line interface for user interaction.

updated Readme:
Here’s a detailed **README** for your AES-256 encryption and decryption tool:

---

# AES-256 Encryption/Decryption Tool

This Python script provides **secure AES-256 encryption and decryption** functionality for files using a password-based key derivation. It ensures confidentiality and integrity through **PBKDF2 key derivation, CBC mode encryption, and padding mechanisms**.

## Prerequisites

Ensure you have **Python 3.x** installed, along with the necessary dependencies:

```bash
pip install pycryptodome
```

---

## Features
- **AES-256 encryption** with a random salt and IV.
- **PBKDF2-derived key** for better security.
- **Padding management** for handling non-block-size data.
- **Command-line interface (CLI)** for encrypting and decrypting files.

---

## How It Works

### 1. **Key Derivation**
The script derives a **secure key** from a **user-defined password** using **PBKDF2**.

### 2. **Encryption Process**
- **Generates a random salt** and **IV**.
- **Derives the encryption key** using PBKDF2.
- **Encrypts the file content** using **AES in CBC mode**.
- **Pads the plaintext** to match AES block size.
- **Combines salt, IV, and ciphertext**, encoding in Base64 for safe storage.

### 3. **Decryption Process**
- **Extracts salt, IV, and ciphertext** from the encoded data.
- **Derives the same key** using PBKDF2.
- **Decrypts the data** using AES-256.
- **Unpads the decrypted text** for proper formatting.

---

## Usage

### **Encrypting a File**
```bash
python script.py encrypt <file_path>
```
Example:
```bash
python script.py encrypt secret.txt
```
This will produce a **encrypted file** named `secret.txt.enc`.

### **Decrypting a File**
```bash
python script.py decrypt <file_path.enc>
```
Example:
```bash
python script.py decrypt secret.txt.enc
```
This restores the **original file**.

---

## Important Notes
- Ensure your password is **strong** and **secure**.
- Decryption **requires the correct password**; otherwise, the process will fail.
- Encrypted files will have a `.enc` extension.
- **Do not lose your password**, as it **cannot** be recovered.

---

## Improvements & Future Enhancements
- Adding **password validation** to prevent weak passwords.
- Supporting **other encryption modes** like GCM for authentication.
- Implementing a **GUI interface** for easier file encryption.

--prev vers readme:--


## a Python script that implements AES-256 encryption and decryption using the pycryptodome library. The script includes enhancements for security, robustness, versatility, and scalability.


This Python script provides a simple way to encrypt and decrypt files using the AES-256 algorithm. It utilizes the `pycryptodome` library for cryptographic operations.

## Features
- **Strong Encryption:** Employs AES-256, a widely used and robust encryption standard.
- **Password-Based:** Uses a user-provided password to derive the encryption key.
- **Salt and IV:** Incorporates salt and initialization vector (IV) for enhanced security.
- **PBKDF2 Key Derivation:** Uses PBKDF2 to generate a strong key from the password.
- **File Handling:** Can encrypt and decrypt files of any type.

## Requirements

- Python 3.6 or higher
- `pycryptodome` library

To install the required library, run:
(Use code with caution, if you encounter a PEP 668 error then try using google colab or a Jupyter Notebook.)

bash pip install pycryptodome

## Usage

1. **Encryption:**

Use code with caution
bash python aes_encrypt_decrypt.py encrypt

Replace `<file_path>` with the path to the file you want to encrypt. You will be prompted to enter a password.
   The encrypted file will be saved with a `.enc` extension.

2. **Decryption:**
Use code with caution
bash python aes_encrypt_decrypt.py decrypt

Replace `<encrypted_file_path>` with the path to the encrypted file (ending with `.enc`). You will be prompted to enter the same password used for encryption.
   The decrypted file will be saved with the original filename (without the `.enc` extension).

**Example:**

To encrypt a file named `data.txt`:
Use code with caution
bash python aes_encrypt_decrypt.py encrypt data.txt

To decrypt the encrypted file `data.txt.enc`:
Use code with caution
bash python aes_encrypt_decrypt.py decrypt data.txt.enc

## Security Considerations

- **Password Strength:** Use a strong and unique password for encryption. The security of your encrypted data depends heavily on the strength of your password.
- **Salt and IV:** The script generates random salt and IV for each encryption operation, ensuring that encrypting the same data with the same password will result in different ciphertexts.
- **PBKDF2:** PBKDF2 is a key derivation function that helps protect against brute-force attacks by making it computationally expensive to derive the encryption key from the password.

## Disclaimer
This tool is intended for educational purposes only. The purpose of this script is to teach python scripting and elementary cryptology.
Use this script at your own discretion, the author claims no liability for mods or unlawful use of the script. 

Acknowledgements: Microsoft Copilot (init commit) ~ Google Colab (testing) ~ ChatGPT-4.o (refinements) ~ Google Gemini (error fixes)

"Cryptoglogy is the ultimate form of non-violent direct action." -Julian Assange 
