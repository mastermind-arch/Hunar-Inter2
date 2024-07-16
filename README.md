

---

# Encryption and Decryption Tool

This Python script implements a simple encryption and decryption tool using AES (Advanced Encryption Standard). Users can securely encode and decode messages or files using this tool, ensuring confidentiality of sensitive information.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)


## Installation

To use this tool, ensure you have Python 3.8 or higher installed on your system.

# Clone the repository:
#from Crypto.Cipher import AES
 from Crypto.Random import get_random_bytes
 from base64 import b64encode, b64decode

# Generate a random key and initialization vector (IV)
#key = get_random_bytes(16)  # 16 bytes for AES-128, 24 bytes for AES-192, 32 bytes for AES-256
 iv = get_random_bytes(AES.block_size)

# Encrypt a message
 def encrypt_message(message, key, iv):
     cipher = AES.new(key, AES.MODE_CFB, iv)
    encrypted_bytes = cipher.encrypt(message.encode())
    return b64encode(encrypted_bytes).decode()

# Decrypt a message
 def decrypt_message(encrypted_message, key, iv):
    cipher = AES.new(key, AES.MODE_CFB, iv)
    decrypted_bytes = cipher.decrypt(b64decode(encrypted_message))
    return decrypted_bytes.decode()

# Example usage with input
# def main():
    print("AES Encryption and Decryption Example")
    print("------------------------------------")

    # Example: Encrypt and Decrypt user input
    user_input = input("Enter a message to encrypt and decrypt: ")

    encrypted_message = encrypt_message(user_input, key, iv)
    print(f"Encrypted message: {encrypted_message}")

    decrypted_message = decrypt_message(encrypted_message, key, iv)
    print(f"Decrypted message: {decrypted_message}")

# if __name__ == "__main__":
    main()


## Usage

### Encrypting a Message

To encrypt a message, run the script and follow the prompts:

```bash
python encryption_tool.py --encrypt "your_message"
```

Replace `"your_message"` with the message you want to encrypt.

### Decrypting an Encrypted Message

To decrypt an encrypted message, run the script and follow the prompts:

```bash
python encryption_tool.py --decrypt "encrypted_message"
```

Replace `"encrypted_message"` with the encrypted message you want to decrypt.

## Contributing

Contributions and feedback are welcome! Feel free to fork the repository and submit pull requests.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Create a new Pull Request

