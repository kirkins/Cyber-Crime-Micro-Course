---
layout: default
title: Installation
nav: install
---

## Installation

To start using this template and take advantage of the automatic building system, follow these steps:

### Create a copy of this repository

There are many ways to do that, though the simplest is probably just by using the GitHub's **Fork** feature, which basically means "duplicate a repository". After forking, you'll have an option to change the repository name.

### Setup a WebHook

Find your repository on GitHub, and go under **Settings** -> **Webhooks & Services**. Find the **Add webhook** button on the top right, and click it.

Fill in the box with the following options (unless told otherwise):

- **Payload URL**: `http://bits.usc.edu/md_receiver/receiver.php`
- **Content type**: `application/json`
- **Secret**: _(ask an admin)_
- **Which events would you like to trigger this webhook?**: Just the `push` event
- **Active**: checked

Secret is in the www/docs/md_receiver/secret.php

 You will also need to add `usc-md-bot` with read access to your website repo. (The bot account used may change - it is defined in `github_account.json` in `md_receiver`.)

### Register your website

Make a change to the [`sites.json` file in the `md_receiver` repository](https://github.com/usc-cs/md_receiver/blob/master/sites.json) and submit a pull request. In a nutshell, this means:

- Fork [`md_receiver`](https://github.com/usc-cs/md_receiver)
- Make your change, add, commit, push
- Submit a Pull Request from GitHub requesting your commit to be merged into the main repository
- Wait for approval, and done.

You'll need to add an object in the json file that describes your site, following this structure:

```js
{
  // other repos here...
  "username_or_orgname/reponame": {
    "target": "target_url"
  }
}
```

Where `target_url` is where your website will be deployed to (e.g., `http://bits.usc.edu/target_url`).

After the sites.json has been updated, you will need to do a pull on the `bits.usc.edu:www/docs/md_receiver` folder.  Use `git pull`.

Alternatively, if you expect that you will be creating multiple sites, ask an admin to become a collaborator of that repository.

### Make your changes as usual

Follow the [Usage Guide]({{ site.url }}/guide.html), and edit your website. Create pages, upload files, etc. Take advantage of git's collaborative nature and go crazy with your fellow teaching staff.

### Deploy!

Make sure you've committed all your changes and pushed to GitHub. After then, run the following line:

```
git push origin master:deploy
```

This command updates the `deploy` branch to where `master` is. The website will only be deployed whenenever the `deploy` branch changes!

**Important!** Notice that this bahvior is different from the original CS 104 website. Now, you can collaborate on the `master` branch without having to worry about deploying an unfinished version of your website.

If everything is setup properly, you should get an email shortly after you push, notifying you of the deployment.



