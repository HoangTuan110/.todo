# Dead links, and how to handle them

Dead links are a mistake that I saw a lot of bloggers on Bear made. In fact, I am one of them. Dead links are links that is intended to point to an external link, but instead points to the post itself or to a non-existent path in your blog.

In this post, I will show you ways to spot and fix these dead links.

## 1. Missing `http://` or `https://`

The most common form of dead links is links that doesn't have `http://` or `https://` at the start of the link. This is an easy fix, as you can just add one of them before the link.

Example: [This post about newsletters](https://archive.ph/MYbmZ) contain dead links with missing HTTP header in every link.

How to fix:

```
[Tsuki](tsk.bearblog.dev). This is the dead link.
[Tsuki](http://tsk.bearblog.dev). This is the right link.
```

## 2. Empty links

Another common form of dead links is links that simply doesn't redirect to anywhere. By default, these links redirect to the post itself.

Example: [Hanki's post about reducing Reddit usage](https://archive.ph/d8aeg) has an empty link on `r/nosurf`.

How to fix:

```
[Tsuki](). This is the dead link.
[Tsuki](http://tsk.bearblog.dev). This is the right link.
```

## 3. Linkrot

I have not seen an example for this one, but it's also worth considering.

According to [Wikipedia](https://en.wikipedia.org/wiki/Link_rot):

> Link rot is the phenomenon of hyperlinks tending over time to cease to point to their originally targeted file, web page, or server due to that resource being relocated to a new address or becoming permanently unavailable.

A quick way to fix linkrot is to use an archive service (Such as [archive.ph](https://archive.ph/) or [Wayback Machine](https://web.archive.org)) to find the lastest snapshot of the link and point to that snapshot.

> [Subscribe to my newsletter](https://buttondown.email/tsuki) |
> [Discuss on HN](https://news.ycombinator.com/item?id=31677401)