# Introduction to Hashing
Feel free to use this as reference or study source!

## What is Hashing?

Hashing is a method used to permanently transform data into a fixed-length output, usually meant for sensitive information such as passwords, messages, and documents.
(* Please note, the term encryption simply means the act of hiding a secret message which can be decoded, while hashing is irreversible)

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/614d239a-9cc8-4c50-bd1b-46340e5e96e4" />

## How does it work?
Hashing works by converting data into these fixed-length strings, or hash values, by using a special algorithm called a hash function.

 <img width="500" height="300" alt="image" src="https://bec49d6c.delivery.rocketcdn.me/wp-content/uploads/2024/06/what-is-hashing.png" />


- The same input always produces the same hash
- Even a tiny change in input creates a completely different hash
- Hashes cannot be reversed back into the original data



## Common passward cracking techniques

- Dictionary attack- A dictionary attack is a cyber threat where attackers use lists of common words and passwords to guess login credentials.
- Brute Force- Automated scripts used to tryout all the possible passwords until the correct one works. Brute-force attacks can be very time consuming because they take a systematic approach to trying all possible permutations of characters in a sequence. The longer the password, the longer it takes. 
- Hybrid attack- Hybrid attacks are a mix of dictionary attacks and brute force. In this case, a bad actor may get a user’s compromised password for one site. The user learns it has been compromised and changes it. The attacker will now try out variations of the old password using a brute force method that automates the additions of numbers, letters and more. 
