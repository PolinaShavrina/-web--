Таблица методов поиска

Метод поиска	Ищет по...	Возвращает...	Ищет внутри элемента?	Живая коллекция?
querySelector	Любой CSS-selector	Один объект	Да	Нет
querySelectorAll	Любой CSS-selector	Коллекцию объектов	Да	Нет
getElementById	id	Один объект	Нет	Нет
getElementsByTagName	тег или *	Коллекцию объектов	Да	Да
getElementsByClassName	имя класса	Коллекцию объектов	Да	Да
getElementsByName	name	Коллекцию объектов	Нет	Да
DOM-узел можно создать двумя методами:				
document.createElement(tag) Создает новый элемент с тегом
document.createTextNode(text) Создаёт новый текстовый узел с заданным текстом
Методы вставки: Чтобы div появился, нам нужно вставить его где-нибудь в document. Например, в document.body. Для этого есть метод append, в нашем случае document.body.append(div).

