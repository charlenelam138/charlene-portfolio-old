# Charlene Lam — Portfolio (plain HTML/CSS/JS rebuild)

This is a hand-coded rebuild of charlene-lam.com, built to replace the Wix version.
No build tools, no framework, no monthly fee, just files.

## What's in here

```
index.html            home page
about.html            about page
engineering.html      engineering project grid
design.html           design project grid
art.html               art project grid
photography.html      concert photography masonry gallery
sageware.html, apple.html, ...   one page per project (placeholders, see below)
project-template.html  the template those project pages were generated from
css/style.css          all styling
js/main.js              mobile nav toggle + photo lightbox
```

## Images — important, do this first

Right now every image tag points straight at your old Wix media URLs
(static.wixstatic.com/...) so the site looks right immediately. That's fine as a
stopgap, but Wix could change or remove those files at any time since your
site no longer lives there. Before you consider this "done":

1. Right-click and save each image you want to keep (or export them from your
   Wix media manager if it lets you).
2. Drop them into the `images/` folder.
3. In each HTML file, swap the `src="https://static.wixstatic.com/..."` with
   `src="images/yourfilename.jpg"`.

## The individual project pages are placeholders

Your old site links out to ~17 project case-study pages (Sageware, Mac R&D,
RoboUmp, the portrait paintings, etc.). I generated a page for each one so
none of the links break, but they currently just have the title, one image,
and a "coming soon" placeholder paragraph. Send me the write-up/photos for
any of them (or point me at the live Wix page) and I'll build out the full
case study to match.

## How to preview it locally

Just open `index.html` in a browser, no server needed. Or, from this folder:

```
python3 -m http.server 8000
```

then visit `http://localhost:8000`.

## How to put it online (free)

**Easiest: Netlify**
1. Go to app.netlify.com, sign up free.
2. Drag this whole folder onto the "Deploy manually" box on your dashboard.
3. You get a live URL in about 10 seconds.
4. Site settings → Domain management → add your own domain
   (charlene-lam.com) and follow the DNS steps it gives you.

**Also good: GitHub Pages**
1. Create a GitHub repo, push these files to it.
2. Repo Settings → Pages → set source to the main branch.
3. Add a `CNAME` file with your domain if you're using a custom one.

Either way, hosting itself is $0/month. The only ongoing cost is the domain
name (~$12–15/year through Namecheap, Cloudflare, or wherever you renew it
now — you can point your existing domain at the new host instead of buying a
new one).

## Editing later

Every page is a plain HTML file, so you can open any of them in a text editor
and change text directly. The header/nav is duplicated at the top of every
page (that's normal for a no-build-tool static site) — if you ever want a
"change it once, updates everywhere" nav, that's the point where moving to a
static site generator (11ty, Astro) or React would start to pay off. For a
portfolio this size, plain HTML is the right call: nothing to install, no
build step, and any future you (or another dev) can read it instantly.
