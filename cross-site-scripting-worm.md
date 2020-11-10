# Cross-site Scripting Worm. XSS.





## Contents at a Glance.
* [About](#about)
* [Documentation.](#documentation)
* [Help](#help)





## About.





## Documentation.


## Anatomy of a XXS Attack
* User enters text in an input field, within text is JavaScript code
* Server accepts text without encoding or sanitizing
* User enter text displayed to user on page, JavaScript code executes

## Prevention of a XXS Attack
* Entered text should be scrubbed of JavaScript characters
* Special characters should be HTML encoded
* For complete precautions refer to OWSAP Cross-Site Scripting Prevention
  * Link in lecture resources


## Help.
