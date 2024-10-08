# How This Site is Made

description: A tour of the software development process used to create this site.

Mar 16, 2024

I provide this page here in case you are wondering how this site is made. It's
fairly simple, but requires some explanation.

Currently, all content on this site is static. The blog articles are written in
markdown. The pages are written in plain HTML. I use Tailwind for styling
because it's just that easy. There's a small script that generates the blog HTML
from markdown files, and the site is currently hosted on a [Digital Ocean](https://www.digitalocean.com/) Droplet.

## Blog Posts

Posts are written in markdown and converted to HTML with
[marked](https://www.npmjs.com/package/marked). The conversion is part of the
build process and the rendered HTML files get placed in `docs/blog`.

I use a simple [template
page](https://github.com/LukeGeneva/l8a.dev/blob/master/blog-page.template.html)
where each blog post is fed into. What's nice about this is that, by wrapping
the template page in a `blog-page` CSS class, I can easily target the rendered
blog post HTML for styling like so:

```css
.blog-page h1 {
  @apply text-4xl font-bold py-2;
}

.blog-page h2 {
  @apply text-2xl font-bold py-2;
}

.blog-page a {
  @apply text-blue-500;
}
```
