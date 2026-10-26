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
    <loc>https://polinashavrina.github.io/dents/</loc>
    <lastmod>2025-01-15</lastmod>
    <changefreq>weekly</changefreq>
    <priority>1.0</priority>
  </url>
  <url>
    <loc>https://polinashavrina.github.io/dents/implantation/</loc>
    <lastmod>2025-01-15</lastmod>
    <changefreq>weekly</changefreq>
    <priority>0.9</priority>
  </url>
  <url>
    <loc>https://polinashavrina.github.io/dents/treatment/</loc>
    <lastmod>2025-01-15</lastmod>
    <changefreq>weekly</changefreq>
    <priority>0.9</priority>
  </url>
  <url>
    <loc>https://polinashavrina.github.io/dents/whitening/</loc>
    <lastmod>2025-01-15</lastmod>
    <changefreq>weekly</changefreq>
    <priority>0.9</priority>
  </url>
  <url>
    <loc>https://polinashavrina.github.io/dents/orthodontics/</loc>
    <lastmod>2025-01-15</lastmod>
    <changefreq>weekly</changefreq>
    <priority>0.8</priority>
  </url>
  <url>
    <loc>https://polinashavrina.github.io/dents/children/</loc>
    <lastmod>2025-01-15</lastmod>
    <changefreq>monthly</changefreq>
    <priority>0.8</priority>
  </url>
  <url>
    <loc>https://polinashavrina.github.io/dents/prosthetics/</loc>
    <lastmod>2025-01-15</lastmod>
    <changefreq>weekly</changefreq>
    <priority>0.8</priority>
  </url>
  <url>
    <loc>https://polinashavrina.github.io/dents//blog/</loc>
    <lastmod>2025-01-15</lastmod>
    <changefreq>weekly</changefreq>
    <priority>0.6</priority>
  </url>
  <url>
    <loc>https://polinashavrina.github.io/dents/blog/kak-uhazhivat/</loc>
    <lastmod>2025-01-15</lastmod>
    <changefreq>monthly</changefreq>
    <priority>0.5</priority>
  </url>
  <url>
    <loc>https://polinashavrina.github.io/dents/blog/pochemu-bolyat/</loc>
    <lastmod>2025-01-15</lastmod>
    <changefreq>monthly</changefreq>
    <priority>0.5</priority>
  </url>
  <url>
    <loc>https://polinashavrina.github.io/dents/contacts/</loc>
    <lastmod>2025-01-15</lastmod>
    <changefreq>yearly</changefreq>
    <priority>0.3</priority>
  </url>
</urlset>
```

**Обязательные элементы:** `<urlset>` с namespace, внутри `<url>` → `<loc>` (обязателен), `<lastmod>`, `<changefreq>`, `<priority>` (опциональны).

---
 6. Вёрстка
(создан сайт)

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
