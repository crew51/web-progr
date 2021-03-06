# Основы HTML

> Важно!!!
> для работы необходимо на рабочей машине иметь установленный [git](git-scm.com) и [node.js](nodejs.org)
> для запуска проекта необходимо в терминале набрать `npm install` затем `npm run start`, запустится небольшое web-приложение по адресу http://localhost:8080. При изменении разметки необходимо обновить страницу в браузере.

## Основные понятия 

HTML - Hypertext markup language (гипертекстовый язык разметки), разработан в 1986 - 1991 годах в ЦЕРНе ученным Тимом Бернерсом-Ли. Благодаря этому языку мы видим большинство страниц в Интернете такими какие они есть. Изначально этот язык придумывался как язык составления технической документации, к сожалению, в век web-приложений это стало проблемой, така текущее его использование не соответствует его первоначальному назначению.

Основным элементом языка является **тег** иобозначается как `<tag-name>`. Теги бывают 2-х типов:
* Одиночные `<img>` - просто описывают элемент документа.
* Парные `<html><body>Содержимое тегов</body></html>` предполагаоют открывающий (`<html>`) и закрывающий (</html>) тег и содержимое внутри них.

Теги образуют элементы догумента, которые в свою очередь быват **строчные** и **блочные**. Блочный элемент подразумевает, что следующий за ним элемент будет размещен под ним, строчный элемент подразумевает, что следующий за ним элемент будет расположен рядом с предыдущим, если позволяет место.

Теги могут применяться совместно с **атрибутами**, у атрибутов могут быть значения. 

Под атрибутом можно понимать некоторое правило (параметр) применения тега. `<img src="/imge.jpg">` - в этом примере тег _img_ применятеся с атрибутом (а иначе и смысоа нет) _src_ значение которого **/image.jpg**

## Базовая структура HTML документа

```html
<!DOCTYPE html>
<html lang="ru">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Window title</>
        <link rel="stylesheet" href="path-to.css">
        <link rel="icon" href="favicon.icon">
        <script type="text/javascript"></script>
        <script src="path-to.js" type="text/javascript"></script>
        <style type="text/css"></style>
    </head>
    <body>
        <!-- begin site content -->
            <!-- start comment directive
            
            end comment directive  -->
        <!-- begin end site content -->
        <script type="text/javascript">
         // inline Java Script code
        </script>
        <script src="path-to.js" type="text/javascript"></script>
    </body>
</html>
```
Тэг `<!DOCTYPE html>` директива браузеру, говорящая что документ использует стандарт **HTML5**, на данный момент это последняя версия стандарта.

Тэг `<html></html>` собственно говорит браузеру _"сейчас будет гипертекст_

Тэг `<head></head>` содержит метаданные для браузера и поисковых систем.

Тэг `<meta></meta>` собственно описание метаданных. `<meta charset="UTF-8">` сообщает браузеру какая кодировка используется на странице. Следующее описание метаданных очень важно.
``` html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```
эта строчка позволяет выполнять медиа запросы, с помощью которых можно применять стили в зависимости от ширины экрана применять к элементам разметки определенные CSS правила.

Тэг `<link>` устанавливает ссылки на ресурсы используемые веб-страницы.

Тэги `<style></style>` и `<script></script>` описывают CSS правила и код JavaScript (JS) соответственно, `<script></script>` может содержать код как в теле (внутри) тега, так и ссылку на файл *.js.

Тэг `<body></body>` собственно содержит разметку которую отобразит браузер пользователю.

## Основные элементы html документа

Тэг `<div></div>` блочный парный тег не имеющий семантического смысла, просто разделяет участки разметки, это один из самых частоиспользуемых тэгов, используемых при разработке клиентской части web-приложения. Для выполнения заданий используйте его для разделения заданий следующим образом `<div class="task-1"></div>`, `<div class="task-2"></div>`, и т. д.

### Заголовки

Теги `h1- h6`, являются блочныпи парными тегами отвечающими за заголовок страницы, цифра уровень заголовка, чем меньше цифра, тем выне уровень заголовка. Тэг `h1` на странице имеет особое значение, для улучшения поиска рекомендуется, чтобы на странице он был и был только один.


> **Задание 1**
> 
> В файле `src/index.html` добавьте заголовки всех шести уровней. _С текстом заголовок n-го уровня_, где n - уровень заголовка прописью.

