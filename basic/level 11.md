# level 11
Sam decided to make a music site. Unfortunately he does not understand Apache. This mission is a bit harder than the other basics.

# objective
Understand and exploit client-side validation and URL parameters to bypass password checks and access the mission.

# solution
- Not understanding Apache is a clue, because directory listing in Apache is often enabled by default. This means a user can map out subdirectories of your site if he or she successfully enters in a URL which resolves to a directory path.
- When you load the mission, text like 'I love my music! "Georgia " is the best!' appears. If you referesh the page, a new song appears in the text. All of these are songs by Elton John.
 Given that we know directory listing is probably enabled, try navigating to some URL structures to see if they work. https://www.hackthissite.org/missions/basic/11/a/, https://www.hackthissite.org/missions/basic/11/b/, etc.
-Eventually https://www.hackthissite.org/missions/basic/11/e/ works. Click through the ensuing directories you discover and you'll end up at
https://www.hackthissite.org/missions/basic/11/e/l/t/o/n/.
- This directory seems empty, but try accessing the .htaccess file at https://www.hackthissite.org/missions/basic/11/e/l/t/o/n/.htaccess.
- The .htaccess file loads, revealing these contents:
```
IndexIgnore DaAnswer.* .htaccess
<Files .htaccess>
require all granted
</Files>
```
Navigate to https://www.hackthissite.org/missions/basic/11/e/l/t/o/n/DaAnswer/. I saw something like this: 'The answer is not here! Just look a little harder.'

Now navigate to https://www.hackthissite.org/missions/basic/11/index.php, enter 'not here' as your password (or whatever the text changes to if the text you see is different), click through, click Go On, and you're done.
