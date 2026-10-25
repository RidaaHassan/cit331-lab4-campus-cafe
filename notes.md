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