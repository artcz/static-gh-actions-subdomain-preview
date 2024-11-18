# static-gh-actions-subdomain-preview
Generate preview link on every PR

This is a demo of a setup based on this repository: https://github.com/artcz/nginx-wildcard-static-server

It's using github actions with scp to deploy a preview to a folder on a remote VPS.
Then it adds/updates a comment with a link to the preview.

## FAQ

**Why use a sanitised branch name and not a commit hash?**

Commit hash would be simpler and better, but the downside is that you can't reload in the browser after you pushed another commit – because the new version will have a new url..

**It just does the scp, it doesn't invalidate old files. Why?**

This is just for demo purposes with a single file to ilustrate the subdomains and the github actions bot.
In practice you probably want to push a tarball to the remote server, and then run a script on that server to deploy it propoperly.
Probably by removing the old folder first, and then unpacking the new one so it's completely replaced.

**What about old, stale versions?**

In this version of the demo/poc, they are not handled (see previous question).
In practice there should be some cleanup action after PR is merged and/or branch deleted.
