# level 6

Network Security Sam has encrypted his password. The encryption system is publically available and can be accessed with this form:
Please enter a string to have it encrypted. 

- You have recovered his encrypted password. It is:
84eh:f>7
  
## 🎯 Objective
Understand how insecure server-side password comparison works and use it to bypass the authentication.

# solution
📌 This challenge can only be solved by analyzing the ASCII table and tracking how each character is shifted based on its position in the string
- Try encrypting several inputs and see what outputs you get. The input which was useful for me was 12345. The encrypted result was 13579.
- This helped me realize the encryption is nothing more than shifting the input n characters on an ASCII table like this, n being the spot the character is in in the input string. So, 12345 becomes: 1 (n = 0, so 1 + 0 = 1) 2 (n = 1, so 2 + 1 = 3) 3 (3 + 2 = 5) 4 (4 + 3 = 7) and so on.
- We know the encrypted password, so reverse it using the same pattern and looking at an ASCII table. 84eh:f>7 becomes 83ce6a80.
