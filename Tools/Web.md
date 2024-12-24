# Tools for Web Explotation ──★

Actually, this is for me to refer, because I have halmeoni's memory hehe... Let's gaurr !!

### robots.txt
Of course, in web challenges. Always check for this part first, it could contains hints, hidden paths, or clues.

Usage:

 http://example.com/robots.txt

---

### Website's Payload
There is a loooooooot, so I will just attach hyperlink of another person's github.

https://github.com/swisskyrepo/PayloadsAllTheThings

---

### Cookie Editor
A cookie editor is a tool (often a browser extension or built-in developer tool) that allows users to view, edit, delete, or create cookies stored by websites in their browsers. These cookies often store session data, preferences, or other user-specific information.

Built in extension such as **'EditThisCookie' / 'CookieEditor'**
or use **BurpSuite** that can intercept and modify HTTP cookie in real-time.

Usage:

1) Modify Session Tokens 
- Edit the session token to impersonate another user and bypass authentication:

    > from { user = guest} --> { user = admin }
