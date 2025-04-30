# EX-NO-7-Implement-DES-Encryption-and-Decryption

## Aim:

To use the Data Encryption Standard (DES) algorithm for a practical application, such as securing sensitive data transmission in financial transactions.

## ALGORITHM:

1. DES is based on a symmetric key encryption technique that encrypts data in 64-bit blocks.
2. DES uses a Feistel network structure with 16 rounds of processing for encryption.
3. DES has a 64-bit key, but only 56 bits are used for encryption (the remaining 8 bits are for parity).
4. DES applies initial and final permutations along with 16 rounds of substitution and permutation transformations to produce ciphertext.

## Program:
```
def encrypt(message, key):
    encrypted = []
    key_length = len(key)
    for i in range(len(message)):
        encrypted_char = ord(message[i]) ^ ord(key[i % key_length])
        encrypted.append(encrypted_char)
    return encrypted

def decrypt(encrypted, key):
    decrypted = []
    key_length = len(key)
    for i in range(len(encrypted)):
        decrypted_char = chr(encrypted[i] ^ ord(key[i % key_length]))
        decrypted.append(decrypted_char)
    return ''.join(decrypted)

print("\n**Simulation of DES-like XOR encryption and decryption**\n")

message = input("Enter the message to encrypt: ")
key = input("Enter the encryption key: ")

encrypted_message = encrypt(message, key)
print("Original Message:", message)

print("Encrypted Message:", ' '.join(f'{char:02X}' for char in encrypted_message))

decrypted_message = decrypt(encrypted_message, key)
print("Decrypted Message:", decrypted_message)
```

## Output:
![Screenshot 2025-04-30 083253](https://github.com/user-attachments/assets/6bc19075-6862-49e1-ba4e-23462607a9dd)

## Result:
  The program is executed successfully

