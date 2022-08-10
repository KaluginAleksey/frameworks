# Современные фреймворки на PHP

## 2. Роутинг. Контроллеры.

1. Подготовьте тестовый контроллер и маршрут до него, чтобы продемонстрировать работу роутинга , контроллера и объекта-запроса в фреймворке.
   #### Laravel
   https://github.com/KaluginAleksey/laravel/blob/lesson2/app/Http/Controllers/TestController.php
   
   #### Symfony
   https://github.com/KaluginAleksey/symfony/blob/lesson2/src/Controller/TestController.php
   
2. Еще раз самостоятельно прочтите документацию и _middleware_ в _Laravel_
3. Добавьте к своему проекту на _Laravel middleware_, реализующий следующую логику:
   https://github.com/KaluginAleksey/laravel/blob/lesson2/app/Http/Middleware/CheckIsAdmin.php

   1. ЕСЛИ в запросе от клиента присутствует заголовок _**X-UserName**_ И значение этого заголовка _**"admin"**_
   ТО проверить наличие заголовка _**X-Password**_
   И ЕСЛИ в нём содержится хэш пароля _**"123456"**_
   ТО продолжить работу
   2. ИНАЧЕ выдать статус _**401**_ и прекратить обработку запроса
4. \* Попробуйте реализовать аналогичную логику в _Symfony_

В Symfony реализовал похожую логику через EventDispatcher
https://symfony.com/doc/current/event_dispatcher/before_after_filters.html

https://github.com/KaluginAleksey/symfony/blob/lesson2/src/EventSubscriber/TokenSubscriber.php
