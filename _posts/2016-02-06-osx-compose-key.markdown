---
layout: post
title:  "Multiple languages and compose key on OS X"
date:   2016-02-06 23:15:00 +0100
categories: post
---

I speak three languages, and I write in all three almost every day.

Two of these languages, Icelandic and Danish, have special characters that are not found on standard English
keyboards, and thus require their own keyboard layout. Switching between keyboard layouts depending on what you are
writing is a terrible user experience, and nobody should have to deal with that.

Imagine my joy when I discovered the [compose key][compose_key], which allowed me to write in all three languages on my
English keyboard layout. By using the compose key to combine two or more characters into one, I could type
`compose`, `/`, `o` and get `ø`, or `compose`, `a`, `e` and get `æ`.

The problem is that only Linux has a built in compose key. There is [a solution for Windows][wincompose], but it's
more complicated on OS X. I used an app called [Ukelele][ukelele] to create a custom keyboard layout with key
sequences that emulated a compose key, and used that for years. However, this solution stopped working when I upgraded
to OS X El Capitan recently.

Turns out that there is now a better solution. It's still not as easy as on Linux and Windows, but using
[Karabiner][karabiner] with custom key mappings essentially gives you a compose key on OS X. I found a
[repository][gnarf-osx-compose-key] on GitHub by [gnarf][gnarf] that provides exactly that, with nice example mappings
for various emoji and the like. I forked and modified the mappings to include Nordic and German characters, and my
compose key is working again.

Find [my mappings on GitHub][viis-osx-compose-key].


[compose_key]: https://en.wikipedia.org/wiki/Compose_key
[wincompose]: https://github.com/samhocevar/wincompose
[ukelele]: http://scripts.sil.org/ukelele
[karabiner]: https://pqrs.org/osx/karabiner/
[gnarf-osx-compose-key]: https://github.com/gnarf/osx-compose-key
[gnarf]: https://github.com/gnarf
[viis-osx-compose-key]: https://github.com/viis/osx-compose-key
