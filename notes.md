# HTTP observations (Lab 4, Task 1)

| Question | My answer |
|----------|-----------|
| Request method for index.html | GET |
| Status code with Disable cache ticked | 200 |
| Status code on a normal reload | 304 |
| Status code for /nothing-here.html | 404 |
| Value of the Content-Type response header | text/html |
| Remote Address (IP and port) | [::1]:80 |
| Protocol in the address bar (http or https) | http |

## Why is this address http and not https?

My address is http because the site runs on my own computer (localhost) with XAMPP, which has no security certificate. Https needs a certificate from a trusted authority, which a live site like GitHub Pages has.

## Specificity experiment

"#main p" turned the hero text red because an id is stronger than a class.
After I changed it to "main p", the text became white again because a class
is stronger than element names. The winner depends on the selector's
strength, not on which rule comes first.

## Selectors I used

| Selector kind | Example from my CSS |
|---|---|
| Element | `body` |
| Class | `.card` |
| ID | `#main` |
| Grouping (comma) | `h1, h2, h3` |
| Descendant (space) | `.nav-list a` |
| Child (>) | `main > section` |
| Adjacent sibling (+) | `h1 + p` |
| Compound (no space, such as a.active) | `a.active` |
| Attribute | `a[href^="http"]` |
| Pseudo-class | `a:hover` |
| Pseudo-element | `.menu-group h2::before` |

## Bug log (Lab 4, Task 6)

| # | What was wrong (file and line) | Which tool showed it | My fix |
|---|---|---|---|
| 1 | bugs.html line 7: `href="style.css"` but the file is bugs.css | Network tab (404) | `href="bugs.css"` |
| 2 | bugs.css: selector `.notes` but the HTML uses `class="note"` | Styles pane | Rename the selector to `.note` |
| 3 | bugs.css `.btn:hover`: no `;` after `background: #0b1f3a` | Styles pane | Add the `;` |
| 4 | bugs.css `.btn`: `colour` is not a CSS property | Styles pane | Change it to `color` |
| 5 | bugs.html: links are in `<div class="menu">`, so there is no navigation landmark | Accessibility tree | Use `<nav>` |
| 6 | bugs.html line 17: `<h4>` right after `<h1>`, skipping heading levels | Accessibility tree, Lighthouse, validator | Change it to `<h2>` |
| 7 | bugs.html line 18: `<img>` has no alt attribute | Lighthouse, validator | Add `alt="Campus Café logo"` |
| 8 | bugs.html line 21: `<label for="mail">` but the input has `id="email"` | Lighthouse, validator | Change it to `for="email"` |
| 9 | bugs.html line 2: `<html>` has no lang attribute | Lighthouse, validator | Change it to `<html lang="en">` |
| 10 | bugs.css `.menu a`: the Home and Menu links had only a margin, so the touch targets were too small and too close | Lighthouse (Touch targets, found only after the other fixes) | `display: inline-block` and `padding: 12px` |

## Live site observations (Lab 4, Task 7)

1. On localhost the address was http, the server was Apache from XAMPP, and the Remote Address was [::1]:80. On the live site the address is https, the server is GitHub.com, the protocol is h2, and the Remote Address is 185.199.111.153:443. It changed because the live site runs on GitHub's servers, which use a certificate and encrypted https on port 443, while my localhost server is only on my own computer and uses plain http on port 80.

2. The padlock means the connection is encrypted and the certificate was issued by Let's Encrypt for *.github.io, valid from 1 October 2026 to 30 December 2026. If the site were plain http, an attacker on the same Wi-Fi could read or change the data sent between my browser and the server.

3. The Saved orders table was empty on the live site because localStorage belongs to an origin (protocol, domain and port). The live site, https://ridaahassan.github.io, is a different origin from http://localhost, so it has its own empty storage and cannot see the orders I saved on localhost.

4. The missing page returned status 404 (File not found). It was sent by GitHub's server, not by my website.