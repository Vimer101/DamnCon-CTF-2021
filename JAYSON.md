# Challenge Overview

Url: http://13.234.204.88/web3.php

If we look the source code (you can with ctrl+u), you can see the line that write the cookie for us as default(**that mean when we refresh or go to any redirection of page will be just this cookie. will not change**)

`document.cookie= "jwt=eyJhbGciOiJIUzUxMiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoiSS1BbS1Ob3QtYWRtaW4ifQ.xkD6eVzcsYajzTA3H4HHmdQ9d57nMdPt2arzlOgrl8IraQIBiKgycSVbtQPk-TXR5HxM2sh-zdSEShGAhScyIQ";`

# Solution
So, we can use https://jwt.io/ to see the cracked detail of jwt token, in the cracked token. we can see that there is `name` with comment named `"name": "I-Am-Not-admin"`. 

So, As a challenge desecription that we knew that we need to be admin, so i just change the comment from `I-Am-Not-admin` to `Admin`. and paste the changed jwt token in text area of **Submit & Get The Flag**. But when we clicked,we don't get back anything and just redirect to `web4.php`.

Well, actually we need to change the redirect action of button(Submit & Get The Flag) from `web4.php` to `web3.php` to see our flag. So we can use developer tools for it, just change the **`form action="web4.php">`** to **`form action="web3.php"`**.
 
So, paste the changed token in text area again and change the `form` action of **Submit button** to `web3.php` and click the button and got flag. COol!

# flag
`DSPH{h@_h@_j@YSON}`
