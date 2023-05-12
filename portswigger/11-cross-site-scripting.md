# Cross-site scripting
- allow attacker to compromise interactions that user have with web app
- bypass same origin policy
- masquerade as victim user & carry out any actions that user is able to perform 
- access user's data
- deface site
- inject trojan into site

# how it works?
- manipulate a site, so it returns malicious javascript
- user executes the js, & attacker compromise the interaction

# types
1. reflected XSS
2. stored XSS
3. DOM-based XSS

# reflected XSS
- http request contains malicious script
- https://example.com/?search=<script>alert()</script>

# stored XSS
- persistent or second-order XSS
- script comes from website's database
- e.g., user comment box -> stored script -> display to other users

```
POST /post/comment HTTP/1.1
Host: example.com
Content-Length: 100

postId=3&comment=lol+this+sucks&name=Jack&email=jack@gmail.com

// comment box shows
<p>lol this sucks</p>

// url encode 
// <script>alert()</script>
comment=%3Cscript%3Ealert%28%29%3C%2Fscript%3E
```

# DOM-based XSS
- exists in client side
