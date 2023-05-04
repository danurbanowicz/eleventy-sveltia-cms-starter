[![Netlify Status](https://api.netlify.com/api/v1/badges/5ebf7378-bb17-482f-8e28-8dfbe0cd8a6a/deploy-status)](https://app.netlify.com/sites/eleventy-sveltia-cms-starter/deploys)

# Eleventy Sveltia CMS Starter

## Demo: https://sveltia-cms.danurbanowicz.com/

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/danurbanowicz/eleventy-sveltia-cms-starter)

## What is it?

This is a template for building a simple blog website with [Eleventy](https://www.11ty.dev) and [Sveltia CMS](https://github.com/sveltia/sveltia-cms), with automatic deployment to [Netlify](https://www.netlify.com).

The aim is to get you up and running in a few minutes with a free, fast, and secure blog website with a headless CMS for editing your content.

## Features

- Scores 100/100/100/100 in Lighthouse tests
- Support for blog posts, authors, tags, and website pages
- Headless [Sveltia CMS](https://github.com/sveltia/sveltia-cms) compatible with Netlify/Decap CMS
- Secure GitHub authentication (OAuth)
- Includes zero clientside JavaScript by default
- [Eleventy Image](https://www.11ty.dev/docs/plugins/image/) (sharp) processor for responsive images in next-gen formats
- Contact form for [Netlify Forms](https://www.netlify.com/products/forms/)
- CSS 1kb minified, inlined for fastest page render
- Minifies your HTML too
- Optional pipeline for minified inline JavaScript
- Uses Nunjucks templates for layout
- Netlify continuous deployment (CD) workflow

## Requirements

- A GitHub account
- A Netlify account
- Basic knowledge of the command line and git

## Quick Deploy to Netlify

Optionally, you can [Deploy to this template to Netlify](https://app.netlify.com/start/deploy?repository=https://github.com/danurbanowicz/eleventy-sveltia-cms-starter) which will create a new GitHub repository for you and link it to your Netlify account, configuring automatic deploys in one step.

*Important: You will still need to configure the CMS and set up an OAuth application in GitHub to be able to authenticate and use the CMS on your live site (see steps below).*

## Install this template

1. Clone this repo or press the **Use this template** button to create a copy in your GitHub account.
2. Make a local copy of your new repo.
3. CD to your local repo root folder and install dependencies using `npm install`
4. Open `admin/config.yml` and enter your GitHub repo details using the existing format and push your changes.
5. In your Netlify account, go to **Sites** > **Add new site** > **Import an existing project**, connect to your GitHub account, and select the new repo you created earlier. Netlify will choose a random site name for you and you can change this to something else, or use your own custom domain.
6. Back in your local copy of the repo, edit `_data/settings.yml` with your site title, description, and Netlify site URL and push your changes to GitHub.
7. Once Netlify has deployed the changes to your site, go to `https://[your-netlify-site].netlify.app/admin/` and follow the steps to log in to the CMS with your GitHub account.
8. You can now delete the sample posts and pages, and create your own new ones!

## Local development

You can work locally with Eleventy and the CMS without needing to configure any GitHub authentication. Make sure you've followed the **Install this template** steps above first.

1. To start a local Eleventy dev server, CD to your project root folder and run `npx eleventy --serve`.
2. In a browser, access the local dev URL which is usually: `http://localhost:8080/`.
3. On changes to your project files, the site will be re-built. Important: live browser reloading is disabled in `.eleventy.js` due to a conflict with Sveltia CMS, therefore you'll need to manually reload the page in the browser to see your changes.
4. To access the CMS, navigate to: `http://localhost:8080/admin/` and press the **Work with Local Repository** button, and select your local repo root folder.
5. Saved changes made to the CMS can then be committed and pushed to your remote repository.

## Configure the CMS for your live site

Sveltia CMS needs to be connected to your GitHub account so it can authenticate you and make changes to your live site's content. Netlify facilitates this connection to GitHub for you. Note that all of your CMS users will need to have push access permissions to your content repository before they can log in. *Sveltia CMS does not yet support Netlify CMS's Git Gateway authentication method.*

1. Set up OAuth: In GitHub, go to your account **Settings** and select **Developer Settings**, then **OAuth Apps** or use [this shortcut](https://github.com/settings/developers).
2. Press the **New OAuth App** button
3. For the **Authorization callback URL**, enter `https://api.netlify.com/auth/done`. For the **Homepage URL** enter your Netlify site URL e.g. `https://[your-netlify-site].netlify.app`. The other fields can contain anything you want.
4. On your new application’s GitHub overview page, make note of the **Client ID**. Generate a **Client Secret** and make note of it for later. You can’t access this secret again.
5. Next, in your Netlify site settings, go to **Site settings** > **Access control** > **OAuth** and under **Authentication Providers**, select **Install Provider**.
6. Select **GitHub** and enter the **Client ID** and **Client Secret** from earlier, then save.
7. Next, edit the following lines in your Sveltia CMS `admin/config.yml` file:

```
backend:
  name: github
  repo: owner-name/repo-name # Path to your GitHub repository
  branch: master # Optional, defaults to master
```
8. Push your changes to GitHub, wait for the new deploy to complete, and try logging in to your CMS admin e.g. `https://[your-netlify-site].netlify.app/admin/`.

## How Sveltia CMS works

Sveltia CMS connects to your GitHub repo in the background via GitHub's GraphQL API. It uses your `admin/config.yml` file to know what your site's data looks like (pages, blog posts etc).

When you edit content through the CMS, it makes changes to the content files in your repo as git commits. Each time you make an edit and save your changes, it pushes a new commit to your repo which in turn triggers a new Netlify build of your site. This type of workflow is commonly referred to as Continuous Deployment (CD).

All of your content edits are saved in your git repo commit history so you can roll back to a previous version of your site at any time using standard git commands, or by using the GitHub.com website UI.

If you choose to install this project locally, you can use the CMS to make changes to your local repo, and then manually push those changes to your remote (see steps above). This will trigger a new Netlify build of your site.

## Getting help with this template

If you need help setting up this template, or if you have any ideas or suggestions, head over to [Discussions](https://github.com/danurbanowicz/eleventy-sveltia-cms-starter/discussions) and create a new discussion.

If you've found a bug or think something in this template is broken (very possible) please [open a new issue](https://github.com/danurbanowicz/eleventy-sveltia-cms-starter/issues) and provide as much information as you can to ensure a fast solution.

If you have a question specifically related to the Sveltia CMS project, we recommend you to head over there and [open a discussion](https://github.com/sveltia/sveltia-cms/discussions) for faster support.

## TO DO
- Add quick CMS tips e.g. Sveltia CMS preferences
- Finish the authors and blog page layouts
- Add descriptive comments in project files to help new users
