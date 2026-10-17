Структура сайта и карта сайта
(sitemap.xml)
2.1. Выбор тематики и проектирование структуры
Выберите тематику сайта:<br>
онлайн-театр<br>
Определите:<br>
типы контента (категории, карточки, статьи, новости,<br>
FAQ, контактные формы)<br>
Тип контента	Описание	Пример<br>
Категории	Жанры спектаклей	Драма, Комедия, Мюзикл, Опера, Балет, Детские<br>
Карточки спектаклей	Краткая информация о постановке	Название, постер, жанр, длительность, возрастное ограничение, цена<br>
Страница спектакля	Полное описание	Сюжет, актёры, режиссёр, трейлер, расписание, отзывы<br>
Новости	Анонсы, премьеры, события театра	«Премьера сезона», «Гастроли»<br>
Статьи (блог)	Познавательный контент	История театра, интервью с актёрами, закулисье<br>
FAQ	Частые вопросы	Как купить билет? Как смотреть онлайн? Возврат билета<br>
Контакты / форма обратной связи	Связь с администрацией	Адрес, телефон, форма, карта<br>
Личный кабинет	Для зарегистрированных пользователей	Мои билеты, история просмотров, подписка<br>
Афиша / расписание	Календарь показов	Онлайн-трансляции по датам<br>

Цели сайта
1.	Основная цель – продажа билетов на онлайн-спектакли и трансляции.
2.	Информационная – предоставление полной информации о репертуаре, актёрах, театре.
3.	Маркетинговая – привлечение новой аудитории, продвижение премьер через новости и блог.
4.	Коммуникационная – обратная связь со зрителями, сбор отзывов.
5.	Удержание – подписка, личный кабинет, рекомендации спектаклей.
6.	ключевые страницы
Ключевые страницы
1.	Главная – баннер с премьерой, афиша, популярные спектакли, новости.
2.	Афиша – список всех спектаклей с фильтрами (жанр, дата, возраст).
3.	Страница спектакля – описание, трейлер, расписание, кнопка «Купить билет».
4.	Жанры / Категории – навигация по типам постановок.
5.	Новости – список новостей + детальная страница.
6.	Блог / Статьи – познавательные материалы
7.	FAQ – вопросы и ответы
8.	Контакты – форма связи, адрес, карта
9.	Личный кабинет – вход/регистрация, мои билеты
10.	Корзина / Оформление заказа – оплата билета.
11.	О театре – история, труппа, миссия.


