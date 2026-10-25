# 🚂 Вокзал виртуальных путешествий

[🇧🇾 Беларуская](#-беларуская) · [🇷🇺 Русский](#-русский) · [🇬🇧 English](#-english)

> Бесплатные виртуальные путешествия по миру — YouTube-туры, экскурсии по музеям и живые веб-камеры в одном SPA.

---

## 🇧🇾 Беларуская

### Пра праект

**Вакзал віртуальных падарожжаў** — гэта аднастаронкавы вэб-дадатак (SPA) для тых, каму дорагі мары пра падарожжы. Тры раздзелы — YouTube-падарожжы, віртуальныя экскурсіі па музеях і анлайн-камеры — дазваляюць адправіцца ў любую кропку планеты без білетаў, чэмаданаў і перасадак.

Праект напісаны на чыстым HTML, CSS і JavaScript — **без зборачных інструментаў, фрэймворкаў і залежнасцей**. Дастаткова адкрыць файл у браўзеры.

### Магчымасці

- 🎬 **Тры тэматычныя раздзелы:** YouTube-падарожжы, музеі, анлайн-камеры
- 🌗 **Дзве тэмы:** дзень і ноч (з захаваннем выбару)
- 🔠 **Тры памеры шрыфту:** малы, сярэдні, буйны — для камфортнага чытання
- 🆕 **Маркеры NEW:** новыя матэрыялы падсвечваюцца, а пасля прагляду больш не паказваюцца (стан у `localStorage`)
- 🍞 **Хлебныя крошкі:** зручная навігацыя паміж узроўнямі «Галоўная → Раздзел → Краіна»
- 📱 **Поўная адаптыўнасць:** тэлефоны, планшэты, дэсктоп
- ♿ **Даступнасць:** ARIA-атрыбуты, кіраванне з клавіятуры, падтрымка `prefers-reduced-motion`, кантрастнасць WCAG AA
- 💾 **Праца без сервера:** калі `data.json` недасяжны, выкарыстоўваюцца ўбудаваныя дэма-дадзеныя

### Хуткі старт

**Варыянт 1 — проста адкрыць файл:**

Скапіруйце `index.html` і адкрыйце ў браўзеры. Усё запрацуе адразу (дзякуючы fallback-дадзеным).

**Варыянт 2 — лакальны сервер (рэкамендуецца):**

```bash
# Python 3
python -m http.server 8000

# або Node.js
npx serve
```

Затым адкрыйце [http://localhost:8000](http://localhost:8000).

### Структура праекта

```
.
├── index.html      # Адзіны файл: HTML-разметка + CSS + JavaScript
├── data.json       # (апцыянальна) Кантэнт: раздзелы → краіны → экскурсіі
└── README.md       # Гэты файл
```

Калі `data.json` адсутнічае або не можа быць загружаны, дадатак выкарыстоўвае ўбудаваныя дэма-дадзеныя.

### Фармат `data.json`

```json
{
  "version": 1,
  "sections": [
    {
      "id": "sec-youtube",
      "title": "YouTube путешествия",
      "icon": "🎬",
      "description": "Кароткае апісанне раздзела",
      "isNew": true,
      "countries": [
        {
          "id": "cnt-switzerland",
          "title": "Швейцария",
          "flag": "🇨🇭",
          "description": "Кароткае апісанне краіны",
          "isNew": true,
          "excursions": [
            {
              "id": "exc-swiss-ptushkin",
              "title": "Назва экскурсіі",
              "author": "Аўтар",
              "url": "https://youtu.be/...",
              "description": "Апісанне экскурсіі",
              "isNew": true
            }
          ]
        }
      ]
    }
  ]
}
```

**Правілы:**
- `id` — унікальныя радкі (выкарыстоўваюцца для захавання стану «прагледжана»)
- `isNew: true` — паказваць маркер NEW, пакуль карыстальнік не адкрые элемент
- Усе тэксты экраніруюцца перад устаўкай у HTML

### Як дадаць новую экскурсію

1. Адкрыйце `data.json` (або зменшыце `FALLBACK_DATA` у `index.html`).
2. Дадайце новы аб'ект у патрэбны масіў `excursions`.
3. Задайце ўнікальны `id`, напрыклад `exc-paris-louvre-2025`.
4. Усталюйце `isNew: true`, каб падсвяціць навінку.

### Тэхналогіі

- Чысты **HTML5**, **CSS3** (кастомныя ўласцівасці, Grid, Flexbox)
- **JavaScript (ES2017+)** — без фрэймворкаў
- **Fetch API** з graceful fallback
- **LocalStorage** для захавання налад і стану прагляду
- Ніякіх залежнасцей, зборачных інструментаў або CDN

### Даступнасць

- Семантычная разметка (`<header>`, `<main>`, `<nav>`, `<footer>`, `<article>`)
- ARIA-ролі і атрыбуты (`aria-pressed`, `aria-label`, `aria-current="page"`)
- Поўнае кіраванне з клавіятуры (Tab, Enter, Space)
- Павага да `prefers-reduced-motion`
- Кантрастнасць тэксту адпавядае WCAG AA
- Бачны фокус для ўсіх інтэрактыўных элементаў

### Ліцэнзія

MIT — выкарыстоўвайце, змяняйце і распаўсюджвайце свабодна. Калі ласка, дадайце файл `LICENSE` у рэпазіторый.

---

## 🇷🇺 Русский

### О проекте

**Вокзал виртуальных путешествий** — одностраничное веб-приложение (SPA) для тех, кому дороги мечты о путешествиях. Три раздела — YouTube-путешествия, виртуальные экскурсии по музеям и онлайн-камеры — позволяют отправиться в любую точку планеты без билетов, чемоданов и пересадок.

Проект написан на чистом HTML, CSS и JavaScript — **без сборщиков, фреймворков и зависимостей**. Достаточно открыть файл в браузере.

### Возможности

- 🎬 **Три тематических раздела:** YouTube-путешествия, музеи, онлайн-камеры
- 🌗 **Две темы:** день и ночь (с сохранением выбора)
- 🔠 **Три размера шрифта:** мелкий, средний, крупный — для комфортного чтения
- 🆕 **Маркеры NEW:** новые материалы подсвечиваются, а после просмотра больше не показываются (состояние хранится в `localStorage`)
- 🍞 **Хлебные крошки:** удобная навигация между уровнями «Главная → Раздел → Страна»
- 📱 **Полная адаптивность:** телефоны, планшеты, десктоп
- ♿ **Доступность:** ARIA-атрибуты, управление с клавиатуры, поддержка `prefers-reduced-motion`, контрастность WCAG AA
- 💾 **Работа без сервера:** если `data.json` недоступен, используются встроенные демо-данные

### Быстрый старт

**Вариант 1 — просто открыть файл:**

Скачайте `index.html` и откройте в браузере. Всё заработает сразу (благодаря fallback-данным).

**Вариант 2 — локальный сервер (рекомендуется):**

```bash
# Python 3
python -m http.server 8000

# или Node.js
npx serve
```

Затем откройте [http://localhost:8000](http://localhost:8000).

### Структура проекта

```
.
├── index.html      # Единственный файл: HTML-разметка + CSS + JavaScript
├── data.json       # (опционально) Контент: разделы → страны → экскурсии
└── README.md       # Этот файл
```

Если `data.json` отсутствует или не может быть загружен, приложение использует встроенные демо-данные.

### Формат `data.json`

```json
{
  "version": 1,
  "sections": [
    {
      "id": "sec-youtube",
      "title": "YouTube путешествия",
      "icon": "🎬",
      "description": "Краткое описание раздела",
      "isNew": true,
      "countries": [
        {
          "id": "cnt-switzerland",
          "title": "Швейцария",
          "flag": "🇨🇭",
          "description": "Краткое описание страны",
          "isNew": true,
          "excursions": [
            {
              "id": "exc-swiss-ptushkin",
              "title": "Название экскурсии",
              "author": "Автор",
              "url": "https://youtu.be/...",
              "description": "Описание экскурсии",
              "isNew": true
            }
          ]
        }
      ]
    }
  ]
}
```

**Правила:**
- `id` — уникальные строки (используются для сохранения статуса «просмотрено»)
- `isNew: true` — показывать маркер NEW, пока пользователь не откроет элемент
- Все тексты экранируются перед вставкой в HTML

### Как добавить новую экскурсию

1. Откройте `data.json` (или отредактируйте `FALLBACK_DATA` в `index.html`).
2. Добавьте новый объект в нужный массив `excursions`.
3. Задайте уникальный `id`, например `exc-paris-louvre-2025`.
4. Установите `isNew: true`, чтобы подсветить новинку.

### Технологии

- Чистые **HTML5**, **CSS3** (кастомные свойства, Grid, Flexbox)
- **JavaScript (ES2017+)** — без фреймворков
- **Fetch API** с graceful fallback
- **LocalStorage** для сохранения настроек и статуса просмотра
- Никаких зависимостей, сборщиков или CDN

### Доступность

- Семантическая разметка (`<header>`, `<main>`, `<nav>`, `<footer>`, `<article>`)
- ARIA-роли и атрибуты (`aria-pressed`, `aria-label`, `aria-current="page"`)
- Полное управление с клавиатуры (Tab, Enter, Space)
- Уважение к `prefers-reduced-motion`
- Контрастность текста соответствует WCAG AA
- Видимый фокус для всех интерактивных элементов

### Лицензия

MIT — используйте, изменяйте и распространяйте свободно. Пожалуйста, добавьте файл `LICENSE` в репозиторий.

---

## 🇬🇧 English

### About the project

**Virtual Travel Station** is a single-page web application (SPA) for those who hold travel dreams dear. Three sections — YouTube travels, virtual museum tours, and live webcams — let you reach any corner of the planet without tickets, suitcases, or transfers.

The project is built with plain HTML, CSS, and JavaScript — **no bundlers, frameworks, or dependencies**. Just open the file in a browser.

### Features

- 🎬 **Three themed sections:** YouTube travels, museums, live webcams
- 🌗 **Two themes:** day and night (with persisted choice)
- 🔠 **Three font sizes:** small, medium, large — for comfortable reading
- 🆕 **NEW badges:** new items are highlighted and stay silent after being viewed (state persisted in `localStorage`)
- 🍞 **Breadcrumbs:** easy navigation between "Home → Section → Country" levels
- 📱 **Fully responsive:** phones, tablets, desktop
- ♿ **Accessibility:** ARIA attributes, keyboard navigation, `prefers-reduced-motion` support, WCAG AA contrast
- 💾 **Works offline:** if `data.json` is unreachable, embedded demo data is used

### Quick start

**Option 1 — just open the file:**

Download `index.html` and open it in a browser. Everything works out of the box (thanks to fallback data).

**Option 2 — local server (recommended):**

```bash
# Python 3
python -m http.server 8000

# or Node.js
npx serve
```

Then open [http://localhost:8000](http://localhost:8000).

### Project structure

```
.
├── index.html      # Single file: HTML markup + CSS + JavaScript
├── data.json       # (optional) Content: sections → countries → excursions
└── README.md       # This file
```

If `data.json` is missing or fails to load, the app uses embedded demo data.

### `data.json` format

```json
{
  "version": 1,
  "sections": [
    {
      "id": "sec-youtube",
      "title": "YouTube Travels",
      "icon": "🎬",
      "description": "Short section description",
      "isNew": true,
      "countries": [
        {
          "id": "cnt-switzerland",
          "title": "Switzerland",
          "flag": "🇨🇭",
          "description": "Short country description",
          "isNew": true,
          "excursions": [
            {
              "id": "exc-swiss-ptushkin",
              "title": "Excursion title",
              "author": "Author",
              "url": "https://youtu.be/...",
              "description": "Excursion description",
              "isNew": true
            }
          ]
        }
      ]
    }
  ]
}
```

**Rules:**
- `id` — unique strings (used to persist the "viewed" state)
- `isNew: true` — display the NEW badge until the user opens the item
- All text is escaped before being inserted into HTML

### How to add a new excursion

1. Open `data.json` (or edit `FALLBACK_DATA` inside `index.html`).
2. Add a new object to the relevant `excursions` array.
3. Assign a unique `id`, e.g. `exc-paris-louvre-2025`.
4. Set `isNew: true` to highlight the newcomer.

### Technologies

- Plain **HTML5**, **CSS3** (custom properties, Grid, Flexbox)
- **JavaScript (ES2017+)** — no frameworks
- **Fetch API** with graceful fallback
- **LocalStorage** for persisting settings and viewed state
- No dependencies, build tools, or CDNs

### Accessibility

- Semantic markup (`<header>`, `<main>`, `<nav>`, `<footer>`, `<article>`)
- ARIA roles and attributes (`aria-pressed`, `aria-label`, `aria-current="page"`)
- Full keyboard navigation (Tab, Enter, Space)
- Respect for `prefers-reduced-motion`
- Text contrast meets WCAG AA
- Visible focus for all interactive elements

### License

MIT — free to use, modify, and distribute. Please add a `LICENSE` file to the repository.

---

<p align="center">
  🚉 <strong>Счастливого пути!</strong> · <strong>Шчаслівай дарогі!</strong> · <strong>Happy travels!</strong>
</p>
