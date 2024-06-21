## Steps for Owen

1. Install hugo. Add it to path (ask claude for help).

2. Move into owen-site. Download submodule with:

```bash
git submodule update --init --recursive
```

3. You're good to go!

## Uploading the site

1. Move into owen-site (cd owen-site)
2. Remove the old build using `rmdir public`
3. Re-build using `hugo`.

Then, add the new files to git:

```bash
git add .
git commit -m "commit message here"
git push
```