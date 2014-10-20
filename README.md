simple-ssi-blog
===============

**Simple Serverside Include Blog**

I built this to support my tilde.club blog: http://tilde.club/~drofmij
My main reason for building this was so I don't need to copy and paste all of the html boilerplate stuff from page to page.

**Features**

- Simple(ish) blog
- Article permalinks with mod rewrite ala: example.com/article/article-name
- Clean + Simple UI
- HTML5

**CONS / TODO**

- some hand editing is needed to make a new article / post (considering scripting this with markdown parser)
- navigation could use some ... tuning :D
- currently only works with apache + ssi + mod rewrite



**INSTALL**

Note: prerequesites of Apache 2 with mod_include and mod_rewrite configured are assumed. I will add that
level of config granularity at a later date.

1. copy contents of simple-ssi-blog/web to your web folder (heretofor referred to as "ROOT")
2. edit ROOT/.htaccess and change instances of /ssi/web to the relative URL path of your ROOT
3. edit ROOT/include/base.inc and change /ssi/web to the relative URL path of your ROOT
 


**YOUR CONTENT**

1. edit ROOT/include/headcontent.shtml and change <title> value to your title
2. edit ROOT/include/header.shtml and change Simple SSI Blog to your site title or logo
3. edit ROOT/article/about.inc and change to your about info

**ARTICLES**

1. copy ROOT/article/example1.shtml.example to ROOT/article/yourarticle.shtml
2. copy ROOT/article/example1-content.shtml.example to ROOT/article/yourarticle-content.shtml
3. edit ROOT/article/yourarticle.shtml change the following line:

```
<!--#include virtual="example1-content.shtml" -->
```

Change to:
```
<!--#include virtual="yourarticle-content.shtml" -->
```
yourarticle.shtml should now look something like:
```
<!--#include virtual="../include/html5start.shtml"-->
<!--#include virtual="../include/headcontent.shtml" -->
<!--#include virtual="../include/analytics.shtml" -->
<!--#include virtual="../include/header.shtml" -->
<!--#include virtual="yourarticle-content.shtml" -->
<!--#include virtual="../include/footer.shtml" -->
```

You should be able to navigate directly to (your site url)/article/yourarticle

4. (OPTIONAL) edit ROOT/articles.shtml and add remove list entries as appropriate
5. edit ROOT/index.shtml and replace:
```
<!--#include virtual="article/article1-content.shtml" -->
```

With Your file:
```
<!--#include virtual="article/article1-content.shtml" -->
```

Thats all for now. :D
