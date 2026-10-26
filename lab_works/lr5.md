<h1>Лабораторная работа №5<br>
Тема: Адаптивный дизайн и UX-аудит</h1>


<p>Используется сайт из лабораторной 3 - sitemap.</p>

<ol>
  <li>Определить брейкпоинты:</li>
  <li>≥1024px — десктоп</li>

  <table>
  <tr>
    <td>
      
    .header-inner {
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: nowrap;   /* было wrap — из-за этого на планшете всё прыгало */
      gap: 10px;
    }
    
    /* Навигация — единый селектор .nav */
    .nav {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      gap: 4px;
    }
    .nav a {
      color: #eee;
      text-decoration: none;
      margin-left: 14px;
      font-size: 14px;
      transition: .2s;
      white-space: nowrap;
    }
    .nav a:hover { color: #e94560; }
    .nav a.active { color: #e94560; font-weight: 600; }
    .nav a.cart {
      background: #e94560;
      padding: 6px 12px;
      border-radius: 5px;
      color: #fff;
      margin-left: 14px;
    }
    .nav a.cart:hover { background: #c73650; color: #fff; }
    
    /* Кнопки внутри навигации */
    .nav button {
      margin-left: 8px;
      padding: 6px 10px;
      font-size: 13px;
      border: 1px solid rgba(255,255,255,.25);
      background: transparent;
      color: #eee;
      border-radius: 5px;
      cursor: pointer;
      transition: .2s;
      white-space: nowrap;
    }
    .nav button:hover { background: rgba(255,255,255,.12); }
    
    /* Гамбургер */
    .hamburger {
      display: none;
      background: none;
      border: none;
      font-size: 26px;
      color: #fff;
      cursor: pointer;
      padding: 4px 8px;
      order: 2;
    }
    
  </td>
  </tr>
</table>


  
  <li>768–1023px — планшет</li>



  <table>
  <tr>
    <td>
      
    @media (min-width: 768px) and (max-width: 1023px) {
    .container_2 { padding: 24px 18px; }
    .grid { grid-template-columns: repeat(auto-fill, minmax(230px, 1fr)); gap: 16px; }
    .hero { padding: 45px 30px; }
    .hero h1 { font-size: 28px; }
    .hero p  { font-size: 16px; }
    h1 { font-size: 26px; }
    h2 { font-size: 22px; }
    .filter-bar { gap: 6px; }
    /* таблицы — обёртка вместо display:block */
    .table-wrap { overflow-x: auto; -webkit-overflow-scrolling: touch; }
    .table-wrap table { min-width: 600px; }
    }
    
  </td>
  </tr>
</table>


  <li><768px — мобильный</li>

  <table>
  <tr>
    <td>
      
     @media (max-width: 767px) {
      .container { padding: 0 14px; }
      .container_2 { padding: 20px 14px; }
    
      /* Header */
      .header-inner { gap: 8px; }
      .logo { font-size: 19px; }
    
      .hamburger { display: block; }
    
      /* Выезжающее меню */
      .nav {
        position: fixed;
        top: 0;
        right: -100%;
        width: 80%;
        max-width: 320px;
        height: 100vh;
        background: #1a1a2e;
        transition: right .3s ease;
        z-index: 1000;
        display: flex;
        flex-direction: column;
        align-items: stretch;
        gap: 2px;
        padding: 70px 16px 20px;
        margin: 0;
        box-shadow: -4px 0 20px rgba(0,0,0,.3);
        overflow-y: auto;
        flex-wrap: nowrap;
      }
      .nav.open { right: 0; }
    
      .nav a,
      .nav button {
        margin: 0;
        width: 100%;
        padding: 12px 10px;
        font-size: 15px;
        color: #eee;
        border-bottom: 1px solid rgba(255,255,255,.07);
        background: transparent;
        border-radius: 0;
        text-align: left;
        white-space: normal;
      }
      .nav a.cart {
        text-align: center;
        margin-top: 10px;
        border-bottom: none;
        border-radius: 5px;
      }
      .nav button:hover { background: rgba(255,255,255,.1); }
    
      /* блокировка скролла при открытом меню */
      body.menu-open { overflow: hidden; }
    
      /* Main */
      main { padding: 20px 0; }
    
      /* Hero */
      .hero { padding: 32px 20px; border-radius: 10px; margin-bottom: 22px; text-align: center; }
      .hero h1 { font-size: 23px; }
      .hero p  { font-size: 15px; }
      .hero .btn { display: block; margin-top: 12px; }
    
      h1 { font-size: 22px; margin-bottom: 14px; }
      h2 { font-size: 19px; margin: 22px 0 12px; }
      h3 { font-size: 17px; }
    
      /* Сетка карточек */
      .grid { grid-template-columns: 1fr; gap: 14px; }
      .card { padding: 16px; }
      .card .price { font-size: 18px; }
    
      /* Кнопки */
      .btn { display: block; width: 100%; text-align: center; padding: 12px 18px; }
      .btn-sm { display: inline-block; width: auto; padding: 6px 12px; }
    
      /* Формы */
      form input, form textarea, form select { font-size: 16px; padding: 11px; }
    
      /* Фильтр */
      .filter-bar { flex-direction: column; align-items: stretch; }
      .filter-bar .btn { margin-top: 0; }
    
      /* Section title */
      .section-title { flex-direction: column; align-items: flex-start; gap: 8px; }
    
      /* Таблицы */
      .table-wrap { overflow-x: auto; -webkit-overflow-scrolling: touch; }
      .table-wrap table { min-width: 560px; }
    
      /* FAQ / новости / блог */
      .faq-item, .news-item, .blog-item { padding: 16px; }
    
      /* Footer */
      footer { padding: 20px 0; font-size: 13px; }
    }
    
  </td>
  </tr>
</table>
  <li>Реализовать Flex/Grid.</li>
  <table>
    <tr>
      <td>
      
            /* Grid & Cards */
          .grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(260px, 1fr)); gap: 20px; }
          .card { background: #fff; border-radius: 10px; padding: 20px; box-shadow: 0 2px 10px rgba(0,0,0,.06); transition: .2s; }
          .card:hover { transform: translateY(-3px); box-shadow: 0 8px 20px rgba(0,0,0,.12); }
          .card h3 { margin-bottom: 8px; }
          .card .genre { display: inline-block; background: #e94560; color: #fff; padding: 2px 10px; border-radius: 12px; font-size: 12px; margin-bottom: 8px; }
          .card .price { font-size: 20px; font-weight: bold; color: #e94560; margin-top: 10px; }
          .card p { color: #666; font-size: 14px; }
          .card .meta { color: #999; font-size: 13px; margin-top: 6px; }

  </td>   
  </tr>
  </table>
  <li>Обновить стили под разные устройства.</li>
</ol>



<h2> Реализуйте дополнительные возможности<br>
сайта<br>
Переключатель темы «День/Ночь»</h2>

<table>
  <tr>
    <td>
      
      const btn = document.getElementById('btn');
      let theme = false;
      function ChangeTheme() {
          theme = !theme;
          const isDark = document.body.classList.toggle('dark-theme');
          btn.textContent = theme ? 'Переключить на светлую': 'Переключить на тёмную';
      }
  </td>
  </tr>
</table>

<h2>Бургер-меню с клавиатурной доступностью</h2>
html
<table>
  <tr>
    <td>
      
      <button class="hamburger">☰</button>
    
  </td>  
  </tr>
</table>

js
<table>
  <tr>
    <td>
      
      let hamburger = document.querySelector('.hamburger');
    let nav = document.querySelector('.nav');
    
    hamburger.addEventListener('click', function(e) {
    	e.stopPropagation();
    	nav.classList.toggle('active');
    });
    
    document.addEventListener('click', function(e) {
    	if (!nav.contains(e.target)) {
    		nav.classList.remove('active');
    	}
    });

    
  </td>  
  </tr>
</table>


<h2>Переключатель «Обычный шрифт / Крупный шрифт»</h2>

html
<table>
  <tr>
    <td>
      
      <button id="btn1">
                А+
      </button>
      <button  id="btn2">
                А-
      </button>
    
  </td>  
  </tr>
</table>

js
<table>
  <tr>
    <td>
      
     const paragraph = document.querySelector('p');
    const zagalovok = document.querySelector('h2');
    
    // Функция для изменения размера
    function changeFontSize() {
      // Находим контейнер
      const controlElement = document.querySelector('.container_2');
      controlElement.style.fontSize = `${currentZoom}%`;
    }
    
    // Обработчики для кнопок
    btn1.addEventListener('click', () => {
        console.log('message: A+');
      // if (currentZoom < percentages[2]) {
      //   currentZoom += 25; // Увеличиваем на 25%
      // }
      paragraph.style.fontSize = '50px';
      zagalovok.style.fontSize = '50px';
    });
    
    btn2.addEventListener('click', () => {
      // if (currentZoom > percentages[0]) {
      //   currentZoom -= 25; // Уменьшаем на 25%
      // }
      paragraph.style.fontSize = '10px';
      zagalovok.style.fontSize = '50px';
    });

    
  </td>  
  </tr>
</table>

<h2>Замерить загрузку в DevTools → Network. Объяснить влияние<br>
задержки на конверсию.</h2>

![Рис1](https://github.com/PolinaShavrina/-web--/blob/main/photo/labwork/la5/Screenshot%202026-10-24%20110548.png)

1. **index.html (Document)**:
   - **Status 200**: Успешная загрузка.
   - **Time: 6 ms**: Это время загрузки самого HTML-документа. В данном случае оно очень мало, что говорит о быстром ответе сервера.
   - **Size: 6.3 kB**: Размер документа.
   - **Initiator: Other**: Запрос инициирован браузером (ввод адреса или переход по ссылке).

2. **style.css (Stylesheet)**:
   - **Initiator: index.html:7**: Файл стилей запрашивается из HTML-документа (строка 7).
   - **Time: 11 ms**: Время загрузки стилей. Поскольку CSS блокирует рендеринг (браузер не отрисует страницу, пока не загрузит стили), этот показатель важен для первой отрисовки.
   - **Size: 13.4 kB**.

3. **script.js (Script)**:
   - **Initiator: index.html:125**: Скрипт подключается в HTML (строка 125).
   - **Time: 37 ms**: Самое долгое время загрузки среди представленных файлов (хотя в абсолютных значениях оно все еще очень быстрое). 
   - **Size: 2.0 kB**.

Задержка загрузки сайта оказывает прямое и измеримое негативное влияние на конверсию. Даже минимальное промедление в десятые доли секунды приводит к потере пользователей на каждом этапе воронки продаж, снижению коэффициента конверсии и, как следствие, к упущенной выручке.

<h2>«Битва конкурентов»<br>
Сравнить демо-сайт ReadyScript с Wildberries по:<br></h2>

![Рис2](https://github.com/PolinaShavrina/-web--/blob/main/photo/labwork/la5/Screenshot%202026-10-26%20143824.png)



1.   Скорость (Анализ по скриншотам)<br>
Первый скриншот (Легкий сайт): Это эталон минимализма. Всего 3 файла. Главный документ (index.html) весит 6.3 КБ и грузится за 6 мс. Общий вес страницы — около 20 КБ. Время загрузки измеряется в единицах миллисекунд. Это возможно только на очень простых сайтах.<br>

Второй скриншот (Wildberries): Это тяжелое SPA-приложение (Single Page Application) на React.<br>

Основной документ грузится за 269 мс (в 45 раз дольше первого).<br>

Загружается множество скриптов (react-vendors, react-app, entry и т.д.), шрифты и SVG.<br>

Критический момент: Запрос preflight (проверка CORS) занимает аж 481 мс. Это значит, что перед тем, как загрузить часть данных (например, цены или наличие товара), браузер ждет почти <br>полсекунды только на проверку безопасности.<br>

Нюанс: На скриншоте ВБ большинство файлов имеют пометку (disk cache), то есть они взяты из кеша браузера. Если бы пользователь зашел впервые (очистив кеш), время загрузки выросло бы в разы.<br>

Вывод по скорости: Легкий сайт (скриншот 1) несоизмеримо быстрее. Wildberries, несмотря на кеширование, имеет задержки на сетевые проверки (preflight) и обработку тяжелого JS-кода. Ozon в <br>этом плане работает похоже на ВБ, но активно борется за метрику LCP (скорость отрисовки главного контента), чтобы скрыть эти технические задержки от глаз пользователя.<br>


 2.  Удобство поиска
Скриншоты показывают только техническую сторону загрузки, но архитектура из второго скриншота (React-приложение, обилие скриптов, preflight-запросы) объясняет, как работает поиск:

Wildberries: Эти тяжелые скрипты нужны для работы сложнейших алгоритмов. Поиск на маркетплейсах — это ML-модели, которые в реальном времени подгружают персонализированную выдачу, учитывают вашу историю, геолокацию и рекламные ставки продавцов. Поиск по фото (на ВБ) — это отдельный ресурсоемкий процесс.

Легкий сайт (скриншот 1): С таким набором файлов (2 КБ скриптов) возможен только базовый поиск по названию товара. Никакой персонализации или сложного ранжирования там нет.

Вывод по поиску: Маркетплейсы (ВБ/Ozon) предлагают несопоставимо более умный и удобный поиск, но платой за это является тяжелая техническая архитектура, которую мы видим на скриншоте 2.


3.  Визуальная структура

   
Wildberries: Огромное количество скриптов на скриншоте (различные default-settings, lang, react-vendors) отвечают за динамическую подгрузку контента. Визуально это выливается в бесконечный скролл, динамические баннеры, всплывающие окна и блоки рекомендаций. Структура страдает от перегруженности (низкая ясность при высоком индексе внимания).

Легкий сайт (скриншот 1): Визуально это будет чистая, статичная страница. Никаких «прыгающих» элементов (layout shift), так как все загружается мгновенно.
