# Ashok Bhupathy K S — Personal Portfolio

A single-page, static portfolio site. No build step, no framework, no dependencies to install — it's plain HTML/CSS/JS and can be opened directly or deployed to GitHub Pages as-is.

---

## A. Final folder structure

```text
portfolio/
├── index.html
├── README.md
├── Ashok_Bhupathy_KS_Resume.pdf
├── css/
│   └── style.css
├── js/
│   └── main.js
└── assets/
    ├── icons/
    │   └── favicon.svg
    ├── images/
    │   ├── profile.jpg                  (hero portrait)
    │   ├── kizuna-logo.png
    │   ├── kizuna-screenshot.jpg
    │   ├── project-face-1.jpg ... 4.jpg (Face Recognition project screenshots)
    │   └── project-anna-1.jpg ... 3.jpg (A.N.N.A. project screenshots)
    └── certificates/
        ├── best-paper-award.jpg
        ├── gold-medal.jpg
        ├── jlpt-n3-certificate.jpg
        ├── accenture-certificate.pdf          (original document, downloadable)
        └── accenture-certificate-preview.jpg  (rendered preview for the on-page card/lightbox)
```

## B. Exact file names — keep these unchanged

The HTML/CSS/JS reference every filename below by exact, case-sensitive path. If you rename any of these, update the matching `src=`, `href=`, `data-full=`, or `data-pdf=` attribute in `index.html`.

| Purpose | Exact filename | Folder |
|---|---|---|
| Resume (download button) | `Ashok_Bhupathy_KS_Resume.pdf` | project root |
| Hero photo | `profile.jpg` | `assets/images/` |
| Best Paper Award | `best-paper-award.jpg` | `assets/certificates/` |
| Gold Medal / Certificate of Excellence | `gold-medal.jpg` | `assets/certificates/` |
| Accenture certificate (original, for download) | `accenture-certificate.pdf` | `assets/certificates/` |
| Accenture certificate (on-page preview image) | `accenture-certificate-preview.jpg` | `assets/certificates/` |
| JLPT N3 certificate | `jlpt-n3-certificate.jpg` | `assets/certificates/` |
| KizunaLingua logo | `kizuna-logo.png` | `assets/images/` |
| KizunaLingua site screenshot | `kizuna-screenshot.jpg` | `assets/images/` |
| Face-recognition project screenshots | `project-face-1.jpg` – `project-face-4.jpg` | `assets/images/` |
| A.N.N.A. project screenshots | `project-anna-1.jpg` – `project-anna-3.jpg` | `assets/images/` |
| Favicon | `favicon.svg` | `assets/icons/` |

---

## C. Certificate deployment details

Every certificate is shown as a **thumbnail card** in the Achievements section (and the N3 certificate again in the Japanese section). Clicking a card opens it full-size in an on-page lightbox (`js/main.js`, `openLightbox()`), closable via the ✕ button, clicking outside the image, or pressing **Escape**.

- **Best Paper Award** → `assets/certificates/best-paper-award.jpg`, referenced in the `.cert-card` with `data-full="assets/certificates/best-paper-award.jpg"`.
- **Gold Medal** → `assets/certificates/gold-medal.jpg`.
- **Accenture Certificate** → the card displays `accenture-certificate-preview.jpg` (an image rendered from the original PDF for fast on-page viewing); the same card carries `data-pdf="assets/certificates/accenture-certificate.pdf"`, which powers a **"Download Original ⬇"** button inside the lightbox so visitors can get the real PDF.
- **JLPT N3 Certificate** → `assets/certificates/jlpt-n3-certificate.jpg`, shown both in Achievements and in the Japanese section.

**To replace a certificate later:** drop the new file into `assets/certificates/` using the *same filename* (simplest — nothing else to change), or use a new filename and update the corresponding `src=`/`data-full=` (and `data-pdf=` for Accenture) attributes in `index.html`.

## D. Photo deployment details

- Filename: `profile.jpg`, folder: `assets/images/`.
- Format: JPEG. Recommended resolution: at least 1000×1250px (4:5 portrait) so it stays sharp at full width on large screens.
- To replace: swap the file (same name), or add a new file and update the `src` on the `<img>` inside `.hero-photo` in `index.html`.

## E. Resume deployment details

- Filename: `Ashok_Bhupathy_KS_Resume.pdf`, location: project root (same folder as `index.html`).
- Three places link to it: the **Download Resume** hero button, the **Resume** section CTA, and it's reused sitewide — search `index.html` for `Ashok_Bhupathy_KS_Resume.pdf` to find every reference.
- To replace: drop in a new PDF with the same filename, or rename and update the `href` in those three spots.

---

## F. GitHub Pages deployment (beginner-friendly)

