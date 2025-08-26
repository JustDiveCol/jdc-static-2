# 🚀 Release Checklist – JustDiveCol Static

Use this checklist whenever you make changes to `static.justdivecol.com`  
(e.g., new tokens, updated logos, fonts, or manifests).

---

## 1. Pick version

- Use **today’s date** as the version number: `YYYY.MM.DD`
- Example: `2025.08.25`

---

## 2. Update files

- In `README.md` → update the **version badge** at the top:
  ```md
  ![Version](https://img.shields.io/badge/version-2025.08.25-blue)
  ```
- In `CHANGELOG.md` → add a new section at the top:
  ```md
  ## [2025-08-25]

  ### Changed

  - Updated tokens with new brand color
  ```

---

## 3. Commit & tag

Run these commands:

```bash
git add README.md CHANGELOG.md
git commit -m "chore(static): release 2025.08.25"
git tag static-v2025.08.25
git push && git push --tags
```

---

## 4. Update apps

In each consuming app (`www`, `my`, etc.), update query strings in imports:

```html
<link
  rel="stylesheet"
  href="https://static.justdivecol.com/css/tokens.css?v=2025.08.25" />
```

---

✅ Done. All apps will now pull the new version of tokens/logos/fonts.
