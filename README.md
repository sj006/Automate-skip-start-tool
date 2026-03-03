# 🚀 Auto Skip / Start Tool (Console Script)

A lightweight JavaScript snippet that automatically detects and clicks buttons containing the text **"Skip"** or **"Start"**.

This script is designed to be pasted directly into the browser console and works even when the text is nested inside elements like `<span>`.

---

## ✨ Features

- Detects buttons with text "Skip" or "Start"
- Works with nested elements (e.g. `<button><span>Skip</span></button>`)
- Case-insensitive detection
- Supports dynamically loaded buttons
- Lightweight and dependency-free

---

## 📌 Usage

1. Open your browser.
2. Open Developer Tools (`F12` or `Ctrl + Shift + I`).
3. Go to the **Console** tab.
4. Paste the script below and press Enter.

```javascript
(function () {
  console.log("Auto Skip/Start watcher running (visible text only)...");

  function isVisible(el) {
    return el.offsetParent !== null;
  }

  function checkAndClick() {
    const elements = document.querySelectorAll(
      "button, [role='button'], input[type='button'], input[type='submit']"
    );

    elements.forEach(el => {
      if (!isVisible(el)) return;

      const text = (el.textContent || el.value || "")
        .trim()
        .toLowerCase();

      if (text === "skip" || text === "start") {
        console.log("Clicking:", el);
        el.click();
      }
    });
  }

  setInterval(checkAndClick, 1000); //set time interval as you want in ms
})();
```

---

## ⚠️ Disclaimer

This project is created **strictly for educational and learning purposes**.

- It is intended to demonstrate DOM manipulation and browser automation concepts.
- It is not designed to bypass paywalls, advertisements, platform protections, or terms of service.
- Users are responsible for ensuring ethical and lawful use.

The author does **not** encourage misuse, abuse, or violation of any website policies.

---

## 📚 Learning Concepts Covered

- DOM traversal
- Query selectors
- Text extraction from nested elements
- Handling dynamically rendered content
- Basic browser automation

---

## 🛠 Future Improvements (Optional Ideas)

- Exact vs partial match toggle
- MutationObserver instead of setInterval
- UI toggle panel
- Chrome extension version

---

## 📄 License

You may use, modify, and distribute this project for educational purposes.

If you build something cool with it, consider giving credit ⭐


