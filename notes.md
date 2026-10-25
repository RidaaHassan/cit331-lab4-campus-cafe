# HTTP observations (Lab 4, Task 1)
 
| Question | My answer |
|----------|-----------|
| Request method for index.html | ... |
| Status code with Disable cache ticked | ... |
| Status code on a normal reload | ... |
| Status code for /nothing-here.html | ... |
| Value of the Content-Type response header | ... |
| Remote Address (IP and port) | ... |
| Protocol in the address bar (http or https) | ... |
 
## Why is this address http and not https?
... (two sentences)
## Specificity experiment
"#main p" turned the hero text red because an id is stronger than a class.
After I changed it to "main p", the text became white again because a class
is stronger than element names. The winner depends on the selector's
strength, not on which rule comes first.
## Selectors I used

| Selector kind | Example from my CSS |
|---|---|
| Element | body |
| Class | .card |
| ID | #main |
| Grouping (comma) | h1, h2, h3 |
| Descendant (space) | .nav-list a |
| Child (>) | main > section |
| Adjacent sibling (+) | h1 + p |
| Compound (no space, such as a.active) | a.active |
| Attribute | a[href^="http"] |
| Pseudo-class | a:hover |
| Pseudo-element | .menu-group h2::before |
## Bug log (Lab 4, Task 6)

| # | What was wrong (file and line) | Which tool showed it | My fix |
|---|---|---|---|
| 1 | bugs.html line 7: href="style.css" but the file is bugs.css | Network tab (404) | href="bugs.css" |
| 2 | bugs.css: selector .notes but HTML uses class="note" | Styles pane | Rename selector to .note |
| 3 | bugs.css .btn:hover: no ; after background: #0b1f3a | Styles pane | Add the ; |
| 4 | bugs.css .btn: "colour" is not a CSS property | Styles pane | Change to color |
| 5 | bugs.html: links are in <div class="menu">, no navigation landmark | Accessibility tree | Use <nav> |
| 6 | bugs.html line 17: <h4> right after <h1> | Accessibility tree, Lighthouse, validator | Change to <h2> |
| 7 | bugs.html line 18: <img> has no alt | Lighthouse, validator | Add alt text |
| 8 | bugs.html line 21: label for="mail" but input id="email" | Lighthouse, validator | for="email" |
| 9 | bugs.html line 2: <html> has no lang | Lighthouse, validator | <html lang="en"> |
| 10 | (fill in after the Lighthouse re-run) | | |