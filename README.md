# hugo-notepadium ![](https://img.shields.io/badge/license-MIT-blue.svg) [![Netlify Status](https://api.netlify.com/api/v1/badges/2f389751-e070-437b-9dbd-3773bd57322e/deploy-status)](https://lvv.me)

a fast [gohugo](https://gohugo.io) theme, **100% JavaScript-free**.

- builtin syntanx highlighting
- builtin all chroma/hljs/prismjs themes
- support comments (Disqus)
- `MathJax` support
- custom `404 page`

![](https://lvv.me/posts/2019/11/24_a_simple_hugo_theme/01.png)

the core CSS is `core.css`, transferred size < 3KB.

preview this theme: https://lvv.me

## Quick Start

```shell
git submodule add https://github.com/cntrump/hugo-notepadium.git themes/hugo-notepadium
```

demo `config.toml`:

```toml
baseURL = "/"
languageCode = "zh-cn"
title = "Lvv's notepad"
theme = "hugo-notepadium"
copyright = "Copyright ©2019 lvv. All rights reserved."
hasCJKLanguage = true
enableRobotsTXT = true
paginate = 10
summaryLength = 140

# Hugo v0.60+ new configuration
[markup.highlight]
codeFences = true
noClasses = false

# old Hugo version
pygmentsUseClasses = true
pygmentsCodeFences = true
pygmentsCodeFencesGuessSyntax = true
```

If you like syntax highlight with JS, both `hljs` and `prismjs` are builtin:

```toml
# enable JS highlight
[params.syntax]
use = "hljs"  # 1. prismjs 2. hljs 3. none
theme = "dracula"  # load css/chroma/* themes when use="none"
enableBuiltinFont = true  # use builtin font: source-code-pro
```

enable `MathJax` support

```toml
[params.MathJax]
enable = true
```

Usage

```
When $a \ne 0$, there are two solutions to \(ax^2 + bx + c = 0\) and they are
$$x = {-b \pm \sqrt{b^2-4ac} \over 2a}.$$
```

You can custom nav items:

```toml
[params.nav]
showCategories = true       # /categories/
showTags = true             # /tags/

# custom links

[[params.nav.custom]]
title = "iOS"
url = "/tags/ios"

[[params.nav.custom]]
title = "Repo"
url = "//github.com/cntrump"

```

Set site slogan and logo

```toml
[params]
logo = "logo.png"
slogan = "code my life ~"
```

enable comments

add [disqus short name](https://help.disqus.com/en/articles/1717111-what-s-a-shortname) in config.toml:

```toml
# disqus
disqusShortname = "XXX"  # your short name
```

by default, comments is disabled for all posts.

you can enable comments like below:

```md
+++
title = "..."
date = 2019-12-08
...
comments = true
+++

...
```
