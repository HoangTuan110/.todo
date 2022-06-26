# Soup - That j thing, but in Python (and for using in the CLI)

For the past few days, I have been brainstorming a CLI program that allows you to fetch data from HTML documents, like this:

```
curl https://gohugo.io/ | soup '.find("h2").text'
```