# Чеклист верстки

Для того чтобы отдавать вёрстку клиенту, достаточно соблюдения первых 5&nbsp;пунктов. 
Для выдачи в&nbsp;продакшен&nbsp;&mdash; первых 6.

1. **Соответствие макету**
 * https://addons.opera.com/ru/extensions/details/perfectpixel-by-welldonecode/
 * https://addons.mozilla.org/ru/firefox/addon/perfectpixel/
 * https://chrome.google.com/webstore/detail/perfectpixel-by-welldonec/dkaagdgjmgdmbnecmcefdhjekcoceebi?hl=ru.
 
 _Расположение блоков должно быть 1:1 по сравнению с макетом. Допускается расхождение до 5px для текста. Разрешены и даже приветствуются правки размеров и расположения криво нарисованных блоков (разница размерах в 1-2px на разных страницах)._ 

2. **Кроссбраузерность, кодировка и&nbsp;DOCTYPE**
 * Кодировка: UTF-8
 * DOCTYPE: HTML5
 * Валидность:
    * Стили сайта соответствуют стандарту CSS3, за исключением хаков и вендорных свойств.
    * Верстка сайта соответствует стандарту HTML5 за исключением уникальных свойств браузеров и результатов выдачи WYSIWYG-редакторов.
    * Не должно быть JavaScript-ошибок.
    * Сайт корректно отображается в следующих браузерах: Firefox (последний), Chrome (последний), Safari (последний), iPhone (iOS 4.2 и 5.0, landscape, portrait), Android 2.2, Opera (последняя), IE7+, Opera Mini (последняя).
    * Сайт корректно отображается при следующей ширине экрана: 1024, 1152, 1280, 1440, 1680, 1920.
    * У всех шрифтов, используемых на странице, прописаны стандартные Win/Mac/Linux-аналоги и общее семейство (serif, sans-serif, mono и т. д.).
    * Все функции сайта доступны при отключенных изображениях.
    * Основные функции сайта доступны при выключенном JavaScript.
    * Основные функции сайта доступны при выключенном Flash, для Flash-навигации создан аналог без флеша для устройств не поддерживающих Flash (iOS, Android).
    * При увеличении шрифта (через настройки браузера или ОС) страницы не ломаются.
    * Skype-плагин не ломает вёрстку.
    * Ресайз textarea не ломает вёрстку.
    * Для проектов, где это оговорено, проверяется наличие:
      * Версии для печати (она должна быть реализована через css).
      * Мобильной версии (таки тоже должна быть через css).
