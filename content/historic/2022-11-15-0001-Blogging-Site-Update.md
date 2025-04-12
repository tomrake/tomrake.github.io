---
layout: post
title: "Updating my site with org-mode"
permalink: /:title/
tags: [blog, org-mode]
---
## I have updated blogging procedure
This is of a technical interest on how I actually produce my blog. 
I have always written by blog pages in emacs and
historically have authored in Markdown syntax and the Beautiful Jekyll theme on GitHub.
I now author my pages in org mode and use org-publish to render them to the Jekyll repository.
Next I ensure that the blog posts are in the _posts/ folder and commit those changes to the git image of my site.
Finally, I upload and push my local site to GitHub.



## How each post is constructed</h2>

All my pages need a special header which looks like this.

```
---
layout: post
title: "Updating my site with org-mode"
permalink: /:title/
tags: [blog, org-mode]
---
```

I then use org-mode to write and format my text.

My org-publish of blog renders all the pages into _drafs/ folder where the jekyll image is located.
I move the post from the _drafts/ folder into the _posts/ folder which makes the post live.
Adding the post to the jekyll image by a git add followed by a git commit.
A git push origin master causes the changed website live.
