# 🎓 Student Portfolio — AI & Python Projects

> A responsive, animated personal portfolio website built with pure **HTML, CSS & JavaScript** — designed to showcase AI/ML beginner projects built during a hands-on workshop.

---

## 🚀 Live Preview

> 📌 **[➜ View Portfolio](#)** ← *(Replace `#` with your GitHub Pages / Netlify URL)*

---

## 📸 Project Overview

This is a **single-page portfolio website** for a B.Sc (CSE) student (2nd Year, 4th Semester) at **Haldia Institute of Management**. It highlights two completed AI/ML projects and showcases Python + data science skills learned through practical workshops.

---

## 🧠 Featured Projects

### 📊 Project 1 — EDA Dashboard (Titanic Dataset)
A beginner-friendly Exploratory Data Analysis project on the classic Titanic dataset.

**What I did:**
- Loaded and explored the dataset using **Pandas**
- Handled missing values using **mean** and **mode** imputation
- Created visualizations: survival count, gender vs. survival, age distribution
- Summarized key insights (presentation-ready)

**Tech:** `Pandas` · `Matplotlib` · `Data Cleaning` · `Google Colab`

---

### 🏠 Project 2 — House Price Prediction (Linear Regression)
Built my first supervised Machine Learning model to predict house prices on unseen data.

**What I did:**
- Performed **train-test split** for unbiased evaluation
- Trained a **Linear Regression** model using `scikit-learn`
- Evaluated using **RMSE** and **R² score**
- Visualized Actual vs. Predicted values and residual errors

**Tech:** `scikit-learn` · `Linear Regression` · `RMSE` · `R²` · `Matplotlib`

---

## 🛠️ Tech Stack

| Category | Tools Used |
|---|---|
| **Language** | Python 3 |
| **Data** | Pandas, NumPy |
| **Visualization** | Matplotlib |
| **ML** | scikit-learn |
| **Environment** | Google Colab |
| **Version Control** | Git & GitHub |
| **Frontend (this portfolio)** | HTML5, CSS3, Vanilla JavaScript |

---

## ✨ Portfolio Website Features

- 🎨 **Glassmorphism UI** with dark theme, gradient blobs, and glowing accents
- ⌨️ **Typing animation** cycling through project types in the hero section
- 🌌 **Particle canvas background** with animated floating dots and connecting lines
- 📜 **Scroll-reveal animations** — cards fade in as you scroll
- 📊 **Scroll progress bar** at the top of the page
- 📱 **Fully responsive** — works on mobile, tablet, and desktop
- 🔗 **Easy link configuration** via a single `LINKS` object in the script

---

## 📁 File Structure

```
📦 portfolio/
 ┗ 📄 index.html       ← Entire portfolio (HTML + CSS + JS in one file)
 ┗ 📄 README.md        ← This file
```

> All styling and interactivity is self-contained in `index.html`. No build tools or dependencies required.

---

## ⚙️ Setup & Customization

### 1. Clone the repo
```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```

### 2. Open in browser
Simply open `index.html` in any browser — no build step needed.

### 3. Personalize your info
Edit the `LINKS` object near the bottom of `index.html`:

```javascript
const LINKS = {
  githubProfile:    "https://github.com/your-username",
  linkedin:         "https://linkedin.com/in/your-profile",
  project1Repo:     "https://github.com/your-username/project1",
  project2Repo:     "https://github.com/your-username/project2",
  project1Notebook: "https://colab.research.google.com/...",
  project2Notebook: "https://colab.research.google.com/...",
  email:            "your@email.com"
};
```

### 4. Update your name & bio
Replace `Student Name` in the `<h1>` tag and update the subtitle paragraph with your real details.

### 5. Quick personalization via URL
You can also inject your name and GitHub link via query params (great for demos):
```
index.html?name=Rahul%20Das&github=https://github.com/rahuldas
```

---

## 🚢 Deployment

This is a **static site** — deploy it anywhere for free:

| Platform | Steps |
|---|---|
| **GitHub Pages** | Push to `main` → Settings → Pages → Deploy from `main` |
| **Netlify** | Drag & drop the folder at [netlify.com/drop](https://netlify.com/drop) |
| **Vercel** | Import repo at [vercel.com](https://vercel.com) — zero config |

---

## 🎓 Workshop & Learning Journey

| Workshop | Details |
|---|---|
| **Ardent — AI & ML Workshop** | 3-day practical workshop with live coding in Google Colab. Built EDA and Linear Regression projects. |
| **Code_ScholarEU** | Learning AI development, automation workflows, and LLM use-cases under mentorship of SK Sahil. |

**Mentor:** [SK Sahil](https://www.instagram.com/code_scholar_eu/) — AI Developer & Tutor who guided me through ML basics, GitHub workflow, and portfolio building.

---

## 📬 Contact

- 📧 **Email:** [student@email.com](mailto:student@email.com) ← *(replace)*
- 💼 **LinkedIn:** [linkedin.com/in/your-profile](#) ← *(replace)*
- 🐙 **GitHub:** [github.com/your-username](#) ← *(replace)*
- 📸 **Instagram (Mentor/Community):** [@code_scholar_eu](https://www.instagram.com/code_scholar_eu/)

> 💡 Open to **internships and collaborations** in Python, Data Analysis, and beginner ML projects.

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

<p align="center">Built with ❤️ using HTML, CSS & JS &nbsp;•&nbsp; Responsive &nbsp;•&nbsp; Ready for GitHub Pages</p>
