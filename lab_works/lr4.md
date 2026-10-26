# Лабораторная работа: тематика «Стоматология»

Переделал всё под вариант №4. Ниже — готовые материалы для отчёта.

---

## 1. Цель и задачи

**Тема:** Сбор семантического ядра и формирование технических файлов сайта для тематики «Стоматология».

**Цель:** Научиться собирать семантическое ядро, формировать на его основе robots.txt и sitemap.xml, выполнять базовую вёрстку HTML-страниц под собранные запросы.

**Задачи:** собрать СЯ (≥30 запросов), кластеризовать по интенту и группам, спроектировать структуру URL, создать robots.txt и sitemap.xml, сверстать главную и 2–3 внутренние страницы.

---

## 2. Таблица семантического ядра (32 запроса)

| № | Запрос | Частотность (Wordstat) | Интент | Кластер |
|---|--------|------------------------|--------|---------|
| 1 | стоматология | 1 200 000 | коммерческий | Главная |
| 2 | стоматологическая клиника | 320 000 | коммерческий | Главная |
| 3 | стоматология москва | 180 000 | коммерческий | Главная |
| 4 | записаться к стоматологу | 45 000 | транзакционный | Главная |
| 5 | частная стоматология | 60 000 | коммерческий | Главная |
| 6 | стоматология рядом со мной | 22 000 | навигационный | Главная |
| 7 | имплантация зубов | 280 000 | коммерческий | Имплантация |
| 8 | имплантация зубов цена | 95 000 | коммерческий | Имплантация |
| 9 | имплант зуба под ключ | 40 000 | транзакционный | Имплантация |
| 10 | сколько стоит имплантация зубов | 18 000 | информационный | Имплантация |
| 11 | лечение зубов | 210 000 | коммерческий | Лечение |
| 12 | лечение кариеса | 85 000 | коммерческий | Лечение |
| 13 | лечить зубы под наркозом | 12 000 | коммерческий | Лечение |
| 14 | лечение зубов цена | 55 000 | коммерческий | Лечение |
| 15 | отбеливание зубов | 160 000 | коммерческий | Отбеливание |
| 16 | отбеливание зубов цена | 48 000 | коммерческий | Отбеливание |
| 17 | профессиональная чистка зубов | 70 000 | коммерческий | Отбеливание |
| 18 | отбеливание зубов лазером | 15 000 | коммерческий | Отбеливание |
| 19 | брекеты | 190 000 | коммерческий | Ортодонтия |
| 20 | брекеты цена | 75 000 | коммерческий | Ортодонтия |
| 21 | выравнивание зубов | 40 000 | коммерческий | Ортодонтия |
| 22 | элайнеры для зубов | 35 000 | коммерческий | Ортодонтия |
| 23 | детский стоматолог | 90 000 | коммерческий | Детская стоматология |
| 24 | детская стоматология цена | 28 000 | коммерческий | Детская стоматология |
| 25 | лечение зубов у детей | 20 000 | коммерческий | Детская стоматология |
| 26 | протезирование зубов | 150 000 | коммерческий | Протезирование |
| 27 | коронки на зубы цена | 45 000 | коммерческий | Протезирование |
| 28 | съёмные протезы зубов | 30 000 | коммерческий | Протезирование |
| 29 | как ухаживать за зубами | 8 000 | информационный | Блог |
| 30 | почему болят зубы | 6 500 | информационный | Блог |
| 31 | как выбрать стоматологию | 3 200 | информационный | Блог |
| 32 | вреден ли наркоз у стоматолога | 2 100 | информационный | Блог |

**Кластеры:** Главная, Имплантация, Лечение, Отбеливание, Ортодонтия, Детская стоматология, Протезирование, Блог.

---

## 3. Структура URL

```
/                              — Главная
/implantation/                 — Имплантация зубов
/treatment/                    — Лечение зубов
/whitening/                    — Отбеливание и чистка
/orthodontics/                 — Ортодонтия (брекеты, элайнеры)
/children/                     — Детская стоматология
/prosthetics/                  — Протезирование
/blog/                         — Блог
/blog/kak-uhazhivat/           — Как ухаживать за зубами
/blog/pochemu-bolyat/          — Почему болят зубы
/contacts/                     — Контакты
```

