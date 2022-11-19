# 😨 DRY

Let’s start with an easy one, I’m sure you’ve seen this one around plenty of times, but do you know what it means?

This is a very common software development principle. It stands for **Don’t Repeat Yourself**. And it essentially means that when you’re writing code, you should consider modularizing functionality that you use more than once.

Don’t get me wrong, by modularization I don’t meant go around creating libraries for a function that you use twice, but rather, if you have the same logic (or similar enough that you can generalize it with little effort) in different places, then you should consider moving that logic inside a function and if you have a function that you’ve defined in several places, then move that into a common module.

And then again, if you happen to be copying a module around from place to place, consider turning that module into a common library.

In other words: _Don’t Repeat Yourself,_ get it?

Personally, no matter the language you’re working on or the platform you’re developing for, there are very few cases when this principle would not be advised. Consider that as a developer, your job is to automate behavior (speaking at a macro scale here), so if you zoom into your particular code you should be doing the same. Instead of writing the same logic over and over again, consider generalizing it and moving it to a commonplace.

Tip: The DRY rule should not be limited to a single repository. To make your modules/components easily discoverable and available across repositories use [**Bit**](https://bit.dev) ([Github](https://github.com/teambit/bit)).

[**Bit**](https://bit.dev/) supports Node, TypeScript, React, Vue, Angular, and more.
