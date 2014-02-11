The New Rad.io
==============

This is an outlet for our thoughts. Posting schedule is to be determined.

Posting an article
------------------

1. Make a new markdown file entitled `_posts/year-month-day-title-with-hyphens.markdown`
2. Write the header like the other posts (see 'Header Options')
3. Write your post in markdown
4. `git add -A`
5. `git commit -m 'my new post'`
6. `git push`

Header Options
--------------

*layout*: The template from `_layouts/` that the post will render.
*title*: The title of the post.
*subtitle*: The subtitle of the post. Goes below the title.
*author*: Your name, or something else.
*date*: The posting date, in the form of `YYYY-MM-DD HH:MM:SS` (24-hour time)
*categories*: The url route prefix for the post. For example, if you had a post with filename `2014-01-01-my-new-post.markdown`, with `categories: foo` defined in the header, the url for that post would be `http://thenewrad.io/foo/2014/01/01/my-new-post.html`.