Тэг `<p>` является блочным парным тэгом используется для размещения текста. Также для оформления текста используются строчные парные теги `<i></i>` - курсив, `<strong></strong>`, `<b></b>` - полужирный, `<tt></tt>` - моноширинный, `<span></span>` - сам по себе есполезен, но в сочетании с CSS позволяет форматировать текст внутри тега как душе угодно. Подробнее об элементах оформления текстом можно узнать [здесь](https://webref.ru/html/type/text). Важно! Теги форматирования текста были придуманы на самой заре появления гипертекста, использовать их в проекте, при верстке страниц - **не рекомендуется**, за исключением тез случаев когда есть достаточные остнования их применять. 

> **Задание 2** 
> 
>Найдите на просторах интернета текст. В файле `src/index.html`  поместите его в тэг `<p></p>`,и или даже в несколько, например поправки в конституцию=). используя строчную цитату вставьте в текст следую щее высказывание:
>> Мы не утописты. Мы знаем, что любой чернорабочий и любая кухарка не способны сейчас же вступить в управление государством. В этом мы согласны и с кадетам, и с Брешковской, и с Церетели. Но мы отличаемся от этих граждан тем, требуем немедленного разрыва с тем предрассудком, будто управлять государством, нести будничную, ежедневную работу управления в состоянии только богатые или из богатых семей взятые чиновники. Мы требуем, чтобы обучение делу государственного управления велось сознательными рабочими и солдатами и чтобы начато оно было немедленно, то есть к обучению этому немедленно начали привлекать всех трудящихся, всю бедноту.
>
> Опционально можно указать автора этого высказывания, а также выделить наиболее важные, как ам кажется слова.
> используя блочную цитату втавьте в текст 
>> Люди всегда были и всегда будут глупенькими жертвами обмана и самообмана в политике, пока они не научатся за любыми нравственными, религиозными, политическими, социальными фразами, заявлениями, обещаниями разыскивать интересы тех или иных классов. Сторонники реформы и улучшений всегда будут одурачиваемы защитниками старого, пока не поймут, что всякое старое учреждение, как бы дико и гнило оно ни казалось, держится силами тех или иных господствующих классов.



### Списки