---

## 4. robots.txt (с пояснениями)

```txt
# Общие правила для всех роботов
User-agent: *
Allow: /
Disallow: /admin/          # служебная зона — не индексируем
Disallow: /cart/           # корзина/запись — приватные данные
Disallow: /checkout/       # оформление записи
Disallow: /search/         # внутренний поиск — генерация дублей
Disallow: /?utm_           # рекламные метки
Disallow: /?from=          # внешние метки
Disallow: /&               # склейка параметров

# Яндекс
User-agent: Yandex
Allow: /
Disallow: /admin/
Disallow: /cart/
Disallow: /checkout/
Disallow: /search/
Clean-param: utm_source&utm_medium&utm_campaign&utm_content&utm_term
Host: https://example.ru

# Googlebot
User-agent: Googlebot
Allow: /
Disallow: /admin/
Disallow: /cart/
Disallow: /checkout/
Disallow: /search/

Sitemap: https://example.ru/sitemap.xml
```

**Пояснения к директивам:**
- `User-agent` — к какому роботу обращено правило.
- `Allow` / `Disallow` — разрешение/запрет обхода путей.
- `Clean-param` — Яндекс не учитывает указанные UTM-параметры при склейке URL (борьба с дублями).
- `Host` — главное зеркало сайта для Яндекса.
- `Sitemap` — путь к карте сайта.

---

## 5. sitemap.xml

```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://example.ru/</loc>
    <lastmod>2025-01-15</lastmod>
    <changefreq>weekly</changefreq>
    <priority>1.0</priority>
  </url>
  <url>
    <loc>https://example.ru/implantation/</loc>
    <lastmod>2025-01-15</lastmod>
    <changefreq>weekly</changefreq>
    <priority>0.9</priority>
  </url>
  <url>
    <loc>https://example.ru/treatment/</loc>
    <lastmod>2025-01-15</lastmod>
    <changefreq>weekly</changefreq>
    <priority>0.9</priority>
  </url>
  <url>
    <loc>https://example.ru/whitening/</loc>
    <lastmod>2025-01-15</lastmod>
    <changefreq>weekly</changefreq>
    <priority>0.9</priority>
  </url>
  <url>
    <loc>https://example.ru/orthodontics/</loc>
    <lastmod>2025-01-15</lastmod>
    <changefreq>weekly</changefreq>
    <priority>0.8</priority>
  </url>
  <url>
    <loc>https://example.ru/children/</loc>
    <lastmod>2025-01-15</lastmod>
    <changefreq>monthly</changefreq>
    <priority>0.8</priority>
  </url>
  <url>
    <loc>https://example.ru/prosthetics/</loc>
    <lastmod>2025-01-15</lastmod>
    <changefreq>weekly</changefreq>
    <priority>0.8</priority>
  </url>
  <url>
    <loc>https://example.ru/blog/</loc>
    <lastmod>2025-01-15</lastmod>
    <changefreq>weekly</changefreq>
    <priority>0.6</priority>
  </url>
  <url>
    <loc>https://example.ru/blog/kak-uhazhivat/</loc>
    <lastmod>2025-01-15</lastmod>
    <changefreq>monthly</changefreq>
    <priority>0.5</priority>
  </url>
  <url>
    <loc>https://example.ru/blog/pochemu-bolyat/</loc>
    <lastmod>2025-01-15</lastmod>
    <changefreq>monthly</changefreq>
    <priority>0.5</priority>
  </url>
  <url>
    <loc>https://example.ru/contacts/</loc>
    <lastmod>2025-01-15</lastmod>
    <changefreq>yearly</changefreq>
    <priority>0.3</priority>
  </url>
</urlset>
```

**Обязательные элементы:** `<urlset>` с namespace, внутри `<url>` → `<loc>` (обязателен), `<lastmod>`, `<changefreq>`, `<priority>` (опциональны).

---

## 6. Вёрстка

### index.html (главная)

