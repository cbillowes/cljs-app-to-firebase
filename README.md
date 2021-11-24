# ClojureScript from scratch series

## Part 3: Google Firebase with GitHub Actions

This template will showcase the configuration of a ClojureScript
web application that can be deployed to Firebase using GitHub actions.

* [Firebase][firebase.google.com]
* [GitHub Actions][github/actions]

[firebase.google.com]: https://firebase.google.com/docs/web/setup
[github/actions]: https://docs.github.com/en/actions

## Part 2: Tailwind CSS

This template creates a ClojureScript web application with Clojure CLI
and integrates with Tailwind CSS.

* [Article][article-part-2]
* [Tailwind CSS][tailwind]
* [Repository][shadow-cljs-tailwindcss] using shadow-cljs

[article-part-2]: https://curiousprogrammer.dev/blog/how-can-i-use-tailwind-in-my-clojure-script-web-app/
[tailwind]: https://tailwindcss.com/
[shadow-cljs-tailwindcss]: https://github.com/jacekschae/shadow-cljs-tailwindcss

## Part 1: Reagent & npm

This template creates a ClojureScript web app with Reagent and npm
using the Clojure CLI tools.

* [Article][article-part-1] on curiousprogrammer.dev
* [Clojure CLI tools][cli-tools]
* [Figwheel-Main][figwheel-main]
* [Reagent][reagent]
* [npm][npm]
* [Webpack][webpack]

[article-part-1]: https://curiousprogrammer.dev/blog/how-can-i-create-a-clojure-script-web-app-from-scratch-with-reagent-and-npm/
[reagent]: https://reagent-project.github.io/
[cli-tools]: https://clojure.org/guides/deps_and_cli
[figwheel-main]: https://figwheel.org/
[npm]: https://www.npmjs.com/
[webpack]: https://webpack.js.org/

## Gotchas

### Range Not Satisfiable (416)

```
Error building classpath. Could not transfer artifact com.google.javascript:closure-compiler-unshaded:jar:v20210808 from/to central (https://repo1.maven.org/maven2/): status code: 416, reason phrase: Range Not Satisfiable (416)
```

I got this error when I tried to build the application.
It failed when downloading dependencies.
According to this [solution][solution-could-not-transfer-artifact], it was suggested to delete the
`~/.m2` dependency directory and try again.
I try not to delete the entire directory.
I did, however, wipe the entire `com.google.javascript` directory.

```bash
rm -rf ~/.m2/repository/com/google/javascript/
```

[solution-could-not-transfer-artifact]: https://clojureverse.org/t/could-not-transfer-artifact/5778
