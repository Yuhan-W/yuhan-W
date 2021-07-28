---
title: An example
subtitle: Linear algebra

# Summary for listings and search engines
summary: Welcome 👋 We know that first impressions are important, so we've populated your new site with some initial content to help you get familiar with everything in no time.

# Link this post with a project
projects: []

# Date published
date: "2020-12-13T00:00:00Z"

# Date updated
lastmod: "2020-12-13T00:00:00Z"

# Is this an unpublished draft?
draft: false

# Show this page in the Featured widget?
featured: false

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.
image:
  caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/CpkOjOcXdUY)'
  focal_point: ""
  placement: 2
  preview_only: false

authors:
- admin

tags:
- Deep Learning

categories:
- Demo
- Test
---

## Overview

1. The Wowchemy website builder for Hugo, along with its starter templates, is designed for professional creators, educators, and teams/organizations - although it can be used to create any kind of site
2. The template can be modified and customised to suit your needs. It's a good platform for anyone looking to take control of their data and online identity whilst having the convenience to start off with a **no-code solution (write in Markdown and customize with YAML parameters)** and having **flexibility to later add even deeper personalization with HTML and CSS**
3. You can work with all your favourite tools and apps with hundreds of plugins and integrations to speed up your workflows, interact with your readers, and much more

{{< figure src="https://raw.githubusercontent.com/wowchemy/wowchemy-hugo-modules/master/academic.png" title="The template is mobile first with a responsive design to ensure that your site looks stunning on every device." >}}

The singular value decomposition (SVD) is a factorization of any $m\times n$ matrix and it can be seen as a generalization of eigendecompostion which can only be applied to diagonalizable matrices. And the SVD also has multiple applications in different fields. This article explains the basic theory of the SVD and its geometric interpretation.

## The Matrices in the SVD
There is an important fact that every real symmetric matrix $S$ has the factorization: $S = Q\Lambda Q^{-1}=Q\Lambda Q^\mathrm{T}$ with orthonormal eigenvectors in [公式] and real eigenvalues in [公式]. Suppose that [公式] is an [公式] matrix, then [公式] and [公式] are symmetric matrices. So it is not difficult to diagonalize [公式] or [公式] using a matrix with a set of orthonormal eigenvectors in its columns. Suppose that [公式] are orthonormal eigenvectors of [公式] and [公式] are eigenvalues of [公式] . Then for [公式], we have

[公式]

It is evident that the eigenvalues of [公式] equal the eigenvalues of [公式] . Similarly, we can find another orthogonal set [公式] (orthonormal eigenvectors of [公式] ). Now, we have

[公式]

[公式] [公式]

The [公式] 's are singular values, square roots of the eigenvalues of [公式] and [公式] . From equations(1), we can get

[公式]

Since [公式], it is easy to find [公式]

[公式] .

Suppose that singular values [公式] to [公式] are positive numbers. Then the equations (3) [公式]show that[公式][公式]

[公式][公式]

or [公式]. Now we include [公式] more [公式] 's and [公式] more [公式] 's in orthogonal matrices [公式] and [公式] .Finally, [公式] becomes [公式] ,i.e. [公式].

### Theorem

Any [公式] matrix [公式] has a decomposition [公式] .

[公式] is an [公式] orthogonal matrix.

[公式] is an [公式] orthogonal matrix.

[公式] is an [公式] matrix [公式] , in which [公式] .

We usually put the singular values of [公式] in descending order, [公式] [公式] [公式] . This kind of factorization is called the singular value decomposition(SVD).

## The Geometry of the SVD
After explaining the matrices in the SVD, let's look at the SVD from a different perspective. The geometric meanings of the SVD are great intuitive interpretations of this kind of factorization. We know that every symmetric matrix [公式] has decomposition: [公式]. This represents a transformation:(rotate)(stretch)(rotate back).

As for the singular value decomposition, any matrix can be separated into three pieces: orthogonal matrix, "diagonal" matrix, another orthogonal matrix. Let's consider a linear transformation [公式] , in which [公式] using SVD. The geometric meanings of this transformation is :(rotate)(stretch)(rotate). The following picture illustrates the geometry behind the SVD when matrix [公式] is a [公式] matrix.