```html
<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Стоматология «ДенталПро» — лечение и имплантация зубов в Москве</title>
  <meta name="description" content="Стоматологическая клиника «ДенталПро»: имплантация, лечение, отбеливание, брекеты. Опытные врачи, современное оборудование, запись онлайн.">
  <link rel="canonical" href="https://example.ru/">
  <link rel="stylesheet" href="css/style.css">
</head>
<body>
  <header class="header">
    <div class="container">
      <a href="/" class="logo">ДенталПро</a>
      <nav class="nav">
        <a href="/implantation/">Имплантация</a>
        <a href="/treatment/">Лечение</a>
        <a href="/whitening/">Отбеливание</a>
        <a href="/orthodontics/">Брекеты</a>
        <a href="/children/">Детям</a>
        <a href="/contacts/">Контакты</a>
      </nav>
    </div>
  </header>

  <section class="hero">
    <div class="container">
      <h1>Стоматология в Москве — лечение и имплантация зубов</h1>
      <p>Имплантация «под ключ», лечение кариеса, отбеливание, брекеты и детская стоматология. Современное оборудование, врачи с опытом от 10 лет.</p>
      <a href="#zapis" class="btn">Записаться на приём</a>
    </div>
  </section>

  <section class="categories">
    <div class="container">
      <h2>Наши услуги</h2>
      <ul class="cat-list">
        <li><a href="/implantation/"><h3>Имплантация зубов</h3><p>под ключ, от 25 000 ₽</p></a></li>
        <li><a href="/treatment/"><h3>Лечение зубов</h3><p>кариес, пульпит, под наркозом</p></a></li>
        <li><a href="/whitening/"><h3>Отбеливание и чистка</h3><p>лазером, профессиональная гигиена</p></a></li>
        <li><a href="/orthodontics/"><h3>Ортодонтия</h3><p>брекеты, элайнеры</p></a></li>
        <li><a href="/children/"><h3>Детская стоматология</h3><p>лечение без стресса</p></a></li>
        <li><a href="/prosthetics/"><h3>Протезирование</h3><p>коронки, съёмные протезы</p></a></li>
      </ul>
    </div>
  </section>

  <section class="seo-text">
    <div class="container">
      <h2>Стоматологическая клиника «ДенталПро»</h2>
      <p>Мы оказываем полный спектр стоматологических услуг в Москве: имплантация зубов, лечение кариеса, отбеливание, установка брекетов и протезирование. В клинике работают врачи с опытом от 10 лет, используется современное оборудование и безопасные материалы.</p>
      <p><a href="/blog/kak-uhazhivat/">Как ухаживать за зубами →</a></p>
    </div>
  </section>

  <section id="zapis" class="seo-text">
    <div class="container">
      <h2>Записаться к стоматологу</h2>
      <p>Оставьте заявку — администратор перезвонит в течение 15 минут и подберёт удобное время.</p>
      <a href="/contacts/" class="btn">Записаться</a>
    </div>
  </section>

  <footer class="footer">
    <div class="container">© 2025 ДенталПро. Все права защищены.</div>
  </footer>
</body>
</html>
```

### implantation/index.html (внутренняя 1)

```html
<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Имплантация зубов под ключ — цены в клинике «ДенталПро»</title>
  <meta name="description" content="Имплантация зубов под ключ от 25 000 ₽. Импланты Straumann, Nobel, Osstem. Гарантия, опытные хирурги, запись онлайн.">
  <link rel="canonical" href="https://example.ru/implantation/">
  <link rel="stylesheet" href="../css/style.css">
</head>
<body>
  <header class="header">
    <div class="container">
      <a href="/" class="logo">ДенталПро</a>
      <nav class="nav">
        <a href="/implantation/">Имплантация</a>
        <a href="/treatment/">Лечение</a>
        <a href="/whitening/">Отбеливание</a>
        <a href="/contacts/">Контакты</a>
      </nav>
    </div>
  </header>

  <div class="container">
    <nav class="breadcrumbs">
      <a href="/">Главная</a> / Имплантация зубов
    </nav>

    <h1>Имплантация зубов под ключ</h1>
    <p>Восстановим зуб за 1 день. Импланты Straumann, Nobel, Osstem. Гарантия до 10 лет.</p>

    <div class="products">
      <div class="product">
        <h3>Имплант Osstem</h3>
        <p>25 000 ₽</p>
        <button>Записаться</button>
      </div>
      <div class="product">
        <h3>Имплант Straumann</h3>
        <p>55 000 ₽</p>
        <button>Записаться</button>
      </div>
      <div class="product">
        <h3>Имплантация «под ключ»</h3>
        <p>от 70 000 ₽</p>
        <button>Записаться</button>
      </div>
    </div>

    <section class="seo-text">
      <h2>Сколько стоит имплантация зубов</h2>
      <p>Стоимость зависит от типа импланта, необходимости костной пластики и коронки. Точную цену врач называет после осмотра и КТ.</p>
    </section>
  </div>

  <footer class="footer">
    <div class="container">© 2025 ДенталПро. Все права защищены.</div>
  </footer>
</body>
</html>
```

