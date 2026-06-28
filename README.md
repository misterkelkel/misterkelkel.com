# misterkelkel.com

A small personal "about me" page.

## Files

```
index.html      → the page
style.css       → all styling
images/photo.jpg → your photo
CNAME           → tells GitHub Pages to serve this at misterkelkel.com
```

## How to put this on GitHub Pages with your domain

1. **Create a repo** on GitHub (e.g. `misterkelkel-site`). It can be public or private — Pages works either way on a paid plan, but must be public on the free plan.

2. **Upload these files** to the repo (drag-and-drop on github.com works fine, or `git push` if you're comfortable with git). Keep the folder structure as-is — `images/photo.jpg` needs to stay at that path since `index.html` references it directly.

3. **Turn on GitHub Pages**:
   - Go to your repo → **Settings** → **Pages**
   - Under "Build and deployment", set **Source** to "Deploy from a branch"
   - Pick the `main` branch and `/ (root)` folder → Save
   - GitHub will give you a URL like `https://yourusername.github.io/misterkelkel-site`

4. **Point your domain at it**:
   - The `CNAME` file in this folder already contains `misterkelkel.com` — that tells GitHub which domain to serve.
   - At your domain registrar (wherever you bought misterkelkel.com), add these DNS records:
     - Four **A records** for the root domain (`@`) pointing to GitHub's IPs:
       ```
       185.199.108.153
       185.199.109.153
       185.199.110.153
       185.199.111.153
       ```
     - One **CNAME record** for `www` pointing to `yourusername.github.io`
   - Back in repo **Settings → Pages**, enter `misterkelkel.com` in the custom domain field and save. Once DNS propagates (can take up to a few hours), check "Enforce HTTPS".

5. Visit **misterkelkel.com** 🎉

## Feedback form

The feedback form uses [Web3Forms](https://web3forms.com) — a free service that emails you form submissions, no backend needed. It's already wired up with your access key, so it should work as-is once the site is live.

- Submissions get emailed to whatever address you used to sign up for Web3Forms.
- The free plan covers a generous number of submissions/month — plenty for a personal site.
- If you ever need to change the access key (e.g. you create a new Web3Forms account), open `index.html` and replace the value in this line:
  ```html
  <input type="hidden" name="access_key" value="YOUR_ACCESS_KEY">
  ```

## Editing later

- **Swap the photo**: just replace `images/photo.jpg` with a new file of the same name (any image works, but keep it roughly portrait-shaped for the frame to look right).
- **Change the text**: open `index.html`, edit the text inside the `<p>` tags in the `.blurb` section, or the `<h1>`/tagline at the top.
- **Change the Instagram link**: edit the `href` in the `<a class="ig-link">` tag in `index.html`.
