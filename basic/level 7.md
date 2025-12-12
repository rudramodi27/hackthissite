# level 7 
This time Network Security sam has saved the unencrypted level7 password in an obscurely named file saved in this very directory.

In other unrelated news, Sam has set up a script that returns the output from the UNIX cal command. Here is the script:

Enter the year you wish to view and hit 'view'.

# objective
Understand that the password is stored in a hidden include file which can be accessed directly through the site’s directory.

# Solution
Unix command is a hint of command injection. I used ‘;’ to run multiple commands.
Command: 2025;ls (; is encoded)
<img width="504" height="337" alt="Screenshot 2025-12-12 112448" src="https://github.com/user-attachments/assets/6edb89cc-7064-497a-8d72-6494b2613359" />
- I found the random file “klkh….php” in response.
- I tried to use cat for reading the file but it did not work then I decided to visit the URL.
- ![1_CPR-xlRwaPrjhbBZboTAMg](https://github.com/user-attachments/assets/23c30e8d-3094-4477-875b-6b81007024c9)
