# Challenge

Url: http://3.239.164.111/

# Solution

Really easy challenge too. Just play around the website and go to `about_us` and `Contact` pages. and you can see that have a **parameter** called `?view` that make the redirection to pages
(**Exmaple: http://3.239.164.111/index.php?view=about.html**)

So clearly that can be lfi(local file inclusion).

So, just write the flag.txt in view parameter (http://3.239.164.111/index.php?view=flag.txt) and got flag.

# flag
dsph{y0u_succ3ssfu11y_r34d_m3}
