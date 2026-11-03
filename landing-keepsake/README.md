# Keepsake – landing page

Адаптивний односторінковий лендінг дизайн-агенції Keepsake за макетом у Figma (Desktop 1280, Tablet 768, Mobile 375, Mobile – menu open, UI states).

- **Демо:** https://YOUR-USERNAME.github.io/landing-keepsake/
- **Макет Figma:** _додайте посилання на макет_

## Технології

- HTML5 + CSS3, без фреймворків і UI-бібліотек, без JavaScript
- Шрифти Google Fonts: Oswald (300/400/700), Open Sans (300/400/700), Dancing Script 700 (`font-display: swap`)
- Іконки – inline SVG (один SVG-спрайт з `<symbol>` + `<use>`)
- Зображення – WebP з `width` / `height` і `loading="lazy"`

## Структура

```
landing-keepsake/
├── index.html
├── css/style.css
├── images/        (work-1.webp … work-8.webp)
└── README.md
```

## Ключові рішення

- **Семантика:** `header`, `nav`, `main`, `section`, `article`, `footer`, `form`; один `h1`, далі `h2` → `h3`.
- **CSS-змінні в `:root`:** кольори, шрифти, відступи, а також розміри, що змінюються по брейкпоінтах (поля контейнера, відступ між секціями, розміри шрифтів, gap сітки). На брейкпоінтах змінюються самі змінні.
- **Mobile first:** базові стилі для 375, далі `@media (min-width: 768px)` і `@media (min-width: 1280px)`. Контейнер центрується, макс. ширина контенту 1100 px.
- **Розкладка:** Flexbox для компонентів, CSS Grid для сітки робіт, послуг, статистики й клієнтів, без `position: absolute` для сітки.
- **Мобільне меню без JS:** `<button popovertarget>` + атрибут `popover` (Popover API). Браузер сам відкриває/закриває меню й віддає стан `expanded` для скрінрідерів; бургер перетворюється на хрестик через `:has(:popover-open)`.
- **Фільтр портфоліо без JS:** приховані radio + `:checked ~ …` і `data-category`. Активний чипс підсвічується тим самим селектором. Кількість карточок: 5 / 8 / 9 (mobile / tablet / desktop).
- **Ховер карточки** (оверлей, «+», назва, коралова лінія, категорія) вмикається також через `:focus-within`, тобто з клавіатури.
- **Форма підписки без JS:** HTML-валідація (`type="email"`, `required` для прапорця), стан error через `:user-invalid`, стан success через `:target` (форма надсилається на `#subscribed`, і замість полів з'являється повідомлення). Помилки пов'язані з полями через `aria-describedby`.
- **Fixed header** і кнопка «вгору» 44×44.
- **Доступність:** видимий `:focus-visible`, `aria-label` на іконкових кнопках, `alt` у змістовних зображень, декоративні елементи з `aria-hidden`.
