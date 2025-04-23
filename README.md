# VIGENERE-CIPHER
## EX.NO:4 IMPLEMETATION OF VIGENERE CIPHER

## Name:NATARAJ KUMARAN S
## Reg No.212223230137
 
## AIM:

To implement the Vigenere Cipher substitution technique using C program.

## DESCRIPTION:

To encrypt, a table of alphabets can be used, termed a tabula recta, Vigenère square,or Vigenère table. It consists of the alphabet written out 26 times in differnt rows, each
 
alphabet shifted cyclically to the left compared to the previous alphabet, corresponding to the 26 possible Caesar ciphers. At different points in the encryption process, the cipher uses adifferent alphabet from one of the rows. The alphabet used at each point repeating keyword.depends on a Each row starts with a key letter. The remainder of the row holds the letters A to Z. Although there are 26 key rows shown, you will only use as many keys as there are unique letters in the key string, here just 5 keys, {L, E, M, O, N}. For successive letters of the message, we are going to take successive letters of the key string, and encipher each message letter using its corresponding key row. Choose the next letter of the key, go along that row to find the column heading that	atches the message character; the letter at the intersection of
[key-row, msg-col] is the enciphered letter.


## ALGORITHM:

STEP-1: Arrange the alphabets in row and column of a 26*26 matrix.

STEP-2: Circulate the alphabets in each row to position left such that the first letter is attached to last.

STEP-3: Repeat this process for all 26 rows and construct the final key matrix.

STEP-4: The keyword and the plain text is read from the user.

STEP-5: The characters in the keyword are repeated sequentially so as to match with that of the plain text.

STEP-6: Pick the first letter of the plain text and that of the keyword as the row indices and column indices respectively.

STEP-7: The junction character where these two meet forms the cipher character.

STEP-8: Repeat the above steps to generate the entire cipher text.


## PROGRAM:
```
def vigenere_encrypt(text, key):
    encrypted_text = []
    key_length = len(key)
    
    for i, char in enumerate(text):
        if 'A' <= char <= 'Z':
            shift = ord(key[i % key_length].upper()) - ord('A')
            encrypted_text.append(chr((ord(char) - ord('A') + shift) % 26 + ord('A')))
        elif 'a' <= char <= 'z':
            shift = ord(key[i % key_length].lower()) - ord('a')
            encrypted_text.append(chr((ord(char) - ord('a') + shift) % 26 + ord('a')))
        else:
            encrypted_text.append(char)  # Keep non-alphabetic characters unchanged
    
    return "".join(encrypted_text)

def vigenere_decrypt(text, key):
    decrypted_text = []
    key_length = len(key)
    
    for i, char in enumerate(text):
        if 'A' <= char <= 'Z':
            shift = ord(key[i % key_length].upper()) - ord('A')
            decrypted_text.append(chr((ord(char) - ord('A') - shift + 26) % 26 + ord('A')))
        elif 'a' <= char <= 'z':
            shift = ord(key[i % key_length].lower()) - ord('a')
            decrypted_text.append(chr((ord(char) - ord('a') - shift + 26) % 26 + ord('a')))
        else:
            decrypted_text.append(char)  
    
    return "".join(decrypted_text)

key = "VAR"
message = "saveethaengineeringcollege"

print("Simulating Vigenère Cipher:")
print("Original Message:", message)
print("Key:", key)

encrypted_message = vigenere_encrypt(message, key)
print("Encrypted Message:", encrypted_message)

decrypted_message = vigenere_decrypt(encrypted_message, key)
print("Decrypted Message:", decrypted_message)
```

## OUTPUT:

![image](https://github.com/user-attachments/assets/17bae89f-304c-42d9-afcc-a4d355778562)


## RESULT:
The program is executed successfully