1. Create a new repository on GitHub (e.g. `ashok-portfolio`).
2. Upload **the entire contents of this `portfolio/` folder** — not the folder itself — so `index.html` sits at the repository root.
3. Confirm `index.html` is directly visible in the repo's file list (not nested inside another folder).
4. Commit the files (via GitHub's web uploader, or `git add . && git commit -m "Deploy portfolio" && git push`).
5. Open the repository's **Settings** tab.
6. Go to **Pages** in the left sidebar.
7. Under **Build and deployment → Source**, select **Deploy from a branch**.
8. Choose the branch (usually `main`) and folder **`/ (root)`**.
9. Click **Save**.
10. Wait 1–2 minutes for GitHub to build and deploy.
11. Open the generated URL (shown at the top of the Pages settings, typically `https://<username>.github.io/<repo-name>/`).
12. Click through every section, certificate, and button to confirm assets loaded correctly on the live URL.

---

## G. Updating the website later

| To update... | Edit this |
|---|---|
| Profile photo | Replace `assets/images/profile.jpg` |
| Resume | Replace `Ashok_Bhupathy_KS_Resume.pdf` |
| Any certificate | Replace the matching file in `assets/certificates/` |
| Gold medal image | Replace `assets/images/... ` → `assets/certificates/gold-medal.jpg` |
| About section text | `index.html` → `<section id="about">` |
| Cognizant / current role | `index.html` → `.status-chip` (top of hero) and the first `.tl-item.current` card in `<section id="experience">` |
| Skills | `index.html` → `<section id="skills">`, add/remove `<span class="chip">` items |
| Projects | `index.html` → `<section id="projects">` |
| Japanese level / progress | `index.html` → `<section id="japanese">`, the `.jp-path` steps |
| KizunaLingua link | `index.html` → search for `kizunalingua-spec.github.io` (appears in hero CTA, KizunaLingua section, footer) |
| Email | `index.html` → search for `ashokbhupathyks@gmail.com` (appears in several `mailto:` links) |
| LinkedIn | `index.html` → search for `linkedin.com/in/ashokbhupathy` |
| GitHub | Not currently linked anywhere — no GitHub URL was provided. Add a link in `.contact-meta` and the footer `.f-links` once you have one. |
| Colors / fonts / spacing | `css/style.css` → the `:root` variables at the top of the file |

---

## H. Troubleshooting

- **GitHub Pages shows a 404** — `index.html` isn't at the repo root, or Pages hasn't finished building yet (wait a minute and refresh). Check Settings → Pages for a green "Your site is live" message.
- **Images not loading** — check the browser console (F12 → Console) for the exact missing path; filenames on GitHub Pages are **case-sensitive** even though your own computer might not be.
- **A certificate won't open** — confirm the file exists under `assets/certificates/` with the exact name referenced in `data-full` in `index.html`.
- **Resume won't download** — confirm `Ashok_Bhupathy_KS_Resume.pdf` is at the repo root, exact filename, exact case.
- **CSS/JS missing on the live site** — check that `css/style.css` and `js/main.js` were actually uploaded, and that the `<link>`/`<script>` paths in `index.html` are relative (they already are, so this usually means a missed upload).
- **Old version still showing after you push changes** — hard-refresh (Ctrl/Cmd+Shift+R) or wait a couple of minutes; GitHub Pages caches briefly.
- **Broken links** — search `index.html` for `href="` and check each one manually if you've edited URLs.
- **Mobile layout looks off** — the site is responsive down to ~375px; if something overflows, it's almost always a very long unbroken word or URL pasted into a text field — wrap it or shorten it.

---

## I. Final deployment checklist

```text
☐ Upload complete project (index.html at repo root)
☐ Verify CSS loads (css/style.css)
☐ Verify JS loads (js/main.js)
☐ Verify profile photo
☐ Verify resume download
☐ Verify Best Paper Award certificate opens
☐ Verify Gold Medal certificate opens
☐ Verify Accenture certificate opens + downloads original PDF
☐ Verify JLPT N3 certificate opens
☐ Test certificate lightbox (open, close via ✕/outside-click/Escape)
☐ Test all navigation links (desktop + mobile hamburger)
☐ Test Email Me / Talk to Me / Hire Me buttons (opens mail client)
☐ Test Download Resume
☐ Test KizunaLingua link (opens kizunalingua-spec.github.io)
☐ Test A.N.N.A. live demo link
☐ Test LinkedIn link
☐ Test on mobile width (~375–430px) and desktop width
☐ Enable GitHub Pages
☐ Test the final deployed URL end-to-end
```

---

## Notes on content accuracy

Per your instruction, nothing on this site was fabricated. Two things worth knowing:

1. **Cognizant role**: your resume and certificates don't mention Cognizant. Per your instructions, the site presents it as your **current role**, in place since **September 2026** — shown in the hero status chip, the About facts, and as the top (current) entry in the Experience timeline. No specific day-to-day responsibilities were invented; the timeline description is intentionally general until you provide the real details to replace it with.
2. **Accenture certificate**: the document in your files is a **Forage job-simulation certificate** ("Data Analytics and Visualization Job Simulation," issued by Forage, completed June 12, 2024) rather than a direct Accenture internship letter. The site labels it accurately as a job simulation while still crediting Accenture, since that's what the certificate itself says.
3. **GitHub**: no GitHub profile URL was found anywhere in your files, so no GitHub link was added. Add one yourself once you have a public profile (see table above for where).
