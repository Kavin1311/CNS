# NAME:T.KAVINAJAI
# REGISTER NO: 212223100020
## EX. NO: 1(A) : IMPLEMENTATION OF CAESAR CIPHER
 

## AIM:

To implement the simple substitution technique named Caesar cipher using C language.

## DESCRIPTION:

To encrypt a message with a Caesar cipher, each letter in the message is changed using a simple rule: shift by three. Each letter is replaced by the letter three letters ahead in the alphabet. A becomes D, B becomes E, and so on. For the last letters, we can think of the
alphabet as a circle and "wrap around". W becomes Z, X becomes A, Y bec mes B, and Z
becomes C. To change a message back, each letter is replaced by the one three before it.

## EXAMPLE:



![image](https://github.com/Hemamanigandan/CNS/assets/149653568/eb9c6c43-8c80-4cdd-b9d4-91705a311c79)


## ALGORITHM:

### STEP-1: Read the plain text from the user.
### STEP-2: Read the key value from the user.
### STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.
### STEP-4: Else subtract the key from the plain text.
### STEP-5: Display the cipher text obtained above.


PROGRAM :-
```
def caesar_cipher(text, key, mode='encrypt'):
    result = ""
    for char in text:
        if char.isalpha():
            ascii_offset = ord('A') if char.isupper() else ord('a')
            if mode == 'encrypt':
                shifted = (ord(char) - ascii_offset + key) % 26 + ascii_offset
            else: 
                shifted = (ord(char) - ascii_offset - key) % 26 + ascii_offset
            result += chr(shifted)
        else:
            result += char
    
    return result
if __name__ == "__main__":
    message = input("Enter a message to encrypt: ")
    key = int(input("Enter the key (0-25): "))
    
    encrypted = caesar_cipher(message, key, 'encrypt')
    print(f"Encrypted message: {encrypted}")
    
    decrypted = caesar_cipher(encrypted, key, 'decrypt')
    print(f"Decrypted message: {decrypted}")
```

OUTPUT :-
![image](https://github.com/user-attachments/assets/6e009a22-ff16-46f7-a024-bbc625215482)

