## WebCore

* [Общие вопросы](General/README.md)
* [Web Technologies](WebTech/README.md)
* [CSS](CSS/README.md)
* [Ещё CSS](CSSfaq/README.md)
* [Web API](WebAPI/README.md)
* [HTML](HTML/README.md)
  
**CORS** (Cross-Origin Resource Sharing, англ. «совместное использование ресурсов разных источников»)
  
стандарт, позволяющий предоставлять веб-страницам доступ к объектам сторонних интернет-ресурсов. Сторонним считается любой интернет-ресурс, который отличается от запрашиваемого протоколом, доменом или портом.  
механизм использует дополнительные HTTP-заголовки.  
С ним браузер пользователя получает разрешения на доступ к выбранным ресурсам, если домен сайта и домен запрашиваемого ресурса отличаются.  
[CORS](https://github.com/AntonGitCode/FEFAQ/blob/master/General/16.md)  
    
**REST**
  
**OSI** [читать](https://github.com/AntonGitCode/FEFAQ/blob/master/WebTech/README.md#osi)

**прогрессивный рендер** [читать](https://github.com/AntonGitCode/FEFAQ/blob/master/WebTech/README.md#prorender)   
  **прогрессивные SSR** [читать](https://github.com/AntonGitCode/FEFAQ/blob/master/WebTech/README.md#ssr)  

**веб-компоненты** - переисп комп ,с брауз напрямую без исп библ [читать](https://github.com/AntonGitCode/FEFAQ/blob/master/WebTech/README.md#webcomp)  
**Поток** - это принцип организации элементов на странице, при отсутствии стилей - [читать](https://github.com/AntonGitCode/FEFAQ/blob/master/WebTech/README.md#potok)  

**ARIA** [читать](https://github.com/AntonGitCode/FEFAQ/blob/master/General/14.md)  
   
 [Richardson](https://github.com/AntonGitCode/FEFAQ/blob/master/WebTech/README.md#richardson)
   
**6 принципов REST**:  
  - Клиент-серверная архитектура - - п добиться масштабируемости.
  - Stateless - сервер не хранит инфу о сессии клиента
  - Кэширование - сервер при след запросе клиента выдаст из кэша (идемпотентность)
  - Единообразие интерфейса - Hypermedia as the Engine of Application State - одно из ограничений REST- сервер возвращает не только ресурс, но и его связи с другими ресурсами и действия, которые можно с ним совершить.
  - Layered system - ни клиент, ни сервер не должны знать о том, как происходит цепочка вызовов дальше своих прямых соседей.
  - Code on demand - Идея передачи некоторого исполняемого кода от сервера клиенту.

**Critical Rendering**  

`Парсинг HTML и создание DOM`  
`DOM` - ответы в виде HTML превращаются в токены, которые в свою очередь превращаются в узлы и в последующем формируют DOM дерево.  
`CSSOM` - все данные о том как стилизовать DOM.  
`JavaScript` - загрузка всех скриптов.  
`Accessibility Tree` - при парсинге HTML, анализируются специальные атрибуты по типу role и aria.  
`Render Tree` - Соединение DOM и CSSOM.  
Layout/Reflow - это процесс определения размеров и позиций всех элементов на странице, а также их отношений друг к другу. Это происходит на основе CSS-правил и содержимого страницы.  
`Paint/Repaint` - это процесс рендеринга элементов на странице. Он включает в себя применение цветов, текстур, градиентов и других стилей к элементам.  
`Compositing` - это процесс объединения всех элементов на странице в одно изображение. Каждый элемент имеет свою прозрачность и слои, которые могут быть объединены в одно изображение для отображения на экране. Это происходит с помощью графического процессора  
  
<br>
<img src="https://github.com/AntonGitCode/FEFAQ/assets/117078390/3b9051ae-c74e-4aff-8979-fb766b8260c8" alt="Image Description" width="550">  


## JS  

* [Вопросы по JavaScript](JavaScript/README.md)
* [Вопросы по тестированию](Testing/README.md)
* [Вопросы по производительности](Performance/README.md)
* [Вопросы по сетям](Network/README.md)
* [Примеры кода на JavaScript](Coding/README.md)
