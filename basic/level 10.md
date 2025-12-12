# level 10
Please enter a password to gain access to level 10

# objective
 Learn how to inspect and manipulate browser cookies to bypass client‑side authentication.

 # solution
- The hint pointed toward JavaScript, so I inspected the cookies using document.cookie in the browser Console.
  ```
  javascript:alert(document.cookie)
  ```
- The site stored an authorization flag: level10_authorized=no,
- which clearly controlled access. Since this validation happens on the client side, I simply modified the cookie value to yes using:
```
javascript:alert(document.cookie="level10_authorized=yes")
```
- After updating the cookie, submitting the form immediately granted access without needing a password. This shows how insecure client‑side authentication can be.
