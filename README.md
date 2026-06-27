# Yash Malakar — Professional UI/UX Resume Website

A modern, animated, responsive resume website built with **HTML, CSS, JavaScript, and Reveal.js**. Includes a printable resume page and an animated slide deck.

## 📁 Files Overview

- **`index.html`** — Main resume website (home page)
- **`styles.css`** — Responsive styling with animations and dark theme
- **`script.js`** — Scroll animations and interactivity
- **`resume-print.html`** — Print-friendly single-page resume (optimized for PDF export)
- **`slides.html`** — Animated presentation deck using Reveal.js (exportable to PDF)
- **`.github/workflows/generate-pdf.yml`** — GitHub Actions workflow for automatic PDF generation

## 🚀 Quick Start

### Option 1: View Locally (No Installation)

1. **Download or clone this repo:**
   ```bash
   git clone https://github.com/yashmalakar200528-lang/resume-site.git
   cd resume-site
   ```

2. **Serve the files locally:**
   - **With Python 3:**
     ```bash
     python3 -m http.server 8000
     ```
   - **With Node.js:**
     ```bash
     npx http-server -p 8000
     ```

3. **Open in browser:**
   - Main site: `http://localhost:8000/index.html`
   - Print resume: `http://localhost:8000/resume-print.html`
   - Slide deck: `http://localhost:8000/slides.html`

### Option 2: View on GitHub Pages

After pushing files to your repo:

1. Go to **Settings → Pages**
2. Select **Source: Deploy from branch → main (/ root)**
3. Click **Save**
4. Your site will be live at: `https://yashmalakar200528-lang.github.io/resume-site/`

## 📄 Generate PDF

### Method 1: Browser Print (Fast & Easy)

1. Open `http://localhost:8000/resume-print.html` (or use GitHub Pages URL)
2. **File → Print** (or `Ctrl+P`)
3. **Destination:** Save as PDF
4. **Settings:**
   - Paper size: A4 or US Letter
   - Margins: Default (8–12mm)
   - ✓ Enable "Background graphics"
5. Click **Save**

### Method 2: GitHub Actions Workflow (Automated)

The workflow `.github/workflows/generate-pdf.yml` automatically generates `resume.pdf` on every push:

1. **Trigger workflow manually:**
   - Go to your repo → **Actions** tab
   - Select **"Generate Resume PDF"**
   - Click **Run workflow**

2. **Download artifact:**
   - Wait for the workflow to complete
   - Click the workflow run → **Artifacts** → download **resume-pdf**

3. **Or**: PDF is auto-committed to the repo if CI setup allows.

### Method 3: Generate Locally with Puppeteer (Advanced)

```bash
npm install puppeteer http-server

# Start server
npx http-server -p 8080 -c-1 . &

# Generate PDF
node -e "
const puppeteer = require('puppeteer');
(async () => {
  const browser = await puppeteer.launch({ args: ['--no-sandbox'] });
  const page = await browser.newPage();
  await page.goto('http://127.0.0.1:8080/resume-print.html', { waitUntil: 'networkidle0' });
  await page.pdf({ path: 'resume.pdf', format: 'A4', printBackground: true });
  await browser.close();
  console.log('PDF saved: resume.pdf');
})();
"
```

## 🎨 Customization

### Change Colors & Fonts

Edit **`styles.css`** root variables:

```css
:root {
  --bg: #0f0b1a;          /* Background */
  --accent: #ff7aa2;      /* Pink accent */
  --accent-2: #7be4ff;    /* Cyan accent */
  --text: #f5f7fb;        /* Text color */
}
```

### Update Content

1. **Main site (`index.html`):**
   - Replace name, email, links, skills, projects
   - Update professional summary and certifications

2. **Print resume (`resume-print.html`):**
   - Update header, summary, skills, experience sections
   - Adjust fonts and layout in `<style>` block

3. **Slide deck (`slides.html`):**
   - Edit `<section>` slides with your content
   - Customize colors and styling in `<style>`

## 🔧 Technologies Used

- **HTML5** — Semantic markup
- **CSS3** — Responsive design, animations, dark theme
- **JavaScript** — Scroll animations, interactivity
- **Reveal.js** — Animated slide presentation
- **Puppeteer** — Headless Chrome PDF generation
- **GitHub Actions** — CI/CD workflow for PDF generation

## 📋 Features

✅ Fully responsive (mobile, tablet, desktop)
✅ Dark theme with creative gradient accents
✅ Scroll animations (fade-in on scroll)
✅ Print-friendly layout (optimized for PDF export)
✅ Animated slide deck (exportable to PDF)
✅ GitHub Pages ready
✅ GitHub Actions workflow for automatic PDF generation
✅ Accessibility-focused semantic HTML

## 📱 Preview

- **Main Resume Site:** Creative dark theme with animations
- **Printable Resume:** Clean, ATS-friendly single-page layout
- **Slide Deck:** Presentation-style slides for interviews or sharing

## 🚢 Deployment

### GitHub Pages (Automatic)

1. Push changes to `main` branch
2. Go to **Settings → Pages**
3. Select **Deploy from branch main / root**
4. Your site goes live in ~1 minute

**URL:** `https://yashmalakar200528-lang.github.io/resume-site/`

### Other Hosting

- Netlify, Vercel, Firebase Hosting, or any static host
- Simply upload the files and enable auto-publishing from GitHub

## 📝 Notes

- **ATS Compatibility:** The print-friendly resume (`resume-print.html`) uses semantic HTML for good parsing by Applicant Tracking Systems (ATS).
- **Accessibility:** High contrast ratios, semantic headings, skip links (can be added).
- **PDF Quality:** Always use "Background graphics" enabled when printing for best results.
- **Slide Transitions:** Edit `reveal.js` config in `slides.html` to customize animations.

## 🤝 Contributing

Feel free to fork and customize for your own resume. Feedback and PRs welcome!

## 📧 Contact

**Yash Malakar**
- Email: [yashmalakar200528@gmail.com](mailto:yashmalakar200528@gmail.com)
- GitHub: [yashmalakar200528-lang](https://github.com/yashmalakar200528-lang)
- LinkedIn: [yash-malakar-dev-op](https://www.linkedin.com/in/yash-malakar-dev-op)
- Location: Kishangarh, Ajmer, Rajasthan

---

**Built with ❤️ using HTML, CSS, JavaScript & Reveal.js**