# 🎂 Happy Birthday Animation

A beautiful, animated birthday greeting page built with **Vanilla JavaScript** and **GSAP**. Fully customizable through a single config file — no coding skills required!

## ✨ Features

- 🎬 Smooth GSAP animations (typing effect, floating balloons, confetti, fireworks, and more)
- 🧩 Modular component system — add, remove, or reorder sections by editing one file
- 🌙 Dark / Light mode toggle
- 📱 Responsive and mobile-friendly
- 🎵 Optional background music
- ⚡ No build step, no framework, no server required

---

## 📁 Project Structure

```
happybirthday/
├── config.js                ← ✨ EDIT THIS FILE ONLY
├── index.html               ← Page template (do not edit)
├── script/
│   ├── main.js              ← Engine (do not edit)
│   └── components/          ← Section components
│       ├── greeting.js
│       ├── announcement.js
│       ├── chatbox.js
│       ├── countdown.js
│       ├── ideas.js
│       ├── quote.js
│       ├── stars.js
│       ├── fireworks.js
│       ├── balloons.js
│       ├── profile.js
│       ├── confetti.js
│       └── closing.js
├── style/
│   └── main.css             ← Styles (do not edit)
├── img/                     ← Put recipient's photo here
└── music/                   ← Put background music here
```

---

## 🔧 Creating Your Own Component

Create a `.js` file in `script/components/` following this template:

```javascript
(function () {
  window.Components = window.Components || {};

  window.Components.mycomponent = {
    // overlay: true,  ← Set true if it layers on top of other sections

    render(container, section, config) {
      const div = document.createElement("div");
      div.className = "section section-mycomponent";
      div.innerHTML = `<p>${section.text || "Hello!"}</p>`;
      container.appendChild(div);
      return div;
    },

    animate(tl, el, config) {
      tl.from(el, { duration: 0.7, opacity: 0, y: 20 })
        .to(el, { duration: 0.7, opacity: 0 }, "+=3");
    },

    // Optional: deferred exit (runs after overlays finish)
    // exit(tl, el) {
    //   tl.to(el, { duration: 0.5, opacity: 0 });
    // },
  };
})();
```

Then use it in `config.js`:
```javascript
{ type: "mycomponent", text: "My custom section!" }
```

Don't forget to add CSS for `.section-mycomponent` in `style/main.css`.

---

## 🛠️ Built With

- [GSAP 3](https://greensock.com/gsap/) — Animation engine
- [SweetAlert2](https://sweetalert2.github.io/) — Alert dialogs
- [Poppins](https://fonts.google.com/specimen/Poppins) — Google Font

---

## 📄 License

Licensed under the [MIT License](LICENSE).

---
