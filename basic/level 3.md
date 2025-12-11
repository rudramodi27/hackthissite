# Level 3
This time Network Security Sam remembered to upload the password file, but there were deeper problems than that.

## 🎯 Objective
Find the hidden password stored on the server by analyzing the page source and linked files.

# solution

- I submitted “pass” in the password field and intercepted the request. It had the file “password.php”

- Like Mission 1, start by checking the page source. The HTML for the password form includes this line:
<input type="hidden" name="file" value="password.php" />.
Try navigating to https://www.hackthissite.org/missions/basic/3/password.php. When I go there I see the password as a plain-text string. Go back to the previous page, enter the password, and submit.
