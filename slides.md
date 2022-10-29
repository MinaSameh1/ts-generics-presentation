---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: public/images/typescript.png
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: Slides for typescript generics.
# persist drawings in exports and build
drawings:
  persist: false
# use UnoCSS
css: unocss
---

# Generics

<div class="abs-br m-6 flex gap-2">
  <a href="https://github.com/MinaSameh1" target="_blank" alt="GitHub"
    class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
layout: cover
class: 'text-center'
highlighter: shiki
background: public/images/cov.png
theme: seriph
---

# Teamwork

<h2>Mina Sameh</h2>
<h2>Ahmed Hamdy</h2>
<h2>Ahmed Hamdy Ameen</h2>

---
class: 'text-xl'
---

# What Are Generics?

<br>
They are a feature of statically typed languages, they help a lot and allow us to:

- Pass types as parameters to other types, functions or classes.
- Reuse components and parts.

<br>
They allow us to create components that can work over a variety of types instead of just one.

<br>
<br>
<br>
<br>

Read more about [Generics](https://www.typescriptlang.org/docs/handbook/2/generics.html)

---

# Hello world in generics

```ts {all|0}
function returnWhatIpassIn(item: string): string {
  return item
}

const StringItem = returnWhatIpassIn('string') // string
const NumItem = returnWhatIpassIn(3) // error
```

<br>

### Using generics

```ts {0|all|1|all}
function returnWhatIpassIn<TItem>(item: TItem): TItem {
  return item
}
const StringItem = returnWhatIpassIn('string') // string
const NumItem = returnWhatIpassIn(3) // number
```

---

## Example with nodejs pg

PG has a type called QueryResult, which normally returns any,
That any means we don't get to use typescript features.
![query_any](/images/query_any.png)

---

## Example with nodejs pg

we can fix this and get typescript features by giving it a type.
<br>
![query_type](/images/query_type.png)
<br>
and we get autocomplete and type checking, the features of ts that we love.
<br>
![auto](/images/auto2.png)