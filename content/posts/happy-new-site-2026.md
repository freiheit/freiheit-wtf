+++
date = '2026-01-01T09:00:00-08:00'
publishDate = '2026-01-01T01:00:00-08:00'
draft = false
title = 'Happy New Site 2026'
tags = ['hugo', 'website', 'wordpress', 'tech']
keywords = 'hugo, website, wordpress, tech, fastmail, freiheit.wtf'
summary = "A writeup about switching freiheit.wtf from Wordpress to Hugo."
Toc = true
+++

## Preamble

I had some extra free time during the winter holidays, and was unhappy with
a few things with my website; so I spent some time totally redoing it.

### Caveat for Friends/Family: Hugo is for techy nerd types

## Background

I went from hosted wordpress (via porkbun option) to
[Hugo](https://gohugo.io/). Hugo is a framework for generating a static
website that covered all the stuff I was doing with Wordpress anyway. I was
paying ~$10/month for wordpress hosting, which felt like a waste when I
wasn't doing much with it.

### Hosting my site

Turns out that the email service I've been using for all my personal email
(such as for `*@freiheit.wtf`) includes a "Files" service that supports
WebDAV and includes free website hosting services. Since I expect my
personal website to be pretty low-traffic I could likely use GitHub Pages,
AWS, CloudFlare or others and fit within the free tiers.

## So, what did I actually do?

1. Skimmed Hugo docs to figure out if it would meet my needs (yes)
2. Skimmed around some of the different hosting options, and determined that
   I had at least a few free or cheap options.
3. Looked at options for migrating my current content over, and found a few
   different options for converting from Wordpress to Hugo.
4. Installed Hugo locally (`dnf install hugo` in a distrobox on my bazzite
   desktop)
5. Followed <https://gohugo.io/getting-started/quick-start/>
   - But browsed available [Hugo Themes](https://themes.gohugo.io/) and went
     with [Terminal](https://themes.gohugo.io/themes/hugo-theme-terminal/)
     instead of the theme there.
6. Since my site really only had a couple "blog" posts and a couple pages, I
   basically just used copy-paste to recreate everything.
   - And tweaked some of the URL settings so that key things stayed with
     same paths.
7. Kept doing `hugo build` and `hugo server -D` and browsing what I was
   making until I was happy with it.
8. Followed <https://jpcaparas.medium.com/automate-fastmail-static-website-deployments-with-hugo-and-github-actions-36f7d71d7519>
   to set up a GitHub workflow so that my `main` branch is automatically
   deployed into a directory on my FastMail account.
   1. Set up `test.freiheit.wtf` website on that directory initially.
   2. Ended up needing to update from `hugo-version: '0.134.0'` to
      `hugo-version: '0.152.2'` to work properly for me.
   3. Struggled a little with the rclone steps and did some of that manually
      locally instead.
      - WEBDAV_PASSWORD needed to be base64 encoded
      - Changed from `vendor = other` to `vendor = fastmail`
   4. I also added `workflow_dispatch:` and a daily schedule to the workflow file,
      so that I can manually run it and so that I can schedule posts for the
      future and have that automatically happen.
9. Various little tweaks and stuff here and there...
10. And after I was adequately happy with everything, I turned off the old
    wordpress site and did a CNAME for <www.freiheit.wtf> and an "ALIAS" for
    freiheit.wtf to point at fastmail's hosting.

## My Code

The actual code for the site is here: <https://github.com/freiheit/freiheit-wtf>

And the code for _this post_ is here: <https://raw.githubusercontent.com/freiheit/freiheit-wtf/refs/heads/main/content/posts/happy-new-site-2026.md>

## Addendum

Note: I wrote this a few days early and scheduled it for posting on Jan 1
via that `publishDate = '2026-01-01T01:00:00-08:00'` earlier.
