# A dumb mistake

While building a tool for searching the web using [Alexandria](https://www.alexandria.org/) from the terminal, I found something strange...

The code that I wrote for the project looks like this:

```python
from typer import run
from httpx import get

def main(keyword: str):
    url = "https://api.alexandria.org/?q=" + keyword
    content = get(url)
    if content.is_error:
        print("Error occured!")
        exit(1)
    return content.text

if __name__ == "__main__":
    run(main)
```

Seems straightforward enough, right?

However, when I execute the program, instead of returning me with the JSON, it returns... nothing.

```
$ python main.py "elixir"
[Few seconds later]
$
```

This seems rather strange.

After a bit of playing around and trying to solve the problem, I decided to implement the same thing, but much more simpler.

```python
from httpx import get

url = "https://api.alexandria.org/?q=elixir"
content = get(url)
print(content.text)
```

When running, I expected it to not really return anything, but it returns the query just like normal!

```
$ python alexandria_api_query.py
{"status":"success","time_ms":64.96620178222656,"total_found":58276,"page_max":10,"results":[{"url":"https:\/\/elixir-lang.org\/","title":"The Elixir programming language","snippet":"Home Install Learning Cases Development Guides Docs Blog Elixir is a dynamic, functional language for building scalable and maintainable app...","score":19200.831788531254,"domain_hash":"1506423652601202248","url_hash":"2489422639746999482","exact_match":1,"phrase_match":0,"year":9999,"is_old":0,"is_subdomain":0,"domain":"elixir-lang.org","exact_match_domain":1,"exact_match_title":1,"exact_match_snippet":1,"ping":"https:\/\/api.alexandria.org\/ping?data=eyJ1IjoiaHR0cHM6XC9cL2VsaXhpci1sYW5
...
```

What is going on?

After some more changing stuff and see if they work, I think that the problem might be that I return the result instead of printing, so I tried it...

```python
from typer import run
from httpx import get

def main(keyword: str):
    url = "https://api.alexandria.org/?q=" + keyword
    content = get(url)
    if content.is_error:
        print("Error occured!")
        exit(1)
    print(content.text)

if __name__ == "__main__":
    run(main)
```

The result? IT WORKS!

Getting confused at first, but then realized it, my first thought is: Ok, that's a dumb mistake.

> [Discuss on HN](https://news.ycombinator.com/item?id=31799415) | [Tweet this post](https://ctt.ac/C68Qo)