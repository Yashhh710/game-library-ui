# 🎮 Game Library UI

**A fan-made game showcase website with smooth animations, a hero carousel and detailed game pages.**
*For design purposes only.*

[![Live Demo](https://img.shields.io/badge/Live%20Demo-Open%20Site-white?style=for-the-badge&logo=githubpages&logoColor=black)](https://yashhh710.github.io/game-library-ui/)
[![Repo](https://img.shields.io/badge/GitHub-Repository-181717?style=for-the-badge&logo=github)](https://github.com/Yashhh710/game-library-ui)

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)

**[🔗 Live Demo](https://yashhh710.github.io/game-library-ui/)** · **[📦 Repository](https://github.com/Yashhh710/game-library-ui)**

</div>

---

## 📸 Preview

| Home page | Game page |
| :---: | :---: |
| ![Home page](<img width="1470" height="894" alt="image" src="https://github.com/user-attachments/assets/be64bca6-fe9e-49c7-85d2-abb84aad9fb0" />) | ![Game page](<img width="1470" height="920" alt="image" src="https://github.com/user-attachments/assets/2d1d6930-c349-4d34-ba47-2d46c89f34bb" />) |

| Welcome popup | 404 page |
| :---: | :---: |
| ![Welcome popup](screenshots/popup.png) | ![404 page](screenshots/404.png) |

> 💡 Put your own screenshots in the `screenshots/` folder with the names above (`home.png`, `game-page.png`, `404.png`). The images show up here automatically.

---

## ✨ Features

- 🎞️ **Animated loading screen** that fades into the site
- 💬 **Welcome popup** after loading, with a glass-style card, numbered notes, and **Close** / **Continue** buttons
- 🧭 **404 page** with a glitch text effect, a floating 👾 and a custom background and tab icon
- 🖼️ **Hero section** that changes its background and details as you hover over a game card
- 🃏 **Smooth hover cards** that lift, zoom, shine and dim their neighbours
- 🌐 **Official Website box** on every page that opens the game's official site in a new tab
- 📄 **Detail page for each game** with a screenshot gallery, lightbox, info panel, system requirements, age rating and FAQ
- 🎬 **Optional trailer slot** on each page (add a YouTube video ID)
- 📱 **Responsive layout** for desktop, tablet and phone
- ♿ **Reduced motion support** that turns animations down when the system asks for it

---

## 🎯 Games included

| | | |
| --- | --- | --- |
| Grand Theft Auto VI | Grand Theft Auto V | Grand Theft Auto III |
| GTA Vice City | The Simpsons: Hit & Run | Minecraft |
| Need for Speed: Most Wanted | Stumble Guys | Red Dead Redemption 2 |
| Cyberpunk 2077 | Euro Truck Simulator 2 | Forza Horizon 5 |
| Forza Horizon 6 | Fortnite | God of War Ragnarök |
| Marvel's Spider-Man 2 | Hogwarts Legacy | Assassin's Creed IV Black Flag |
| Black Myth: Wukong | Resident Evil 4 | Microsoft Flight Simulator 2024 |

---

## 🗂️ Project structure

```
game-library-ui/
├── index.html              # Home page: loading screen, popup, hero, game cards, 404 overlay
├── GTA5.html               # One page per game (same layout)
├── GTA6.html
├── RDR2.html
├── Cyberpunk.html
├── ...                     # Other game pages
├── models/
│   ├── main/               # Shared images (e.g. 404.png, gta-5.png)
│   ├── GTA5/               # Images for one game
│   │   ├── 1.png ... 7.png     # Big banner slides
│   │   ├── w1.png ... w7.png   # Screenshot thumbnails
│   │   ├── faq.png             # FAQ background
│   │   └── poster.png          # Card image on the home page
│   └── ...                 # One folder per game
├── screenshots/            # Images used in this README
└── README.md
```

---

## 🚀 Getting started

No build step is needed. It's plain HTML, CSS and JavaScript.

```bash
# 1. Clone the repo
git clone https://github.com/Yashhh710/game-library-ui.git

# 2. Open the folder
cd game-library-ui

# 3. Open index.html in your browser
```

For the best results, serve it with a small local server:

```bash
# Python
python3 -m http.server 8000

# or Node
npx serve .
```

Then open `http://localhost:8000`.

> The pages load Tailwind CSS, fonts and some artwork from the internet, so you need to be online.

---

## ➕ Adding a new game

1. **Make a page.** Copy an existing game page (for example `RDR2.html`) and rename it, for example `MyGame.html`. Update the title, description, tags, system requirements and links inside.
2. **Add images.** Create `models/MyGame/` and add `1.png`–`7.png`, `w1.png`–`w7.png`, `faq.png` and `poster.png`.
3. **Point the page at your images.** In the page's script, set `hero` and `shots` to your files:

   ```js
   const hero  = ['models/MyGame/1.png', 'models/MyGame/2.png'];
   const shots = ['models/MyGame/w1.png', 'models/MyGame/w2.png'];
   ```

4. **Add a card to the home page.** In `index.html`, add an entry to the `GAMES` array:

   ```js
   {
     id: 'mygame', title: 'My Game', big: 'MY GAME', year: 2026, rating: '16+',
     genres: 'Action & Adventure',
     desc: 'A short description of the game.',
     by: 'Developer Name',
     hero: 'models/MyGame/1.png', poster: 'models/MyGame/poster.png',
     url: 'MyGame.html', official: 'https://example.com/'
   }
   ```

5. **Optional trailer.** In the game page, set the YouTube video ID:

   ```js
   const VIDEO_ID = 'YOUR_VIDEO_ID';
   ```

   For `https://www.youtube.com/watch?v=hvoD7ehZPcM`, the ID is `hvoD7ehZPcM`.

---

## ⚙️ Settings you can change

| What | Where | How |
| --- | --- | --- |
| Login redirect | top of `index.html` script | `REQUIRE_LOGIN = false` (set `true` only if the site sits behind your own login page) |
| Welcome popup text | `#designModal` in `index.html` | Edit the list items |
| 404 background | `models/main/404.png` | Replace the image |
| Trailer | each game page | Set `VIDEO_ID` |
| Official website link | each game page and its `GAMES` entry | Change the URL |

---

## 🌍 Deploying with GitHub Pages

1. Push the project to your repository.
2. Open **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Select the `main` branch and the `/ (root)` folder, then save.
5. After a minute your site is live at `https://yashhh710.github.io/game-library-ui/`.

---

## ⚠️ Disclaimer

This is a **fan-made project created only to demonstrate web design, layout and animation.**

- It is **not** an official website and is **not** affiliated with or endorsed by any game developer or publisher.
- **No games are hosted, sold or distributed** here. Use the Official Website buttons to visit the real pages.
- All game names, logos, artwork and trademarks belong to their respective owners.
- Information such as release dates, ratings and system requirements may be approximate. Check the official sources for accurate details.
- If you are a rights holder and want something removed, please open an issue and it will be taken down.

---

## 🛠️ Built with

- HTML5, CSS3 and vanilla JavaScript
- [Tailwind CSS](https://tailwindcss.com/) (CDN)
- [Google Fonts](https://fonts.google.com/)

---

<div align="center">

Made by **[Yashhh710](https://github.com/Yashhh710)**

⭐ If you like this project, give it a star!

</div>
