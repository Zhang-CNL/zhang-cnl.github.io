# Minimalist Hugo Template for Academic Websites

This repository contains a [Hugo](https://github.com/gohugoio/hugo) template to create a personal academic website. The template uses the [PaperMod theme](https://github.com/adityatelange/hugo-PaperMod) but modifies it in various ways to be more minimalist and better suited for academic websites. The website is hosted on [GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages).

## Documentation

The template is documented at https://pascalmichaillat.org/b/.

## Illustration

The website produced by the template can be viewed at https://pascalmichaillat.org/hugo-website/.

## Installation

+ The first time that you push your repository to GitHub, you need to allow GitHub Actions and GitHub Pages so the website can be built and deployed to GitHub Pages.
+ The first step is to [ask GitHub to publish the website with a GitHub Action](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#publishing-with-a-custom-github-actions-workflow). GitHub offers a ready-made action to publish a Hugo website, called `Deploy Hugo site to Pages`. This action must be enabled in the [Pages Settings](https://github.com/pmichaillat/hugo-website/settings/pages) of your GitHub repository. You can view the workflow triggered by the action in the `.github/workflows/hugo.yml` file.
+ Once the GitHub Actions are enabled, GitHub will build and publish the website as soon as the repository is updated. 
+ If you would like to update the deployment action (for instance because it became outdated and fails to deploy the site), you can find the [most recent action on GitHub]( https://github.com/actions/starter-workflows/blob/main/pages/hugo.yml). You can place this file directly in the `.github/workflows` folder to replace the old `hugo.yml` file—but make sure to set `push: branches` to `["main"]`.

## Usage

### Online deployment

Once your website is ready to be made public, commit your content and template changes and push them to the website repository on GitHub. It is convenient to use GitHub Desktop for this Git operation.

On each push, the [GitHub Actions workflow](https://github.com/pmichaillat/hugo-website/actions/workflows/hugo.yml) invokes Hugo to generate the website and deploys the output to [GitHub Pages](https://github.com/pmichaillat/hugo-website/deployments/github-pages). During the workflow, Hugo processes your content, templates, and other project files and generates a static website.

### Publishing lab content
+ Clone the repository and `cd` into it
+ `cd` into the `content/` folder and either `blog/`, `books/`, or `papers/`
+ Add a new folder with the title of your post
+ Create a file titled `index.md` and write everything necessary in there. Any supplementary materials/pdfs should go in the same folder
    + A template for `index.md` is at the bottom and in [this repo](./archetypes/paper.md)
+ Push your changes to main and github actions will automatically refresh the site.

## License

This repository is licensed under the [MIT License](LICENSE.md).

## Index template
```
---
title: "[Title as string]"
date: YYYY-MM-DD
tags: ["tags","as","array","of","strings"]
author: ["Authors","as","array"]
description: "Long description of paper/background"
summary: "Long summary of paper"
cover:
    image: "title-picture-in-same-folder.png"
    alt: "Alternative title"
    relative: true
editPost:
    URL: "https://url-to-somewhere-to-edit.com"
    Text: "Journal publication/whatever to display in front of url"
---
Actual text of your article.
Markdown and LaTeX support via [KaTeX](https://katex.org/).
```
