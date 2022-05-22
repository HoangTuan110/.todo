# Bear: The good and the bad

I have been using Bear for almost 3 months, posting a handful of blog posts, and got two posts [blow](https://news.ycombinator.com/item?id=31432527) [up](https://news.ycombinator.com/item?id=31455657). With this, I decided to write about what I like and don't like so much about Bear.

## The good

### Simple and easy-to-use

A thing that makes Bear attractive, in my opinion, is that it is dead simple and easy-to-use. Create a new account is very easy, and creating a new post is just a few clicks away. Bear handles all of the hassle for you, such as web hosting, navigation, posts, analytics, etc.

### Customizable

Another plus of Bear is it allows you to freely customize your blog. You can use the default layout of Bear, or use a no-class CSS framework, or, if you like me, go crazy.

### Freedom

While other social networks can block or censor you because you express your own opinion, Bear doesn't. On Bear, you can express your opinions without worry about getting blocked or censored.

## The bad

### Freedom is a double-edge sword

Bear allows you to share your opinions freely. While this is a great thing for the platform, it can also be used for hate speech, discrimination, and other nasty stuff.

### Broken algorithm

Bear uses an algorithm to rank posts in the `Trending` section of `Discovery feed` that is represented at the bottom of the section. Here is a copy of it:

```
S = U/(T+4)^G

Where,
U = Upvotes (toasts) of a post
T = Time since submission (in hours)
G = Gravity (currently at 1.2) to keep page content fresh
```

A problem with many deterministic algorithm like this is that posts with a few upvotes get to stay on the section for way too long. Posts with about 7-8 upvotes can stay on the `Trending` section for WEEKS.