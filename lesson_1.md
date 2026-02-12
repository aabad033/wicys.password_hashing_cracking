# John the Ripper Password Cracking Lab

Lab Title: Password Cracking Techniques Using John the Ripper

============================================================

LAB OBJECTIVE

In this lab you will practice multiple password cracking techniques using John the Ripper (JtR):

- Single crack mode
- Wordlist mode
- Wordlist with rules
- Incremental (brute force) mode
- Mask mode
- Understanding the .pot file

============================================================

IMPORTANT ETHICAL NOTICE

Only crack password hashes you are authorized to test.
Do NOT use real personal passwords.
Perform this lab in a controlled lab environment.
Unauthorized password cracking is illegal.

============================================================

SECTION 1 – SETUP

Step 1: Make sure unzip is installed

Debian/Ubuntu:
sudo apt install unzip

RHEL/CentOS:
sudo yum install unzip

Verify installation:
unzip -v

------------------------------------------------------------

Step 2: Extract the lab files

Navigate to the directory containing crackfiles.zip:
cd /path/to/your/files

Unzip the file:
unzip crackfiles.zip

You should now see:
crackA.txt
crackB.txt
crackC.txt
lower.lst

============================================================

SECTION 2 – CRACKING crackA.txt (Single Mode)

Run:
john --single crackA.txt

Show results:
john --show crackA.txt

What does --single do?

Single mode:
- Uses username information
- Tries variations of the username
- Applies built-in mangling rules
- Efficient for weak passwords

============================================================

SECTION 3 – CRACKING crackB.txt (Wordlist Mode)

Run:
john --wordlist=lower.lst crackB.txt

Show results:
john --show crackB.txt

What is Wordlist Mode?

- Tries every word in the dictionary file
- Effective against common passwords
- Faster than brute force

============================================================

SECTION 4 – Wordlist + Leetspeak Rules

Run:
john --wordlist=lower.lst crackB.txt --rules=l33t

Show results:
john --show crackB.txt

What does --rules=l33t do?

Applies character substitutions such as:
a becomes 4
e becomes 3
i becomes 1
o becomes 0
s becomes 5
t becomes 7

Example:
password becomes p455w0rd

============================================================

SECTION 5 – Toggle Case Rule (Upper/Lower Mix)

Run:
john --wordlist=lower.lst crackB.txt --rules

Show results:
john --show crackB.txt

This attempts variations such as:
password
Password
pAssword
PASSword

============================================================

SECTION 6 – CRACKING crackC.txt (Wordlist Attempt)

First attempt:
john --wordlist=lower.lst crackC.txt

Show results:
john --show crackC.txt

If unsuccessful, move to brute-force methods.

============================================================

SECTION 7 – Incremental Mode (Digits Only)

If the password contains only digits:

john --incremental=digits --min-length=4 --max-length=8 crackC.txt

Explanation:
--incremental=digits limits characters to numbers only
--min-length=4 sets minimum password length
--max-length=8 sets maximum password length

This reduces brute-force time by limiting the search space.

============================================================

SECTION 8 – Mask Mode Attack

If the password follows a known structure:
digit, uppercase letter, lowercase letter, lowercase letter

Run:
john --mask=?d?u?l?l crackC.txt

Mask definitions:
?d = digit
?l = lowercase letter
?u = uppercase letter
?a = all printable characters

Mask mode is efficient when part of the password pattern is known.

============================================================

SECTION 9 – The .pot File

John stores cracked passwords in:

~/.john/john.pot

The file contains entries formatted as:
hash:plaintext_password

Why this matters:

- Cracked passwords are stored in plaintext
- Anyone with system access can read the file
- John remembers previously cracked passwords

View the file:
cat ~/.john/john.pot

Delete the file (lab use only):
rm ~/.john/john.pot

IMPORTANT:
Do not crack your own real passwords.
John stores cracked passwords and they can be accessed later.

============================================================

DISCUSSION QUESTIONS

1. Why is wordlist mode faster than incremental mode?
2. Why do rules increase cracking success?
3. How does limiting character sets improve brute-force efficiency?
4. Why is plaintext storage of cracked passwords dangerous?
5. What characteristics make a password difficult to crack?

============================================================

KEY TAKEAWAYS

- Weak passwords fall quickly to dictionary attacks.
- Rules significantly enhance wordlist effectiveness.
- Brute force is powerful but resource-intensive.
- Mask attacks are efficient when patterns are known.
- Password cracking tools must be used responsibly.


