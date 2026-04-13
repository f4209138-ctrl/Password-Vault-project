Secure Password Generator & Vault 🔐
A lightweight, locally-hosted desktop application that generates highly secure passwords and safely stores them using symmetric encryption. Built with Python and Tkinter, this tool ensures your credentials never leave your machine and are guarded by a unique 3-tier master password system.

Available as a standalone executable (.exe) for Windows, requiring no installation or Python environment setup!

✨ Features
Triple-Factor Master Login: Requires exactly three master passwords to derive the decryption key, adding complexity against brute-force attacks.

Strong Password Generation: Automatically generates secure 16-character passwords containing uppercase letters, lowercase letters, numbers, and special symbols.

Local AES Encryption: Uses the cryptography.fernet library to encrypt your data locally. Your credentials are saved to an encrypted file (my_vault.enc) in the same directory.

Read & Manage: Easily view your decrypted vault within the app.

Delete Entries: Target and remove specific website credentials from your vault, automatically re-encrypting the remaining data.

🛡️ How the Security Works
This application does not store your master passwords anywhere. Instead, it uses a Key Derivation mechanism:

The three master passwords you enter are combined.

The combined string is hashed using SHA-256.

That hash is encoded into a URL-safe base64 string to create a valid Fernet Key.

This key is used to decrypt the vault file upon login and re-encrypt it when saving new entries.

⚠️ CRITICAL WARNING: Because the master passwords are never saved, there is no "Forgot Password" feature. If you forget any of your three master passwords, you will permanently lose access to your vault.

🚀 Usage Instructions
Running the Executable (.exe)
If you just want to use the app without touching the code:

Download the latest .exe file from the Releases tab.

Place the executable in a dedicated folder (e.g., Documents/PasswordVault). Note: The encrypted vault file (my_vault.enc) will be generated in the same folder as the executable.

Double-click to run.

Running from Source
If you prefer to run the Python script directly:

Clone the repository:

Bash
git clone https://github.com/yourusername/your-repo-name.git](https://github.com/f4209138-ctrl/Password-Vault-project.git
Install the required dependencies:

Bash
pip install cryptography
(Note: tkinter, hashlib, and base64 are included in Python's standard library).

Run the script:

Bash
python vault_app.py
📂 File Structure
vault_app.py: The main Python source code.

my_vault.enc: The encrypted vault file (automatically generated upon your first save). Do not delete this file unless you want to wipe your vault.

🛠️ Built With
Python 3

Tkinter (GUI Framework)

Cryptography (Fernet symmetric encryption)