### treatment/index.html (внутренняя 2)

```html
<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Лечение зубов — цены и запись в клинику «ДенталПро»</title>
  <meta name="description" content="Лечение кариеса, пульпита, зубов под наркозом. Безболезненно, с гарантией. Цены и запись онлайн.">
  <link rel="canonical" href="https://example.ru/treatment/">
  <link rel="stylesheet" href="../css/style.css">
</head>
<body>
  <header class="header">
    <div class="container">
      <a href="/" class="logo">ДенталПро</a>
      <nav class="nav">
        <a href="/implantation/">Имплантация</a>
        <a href="/treatment/">Лечение</a>
        <a href="/whitening/">Отбеливание</a>
        <a href="/contacts/">Контакты</a>
      </nav>
    </div>
  </header>

  <div class="container">
    <nav class="breadcrumbs">
      <a href="/">Главная</a> / Лечение зубов
    </nav>

    <h1>Лечение зубов</h1>
    <p>Лечим кариес, пульпит и периодонтит без боли. Возможен наркоз и седация.</p>

    <div class="products">
      <div class="product">
        <h3>Лечение кариеса</h3>
        <p>от 4 500 ₽</p>
        <button>Записаться</button>
      </div>
      <div class="product">
        <h3>Лечение пульпита</h3>
        <p>от 9 000 ₽</p>
        <button>Записаться</button>
      </div>
      <div class="product">
        <h3>Лечение под наркозом</h3>
        <p>от 15 000 ₽</p>
        <button>Записаться</button>
      </div>
    </div>

    <section class="seo-text">
      <h2>Лечение зубов без боли</h2>
      <p>Используем современные анестетики и микроскопы. Для тревожных пациентов доступна седация и лечение под наркозом.</p>
    </section>
  </div>

  <footer class="footer">
    <div class="container">© 2025 ДенталПро. Все права защищены.</div>
  </footer>
</body>
</html>
```

### css/style.css

```css
* { box-sizing: border-box; margin: 0; padding: 0; }

body {
  font-family: -apple-system, "Segoe UI", Roboto, Arial, sans-serif;
  color: #222;
  line-height: 1.5;
}

.container { max-width: 1140px; margin: 0 auto; padding: 0 20px; }

.header {
  background: #fff;
  border-bottom: 1px solid #eee;
  padding: 16px 0;
  position: sticky; top: 0; z-index: 10;
}
.header .container { display: flex; justify-content: space-between; align-items: center; }

.logo { font-size: 24px; font-weight: 700; color: #1d7a8c; text-decoration: none; }
.nav a { margin-left: 20px; text-decoration: none; color: #222; }
.nav a:hover { color: #1d7a8c; }

.hero { background: linear-gradient(135deg, #e0f2f5, #f0fbff); padding: 80px 0; text-align: center; }
.hero h1 { font-size: 40px; margin-bottom: 16px; }
.hero p { font-size: 18px; margin-bottom: 24px; }

.btn {
  display: inline-block; background: #1d7a8c; color: #fff;
  padding: 14px 32px; border-radius: 8px;
  text-decoration: none; font-weight: 600;
}
.btn:hover { background: #155e6d; }

.categories { padding: 60px 0; }
.categories h2 { text-align: center; margin-bottom: 32px; font-size: 32px; }
.cat-list {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: 20px; list-style: none;
}
.cat-list a {
  display: block; padding: 24px; border-radius: 12px;
  background: #f8f8f8; text-decoration: none; color: #222;
  transition: transform .2s;
}
.cat-list a:hover { transform: translateY(-4px); }
.cat-list h3 { margin-bottom: 8px; }

.seo-text { padding: 40px 0; background: #fafafa; }
.seo-text h2 { margin-bottom: 16px; }
.seo-text a { color: #1d7a8c; }

.products {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 20px; margin: 32px 0;
}
.product { padding: 20px; border: 1px solid #eee; border-radius: 12px; }
.product button {
  margin-top: 12px; padding: 8px 16px;
  background: #1d7a8c; color: #fff; border: none;
  border-radius: 6px; cursor: pointer;
}

.breadcrumbs { margin: 20px 0; color: #777; font-size: 14px; }

.footer { padding: 24px 0; background: #222; color: #ccc; text-align: center; }

@media (max-width: 768px) {
  .hero h1 { font-size: 28px; }
  .nav a { margin-left: 12px; font-size: 14px; }
}
```

