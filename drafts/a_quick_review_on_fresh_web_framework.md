# A quick review of the Fresh web framework

Unless you have been living under a rock, then you probably have heard of [Fresh](https://fresh.deno.dev/), the shiny new TypeScript web framework.

Fresh boasts some impressive features, such as:

- No build step
- No config needed
- TypeScript support out of the box
- No JavaScript is shipped to the client by default

But how good is Fresh in terms of developer experience?

To answer that question, I have built a simple file-system based pastebin service, called [Petunia](https://github.com/HoangTuan110/petunia), using Fresh and Deno.

Short answer?

Fresh is pretty good if you already know React and Tailwind, though it has some quirks that you have to get used to, like handling input.

The longer answer?

Fresh relies on [Preact](https://preactjs.com/)--a lightweight version of React--to display components, so if you are a React developer, then Fresh should feel like home to you.

When initializing a new project, Fresh will also ask if you want to use [Twind](https://twind.dev/), which is a Tailwind-to-JS library. If you choose this option, then you will have the power of Tailwind without creating a config file or using PostCSS, which I thought is pretty cool.

Here are a few things to notice though:

- Fresh uses [NextJS's file-system based routing](https://nextjs.org/docs/routing/introduction), so for example `routes/link/[id].ts` becomes `/link/:id` in the web app.

- The way Fresh handles form submission is very different from React. Instead of using states like React, Fresh takes advantage of the HTML `<form>` element, by getting form data from `<form>` when the user enters the form, then using a custom handler to process that data, and return that data to the front-end.

Here's [an example](https://fresh.deno.dev/docs/getting-started/form-submissions) on the Fresh documentation, implementing a search form that filters an array of names server-side:

```ts
/** @jsx h */
import { h } from "preact";
import { Handlers, PageProps } from "$fresh/server.ts";

const NAMES = ["Alice", "Bob", "Charlie", "Dave", "Eve", "Frank"];

interface Data {
  results: string[];
  query: string;
}

export const handler: Handlers<Data> = {
  GET(req, ctx) {
    const url = new URL(req.url);
    const query = url.searchParams.get("q") || "";
    const results = NAMES.filter((name) => name.includes(query));
    return ctx.render({ results, query });
  },
};

export default function Page({ data }: PageProps<Data>) {
  const { results, query } = data;
  return (
    <div>
      <form>
        <input type="text" name="q" value={query} />
        <button type="submit">Search</button>
      </form>
      <ul>
        {results.map((name) => <li key={name}>{name}</li>)}
      </ul>
    </div>
  );
}
```

> [Discuss on HN](https://news.ycombinator.com/item?id=31974795) | [Tweet this post](https://ctt.ac/fe25i)