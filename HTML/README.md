## Вопросы по HTML

* [Для чего нужен doctype?](1.md)
* [section и article](#secart)
* [как подлкючать скрипты?](#scr)
* DomContentLoaded
* iframe
* [Как следует оформлять страницу, содержимое которой может быть на разных языках?](2.md)
* [На что необходимо обратить внимание при разработке мультиязычных сайтов?](3.md)
* [Для чего нужны атрибуты, начинающиеся с data-?](4.md)
* [Представьте HTML5 как открытую веб-платформу. Из каких блоков состоит HTML5?](5.md)
* [Объясните разницу между cookie, sessionStorage и localStorage.](6.md)
* [Объясните разницу между `<script>`, `<script async>` и `<script defer>`.](7.md)
* [Почему хорошей практикой считается располагать `<link>` для подключения CSS между `<head></head>`, а `<script>` для подключения JS ставить перед </body>? Знаете ли вы исключения?](8.md)
* [Что такое прогрессивная отрисовка?](9.md)
* [Для чего используется атрибут srcset в теге изображения? Опишите процесс, который использует браузер при оценке содержимого этого атрибута.](10.md)
* [Приходилось ли вам работать с языками HTML-шаблонизации?](11.md)


article можем сделать независимым и переиспользовать.

инлайновый стиль можно переопределить с помощью !important

<h2>как подключить скрипты</h2>

```html
<script src="">
<link rel="stylesheet">
<import>
<include>

// подключение документов
<head>
  <link rel="import" href="/path/to/imports/stuff.html">
</head>
```

**import**  
  
```html
import defaultExport from "module-name";
import * as name from "module-name";
import { export } from "module-name";
import { export as alias } from "module-name";
import { export1 , export2 } from "module-name";
import { export1 , export2 as alias2 , […] } from "module-name";
import defaultExport, { export [ , […] ] } from "module-name";
import defaultExport, * as name from "module-name";
import "module-name";
import("/module-name.js").then(module => {…}) // Динамический импорт  
```
_Примечание: браузеры игнорируют повторные запросы на один и тот же URL. Это значит, что из одного адреса будет выполнена только одна загрузка сколько бы ни было подключений на странице_  

_Tree Shaking_ - удаление мертвого кода, на динамич импортах-экспортах. в вебпаке автоматом  
  
<h2>async vs defer</h2>

<h2>iframe</h2> 

внутри открыть другой html документ
небезопасно, потому что можно закинуть скрипты
как избежать этого? можно использовать экранирование одних символов безопасными. 
CSP content security policy

## виды инпутов  

type дефолтно text
- `radio`
- `checkbox`
- `emal` , `number`
- `submit`: Кнопка для отправления формы
- `checked`
- `pattern` - прописать маску в виде регулярки
- `placeholder`

<textarea> - многострочный инпут  
  
## form  

Формы в документе входят в специальную коллекцию `document.forms`  
  
Элементы формы 

```html
input.value = "Новое значение";  
textarea.value = "Новый текст";  

```

## жизненный цикл HTML-страницы  

**DOMContentLoaded** – браузер полностью загрузил HTML, было построено DOM-дерево, но внешние ресурсы, такие как картинки <img> и стили, могут быть ещё не загружены.  
**load** – браузер загрузил HTML и внешние ресурсы (картинки, стили и т.д.).  
**beforeunload/unload** – пользователь покидает страницу.  

    





