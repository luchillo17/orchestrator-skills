# Workspace page

Use this for a file in `docs/` when a picture carries the point. Markdown remains the default. A diagram belongs on the page only when it is a relationship, a flow, or a comparison that a sentence cannot carry.

Tailwind loads from the CDN. Load Mermaid only on a page that has a Mermaid diagram. The page is static.

## Scaffold

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <title>{{title}}</title>
    <script src="https://cdn.tailwindcss.com"></script>
  </head>
  <body class="bg-stone-50 text-slate-900 font-sans">
    <main class="max-w-3xl mx-auto px-6 py-12 space-y-6">
      <header class="space-y-3">
        <p class="text-xs uppercase tracking-wider text-slate-500">{{date}}</p>
        <div class="flex items-center gap-3">
          <h1 class="font-serif text-3xl">{{title}}</h1>
          <span class="rounded-full bg-indigo-100 px-2 py-1 text-xs uppercase tracking-wider text-indigo-800">{{kind}}</span>
        </div>
      </header>
      <section class="space-y-3">
        <p>{{one sentence}}</p>
        <ul class="list-disc pl-5 text-sm">{{bullets or links}}</ul>
      </section>
    </main>
  </body>
</html>
```

A diagram, when the page needs one, is a Mermaid block (`<pre class="mermaid">`, with the Mermaid CDN added to the head) or a hand-built picture. One picture is enough.

## Show

Give the user the absolute path and show the page.
