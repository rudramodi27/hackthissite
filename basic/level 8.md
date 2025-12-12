# Level 8
Sam remains confident that an obscured password file is still the best idea, but he screwed up with the calendar program. Sam has saved the unencrypted password file in /var/www/hackthissite.org/html/missions/basic/8/
- However, Sam's young daughter Stephanie has just learned to program in PHP. She's talented for her age, but she knows nothing about security. She recently learned about saving files, and she wrote a script to demonstrate her ability.
- Enter your name:

# Objective
Understand how to inspect and analyze client‑side JavaScript to reveal and reverse the password validation logic.

# solution
Like Mission 7, this challenge also gives two hints:

1. The password is stored in a file inside the same directory.

2. The solution involves using PHP / server‑side commands.

- Initially, inputs similar to Mission 7 did not work, but it was clear the idea was still related to directory listing and server‑side include injections (SSI).
After researching SSI injection, I tested common characters like <, >, and #. When I entered <>, the page incorrectly reported the name length, which confirmed that the input was being interpreted by the server.

I then tried SSI commands.
<!--#exec cmd="ls -lsa" --> didn’t fully work, but it indicated I was close.

However:
```
<!--#exec cmd="ls" --> successfully listed several .shtml files.
```
- The output showed I was inside the /tmp/ directory, not /missions/basic/8/.

So I moved one directory up:
```
<!--#exec cmd="ls ../" -->
```
- This revealed a randomly‑generated PHP filename (example: au12ha39vc.php).
Opening it directly in the browser:
```
https://www.hackthissite.org/missions/basic/8/au12ha39vc.php
```

displayed the final password.
