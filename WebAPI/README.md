<h3>
  <img src="../assets/WWW.png" width="16" height="16" />
  <span>Web API:</span>
</h3>

- [Что такое `HTTP`?](1.md)
- [Из чего состоит `HTTP`-запрос?](1.md)
- [Какие методы может иметь `HTTP`-запрос?](1.md)
- [Что такое `HTTP` cookie? Для чего они используются?](2.md)
- [Разница между `HTTP` и `HTTPS`?](3.md)
- [Разница между `HTTP/1`  и `HTTP/2`?](3.md)
- [Как работает мультиплексирование в `HTTP/2`?](3.md)
- [Что такое “трехстороннее рукопожатие” (Triple handshake)?](4.md)
- [Разница между `PUT`- и `POST`-запросами?](5.md)
- [Разница между протоколами `TCP` и `UDP`?](5.md)
- [Что такое `WebSocket`? В чем принцип его работы?](6.md)
- [Разница между Long-Polling, Websockets и Server-Sent Events?](7.md)
- [Как работает `JSONP`?](8.md)
- [Что такое IndexedDB в браузере? Преимущества IndexedDB?](9.md)
- [Что такое Service Workers?](10.md)
- [Что такое Web Workers?](11.md)
- [Что такое Web Worklet?](12.md)
- [Что такое `SSL`/`TLS`? Зачем они используются в веб-разработке?](121.md)
- [Механизм установки сеанса между клиентом и сервером?](14.md)
- [Что Такое API?](15.md)
- [Что такое CDN?](15.md)
- [Что такое IP-адрес?](ip.md)
- [Разница между host и domain?](15.md)
- [Разница между URI и URL?](16.md)
- [Почему очищать кэш важно? Как это можно сделать?](https://thecode.media/cache/)
- [Разница между идентификацией, аутентификацией, авторизацией?](17.md)
- [Виды аутентификации?](auth.md)
- [Что такое безопасные (Secure) и HttpOnly cookies?](18.md)
- [Что такое Content Security Policy (CSP)?](19.md)
- [Что такое CORS?](20.md)
- [Что такое межсайтовый скриптинг (XSS)?](21.md)
- [Методы повышения безопасности веб-приложений?](secur.md)
- [Что такое OWASP Top 10?](22.md)

### Что означает CORS и какую проблему решает?  

**CORS (Cross-Origin Resource Sharing, англ. «совместное использование ресурсов разных источников») — это стандарт, позволяющий предоставлять веб-страницам доступ к объектам сторонних интернет-ресурсов. Сторонним считается любой интернет-ресурс, который отличается от запрашиваемого протоколом, доменом или портом.**  

  Этот **механизм использует дополнительные HTTP-заголовки**.    
С ним **браузер пользователя получает разрешения на доступ к выбранным ресурсам, если домен сайта и домен запрашиваемого ресурса отличаются.**  
  
**CORS** предоставляет веб-серверам возможность контролировать междоменные запросы и позволяет производить безопасный обмен данными между разными доменами.  

```

```
**По умолчанию в браузере действует политика безопасности Same Origin Policy**.  
Это означает, что доступ к ресурсам можно получить, только **если источник этих ресурсов и источник запроса совпадают**.  
Основной концепцией здесь является происхождение — триплет домен/порт/протокол.  
  
Со временем разработчики поняли, что хотят уметь отправлять данные на сервер и получать их при помощи асинхронных запросов. Но политика Same Origin не позволяет сделать этого. После долгих обсуждений был предложен механизм CORS — **Cross-Origin Resource Sharing**.  CORS появился с целью смягчения политики одинакового источника и для тонкой настройки доступа между различными источниками.  

тэги делятся:    
  1. **Вставки** из разных источников — это теги, загружаемые через ```<script>```, ```<link>```, ```<img>```, ```<video>```, ```<audio>```, ```<object>```, ```<embed>```, ```<iframe>``` и т.п. Все они разрешены по умолчанию.  
  2. **Считывание** - это теги, загружаемые через вызовы AJAX/ fetch 
  3. **Запись**

**Предварительные запросы** (OPTIONS) выполняются перед запросами, которые CORS считает **сложными запросами**.  
Признаки, свидетельствующие о сложности запроса:

  1. Запрос использует методы отличные от GET, POST, или HEAD  
  2. Запрос включает заголовки отличные от Accept, Accept-Language или Content-Language  
  3. Запрос имеет значение заголовка Content-Type отличное от application/x-www-form-urlencoded, multipart/form-data, или text/plain.  
  
```
GET /request
Host: anywhere.com
Origin: https://javascript.info
```
  
Сервер может проверить **Origin** и, если он согласен принять такой запрос, добавить в ответ специальный заголовок **Access-Control-Allow-Origin**     
  
```
200 OK
Content-Type:text/html; charset=UTF-8  
Content-Length: 12345  
Content-Encoding: gzip  
API-Key: 2c9de507f2c54aa1  
Access-Control-Allow-Origin: https://javascript.info  
Access-Control-Expose-Headers: Content-Encoding,API-Key  
```

Механизм CORS используется как более защищенная альтернатива технологии JSONP, так как позволяет использовать все преимущества xml-запросов через http, и является неуязвимым для внедрения в запрос стороннего кода (SQL-инъекций).  

<h2>Механизм установки соединения между клиентом и сервером</h2>  
  
1. Клиент и сервер начинают процесс обмена информацией. Клиент отправляет запрос на соединение с сервером.
2. Cервер отвечает клиенту с помощью пары ключей: открытый и закрытый ключи. Открытый ключ является общедоступным, а закрытый ключ известен только серверу.
3. Клиент проверяет подлинность сертификата сервера, который содержит открытый ключ сервера. Сертификат предоставляется доверенным сторонним центром сертификации (Certificate Authority) и содержит информацию о сервере, а также цифровую подпись, подтверждающую подлинность сертификата.
4. Если клиент доверяет сертификату сервера, он генерирует случайный ключ (session key), который будет использоваться для симметричного шифрования данных во время сеанса.
5. Клиент использует открытый ключ сервера для зашифровки сессионного ключа и отправляет его на сервер.
6. Сервер использует свой закрытый ключ для расшифровки сессионного ключа, получает его и сохраняет на сеансе.

Теперь клиент и сервер имеют общий секретный сессионный ключ, который используется для шифрования и расшифровки данных во время сеанса. Это обеспечивает конфиденциальность передаваемых данных.

Клиент и сервер свободно обмениваются зашифрованными данными во время сеанса, используя сессионный ключ для шифрования и расшифровки.

<h2>Websocket</h2>
  
это **протокол связи между клиентом и сервером**, который позволяет устанавливать постоянное двустороннее соединение между ними, и обмениваться данными друг с другом в режиме реального времени **без необходимости создавать новые HTTP-запросы для каждого обновления**.  

<h2>Web Workers</h2>  

 **Web Workers** - это механизм, который позволяет  
 **запускать скрипты JavaScript в отдельном потоке, отличном от основного потока выполнения веб-страницы**.  
 **не блокируя пользовательский интерфейс**.  

<h2>Service Workers</h2>  

**это сценарии JavaScript, которые   
выполняются в фоновом режиме и отвечают за обработку событий и выполнение задач веб-приложения, даже  
КОГДА само ПРИЛОЖЕНИЕ ЗАКРЫТО ИЛИ НЕАКТИВНО**.   
  
  могут использоваться для кэширования данных, обработки уведомлений, оффлайн-работы и других функций. 
  **полностью асинхронный**; как следствие, синхронные API, такие как XHR и localStorage, в Service Worker'е использовать нельзя.
  работают только по HTTPS

  
![image](https://github.com/AntonGitCode/FEFAQ/assets/117078390/37410ae2-d2ff-4ca7-a753-23aeae7f0ab5)
