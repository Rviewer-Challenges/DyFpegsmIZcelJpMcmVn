# Twitter Mirroring

Who doesn't have a Twitter account? One of the biggest and controversial social networks of this decade, which has
been revamped multiple times due to its UX problems.

Most of the time we don't realize how important the UI and UX are in the apps we use every day. Would Twitter, Spotify
or Slack have become what they are today without having taken so much care of the user interface? Probably not.

For years, Twitter has been very selective with its features, and has focused on providing its users with a great user
experience. The quality of this can be one of the main key points for our app success.

Well, the goal of this Challenge is to replicate the Twitter interface!

![Brais Moure Challenge card](moure_twitter-mirroring.png)

> This is a challenge created by [MoureDev](https://www.twitch.tv/mouredev). He will review and give feedback to some
> proposed solutions from the community in one of his Twitch livestreams 😻

**Surprise us! 😉**

## How it works?

You will have to create an application that represents as much as possible a fake Twitter timeline, showing
different types of tweets.

The more faithful to the original design, the better, although it's not necessary to display all current Twitter
functionalities. The aim of the challenge is focused on the ability to know how to create UI based on an existing
design.

The feed should display Tweets of the following types:

* Text tweet.
* Tweet with an image.
* Tweet with up to 4 images.
* Tweet with a GIF.

The data to be displayed doesn't have to be real. You can define your own mocked set of tweets, containing images,
texts, likes and so on.

Each Tweet should contain the following functionalities:

* Display the number of likes, retweets or comments.
* Represent hashtag or mentions (without filtering interaction).
* Represent links (with interaction and opening in a browser).
* User photo, name, date, tweet body and action buttons (without the profile edit feature)
* Up to you to choose other extra functionalities. For example:
    * Tweets with video or poll.
    * Tweets detail page, showing comments.
    * Image detail and zoom.

### Extra points

Every Twitter user knows that there are some key points of the application that could be improved, even Elon Musk! 😜

So, if you want to challenge you a bit more, try to improve the Twitter's application on these features that you 
guess that could be room for it. You can focus these improvements just on the UI, or even the UX and user flows.

## Technical requirements

* Create a **clean**, **maintainable** and **well-designed** code. We expect to see a good and clear architecture that
  allows to add or modify the solution without so much troubles.
* **Test** your code until you are comfortable with it. We don't expect a 100% of Code Coverage but some tests that
  helps to have a more stable and confident base code.

To understand how you take decisions during the implementation, **please write a COMMENTS.md** file explaining some of
the most important parts of the application. You would also be able to defend your code through
[Rviewer](https://rviewer.io), once you submit your solution.

---

## How to submit your solution

* Push your code to the `devel` branch - we encourage you to commit regularly to show your thinking process was.
* **Create a new Pull Request** to `main` branch & **merge it**.

Once merged you **won't be able to change or add** anything to your solution, so double-check that everything is as you
expected!

Remember that **there is no countdown**, so take your time and implement a solution that you are proud!

--- 

<p align="center">
  If you have any feedback or problem, <a href="mailto:help@rviewer.io">let us know!</a> 🤘
  <br><br>
  Made with ❤️ by <a href="https://rviewer.io">Rviewer</a>
</p>

# Svelte + Vite

This template should help get you started developing with Svelte in Vite.

## Recommended IDE Setup

[VS Code](https://code.visualstudio.com/) + [Svelte](https://marketplace.visualstudio.com/items?itemName=svelte.svelte-vscode).

## Need an official Svelte framework?

Check out [SvelteKit](https://github.com/sveltejs/kit#readme), which is also powered by Vite. Deploy anywhere with its serverless-first approach and adapt to various platforms, with out of the box support for TypeScript, SCSS, and Less, and easily-added support for mdsvex, GraphQL, PostCSS, Tailwind CSS, and more.

## Technical considerations

**Why use this over SvelteKit?**

- It brings its own routing solution which might not be preferable for some users.
- It is first and foremost a framework that just happens to use Vite under the hood, not a Vite app.
  `vite dev` and `vite build` wouldn't work in a SvelteKit environment, for example.

This template contains as little as possible to get started with Vite + Svelte, while taking into account the developer experience with regards to HMR and intellisense. It demonstrates capabilities on par with the other `create-vite` templates and is a good starting point for beginners dipping their toes into a Vite + Svelte project.

Should you later need the extended capabilities and extensibility provided by SvelteKit, the template has been structured similarly to SvelteKit so that it is easy to migrate.

**Why `global.d.ts` instead of `compilerOptions.types` inside `jsconfig.json` or `tsconfig.json`?**

Setting `compilerOptions.types` shuts out all other types not explicitly listed in the configuration. Using triple-slash references keeps the default TypeScript setting of accepting type information from the entire workspace, while also adding `svelte` and `vite/client` type information.

**Why include `.vscode/extensions.json`?**

Other templates indirectly recommend extensions via the README, but this file allows VS Code to prompt the user to install the recommended extension upon opening the project.

**Why enable `checkJs` in the JS template?**

It is likely that most cases of changing variable types in runtime are likely to be accidental, rather than deliberate. This provides advanced typechecking out of the box. Should you like to take advantage of the dynamically-typed nature of JavaScript, it is trivial to change the configuration.

**Why is HMR not preserving my local component state?**

HMR state preservation comes with a number of gotchas! It has been disabled by default in both `svelte-hmr` and `@sveltejs/vite-plugin-svelte` due to its often surprising behavior. You can read the details [here](https://github.com/rixo/svelte-hmr#svelte-hmr).

If you have state that's important to retain within a component, consider creating an external store which would not be replaced by HMR.

```js
// store.js
// An extremely simple external store
import { writable } from 'svelte/store'
export default writable(0)
```
