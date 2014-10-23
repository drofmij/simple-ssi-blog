simple-ssi-blog
===============

**Simple Serverside Include Blog**

So I was hanging out at tilde.club (my site over there: http://tilde.club/~drofmij) and someone mentioned in the (internal) IRC that Server Side Includes was turned on. Somehow I skipped this technology and went straight to PHP. So given that I was building a site in a Retro *NIX community server I figured I would use an older technology to build it.

**Demo Site**

Live demo is at: http://tilde.club/~drofmij/simple-ssi-blog

**Features**

- Simple(ish) blog
- Blog Post permalinks with mod rewrite ala: example.com/blog/blog-name
- Clean + Simple UI
- HTML5

**CONS / TODO**

- some hand editing is needed to make a new blog / post (considering scripting this with markdown parser)
- navigation could use some ... tuning :D
- currently only works with apache + ssi + mod rewrite



**INSTALL**

Note: prerequesites of Apache 2 with mod_include and mod_rewrite configured are assumed. I will add that
level of config granularity at a later date.

1. copy contents of simple-ssi-blog/web to your web folder (heretofor referred to as "ROOT")
2. edit ROOT/.htaccess and change instances of /ssi/web to the relative URL path of your ROOT
3. edit ROOT/include/base.inc and change /ssi/web to the relative URL path of your ROOT
 


**YOUR CONTENT**

1. edit ROOT/blog/about.inc and change to your about info
2. edit ROOT/include/analytics.shtml and add your analytics stuff (if any)
3. edit ROOT/include/footer.shtml and update with your footer info
4. edit ROOT/include/headcontent.shtml and change <title> value to your title
5. edit ROOT/include/header.shtml and change Simple SSI Blog to your site title or logo

**ARTICLES**

1. copy ROOT/blog/example1.shtml.example to ROOT/blog/yourpost.shtml
2. copy ROOT/blog/example1-content.shtml.example to ROOT/blog/yourpost-content.shtml
3. edit ROOT/blog/yourpost.shtml change the following line:

```
<!--#include virtual="example1-content.shtml" -->
```

Change to:
```
<!--#include virtual="yourpost-content.shtml" -->
```
yourpost.shtml should now look something like:
```
<!--#include virtual="../include/html5start.shtml"-->
<!--#include virtual="../include/headcontent.shtml" -->
<!--#include virtual="../include/analytics.shtml" -->
<!--#include virtual="../include/header.shtml" -->
<!--#include virtual="yourpost-content.shtml" -->
<!--#include virtual="../include/footer.shtml" -->
```

You should be able to navigate directly to (your site url)/blog/yourpost

4. (OPTIONAL) edit ROOT/posts.shtml and add remove list entries as appropriate
5. edit ROOT/index.shtml and replace:
```
<!--#include virtual="blog/blogpost1-content.shtml" -->
```

With Your file:
```
<!--#include virtual="blog/yourpost1-content.shtml" -->
```

Thats all for now. :D