## Get Started

- 👉 [**Create a new site**](https://wowchemy.com/templates/)
- 📚 [**Personalize your site**](https://wowchemy.com/docs/)
- 💬 [Chat with the **Wowchemy community**](https://discord.gg/z8wNYzb) or [**Hugo community**](https://discourse.gohugo.io)
- 🐦 Twitter: [@wowchemy](https://twitter.com/wowchemy) [@GeorgeCushen](https://twitter.com/GeorgeCushen) [#MadeWithWowchemy](https://twitter.com/search?q=(%23MadeWithWowchemy%20OR%20%23MadeWithAcademic)&src=typed_query)
- 💡 [Request a **feature** or report a **bug** for _Wowchemy_](https://github.com/wowchemy/wowchemy-hugo-modules/issues)
- ⬆️ **Updating Wowchemy?** View the [Update Guide](https://wowchemy.com/docs/guide/update/) and [Release Notes](https://wowchemy.com/updates/)

## Crowd-funded open-source software

To help us develop this template and software sustainably under the MIT license, we ask all individuals and businesses that use it to help support its ongoing maintenance and development via sponsorship.

### [❤️ Click here to become a sponsor and help support Wowchemy's future ❤️](https://wowchemy.com/plans/)

As a token of appreciation for sponsoring, you can **unlock [these](https://wowchemy.com/plans/) awesome rewards and extra features 🦄✨**

## Ecosystem

* **[Hugo Academic CLI](https://github.com/wowchemy/hugo-academic-cli):** Automatically import publications from BibTeX

## Inspiration

[Check out the latest **demo**](https://academic-demo.netlify.com/) of what you'll get in less than 10 minutes, or [view the **showcase**](https://wowchemy.com/user-stories/) of personal, project, and business sites.

## Features

- **Page builder** - Create *anything* with [**widgets**](https://wowchemy.com/docs/page-builder/) and [**elements**](https://wowchemy.com/docs/writing-markdown-latex/)
- **Edit any type of content** - Blog posts, publications, talks, slides, projects, and more!
- **Create content** in [**Markdown**](https://wowchemy.com/docs/writing-markdown-latex/), [**Jupyter**](https://wowchemy.com/docs/import/jupyter/), or [**RStudio**](https://wowchemy.com/docs/install-locally/)
- **Plugin System** - Fully customizable [**color** and **font themes**](https://wowchemy.com/docs/customization/)
- **Display Code and Math** - Code highlighting and [LaTeX math](https://en.wikibooks.org/wiki/LaTeX/Mathematics) supported
- **Integrations** - [Google Analytics](https://analytics.google.com), [Disqus commenting](https://disqus.com), Maps, Contact Forms, and more!
- **Beautiful Site** - Simple and refreshing one page design
- **Industry-Leading SEO** - Help get your website found on search engines and social media
- **Media Galleries** - Display your images and videos with captions in a customizable gallery
- **Mobile Friendly** - Look amazing on every screen with a mobile friendly version of your site
- **Multi-language** - 34+ language packs including English, 中文, and Português
- **Multi-user** - Each author gets their own profile page
- **Privacy Pack** - Assists with GDPR
- **Stand Out** - Bring your site to life with animation, parallax backgrounds, and scroll effects
- **One-Click Deployment** - No servers. No databases. Only files.

## Themes

Wowchemy and its templates come with **automatic day (light) and night (dark) mode** built-in. Alternatively, visitors can choose their preferred mode - click the moon icon in the top right of the [Demo](https://academic-demo.netlify.com/) to see it in action! Day/night mode can also be disabled by the site admin in `params.toml`.

[Choose a stunning **theme** and **font**](https://wowchemy.com/docs/customization) for your site. Themes are fully customizable.

## License

Copyright 2016-present [George Cushen](https://georgecushen.com).

Released under the [MIT](https://github.com/wowchemy/wowchemy-hugo-modules/blob/master/LICENSE.md) license.
