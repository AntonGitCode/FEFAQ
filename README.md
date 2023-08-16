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

<br>
<img src="https://github.com/AntonGitCode/FEFAQ/assets/117078390/3b9051ae-c74e-4aff-8979-fb766b8260c8" alt="Image Description" width="550">  


## JS  

* [Вопросы по JavaScript](JavaScript/README.md)
* [Вопросы по тестированию](Testing/README.md)
* [Вопросы по производительности](Performance/README.md)
* [Вопросы по сетям](Network/README.md)
* [Примеры кода на JavaScript](Coding/README.md)
