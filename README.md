# PRODIGY_CS_01

---

# **Caesar Cipher - Python Implementation**  

## **📌 About the Project**  
This project is a simple implementation of the **Caesar Cipher** algorithm in Python. The **Caesar Cipher** is a fundamental encryption technique where each letter in a given text is replaced by a letter some fixed number of positions down the alphabet. It is one of the simplest and oldest known encryption techniques.  

This program allows the user to **encrypt** and **decrypt** messages using a shift value. The shift value determines how many positions each letter should be moved in the alphabet.  

---

## **🔹 Features**
✅ Encrypts a message using a shift value  
✅ Decrypts an encrypted message back to its original form  
✅ Preserves uppercase and lowercase letters  
✅ Ignores numbers, symbols, and spaces (does not alter them)  
✅ Simple user input for interactive use  

---

## **📜 How the Caesar Cipher Works**
1. Choose a **shift value** (e.g., shift = 3).  
2. For **encryption**, shift each letter in the input forward by 3 places:  
   - `"HELLO"` → `"KHOOR"`  
3. For **decryption**, shift each letter backward by 3 places:  
   - `"KHOOR"` → `"HELLO"`  
4. Non-alphabetic characters remain unchanged (e.g., punctuation, spaces, numbers).  

---

## **🛠 Technologies Used**
- Python 3  
- String manipulation  
- ASCII encoding  

---

## **📌 Code Implementation**
```python
def caesar_cipher(text, shift, mode="encrypt"):
    result = ""
    
    if mode == "decrypt":
        shift = -shift  # Reverse the shift for decryption
    
    for char in text:
        if char.isalpha():
            start = ord('A') if char.isupper() else ord('a')
            result += chr(start + (ord(char) - start + shift) % 26)
        else:
            result += char
    
    return result


# Taking input from the user
message = input("Enter the message: ")
shift = int(input("Enter shift value: "))
mode = input("Choose mode (encrypt/decrypt): ").strip().lower()

# Processing the message
output = caesar_cipher(message, shift, mode)
print(f"Output: {output}")
```

---

## **💻 How to Run the Program**
1. Install **Python** (if not already installed).  
2. Copy the code into a new Python file (`caesar_cipher.py`).  
3. Run the script in a terminal or command prompt using:  
   ```
   python caesar_cipher.py
   ```
4. Enter a message and shift value when prompted.  
5. Choose **encryption** or **decryption** mode.  
6. The output will display the transformed text.  

---

## **🚀 Example Usage**
```
Enter the message: Hello World!
Enter shift value: 3
Choose mode (encrypt/decrypt): encrypt
Output: Khoor Zruog!
```
```
Enter the message: Khoor Zruog!
Enter shift value: 3
Choose mode (encrypt/decrypt): decrypt
Output: Hello World!
```

---