Пример MindMap / схемы навигации:

 ![Рисунок 1](https://github.com/PolinaShavrina/-web--/blob/main/photo/Рисунок1.png)


https://polinashavrina.github.io/online-theatre/


```markdown
| № | Раздел | Подразделы | Пример URL | Частота | Приоритет |
|---|--------|------------|------------|---------|-----------|
| 1 | Главная | – | https://polinashavrina.github.io/online-theatre/ | daily | 1.0 |
| 2 | Афиша | – | https://polinashavrina.github.io/online-theatre/afisha.html | daily | 0.9 |
| 2.1 | Афиша | Афиша -> Жанры (Список жанров) | https://polinashavrina.github.io/online-theatre/genres.html | weekly | 0.8 |
| 2.2 | Афиша | Афиша -> Жанры -> Спектакли (Драма / Комедия / Балет / Опера / Детские) | https://polinashavrina.github.io/online-theatre/genre.html | weekly | 0.7 |
| 2.3 | Афиша | Афиша -> Спектакль (Карточка спектакля) | https://polinashavrina.github.io/online-theatre/play.html | weekly | 0.9 |
| 2.4 | Афиша | Афиша -> Расписание (Календарь показов) | https://polinashavrina.github.io/online-theatre/schedule.html | daily | 0.8 |
| 2.5 | Афиша | Афиша -> Отзывы (Отзывы зрителей) | https://polinashavrina.github.io/online-theatre/reviews.html | weekly | 0.6 |
| 3 | Корзина | – | https://polinashavrina.github.io/online-theatre/cart.html | monthly | 0.5 |
| 4 | Оплата | – | https://polinashavrina.github.io/online-theatre/checkout.html | monthly | 0.5 |
| 5 | Новости | Список новостей | https://polinashavrina.github.io/online-theatre/news.html | daily | 0.8 |
| 5.1 | Новости | Новости -> Новость (Детальная страница) | https://polinashavrina.github.io/online-theatre/news-item.html | weekly | 0.7 |
| 6 | Блог | Список статей | https://polinashavrina.github.io/online-theatre/blog.html | weekly | 0.7 |
| 6.1 | Блог | Блог -> Статья (Детальная страница) | https://polinashavrina.github.io/online-theatre/blog-item.html | monthly | 0.6 |
| 7 | FAQ | – | https://polinashavrina.github.io/online-theatre/faq.html | monthly | 0.6 |
| 8 | О театре | – | https://polinashavrina.github.io/online-theatre/about.html | monthly | 0.7 |
| 9 | Контакты | – | https://polinashavrina.github.io/online-theatre/contacts.html | monthly | 0.6 |
| 10 | Личный кабинет | – | https://polinashavrina.github.io/online-theatre/account.html | weekly | 0.4 |
| 10.1 | Личный кабинет | Личный кабинет -> Вход | https://polinashavrina.github.io/online-theatre/login.html | yearly | 0.3 |
| 10.2 | Личный кабинет | Личный кабинет -> Регистрация | https://polinashavrina.github.io/online-theatre/register.html | yearly | 0.3 |
```


<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">

    <url>
        <loc>https://polinashavrina.github.io/online-theatre/</loc>
        <changefreq>daily</changefreq>
        <priority>1.0</priority>
    </url>

    <url>
        <loc>https://polinashavrina.github.io/online-theatre/afisha.html</loc>
        <changefreq>daily</changefreq>
        <priority>0.9</priority>
    </url>

    <url>
        <loc>https://polinashavrina.github.io/online-theatre/genres.html</loc>
        <changefreq>weekly</changefreq>
        <priority>0.8</priority>
    </url>

    <url>
        <loc>https://polinashavrina.github.io/online-theatre/genre.html</loc>
        <changefreq>weekly</changefreq>
        <priority>0.7</priority>
    </url>

    <url>
        <loc>https://polinashavrina.github.io/online-theatre/play.html</loc>
        <changefreq>weekly</changefreq>
        <priority>0.9</priority>
    </url>

    <url>
        <loc>https://polinashavrina.github.io/online-theatre/schedule.html</loc>
        <changefreq>daily</changefreq>
        <priority>0.8</priority>
    </url>

    <url>
        <loc>https://polinashavrina.github.io/online-theatre/reviews.html</loc>
        <changefreq>weekly</changefreq>
        <priority>0.6</priority>
    </url>

    <url>
        <loc>https://polinashavrina.github.io/online-theatre/cart.html</loc>
        <changefreq>monthly</changefreq>
        <priority>0.5</priority>
    </url>

    <url>
        <loc>https://polinashavrina.github.io/online-theatre/checkout.html</loc>
        <changefreq>monthly</changefreq>
        <priority>0.5</priority>
    </url>

    <url>
        <loc>https://polinashavrina.github.io/online-theatre/news.html</loc>
        <changefreq>daily</changefreq>
        <priority>0.8</priority>
    </url>

    <url>
        <loc>https://polinashavrina.github.io/online-theatre/news-item.html</loc>
        <changefreq>weekly</changefreq>
        <priority>0.7</priority>
    </url>

    <url>
        <loc>https://polinashavrina.github.io/online-theatre/blog.html</loc>
        <changefreq>weekly</changefreq>
        <priority>0.7</priority>
    </url>

    <url>
        <loc>https://polinashavrina.github.io/online-theatre/blog-item.html</loc>
        <changefreq>monthly</changefreq>
        <priority>0.6</priority>
    </url>

    <url>
        <loc>https://polinashavrina.github.io/online-theatre/faq.html</loc>
        <changefreq>monthly</changefreq>
        <priority>0.6</priority>
    </url>

    <url>
        <loc>https://polinashavrina.github.io/online-theatre/about.html</loc>
        <changefreq>monthly</changefreq>
        <priority>0.7</priority>
    </url>

    <url>
        <loc>https://polinashavrina.github.io/online-theatre/contacts.html</loc>
        <changefreq>monthly</changefreq>
        <priority>0.6</priority>
    </url>

    <url>
        <loc>https://polinashavrina.github.io/online-theatre/account.html</loc>
        <changefreq>weekly</changefreq>
        <priority>0.4</priority>
    </url>

    <url>
        <loc>https://polinashavrina.github.io/online-theatre/login.html</loc>
        <changefreq>yearly</changefreq>
        <priority>0.3</priority>
    </url>

    <url>
        <loc>https://polinashavrina.github.io/online-theatre/register.html</loc>
        <changefreq>yearly</changefreq>
        <priority>0.3</priority>
    </url>

</urlset>

 
![picture](https://github.com/PolinaShavrina/-web--/blob/main/photo/Рисунок2.png)

 ![picture](https://github.com/PolinaShavrina/-web--/blob/main/photo/Рисунок3.png)


Вопросы.

1 Что такое структура сайта и как она влияет на SEO и UX?

Структура сайта – это то, как страницы связаны между собой и как они организованы. Проще говоря, это «скелет» сайта: какие разделы есть, какие страницы в них лежат, как пользователь и поисковик попадают с одной страницы на другую.<br>
Хорошая структура – это когда всё логично: главная -> категория -> подкатегория -> конкретный товар или статья. Пользователь за пару кликов находит нужное, не плутает. Поисковик тоже легко обходит сайт и понимает, какая страница главная, а какая второстепенная.<br>
Для SEO структура важна потому, что поисковики оценивают сайт по иерархии: чем ближе страница к главной и чем больше на неё ссылок изнутри, тем выше её «вес». Ещё структура помогает распределять так называемый ссылочный вес и не создавать дубли.<br>
Для UX структура – это про удобство. Если человек не может найти нужное за 2–3 клика, он уходит. Плоская и понятная структура снижает отказы и увеличивает глубину просмотра.
2 Для чего нужен файл sitemap.xml?<br>


Sitemap.xml – это файл, в котором вы перечисляете поисковику все важные страницы сайта. Это как карта: «вот эти URL у меня есть, обрати на них внимание».
Он не гарантирует индексацию, но помогает поисковику быстрее узнать о новых страницах, особенно если на них мало внутренних ссылок или сайт большой.<br>


3 Какие теги обязательны в sitemap.xml?<br>
Обязателен только один тег внутри каждого <url> – <loc>. В нём указывается адрес страницы.<br>
Всё остальное (<lastmod>, <changefreq>, <priority>) – необязательное. Корневой тег <urlset> с правильным namespace тоже обязателен по структуре.<br>


4 Что означают <lastmod>, <changefreq>, <priority>?<br>
<lastmod> – дата последнего изменения страницы. Помогает поисковику понять, стоит ли переобходить страницу.<br>
<changefreq> – как часто страница меняется: daily, weekly, monthly и т.д. Это скорее подсказка, чем команда. Google, например, в основном игнорирует этот тег.<br>
<priority> – приоритет страницы от 0.0 до 1.0. Тоже подсказка. Не влияет на позиции напрямую, и Google его не учитывает.<br>


5 Почему <loc> должен быть абсолютным URL?<br>


Потому что sitemap.xml могут читать с разных доменов и поддоменов, и относительный путь будет непонятен. Абсолютный URL – это полный адрес с протоколом и доменом, например https://example.com/page. Так поисковик точно знает, куда идти.<br>

6 Как правильно связать sitemap.xml и robots.txt?<br>


В robots.txt нужно добавить строку с указанием, где лежит карта сайта:<br>
Sitemap: https://example.com/sitemap.xml<br>


Это стандартный способ сообщить поисковикам о наличии sitemap. Можно указать несколько Sitemap-строк, если карт несколько.<br>


7 Каковы ограничения файла sitemap.xml по размеру и
количеству URL?<br>

Один файл sitemap.xml может содержать не больше 50 000 URL и весить не больше 50 МБ (в несжатом виде). Если у вас больше страниц – нужно разбивать на несколько карт и объединять их через Sitemap Index.<br>


8 Что такое Sitemap Index? Когда его использовать?<br>

Sitemap Index – это файл-контейнер, который ссылается на другие sitemap-файлы. Используется, когда у вас больше 50 000 URL или несколько карт по разным типам контента (товары, статьи, изображения).<br>

9 Как учитывать многоязычность (hreflang)?<br>

В sitemap.xml можно указывать альтернативные языковые версии через xhtml:link с атрибутом hreflang. Это делается внутри каждого <url>:
xml
<url>
  <loc>https://example.com/ru/page</loc>
  <xhtml:link rel="alternate" hreflang="en" href="https://example.com/en/page"/>
  <xhtml:link rel="alternate" hreflang="ru" href="https://example.com/ru/page"/>
</url>
Это помогает поисковику показать нужную языковую версию нужному пользователю.

10 Какие ошибки мешают индексации URL из sitemap.xml?<br>
Частые проблемы: URL возвращает 404 или 500, страница закрыта в robots.txt, стоит noindex, URL редиректит на другой адрес, в sitemap указаны неканонические версии, файл недоступен по указанному адресу, в <loc> относительный путь или битая ссылка.

Ещё одна частая ошибка – указывать в sitemap страницы, которые не нужны в индексе (служебные, пагинация, фильтры).<br>

11 Как формировать sitemap.xml для динамических
разделов (новости, каталог)?<br>
Для новостей, каталогов и других динамических разделов sitemap обычно генерируется автоматически на стороне сайта: скрипт берёт список URL из базы данных и формирует XML. Обновляется по расписанию или при добавлении нового контента.<br>

Для больших каталогов имеет смысл разбивать карту по разделам или по типам страниц. Для новостей – использовать news sitemap, если это актуально для Google News.
12 Когда нужно использовать отдельные карты: для
изображений, видео или новостей?<br>
Отдельные карты нужны, когда вы хотите передать поисковику дополнительную информацию, которую обычный sitemap не передаёт.

Для изображений – image sitemap, чтобы поисковик лучше понял, что за картинки на странице.<br>

Для видео – video sitemap с метаданными: название, описание, длительность, превью.<br>

Для новостей – news sitemap, чтобы попасть в Google News. Там указываются только свежие статьи за последние 48 часов.<br>

Их можно включать как отдельные файлы или как расширения внутри основного sitemap.<br>
