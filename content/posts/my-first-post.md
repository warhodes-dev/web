+++
title = 'Creating This Site'
date = 2024-03-22T12:55:41-04:00
draft = true
+++

My instinct tells me that if I want to learn the web, I better make my site completely from scratch in order to maximize my exposure to as many technical details as possible. However, this turns out to be a pretty bad strategy if my goal is an actual working website, I tend to get bored and quit after going 50 wikipedia layers deep into the history of ECMAScript or something. No, I need a plan that is a bit more 'starter' but also a bit more 'pro'. Let's look into some industry standard solutions for this.

Considerations:
- I want the full capability to tweak and modify the website should the need arise.
- I want something that is vetted, secure, stable, and reliable - not hacked together.
- I want hosting to be as cheap (or free) as possible.

Research leads me to a major fork in the decision making process: do I want a **static** or **dynamic** site. 

**Dynamic site**: Dynamic site use a [content management system](  ) to generate content on-the-fly as visitors request pages. A dynamic site would allow me to submit blog posts easily through a web interface where they would automatically be added to a database and served as needed. The major downside: I'd need to pay for hosting a web server.

**Static site**: Static sites are an unchanging directory of files that the web server will *always* respond to requests with. It never responds with something different, it's 'static'.. These can often be hosted for free using Github Pages or similar services.

Static site is looking good so far. Since a static site is a directory full of HTML/CSS/JS files, we *could* artisnally hand-craft the site off of a template we find online. But it's much easier to use a [static site generator](https://en.wikipedia.org/wiki/Static_site_generator) to handle the tedium. Some popular SSGs you may have heard of are [Gatsby](https://www.gatsbyjs.com/), [Jekyll](https://github.com/jekyll/jekyll), and [Hugo](https://github.com/gohugoio/hugo). Between these, I chose Hugo because I was able to find a well supported template/theme I like called [PaperMod](https://github.com/adityatelange/hugo-PaperMod)

---

### Hugo

Hugo is easily installed and initialized. On my mac:

```bash
brew install hugo
hugo new site personal
```
Then, you need a 'theme'. The theme handles the visual design, layout, and functionality of the site. This is where we're using [PaperMod](https://github.com/adityatelange/hugo-PaperMod) theme, which is downloaded and enabled like this:

```bash
git submodule add https://github.com/adityatelange/hugo-PaperMod themes/PaperMod
echo "theme = 'PaperMod'" >> hugo.toml
```

Done. The site is actually done now. The coding is finished, do you feel like a programmer now?

If you want to add a post to the blog, you simply create a [markdown](https://en.wikipedia.org/wiki/Markdown) file (.md) under `content/posts`. You can also run `hugo new content posts/my-post.md` as a shortcut.

Finally, you can test the site by hosting it locally with `hugo server` and opening `localhost:1313` in the browser.

---

### Hosting
