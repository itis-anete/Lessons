# Лекция №11
 - ASP.NET MVC
   - Передача данных через HTTP
     - Тип кодирования
       - application/x-www-form-urlencoded
       - multipart/form-data
       - text/plain
       - application/json
   - Структура протокола HTTP
     - Стартовая строка
     - Заголовок
     - Тело запроса
   - Привязка данных к модели
   - Типы данных
     - Маршрут
     - Форма
     - Строка запроса
   - Неявное управление привязкой модели
     - [BindRequired]
     - [BindNever]
     - [FromHeader]
     - [FromQuery]
     - [FromRoute]
     - [FromForm]
     - [FromServices]
     - [FromBody]
     - [ModelBinder]
   - Глобальное управление привязкой модели
     - Форматтер сериализации
   - Определение значения
     - IValueProvider
     - IValueProviderFactory
   - Связывание значений
     - IModelBinder
     - IModelBinderProvider
     
   
# Доп. материалы №1
http://www.techbloginterview.com/wp-content/uploads/2018/04/Screen-Shot-2018-04-14-at-10.37.30-PM.png
![MVC](http://www.techbloginterview.com/wp-content/uploads/2018/04/Screen-Shot-2018-04-14-at-10.37.30-PM.png "ASP.NET MVC .Net Core lifecycle ")

#Доп. материалы №2
## Запрос:
```GET /wiki/страница HTTP/1.1
Host: ru.wikipedia.org
User-Agent: Mozilla/5.0 (X11; U; Linux i686; ru; rv:1.9b5) Gecko/2008050509 Firefox/3.0b5
Accept: text/html
Connection: close
(пустая строка)
```

## Ответ:
```HTTP/1.1 200 OK
Date: Wed, 11 Feb 2009 11:20:59 GMT
Server: Apache
X-Powered-By: PHP/5.2.4-2ubuntu5wm1
Last-Modified: Wed, 11 Feb 2009 11:20:59 GMT
Content-Language: ru
Content-Type: text/html; charset=utf-8
Content-Length: 1234
Connection: close
(пустая строка)
(запрошенная страница в HTML)
```
