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
  <li>Реализовать Flex/Grid.</li>
  <li>Обновить стили под разные устройства.</li>
</ol>
