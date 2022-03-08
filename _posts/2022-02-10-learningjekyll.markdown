---
layout:     post
title:      Setup Curcifer Tech first time
author:     YWS
date:       2022-02-10
categories: learning jekyll
tags: 		jekyll
youtubeId:  ""
description: "Hello people, I want to share a little bit about website build using github pages and jekyll.
I am also new on jekyll static website, so please bear with me :)
</br></br>
To setup first website using github pages is pratically easy,
let's do it step by step.<br/>"
---


Hello people, I want to share a little bit about website build using github pages and jekyll.
I am also new on jekyll static website, so please bear with me :)

To setup first website using github pages is pratically easy,
let's do it step by step.

- setup account in github
- add repository yoursite.github.io
- install jekyll on your local machine by following this [doc][gt-doc]
- initialize jekyll project

don't forget to bundle install it first after initialize project.
after all setup done, you can run it using `bundle exec jekyll serve`

if somehow it complain permission denied.
you can do `sudo chown -R your_username` if you like, to bring root permission.

and done, congratulation!.

also you still need to do extra configuration if want to update your website.

---

reference:
- include [doc][gt-doc]
- Website Theme powered by [monophase][theme-doc]
- Environment manager [rubyenv][rubyenv]


[gt-doc]: https://jekyllrb.com/docs/
[theme-doc]: https://github.com/zivhub/monophase
[rubyenv]: https://github.com/rbenv/rbenv

