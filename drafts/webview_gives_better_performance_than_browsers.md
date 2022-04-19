# Webview gives better performance than normal browsers (when playing web games)

Yesterday I learned that using Webview for playing web games gives better performance than using a browser.

I was trying to login into [TETR.IO](https://tetr.io), a modern Tetris implementation. I enter my username,
password, and a code stored in my Twilio Authy which serves as 2FA. Then, bam! I was greeted by a
disorientedly displayed "A-Lined" and a message telling me that I have been banned from the service.

![A-Lined from TETR.IO](https://files.catbox.moe/pjmmv6.png)

When I first saw the message, I was dazed. I haven't log into my account for months, and in the time while
I was still playing the game, I have not used any cheat tools or played unfairly in any way, as I have no
intent to.

As an attempt to play the only interesting game in my tiny game library, I decided to open up the terminal
and visit an old project I hastily wrote about a month ago, called Weapp.

Weapp is basically a Python script that runs and displays content of the URL given using Webview. It is just
in 14 lines of code:

```py
from typer import run
import webview

def main(title: str, url: str):
    """
    Main function
    """
    print(f"Title: {title}")
    print(f"URL: {url}")
    webview.create_window(title, url)
    webview.start()

if __name__ == "__main__":
    run(main)
```
