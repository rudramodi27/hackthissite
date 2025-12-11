# Level 4
his time Sam hardcoded the password into the script. However, the password is long and complex, and Sam is often forgetful. So he wrote a script that would email his password to him automatically in case he forgot. Here is the script:

## 🎯 Objective
Bypass a form that looks secure but actually sends the data using a **GET request**, making the password visible in the URL.
# solution
- If you click the 'Send password to Sam' button, you'll see it indeed sends a password reminder email. Next, check the page source. 
- There's this line in the HTML:
<input type="hidden" name="to" value="sam@hackthissite.org" />
What if you change the email address to your own (or more specifically, the email address you used to sign up for Hack this Site)? Edit the value attribute using Developer Tools and click the password reset button. The password should be emailed to you.
