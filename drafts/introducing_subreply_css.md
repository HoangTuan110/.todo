# Introducing Subreply CSS - A beautiful classless CSS style

Recently, I came across this website called [Subreply](https://subreply.com/about), which is an English-only forum with a very clean and simplistic design.

When I first saw it, I immediately fall in love with its design: Simple, yet modern and beautiful.

I love it so much that I decided to rip the CSS from the website and turn it into a classless CSS style.

And after about 2 days of active working, I introduce to you, Subreply CSS!

Subreply CSS is a classless CSS style that is designed to be modern, beautiful, and simple, just like where it came from.

Features include:

- Lightweight - Only weights 4 kb! [^1]
- Automatic dark/light theme (based on OS preferences)
- Custom emojis before `mailto:`, `sms:`, and `tel:` links
- Custom blockquotes and code blocks [^2]
- Beautiful font ([Route 159](https://dotcolon.net/font/route159/))
- Fixing missing features from the original Subreply, such as radios and checkboxes

Subreply CSS is suitable for both personal blogs and simple websites!

# Wow! That's exciting! Where can I know more about it?

You can go to the [Sourcehut repo](https://git.sr.ht/~tsukii/subreply-css), which contains further information about the project and how to install them.

# I'm still skeptical, I wanna try it first

You can try this [demo](https://srht.githack.com/~tsukii/subreply-css/blob/main/test.html) [^3] or just playing around with my website (yes, it has Subreply CSS applied).

# Downsides

Even though it has a lot of good points, Subreply CSS also has some downsides:

- All of the fonts are currently hosted on [Catbox](https://catbox.moe/), a file hosting service that I am relying on.

This means that if Catbox goes down, all of the fonts will rendered unusable.

The best solution for this is to host fonts locally, and I am planning on writing a blog post just for that, so stay tuned!

[^1]: For both original and minified version
[^2]: The blockquotes are stolen from [here](https://css-tricks.com/snippets/css/simple-and-nice-blockquote-styling/) and the code blocks are stolen from [here](https://adis.ca/entry/2011/pretty-code-block-in-css/)
[^3]: Note that the demo version is a bit outdated.