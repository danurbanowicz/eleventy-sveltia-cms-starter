---
layout: layouts/contact.njk
title: Contact
description: This is a sample meta description. If one is not present in your page/post's front matter, the default settings.description will be used instead.
section: contact
date: 2018-01-01
permalink: /contact/index.html
eleventyNavigation:
  key: contact
  title: Contact
  order: 3
---
This is an example of a contact page.

You can edit this content with the CMS  at [Pages > Contact](/admin/#/collections/pages/entries/contact) or you can edit the Markdown file directly at `pages/contact.md`.

This page uses a custom page template located at `includes/layouts/contact.njk`.

The contact form on this page uses [Netlify Forms](https://www.netlify.com/docs/form-handling/) to process submissions,
and saves them in the connected Netlify account where notifications can
optionally be configured. Each submission is passed through a spam filter and
if flagged, will display a CAPTCHA challenge to the user.

After deployment, you should see this form show up in your Netlify site settings under **Forms**.
