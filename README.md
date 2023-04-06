**🚨 Note: This project is a work in progress. Use at your own risk. Setup steps are incomplete and may be outdated. The deploy to Netlify buttons might not work. I hope to have this project ready to use by mid April 2023. 🚨**

[![Netlify Status](https://api.netlify.com/api/v1/badges/5ebf7378-bb17-482f-8e28-8dfbe0cd8a6a/deploy-status)](https://app.netlify.com/sites/eleventy-sveltia-cms-starter/deploys)

# Eleventy Sveltia CMS Starter

## https://sveltia-cms.danurbanowicz.com/

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/danurbanowicz/eleventy-sveltia-cms-starter&stack=cms)

### TODO
- Add steps for auth setup
- Add steps for configuring the CMS
- Add quick CMS tips e.g. preferences
- Add steps for local Eleventy development

### What is it?

This is a template for building a simple blog website with [Eleventy](https://www.11ty.dev), [Sveltia CMS](https://github.com/sveltia/sveltia-cms), and with automatic deployment to [Netlify](https://www.netlify.com).

The aim is to get you up and running in a few minutes with a free, fast, and secure blog website with a CMS for editing your content.

### Requirements

- A GitHub account
- A Netlify account
- Basic knowledge of the command line and git if you want to install locally

### Install this template (Easy 🦥)

1. Press the [Deploy to Netlify](https://app.netlify.com/start/deploy?repository=https://github.com/danurbanowicz/eleventy-sveltia-cms-starter&stack=cms) button
2. Follow the simple steps
3. Be awestruck by your awesomeness for choosing the easy way ✨

### Install this template (Advanced 🧪)

1. Clone this repo or press the Use this template button to create a copy in your GitHub account.
2. Make a local copy of your new repo on your computer.
3. CD to your local repo root folder and install dependencies using `npm install`
4. Open admin/config.yml and enter your GitHub repo details using the existing format and push your changes.
5. In your Netlify account, go to Sites > Add new site > Import an existing project, connect to your GitHub account, and select the new repo you created earlier. Netlify will choose a random site name for you and you can change this to something else, or use your own custom domain.
6. Back in your local copy of the repo, edit `_data/settings.yml` with your site title, description, and Netlify site URL and push your changes to GitHub.
7. Once Netlify has deployed the changes to your site, go to `https://[your-netlify-site].netlify.app/admin/` and follow the steps to log in to the CMS with your GitHub account.
8. You can now delete the sample posts and pages, and create your own new ones!

### Configure the CMS

Sveltia CMS needs to be connected to your GitHub account so it can authenticate you and make changes to your site's content. Netlify facilitates this connection to GitHub for you. Note that all of your CMS users will need to have push access to your content repository for this to work.



1. Add the following lines to your Sveltia CMS `config.yml` file:

```
backend:
  name: github
  repo: owner-name/repo-name # Path to your GitHub repository
  # branch: main # optional, defaults to master
```

### How it works

Sveltia CMS connects to your GitHub repo in the background via GitHub's GraphQL API. It uses your `config.yml` file to know what your site's data looks like (pages, blog posts etc).

When you edit content through the CMS, it makes changes to the content files in your repo as git commits. Each time you make an edit and save your changes, it pushes a new commit to your repo which in turn triggers a new Netlify build of your site. This type of workflow is commonly referred to as Continuous Deployment (CD).

All of your content edits are saved in your git repo commit history (a bit like a backup) so you can roll back to a previous version of your site at any time using standard git commands, or by using the GitHub.com website.

If you choose to install this project locally, you can use the CMS to make changes to your local repo, and then manually push those changes to your remote. This will trigger a new Netlify build of your site.


[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/danurbanowicz/eleventy-sveltia-cms-starter&stack=cms)