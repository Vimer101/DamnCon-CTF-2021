# Challenge overview

If we go to page we can see the **pop alert box** that tell bla.....!(not interesting)

If we look the source of web page,we can see the username and password for admin 

Username: admin
Password: p4ssw0rd

So, We can login with that.

But if you logined, we can see the following text in page `You are logged in but your token is not correct. So we can't show you the sensitive data!`

So, that mean clearly that we need to know correct cookie `value` of `token`.

I find it about 2 hours. but don't see in anywhere. but after i noticed a `main.js` in website page source.

If you scroll all the way down of `main.js` page view-source. you can see the following text `var token="1_4m_4n_3mpl0y33" //Because of my recent disease of memory loss, I am adding this token here. Since the token is really very sensitive so, I'll delete it later.`

# Solution

So, now we got real token.(**1_4m_4n_3mpl0y33**). So, past it in token's value place, (you can do in browser developer tool or in cookie manger too)

And refresh page and got flag

# flag
DSPH{y0u_h4ckedd_DspH}
