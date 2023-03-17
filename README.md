# [Reveal.js](https://revealjs.com/) + [Asciinema player](https://github.com/asciinema/asciinema)

[Reveal.js](https://revealjs.com/) is an HTML presentation framework and [asciinema player](https://github.com/asciinema/asciinema-player) is a web player for terminal sessions (recorded with [asciinema](https://github.com/asciinema/asciinema)). If you want to use both [Reveal.js](https://revealjs.com/) and [asciinema player](https://github.com/asciinema/asciinema-player) you may encounter display problems.

This problem is described as follows. Sometimes we can have three [asciinema](https://github.com/asciinema/asciinema) sessions which displayed, sometimes four, sometimes one. To solve the problem, we need to refresh the web browser on the current [Reveal.js](https://revealjs.com/) slide where the [asciinema](https://github.com/asciinema/asciinema) session is hidden. Hidden [asciinema players](https://github.com/asciinema/asciinema-player) are created, but the size is null.

* If you want to reproduce the problem between [Reveal.js](https://revealjs.com/) and [Asciinema player](https://github.com/asciinema/asciinema), turn the root directory into a simple HTTP web server:

```
$ python3 -m http.server
```

> http.server is probably the best solution to expose a HTTP web server for test. Why? Because Python3 is installed by default on the most Operating Systems.

* Open the https://localhost:8000/bug.html URL with your web browser.

In this version, we create all [asciinema players](https://github.com/asciinema/asciinema-player) all at once. I suppose [Reveal.js](https://revealjs.com/) does not have time to compute the size of the [asciinema players](https://github.com/asciinema/asciinema-player).

To solve the problem, we create the [asciinema player](https://github.com/asciinema/asciinema-player) only when the slide (which must contain the [asciinema player](https://github.com/asciinema/asciinema-player)) is displayed.

* Open the https://localhost:8000/workaround.html URL with your web browser and test the result.
