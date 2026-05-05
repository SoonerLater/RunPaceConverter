# Pace Converter

A simple Progressive Web App (PWA) to convert running pace between **minutes per mile** and **minutes per kilometer**. Works offline and can be installed on Android (or iPhone) from the browser.

---

## Deploy to GitHub Pages (recommended)

1. **Create a new repository** on GitHub — name it anything, e.g. `pace-converter`
2. **Upload all these files**, keeping the folder structure:
   ```
   index.html
   manifest.json
   sw.js
   icons/
     icon-192.png
     icon-512.png
   ```
3. Go to your repo's **Settings → Pages**
4. Under *Source*, choose **Deploy from a branch → main → / (root)**
5. Click **Save**. GitHub will give you a URL like `https://yourusername.github.io/pace-converter/`

That's it! Share that URL with your daughter.

---

## How she installs it on her Android phone

1. Open the URL in **Chrome**
2. Tap the **three-dot menu (⋮)** in the top right
3. Tap **"Add to Home screen"**
4. Tap **Add** — it will appear on her home screen like a regular app
5. It works **offline** after the first visit

---

## Deploy to GitLab Pages (alternative)

1. Create a new GitLab project
2. Upload the same files
3. Add this file as `.gitlab-ci.yml`:

```yaml
pages:
  stage: deploy
  script:
    - mkdir -p public
    - cp -r index.html manifest.json sw.js icons public/
  artifacts:
    paths:
      - public
  only:
    - main
```

4. Push — GitLab will publish to `https://yourusername.gitlab.io/pace-converter/`

---

## How it works

- Type a pace into either field (min + sec separately)
- The other field updates instantly as you type
- The green border shows which field is "driving" the conversion
- Tap **Clear** to reset both fields
- The conversion factor used is **1 mile = 1.60934 km**