Для описания списков используются блочные парные теги `<ul></ul>`- маркированнный список, `<ol></ol>` - нумерованный список, `<dl></dl>` -список описаний. Для тегов `ol` и `ul` элемент списка описывается внутри блочного парного тега `<li></li>`, для `dl` все немного по-другому. Нумерованные и макированные списки могут быть включены друг в друга. подробнее о списках можно узнать [здесь](https://webref.ru/html/type/list). 

Важно! Существует заблуждение, что для для верстки однотипных элементов сайта, например пунктов меню, списка преимуществ, основных характеристик и так далее, нужно обязательно использовать списки. Нет, достаточно использовать `div` элементы с указанием класса. Списки нужно использовать только для списков в тексте.

Примеры списка.
```html
Кто ты без костюма?
<ul>
    <li>Гений</li>
    <li>Миллиардер</li>
    <li>Плэйбой</li>
    <li>Филантроп</li>
</ul>
<ol>
    <li>Гений</li>
    <li>Миллиардер</li>
    <li>Плэйбой</li>
    <li>Филантроп</li>
</ol>

<dl>
    <dt>HTML<dt>
    <dd>Hyprttext Mrkup Language</dd>
    <dt>CSS<dt>
    <dd>Cascade Style Sheets</dd>
    <dt>JS<dt>
    <dd>JavaScript - the <del>best</del> programming language in the world </dd>
</dd>
```

> **Задание 3**
> 
>В файле `src/index.html` создайте иерархический список изучаемых вами дисциплин первый уровень иерархии нумерованный список с надписью - "Семестр - n", где n - номер семестра. Второй уровень иерархии маркированный список дисциплин изучаемых в семестре.

>Создайте список терминов (определений) для каждого вида типизации: сильная/ слабая, статическая/динамическая, явная/неявная.

### **Таблицы**
Tэг `<table></table>` блочный парный тэг представляет собой _"точку монтирования"_ таблицы. Тэг `<tr></tr>` блочный парный тэг представляет собой строку таблицы. Тэг `<td></td>`, бочный парный тэг представляте собой ячейку в строке, `<th></th>` технически это тоже ячейка, но используется в _"шапке таблицы"_ пожробнее о таблицах можно узнть [здесь](https://webref.ru/html/type/table). 

Пример описания таблицы.
```html
<table>
    <tr>
        <th>#</th><th>Employee</th><th>Position</th><th>Salary, $</th>
    </tr>
    <tr>
        <td>1</td><td>Lobov A.</td><td> Senior software developer</td><td>100</td>
    </tr>
    <tr>
        <td>2</td><td>Doe J.</td><td> Software developer</td><td>50</td>
    </tr>
    <tr>
        <td>3</td><td>Cartman E.</td><td> DevOps</td><td>90</td>
    </tr>
    <tr>
        <td>4</td><td>Mascon M.</td><td> Project manager</td><td>150</td>
    </tr>
</table>
```
Тэгам `th` и `td` можно устанавливать атрибуты `collspan` и `rowspan`, которые позволяет _"склеивать"_ (объединять) колонки и строки соответственно. Применяется как `collspan="n"`, где n количество объединяемых ячеек начиная с той к которой применен атрибут.

**Важно!!!** _Серьезно важно_. Никогда, не используйте таблицы для позиционирования элементов содержимого страницы. _Но ведь..._ **Никогда!** Даже если очень хочется, но ведь есть сайты которые используют... [(|)](https://www.youtube.com/watch?v=VPDJXngp2bM&feature=youtu.be&t=260). Вот кто использует таблицы для верски сайтов. Использование таблиц аналогично использованию списков, таблицы только для таблиц. Если действительно нужно обеспечить отображение элементов содержимого страницы как таблицу,разумнее использовать CSS стили. Таблицы можно вкладываь ячейки других таблиц.

> **Задание 4**
>
>Сделайте таблицу  отображающую следующие данные:
>- номе по порядку;
>- наименование дисциплины;
>- форма контроля;
>- оценка/отметка;
>- преподаватель.
>
>Сделайте разбивку по семестрам.

### **Изображения и ссылки**

Тэг `<img>` строчный, одиночный тег, испоьзуется для указания ссылки на изобюражение и отображение этого изображения в теле документа. При использованиии этого тега необходимо указать атрибут `src` со значением пути к изображению `<img src="path-to.image-extention">`. Также сопровождаются дополнительными атрибутами `alt` - текст который, отображается в том случае если по указанному пути изображение не найдено и `title` - текст, который отображается при наведении курсора мыши на изображение, очень полезно для поисковой оптимизации.

Тэг `<a></a>` - парный строчный тэг используется для указания ссылки на другую странцу или другой web-ресурс.
```html
 <a href="/about">О сайте</a> <!--Ссслка на раздел текущего сайта-->
 <a href="https://github.com">https://github.com</a> <!--Ссслка на внешний сайт-->
```
> **Задание 5**
>
> В файле `src/index.html` добавьте тег `img` указав ему путь `images/yoda.jpg`. Сделайте это изображение ссылкой на страницу `about.html`. На странице `about.html` сделайте две ссыслки одну на `index.html` вторую на ваш репозиторий в github.

### **Формы**

В силу изначального назначения HTML web-страница _"пассивна"_ то есть она не предполагает обработку действий со стороны пользователя, задача web-страницы предоставить пользователю информацию. Так было долгое время, но все течет, все изменяется. Редактор кода Visual Studio Code, написана на JavaScript и HTML/CSS, серьезно можете в исходники посмотреть. Формы предоставляют возможность обработать данные отправленные пользователем.

Тэг `<form></form>` блочный парный тэг пердставляющий собой точку монтирования формы. Пример разметки формы.
```html
    <form action="/path-to-server-endpoint" method="get">
        <input type="submit" value="Send"> <!--Это кноппка Send, так можно но не стоит, лучше использовать тэг button-->
    </form>
```
Тэг `form` можно использовать для атрибутов `action` `method` в таком случае значением `action` будет считаться путь web-страницы, на которой расположена форма, т. е. если в браузере открыта сраница `http://localhost:8080/feedback`, тогда значение `action` будет `action="/feedback"`. Если не указано значение атрибута `action`, значением будет `action="get"`, эти значения не будут отображены в разметке, но браузер это будет воспринимать именно так. Мое мнение указывать значения атрибутов `action` и `method` является хорошим тоном. Подробно о формах можно узнать [здесь](https://webref.ru/html/type/form). 

Значение атрибута `method` могут быть следующими:

- **post** - отправка данных формы в теле http-запроса, с целью изменения состояния данных в хранилище на серверной части web-приложения;
- **get** - отправка данных формы в строке запроса http-запроса, с целью получения даннх от червера.

Технически можно отправив гет запрос можно извлечь данные из строки запроса и сохранить их в хранилище на серверной стороне однако так делает следующая категория разработчиков
![Люди снежинки](https://ic.pics.livejournal.com/cartmendum/9715553/11571/11571_original.png)

Не надо так, только если иного пути нет.

Основным элементом ввода данных в форме являются:
- `<input>` - одиночный строчный тег, в зависимости от значения атрибута `type` отрисовывается элемент управления подробнее о возможный значениях можно узнать [здесь](https://webref.ru/html/input/type) а заодно поэксперементировать. Важно указывать и значение атрибута `name` это значение также отправляется на сервер, как часть запроса, также важно указывать значение атрибута `value` оно тоже отправляется на сервер как чать запроса.
- `<select></select>` - строчный парный тэг представляющий из себя обычный список выбора. Если необходимо выбрать несколько вариантов в этом списке необходимо указать атрибут `multiple` и атрибут `name` как `variableName[]`или `name="books[]"`, квадратные скобки тонко намекают на массив, если вы понимаете о чем я... В случе когда множественного выбора не требуется то значение атрибута указывается как обчно `name="books"`. Для указания возможный значений используется тэг `<option></option>` В атрибуте `value` указывается значение которое будет отправлено на сервер. Подробнее узнать об этом теге вы можете сами знаете где...
- `<textarea></textarea>` - строчный парный элемент ввода многострочного текста, желательно указывать значение атрибута `rows` указывающего минмальное количество строк текста.

Основными элементами ввода, требующими особого внимния можно отметить `input type="file"` и `<button></button>`
```html
<form action="/path-to-server-endpoint" method="post" enctype="multipart/form-data">
    <input name="photo" type="file">
    <button type="submit">
        <i>Отправить</i><strong>Фото</strong>
    </button>
</form>
```
При отправке файла необходимо  для тега `form` указать атрибут `enctype="multipart/form-data"`, метод обязательно должен быть **post**

Тэг `<button></button>` - строчный парный тег, позволяющий тонко настроить содержимое кнопки. Подробнее о типах кнопки, и особенности каждого из них вы можете узнать... [ну вы поняли...](https://webref.ru/html/button/type)

Тэг `<label></label>` строчный парный тэг позволяющий прикрепить текстовую метку к тэгу ввода данных крайне полезно с тегами типа `<input name="addSugar" value="50" type="checkbox">`, он позволяет связать метку и тег `input`.

```html
 <form action="/path-to-server-endpoint" method="post">
    <label>Адрес
        <input type="text" name="address">
    </label>
    <div>
        <input id="tea" type="radio" name="beverage" checked value="Tea"><label for="tea">Tea</label>
        <input id="cofee" type="radio" name="beverage" value="Cofee"><label for="cofee"></label>
    </div>
    <div>
        <input id="milk" type="checked" name="add" value="10"><label for="milk">Milk</label>
        <input id="sugar" type="checked" name="add" value="5"><label for="sugar">Sugar</label>
        <input id="cream" type="checked" name="add" value="50"><label for="cream">Cream</label>
    </div>
    <div>
        <label>Cash
            <input type="radio" name="beverage" checked value="false">
        </label>
        <label>Bank cark
            <input type="radio" name="beverage" value="true">
        </label>
    </div>
    <div>
        <button type="submit">Order</button>
    </div>
 </form>
```
**Важно!** значения тега _"чекбокс"_ `<input id="milk" type="checked" name="add" value="10">`, если не отмечен ни один чекбокс, сведения об этом поле формы на сервер не передается вообще.

>**Задание 6**
>
>Создайте форму которая содержит следующие поля:
>- Имя;
>- Фамилия;
>- Фото;
>- Пароль;
>- Подтверждение пароля;
>- Город (выбирать из списка), добавить минимум 5 вариантов выбора;
>- Коротко о себе (несколько строк текста);
>- Пол;
>- Любимые дисциплины (выбрать несколько из списка);
>- Планируете поступать в магистратуру (Да/Нет/Не знаю (по умолчанию)) 
>- Что вам нравиться в вашей специальности чекбокс (Люблю компы, Обожаю матан и физику, Перспективы высокой зарплаты, Программы делают жизнь лучше);
>- Предпочитаемые источники информации (Книги/Хабр/Секретный форум в даркнете/YouTube/Спросить у специалиста/У мен я есть специальнообученный раб, который делает все за меня);
>- Кнопка "Сбросить";
>- Кнопака "Пожтвердить";



### **Фреймы**

Фреймы позволяют внедрить в web-страницу другую web-страницу, используется например для вставки видео с YouTube, или сообщения VK или еще что-нибуть. Подробнее о фреймах [здесь](https://webref.ru/html/iframe)

> **Задание 7**
>
>[Вот видяха](https://www.youtube.com/watch?v=VPDJXngp2bM&feature=youtu.be&t=260). Вставьте видяху в файл `src/index.html`.
