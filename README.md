# 🔐 Password Strength Evaluator

> A client-side password security analysis tool built with vanilla HTML, CSS, and JavaScript — no frameworks, no dependencies, no data ever leaves your browser.

![License](https://img.shields.io/badge/License-MIT-green.svg)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)
![OWASP](https://img.shields.io/badge/OWASP-A07%20Compliant-blue)

---

## 📌 Overview

The **Password Strength Evaluator** is a fully browser-based security tool that analyzes password quality in real time using:

- **Shannon Entropy** calculation (bits) based on true character pool size
- **OWASP A07:2021** (Identification & Authentication Failures) compliance checks
- **Pattern detection** — keyboard walks, sequences, repeats, leet-speak substitutions
- **Breach list matching** — flags passwords found in known common/breached password databases
- **Offline GPU crack time estimation** — modeled at 1 trillion guesses/second
- **Ultra-strong password generator** — cryptographically random via `crypto.getRandomValues()`

All analysis happens 100% client-side. No API calls. No servers. No telemetry.

---

## ✨ Features

| Feature | Description |
|---|---|
| 🔢 Entropy Analysis | Calculates Shannon entropy in bits using real charset size |
| 🛡️ OWASP A07 Checks | 8-point checklist against authentication security guidelines |
| 🎨 Visual Strength Meter | 5-segment color-coded strength indicator |
| ⚠️ Security Flags | Contextual warnings for patterns, breaches, and structure |
| 💡 Improvement Suggestions | Tailored, actionable advice based on detected weaknesses |
| ⏱️ Crack Time Estimate | GPU-speed offline attack time estimation |
| 🎲 Password Generator | Cryptographically secure 20-char gibberish password generator |
| 📋 One-Click Copy | Copy generated password directly to clipboard |
| 👁️ Show/Hide Toggle | Reveal or mask input password |
| 🌙 Dark Mode Ready | Fully supports system dark/light mode preference |

---

## 🖥️ Demo

> **Try it live:** [https://juttsahib1999.github.io/password-strength-evaluator/](https://juttsahib1999.github.io/password-strength-evaluator/)

---

## 🚀 Getting Started

### Prerequisites

None. This is a pure HTML/CSS/JS project. All you need is a modern web browser.

> Tested on: Chrome 120+, Firefox 121+, Edge 120+, Safari 17+

---

### Installation

#### Option 1 — Clone the Repository

```bash
git clone https://github.com/JuttSahib1999/password-strength-evaluator.git
cd password-strength-evaluator
```

Then open `index.html` directly in your browser:

```bash
# macOS
open index.html

# Linux
xdg-open index.html

# Windows (PowerShell)
start index.html
```

#### Option 2 — Download ZIP

1. Click the green **Code** button on the repository page
2. Select **Download ZIP**
3. Extract the archive
4. Open `index.html` in your browser

#### Option 3 — GitHub Pages (Live Hosting)

To host it yourself for free:

1. Fork this repository
2. Go to your fork → **Settings** → **Pages**
3. Under **Source**, select `main` branch → `/ (root)`
4. Click **Save**
5. Your tool will be live at `https://<your-username>.github.io/password-strength-evaluator/`

---

## 📁 Project Structure

```
password-strength-evaluator/
│
├── index.html          # Single-file application (HTML + CSS + JS)
└── README.md           # Project documentation
```

This is intentionally a single-file build — easy to share, embed, or host anywhere.

---

## 🔬 How It Works

### Entropy Calculation

Entropy is calculated as:

```
Entropy (bits) = Password Length × log₂(Charset Size)
```

Where charset size is determined by which character categories are present:

| Category | Characters | Pool Size |
|---|---|---|
| Lowercase | a–z | +26 |
| Uppercase | A–Z | +26 |
| Digits | 0–9 | +10 |
| Symbols | !@#$%^&*… | +32 |

### Strength Scoring

| Entropy Range | Base Score | Grade |
|---|---|---|
| < 36 bits | 0 | Very Weak |
| 36–51 bits | 1 | Weak |
| 52–69 bits | 2 | Fair |
| 70–89 bits | 3 | Strong |
| ≥ 90 bits | 4 | Very Strong |

Score is **penalized** for: common passwords, all-digit inputs, keyboard walks, and repeated patterns.

### OWASP A07 Compliance

The tool checks against the [OWASP Application Security Verification Standard (ASVS)](https://owasp.org/www-project-application-security-verification-standard/) criteria for authentication:

- ✅ Minimum 8 characters
- ✅ Recommended 12+ characters
- ✅ Uppercase letters present
- ✅ Lowercase letters present
- ✅ Numeric digits present
- ✅ Special/symbol characters present
- ✅ Not found in common/breached password list
- ✅ No keyboard walk or sequential patterns

### Password Generator

The generator uses the Web Crypto API (`crypto.getRandomValues()`) — a cryptographically secure pseudo-random number generator (CSPRNG):

- Guaranteed inclusion of: 2 uppercase, 2 lowercase, 2 digits, 2 symbols
- Remaining 12 characters drawn randomly from full 74-character pool
- Fisher-Yates shuffle applied for uniform distribution
- Visually ambiguous characters (`0`, `O`, `1`, `l`, `I`) excluded

---

## 🔒 Privacy & Security

- ✅ **Zero network requests** — no passwords are ever transmitted
- ✅ **No localStorage / sessionStorage** — nothing is persisted
- ✅ **No external scripts** — runs entirely from the single HTML file
- ✅ **No analytics or tracking**
- ✅ **Open source** — audit every line yourself

---

## 🧠 Technical Reference

| Component | Specification |
|---|---|
| Crack time model | Offline GPU attack, 10¹² guesses/second |
| Breach list size | ~50 most common passwords + leet-speak variants |
| Generator charset | 74 characters (uppercase, lowercase, digits, symbols) |
| Generator length | 20 characters (≈ 126 bits entropy) |
| CSPRNG | Web Crypto API — `crypto.getRandomValues()` |

---

## 🤝 Contributing

Contributions are welcome and appreciated!

1. Fork the repository
2. Create your feature branch

   ```bash
   git checkout -b feature/your-feature-name
   ```

3. Commit your changes

   ```bash
   git commit -m "Add: your feature description"
   ```

4. Push to the branch

   ```bash
   git push origin feature/your-feature-name
   ```

5. Open a **Pull Request** against the `main` branch

Please keep the single-file architecture and zero-dependency philosophy intact.

---

## 🐛 Reporting Issues

Found a bug or have a suggestion? Open an issue on the [Issues page](https://github.com/JuttSahib1999/password-strength-evaluator/issues) with:

- A clear title
- Steps to reproduce
- Browser and OS version
- Expected vs actual behavior

---

## 📜 License

This project is licensed under the **MIT License** — free to use, modify, and distribute for personal or commercial purposes.

```
MIT License

Copyright (c) 2026 Abdul Muqeet Tabraiz (JuttSahib1999)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## 👨‍💻 Author

**Abdul Muqeet Tabraiz**
- GitHub: [@JuttSahib1999](https://github.com/JuttSahib1999)
- LinkedIn: [Abdul Muqeet Tabraiz](https://www.linkedin.com/in/abdul-muqeet-tabraiz)
- Certifications: CEH | CHFI | Blue Team Specialist

---

## ⭐ Show Your Support

If this tool helped you or you found it useful, consider leaving a **star** ⭐ on the repository — it helps others discover the project and motivates continued development.

---

*Built with security in mind. Tested against OWASP A07:2021 guidelines.*