3. **Валидность (включая CSSLint и JSHint), доступность (ARIA, WCAG), микроформаты (microformats 1 & 2, microdata)**
  * Не должно быть js-ошибок!
  * Проверить валидность титульника
     * Ошибки простительны в следующих случаях: -Секретарша "копипастит" тексты из Word’а в визиг; - Программеру ну очень нужны кастомные атрибуты (хотя для этого в HTML5 ввели специальные пользовательские атрибуты «data-*»).
  * CSS валидируется по версии 3.0, его валидность не требуется, а вот синтаксические ошибки (типа margin: 10xp) исправлять надо.
  * WCAG имеет три уровня сложности, если проходит хотя бы WCAG1 A (Priority 1) – уже хорошо. Идеальный вариант – WCAG2 Priority 3 (AAA). Самый просто способ проверить что скорей всего WCAG1 Priority A соблюдён — www.cynthiasays.com (или addon Web Developer →Инструменты →Проверить WAI).

  * Микроформаты должны быть. Как минимум – hCard. Желательно также hCalendar, XFN, hAtom.
  * Проверка статическими анализаторами качества кода: [CSSLint](http://csslint.net/) и [JSHint](https://jshint.com)
4. **Независимость блоков в&nbsp;CSS: минимизация каскада, использование техник БЭМ**

    _Проверяется в FF через плагин addon Firebug. При наведении на любой блок, в его стилях не должно быть множество перечёркнутых правил. Для минимизации каскада и построения надёжной, современной, масштабируемой вёрстки сейчас применяют следующие техники: БЭМ, MCSS и SMACSS._ 

5. **Сайт должен нормально смотреться во&nbsp;всех стандартных разрешениях от&nbsp;1024 и&nbsp;выше, не&nbsp;иметь горизонтального скролла и&nbsp;вписываться в&nbsp;экран мобильных устройств**
6. Корректная работа при вбивании реального текста, надёжность вёрстки
  * **Перепроверить порядок верстки**

    _Вёрстка должна тянутся, не разваливаться и не терять дизайнерский вид при изменении контента на странице. Его может быть больше или меньше чем на макете, он может быть обёрнут во всякие
из визига и т.п. Обязательно нужно проверять удаление заголовков!_
  * **Проверить введение и удаление данных**

    _Проверяется: на странице с контентом, пробуем добавлять и удалять содержимое – «что будет когда текста много?», «а когда мало?». Обязательно пробовать менять расположение элементов, чтоб после того как ты поменял блоки местами не развалилось оформление._
  * **Удостовериться в корректности работы стилей**

    _Проверяется: на страницы с контентом вбиваем текст с абзацами и без абзацев (важно! бывает горе-верстальщики прописывают стили только для абзацев), со списками и картинками, таблицами и заголовками разных уровней (H1-H6, ul, ol, li, blockquote, pre, table, p)._

7. CSS должен быть написан с&nbsp;использованием препроцессоров (LESS/Sass/Stylus). Желательно использование систем сборки (Grunt/Gulp) и&nbsp;построцессоров (PostCSS/Autoprefixer).
8. Проверка и&nbsp;оптимизация скорости загрузки: https://github.com/ihorzenich/WebPerformanceChecklist
9. Поддержка Retina
10. Наличие Win/Mac/Linux-аналогов шрифтов
11. Доступность при выключенных(загружающихся) картинках
12. HTML5&nbsp;формы, линковка, валидация
13. Семантичность. Отсутствие глупостей в&nbsp;html и&nbsp;css, единообразие, аккуратность (смотри "Плохо/хорошо")
14. Правильная структура заголовков (H1,H2,… и&nbsp;т.д. и&nbsp;TITLE)
15. Работоспособность при выключенном (незагруженном) JavaScript
16. Работоспособность при выключенном Flash
17. Отсутствие багов при увеличенном шрифте

<h2>13. &quot;Плохо&quot;/&quot;Хорошо&quot;</h2>
Важно понимать что семантика&nbsp;&mdash; может быть не&nbsp;только в&nbsp;используемых элементах, но&nbsp;и&nbsp;в&nbsp;именах классов. И&nbsp;БЭМ-иерархия классов&nbsp;&mdash; это новый уровень семантики.

<b>Плохо:</b>
<ul><li><strong>Самое страшное, к&nbsp;счастью уже редкое&nbsp;&mdash; <code>float: left</code> для всех блоков.</strong> Безумный верстальщик эмулирует привычные ячейки таблиц, расставляя блоки как кирпичи друг за&nbsp;другом. Вон из&nbsp;профеcсии!<br/>
Проверяется в extension для браузеров <strong>Web Developer</strong> &rarr; Outline &rarr; Outline Floated Elements, если всё в&nbsp;красных блоках, вёрстку нужно выкидывать на&nbsp;помойку. <br/>
Так же, такая верстка получается при создании сайтов на <strong>Adobe Muse</strong>. <br/>
<strong>Примеры</strong>: <a href="http://www.cardiganium.ru/" target="_blank">один</a> - <a href="http://www.zebraproject.ru/" target="_blank">два</a> - <a href="http://www.jurist-kavykina.ru/" target="_blank">три</a>  
</li>
<li>Отступы между блоками на&nbsp;сайте должны быть за&nbsp;счёт margin у&nbsp;блоков, а&nbsp;не&nbsp;выпирающих наружу margin у&nbsp;содержимого блоков.</li>
<li>Плохо&nbsp;&mdash; отсутствие тайтлов.</li>
<li>Плохо&nbsp;&mdash; отсутствие alt у&nbsp;картинок.</li>
  <li>Плохо&nbsp;&mdash; хаки для браузеров внутри main.css (как без фильтров, так и&nbsp;с&nbsp;ними). Без фильтров&nbsp;&mdash; это когда когда просто пишем <code>{zoom: 1;}</code> — это&nbsp;оч. плохо, т.к. будет применяться ко&nbsp;всем&nbsp;IE, а&nbsp;не&nbsp;только к&nbsp;тому, в&nbsp;котором проблема. С&nbsp;фильтрами&nbsp;&mdash; когда пишут <code>(* html, *+html и т.д.)</code> — плохо, потому что это засоряет код, делает его менее читабельным, а&nbsp;какие-то хаки могут быть и&nbsp;вообще невалидными и&nbsp;нарушать прогон CSSLint. Conditional Comments&nbsp;&mdash; тоже плохо, хотя раньше считалось хорошей техникой, плохо т.к. это увеличение кол-ва css-файлов и&nbsp;главное&nbsp;&mdash; это разнесение кода в&nbsp;разные места. Сейчас рекомендуется использовать специальные классы типа <code>html.ie7, html.ie8,…</code> (из&nbsp;HTML5&nbsp;Boilerplate), Modernizer-детектирование фич (классы вида <code>html.js.flexbox.canvas.no-touch…</code>) и&nbsp;JS-детектирование браузера и&nbsp;платфорым (например CSS Browser Selector генерирующий классы вида <code>html.webkit.chrome.chrome25.win.win8…</code>)</li>
<li>Плохо&nbsp;&mdash; не&nbsp;проверять tabindex в&nbsp;формах.</li>
<li>Плохо&nbsp;&mdash; писать стили не&nbsp;думая о&nbsp;логике размещения элементов. Например, если элемент всегда находится сверху, у&nbsp;него должен быть большой z-index, нельзя надеяться на&nbsp;то&nbsp;что сейчас всё нормально смотрится&nbsp;&mdash; стили должны быть железобетонными. Если элемент всегда должен находится на&nbsp;каком-то месте, в&nbsp;независимости от&nbsp;окружающих его элементов&nbsp;&mdash; это position: absolute; а&nbsp;не&nbsp;float и&nbsp;т.д.
Блоки независящие друг от&nbsp;друга не&nbsp;должны быть внутри одного блока (например телефон компании и&nbsp;поиск по&nbsp;сайту). Блоки независящие по&nbsp;расположению друг от&nbsp;друга должны быть position absolute, а&nbsp;не&nbsp;float&rsquo;ится.</li>
<li>Очень плохо&nbsp;&mdash; презентационные классы (right, red).</li>
<li>Нежелательно когда вёрстка содержит пустые блоки для презентационных целей, для этого существуют псевдоэлементы</li>
<li>Плохо когда нет базовых стилей у&nbsp;стандартных элементов. Т.е. просто h1,h2,ul,table,etc без классов должны смотреться красиво и&nbsp;органично. Проще говоря&nbsp;&mdash; используйте Normalize, a&nbsp;не&nbsp;Reset CSS.</li>
<li>Плохо когда нет постепенного уточнения стилей для текста, когда стиль выписывается для каждого элемента отдельно, а&nbsp;за&nbsp;его пределами&nbsp;&mdash; внешний вид может быть кардинально другой. Речь о&nbsp;ситуации когда например текст, написанный без абзацев, имеет вообще не&nbsp;тот стиль что у&nbsp;всех элементов в&nbsp;блоке. Надо вести стили снизу вверх, постепенно уточняя&nbsp;их. Тут важно не&nbsp;путать стили для текста и&nbsp;стили для блоков. Для текста&nbsp;&mdash; каскад это добро, для блоков сайта&nbsp;&mdash; нужно использовать БЭМ.</li>
<li>Ещё хуже&nbsp;&mdash; чересчур детализированные глобальные стили. Например <code>a {font: italic 10px Tahoma;}</code>. Потом приходится переопределять стиль ссылок для каждого блока.</li>
<li>Размеры и&nbsp;позиционирование элемента должны указываться в&nbsp;одних единицах измерения. Т.е. высота/ширина блока в&nbsp;px&nbsp;и&nbsp;margin/padding в&nbsp;em&nbsp;&mdash; это странно и&nbsp;скорей всего ошибка. Line-height&nbsp;&mdash; лучше задавать коэффициентом (1/1.2/1.4... т.е. без указания единицы измерения&nbsp;&mdash; это цифра на&nbsp;которую умножается font-size и&nbsp;получится межстрочный интервал). Если задали font-size/height в&nbsp;em&nbsp;&mdash; значит задаём и&nbsp;margin/padding тоже в&nbsp;em. Классический пример: список dl-dt-dd, где dt&nbsp;и&nbsp;dd&nbsp;ставятся друг на&nbsp;против друга с&nbsp;помощью подтягивания dd&nbsp;отрицательным margin вверх. Или&nbsp;&mdash; выделили padding&rsquo;ом место под position: absolute какого-то текстового блока. У&nbsp;текстовых элементов (абзацей, ячеек таблиц) задаём padding и&nbsp;height в&nbsp;em (чтоб корректно увеличивать размер шрифта) .</li>
<li><s>Плохо</s>(недопустимо!) вешать стили на&nbsp;селекторы вложенных стандартных тэгов, без классов. Т.е. допустим пишем что-то типа <code>h2&nbsp;a span {какая-то крепкая штука, типа картинки с&nbsp;графикой, что закрывает текст в заголовке}</code>, а&nbsp;потом клиент в&nbsp;визиге внезапно вбивает такое сочетание! И&nbsp;получаем невероятный баг. На просто одиночные теги для вывода текста из БД — можно, но используя блок .b-text (смотри BEM CSS).</li>
<li>Плохо&nbsp;&mdash; напрямую задавать визуальное отображение элементов через&nbsp;js: <code>$('.element').css(color,"#f00")</code>. Это должно делаться через установку/смену классов.</li></ul>

<b>Хорошо:</b>
<ul><li><strong><a href="http://getbem.com/">БЭМ</a></strong>! Важно понимать что это методология, а&nbsp;не&nbsp;инструменты. Для обычных сайтов достаточно вёрстки по&nbsp;<a href="http://delka.github.io/talks/webcamp/2015/bem/">BEM CSS</a>, без использования библиотеки блоков и&nbsp;bem-tools. <a href="http://delka.name/blog/2013/04/bem-otkroveniya-prinyavshih-veru/">Я&nbsp;долго считал что &laquo;BEM&nbsp;&mdash; это классная идея, но&nbsp;это чересчур, так категорично не&nbsp;надо, надо чуть по-другому, под себя...&raquo;</a>, так вот&nbsp;&mdash; это неверно! Нужно обязательно уходить от&nbsp;каскада, а&nbsp;БЭМ&nbsp;&mdash; это один из&nbsp;отличных вариантов решения.</li>
<li>Хорошо&nbsp;&mdash; структурировать код в&nbsp;блоки описывающие логику документа. Т.е. создавать div даже там, где он&nbsp;для презентационных целей не&nbsp;нужен. И&nbsp;наоборот&nbsp;&mdash; стараться не&nbsp;ставить лишний div там, где структура этого не&nbsp;требует, а&nbsp;это нужно лишь для визуальных эффектов.</li>
<li><strong><a href="http://html5boilerplate.com">HTML5 Boilerplate</a></strong>&nbsp;&mdash; замечательный стартовый шаблон от&nbsp;&laquo;отцов&raquo;. Используйте и&nbsp;присоединяйтесь к&nbsp;разработке, добавляйте свои велосипеды туда! 
Раньше у&nbsp;нас был свой самописный framework-стартовый html, теперь используем Boilerplate как основу, а&nbsp;в&nbsp;него уже добавляем старые наработки.</li>
<li>Используйте наработанные решения, чужие модули, jQuery-плагины, не&nbsp;изобретайте велосипедов, а&nbsp;если изобретаете&nbsp;&mdash; поддерживайте&nbsp;их, ведите библиотеку кода (после каждого нового проекта добавляйте туда код, обновляйте старый).</li>
<li>Для текстовых блоков, что редактируются в&nbsp;админке, должна обеспечиваться атомарность текстовых стилей. Т.е. есть у&nbsp;нас страничка с&nbsp;каким-то текстовым блоком, примерно такой структуры:
```css
.content-text h1
.content-text .entry
.content-text .entry .somenamedblock
```
То .somenamedblock должен получать текстовые стили непосредственно&nbsp;&mdash; <code>.somenamedblock {font: …; color: …;}</code>, т.к. иначе в&nbsp;визиге админки мы&nbsp;не&nbsp;сможем их&nbsp;застайлить.</li>
<li>одинаковый html-код для блоков на&nbsp;морде и&nbsp;внутряках, с&nbsp;идентичным контентом, но&nbsp;разным визуальным представлением данных. Реализуется через модификаторы блоков и элементов, но не через модификацию от родителя (каскад от body.pagename например!)</li></ul> 

<h2>Важные мелочи</h2>

<ul><li>Лого на&nbsp;внутряках должно вести на&nbsp;титулку. На&nbsp;титулке logo = h1, на&nbsp;внутряках H1=заголовок контента, а&nbsp;Logo=div</li>
  <li>У&nbsp;каждой страницы должен быть свой уникальный TITLE формата <code>About Us&nbsp;&mdash; %CompanyName%</code></li>
  <li>Все страницы должны быть слинкованы и&nbsp;<a href="http://home.snafu.de/tilman/xenulink.html">проверены на&nbsp;наличие битых ссылок</a>.</li>
  <li>Все ссылки должны как-то реагировать на :hover, :active и :focus&nbsp;&mdash; показыванием/убиранием подчёркивания, сменой цвета, чем угодно. У&nbsp;всех ссылок, кроме пунктов меню, должна быть реакция на :visited</li>
  <li>Проверять что все интерактивные элементы страницы что должны работать&nbsp;&mdash; работают.</li>
  <li>&laquo;Контент в&nbsp;начале страницы&raquo;&nbsp;&mdash; содержимое страницы должно идти в&nbsp;начале кода, до&nbsp;всяких сайдбаров и&nbsp;прочего.</li>
  <li>Все созданные странички изначально должны быть порезаны на шаблоны, чтоб программеру было легче их интегрировать.</li>
  <li><a href="http://habrahabr.ru/blogs/typography/23812/">Копирайт должен быть написан правильно</a>.</li>
  <li>Должны быть favicon.ico (желательно с&nbsp;включенными внутрь неё 32&times;32, 48&times;48 и&nbsp;64&times;64&nbsp;вариациями) и&nbsp;apple-touch-icon</li>
  <li>В&nbsp;вёрстке не&nbsp;должны оставаться закомментированные &laquo;на&nbsp;всякий случай&raquo; куски кода, лишние неиспользуемые файлы, старые версии файлов и&nbsp;т.п. Все бекапы можно вытянуть из&nbsp;системы контроля версий (например Git или SVN), а&nbsp;на&nbsp;живом проекте &laquo;мусор&raquo; потом мешает разобраться как что работает.</li>
  <li>Размеры для блоков, чьи размеры зависят от&nbsp;содержащегося в&nbsp;них текста, нужно задавать в&nbsp;em, а&nbsp;не&nbsp;px.</li>
  <li>Если url ссылки неизвестен, то&nbsp;он&nbsp;должен быть равен её&nbsp;анкору, написанному латиницей с&nbsp;заменой пробелов/спецсимволов на&nbsp;тире.</li>
  <li>Skype-плагин не&nbsp;должен ломать вёрстку</li>
  <li>Ресайз textarea не&nbsp;должен ломать вёрстку</li>
  <li>При проверке frontend в&nbsp;целом&nbsp;&mdash; 404-страница должна отдаваться с&nbsp;кодом 404&nbsp;а не&nbsp;200.</li>
  <li>Нужно подстраховываться фиксируя в&nbsp;css размеры картинок, выводящихся программно.</li>
  <li>Проверка орфографии Word&rsquo;ом или <a href="http://www.artlebedev.ru/tools/orfograf/">Орфографом</a>, желательно&nbsp;&mdash; <a href="http://www.artlebedev.ru/tools/typograf/">оттипографить</a> контент.</li>
  <li>Ссылки на&nbsp;чужие сайты должны быть с&nbsp;<code>target="_blank"</code>, желательно выделять их&nbsp;иконкой &laquo;внешняя ссылка&raquo;.</li>
  <li>Разумеется картинки должны быть в&nbsp;отдельной папке, css&nbsp;&mdash; в&nbsp;отдельной и&nbsp;js&nbsp;&mdash; в&nbsp;отдельной. Графика, не являющаяся частью дизайна (всякие илююстрации, фото в новостях и т.д.) — нужно положить в отдельную папку, например userfiles.</li>
  <li>Изображения должны масштабироваться в зависимости от размера окна <code>(max-width:100%; height:auto;)</code></li>
</ul>
