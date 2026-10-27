<div align="center">

# 🏰 Tower Defense

**Hold the path. Build, upgrade and sell towers to stop waves of goblins, trolls and bosses.**

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=flat-square&logo=python&logoColor=white)
![Pygame](https://img.shields.io/badge/Pygame-2.x-34d399?style=flat-square)
![Resolution](https://img.shields.io/badge/1536×768-60%20FPS-a78bfa?style=flat-square)
![Installer](https://img.shields.io/badge/installer-PyInstaller%20+%20Inno%20Setup-0ea5e9?style=flat-square)

[Gameplay](#-gameplay) · [Balance](#-balance) · [Under the hood](#-under-the-hood) · [Play](#-play) · [Türkçe](#-türkçe)

</div>

---

A complete tower-defense game written in Python as an object-oriented programming project: a tile
map with a fixed path, three tower types, an economy, wave management and a Windows installer.

## 🎮 Gameplay

| Control | Action |
|---|---|
| Left click on a green tile | Choose and build a tower |
| Click a tower | Upgrade or sell |
| `Space` / **Start** | Launch the next wave |
| `F1` / **Speed** | Toggle game speed |
| `Esc` | Cancel selection |

**Towers**: 🏹 **Arrow** (fast single target) · 💣 **Cannon** (area damage) · ❄️ **Ice** (slows enemies).
Upgrades give **+25 % damage** and **+10 % range** for 60 % of the build cost.

**Enemies**: 👺 **Goblin** (fast, 60 HP) · 🧌 **Troll** (250 HP with 30 % armour) · 👑 **Boss** (1000 HP, slow), worth 10, 25 and 100 gold.

## ⚖️ Balance

| Tower | Goblin (60 HP) | Troll (250 HP) | Boss (1000 HP) |
|---|---|---|---|
| Arrow (20 dmg) | 3 hits | ~26 hits (armour) | ~72 hits |
| Cannon (80 dmg, AoE) | 1 hit | ~7 hits (armour) | ~18 hits |
| Ice (10 dmg + slow) | 6 hits | ~36 hits | ~143 hits |

A goblin crosses the ~2,050 px path in about 11 s and the boss takes about 40 s.

## ⚙️ Under the hood

- **Layered OOP design**: an abstract `GameObject` base with enemy, tower and projectile hierarchies and polymorphic `update` / `draw` calls.
- **Managers**: `GameManager`, `WaveManager`, `UIManager`.
- **Map system**: tile grid, path waypoints and buildable tiles.
- **Windows installer**: PyInstaller, Inno Setup and a **single-install lock** in the registry (HKLM and HKCU).

Full write-up (in Turkish): [`docs/technical_documentation.md`](docs/technical_documentation.md).

## ▶️ Play

```bash
pip install pygame
python main.py
```

Build the installer on Windows with `installer\build.bat`.

## 📁 Project structure

```
src/
├── entities/   game_object, enemies/ (goblin, troll, boss), towers/ (arrow, cannon, ice), projectiles/
├── managers/   game, wave, ui
├── map/        game_map, tile
├── player/     player (gold, lives)
└── game.py
installer/      PyInstaller + Inno Setup scripts, registry check
settings.py     all tunables
```

## 🇹🇷 Türkçe

Python ve Pygame ile geliştirilmiş bir kule savunma oyunu. Ok, top ve buz kuleleriyle goblin, trol ve boss
dalgalarını durdurursunuz. Kuleler yükseltilip satılabilir, oyun hızı değiştirilebilir. Katmanlı nesne yönelimli
mimari, dalga ve ekonomi sistemi ile PyInstaller + Inno Setup kurulum paketi içerir. Nesneye Yönelik Programlama
dersi projesidir.

---

<div align="center"><sub>Built by <a href="https://github.com/Soap2647">Mert Yasin Yılmaz</a></sub></div>
