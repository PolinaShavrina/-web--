<h1>Лабораторная работа №5<br>
Тема: Адаптивный дизайн и UX-аудит</h1>


<p>Используется сайт из лабораторной 3 - sitemap.</p>

<ol>
  <li>Определить брейкпоинты:</li>
  <li>≥1024px — десктоп</li>

  <table>
  <tr>
    <td>
      
    /* ---------- Базовые настройки (десктоп ≥1024px) ---------- */<br>
    .container { width: 100%; }
    /* Сетка карточек: на десктопе 3–4 колонки */
    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
      gap: 20px;
    }
    /* Контейнер для товаров/контента (используется в разметке) */
    .container_2 {
      max-width: 1200px;
      margin: 0 auto;
      display: grid;
      grid-template-columns: repeat(3, 1fr); /* 3 колонки на десктопе */
      gap: 20px;
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