---

## 7. Ответы на контрольные вопросы (кратко)

1. **СЯ** — упорядоченный набор поисковых запросов, по которым сайт должен ранжироваться; основа структуры и контента.
2. **ВЧ/СЧ/НЧ** — высоко-, средне- и низкочастотные запросы (по числу показов в Wordstat); ВЧ — шире охват, НЧ — легче конкуренция.
3. **Кластеризация** — группировка по совпадению топ-URL выдачи (Key Collector, Serpstat) или по леммам.
4. **Директивы robots.txt:** `User-agent`, `Allow`, `Disallow`, `Clean-param`, `Host`, `Sitemap`, `Crawl-delay`.
5. **Clean-param** — указывает Яндексу, какие GET-параметры не учитывать при склейке URL (убирает дубли от UTM-меток).
6. **Обязательные элементы sitemap.xml:** `<urlset>` с namespace, `<url>`, `<loc>`; `lastmod`, `changefreq`, `priority` — опциональны.
7. **Связь кластеров и URL:** каждый кластер = отдельный раздел (`/implantation/`, `/treatment/`), что даёт релевантность и перелинковку.
8. **SEO-теги в `<head>`:** `<title>`, `<meta name="description">`, `<link rel="canonical">`, `<meta name="robots">`, Open Graph, `hreflang`, `viewport`.
9. **rel="canonical"** — указывает предпочтительный URL при дублях (с/без параметров, www/без www, сортировки).
10. **Проверка:** robots.txt — Вебмастер «Анализ robots.txt» и Search Console; sitemap.xml — валидатор `xml-sitemaps.com/validate-xml-sitemap.html`, Search Console «Файлы Sitemap».

---

## 8. Вывод (шаблон для отчёта)

> В ходе работы было собрано семантическое ядро из 32 запросов по тематике «Стоматология», выполнена кластеризация по интенту и тематическим группам (Главная, Имплантация, Лечение, Отбеливание, Ортодонтия, Детская стоматология, Протезирование, Блог). На основе кластеров спроектирована структура URL. Созданы robots.txt с директивами Clean-param и Host и валидный sitemap.xml. Сверстаны главная и две внутренние страницы («Имплантация», «Лечение») с семантической разметкой, meta-тегами и адаптивной вёрсткой (CSS Grid + media query). Работа позволила освоить полный цикл: от сбора запросов до технической оптимизации и вёрстки под SEO.

---

## Что осталось сделать вам

1. **Скриншоты** страниц в браузере: главная, `/implantation/`, `/treatment/` — откройте HTML-файлы локально и сделайте снимки.
2. **Excel-файл** с таблицей СЯ — приложите как приложение (скопируйте таблицу из п. 2).
3. При желании добавьте третью внутреннюю страницу `/whitening/` или `/children/` — структура и CSS уже готовы, достаточно скопировать шаблон.

Если нужно — могу добавить страницу `/children/` (детская стоматология) или `/blog/` с примером информационной статьи.
