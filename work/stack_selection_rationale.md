# Tech Stack Evaluation & Selection Rationale (Three Roads)

## 1. Real Constraints & Requirements
- **Budget:** Free hosting only.
- **Skill Level:** Comfortable with HTML/CSS, Python, Markdown, and Git workflows; no complex Node.js or React setup needed.
- **Display Needs:** Executable Google Colab embedded links, GitHub code repos, clean LaTeX-formatted math, and benchmark charts.
- **Dynamic Needs:** Static site only for now; dynamic backend is **not yet** required.

---

## 2. Evaluation of Three Stack Options

### **Option 1: GitHub Pages + Static HTML/Tailwind CSS (Chosen Stack)**
- **How to build:** Pure static HTML5 page styled with Tailwind CSS via CDN.
- **Hosting:** GitHub Pages (`mickael044.github.io`).
- **Pros:** Completely free, instant deployment via Git commits, zero build tools or dependency overhead, highly maintainable.
- **Cons:** Manual updates required for new projects.

### **Option 2: Next.js + Vercel**
- **How to build:** React-based framework with modern UI components.
- **Hosting:** Vercel Hobby Free Tier.
- **Pros:** Highly dynamic, component modularity, excellent transition effects.
- **Cons:** High maintenance overhead, unnecessary build steps for a static portfolio, potential API breakages.

### **Option 3: Streamlit / Gradio App Hosting**
- **How to build:** Python-only framework using Streamlit Cloud.
- **Hosting:** Streamlit Community Cloud / Hugging Face Spaces.
- **Pros:** Native Python execution for interactive model demos.
- **Cons:** Slower page load times, layout constraints for reading technical reports, occasional cold starts.

---

## 3. Decision & Trade-Off Rationale

- **Selected Stack:** **Option 1 (GitHub Pages + Static HTML/Tailwind)**.
- **Why I Chose It:** It perfectly balances zero maintenance cost with ultra-fast page speeds. It presents code repositories and technical write-ups cleanly without backend complexity.
- **Why I Rejected Option 2 & 3:** Next.js adds build complexity that hinders rapid maintenance. Streamlit is great for interactive demos, but fails as a primary, fast-loading portfolio landing page.
