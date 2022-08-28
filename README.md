# Дипломный проект "Интернет-магазин"

## Цель проекта

Отработка знаний, полученных в ходе прохождения курса и самостоятельное применение отдельных навыков при разработке интернет-магазин спортивного снаряжения на базе 1С-Битрикс.
Реализация клиентской и административной части интернет-магазина

Вам предстоит:
- разработать интернет-магазин спортивного снаряжения
- спроектировать и реализовать каталог товаров
- настроить способы оплаты и доставки, а также оформление заказа

------

## Чеклист готовности к работе над проектом

У вас должен быть установлено:
- [x] Веб-сервер Apache соответствующий требованиям bitrix_server_test.php
- [x] MySQL 5.6 и выше
- [x] PHP 7.4
- [x] 1С-Битрикс: Управление сайтом (БУС) 
- [x] Редактор кода, с которым работаете
- [x] GIT и создан аккаунт на Github.


Если все этапы чеклиста пройдены, то можете смело приступать к работе над проектом. Успехов в работе!

## Описание проекта

Вам нужно разработать интернет-магазин GO&RIDE, который продаёт велосипеды и аксессуары для них.

### Структура сайта
В магазине обязательно должны быть следующие страницы и разделы:
1. Главная страница
2. Каталог, состоящий из страниц разделов и детальных карточек товаров
3. Страница корзины
4. Страница оформления заказа
5. Страница Контакты с формой обратной связи
6. Страница Поиска, а также форма поиска интегрированная в шаблон сайта
7. Раздел Личного кабинета покупателя, содержащий стандартные страницы из тиражного решения 1С-Битрикс: Управление сайтом. Современный интернет-магазин
8. Раздел Отзывы, состоящий из страницы со списком отзывов и детальной страницей отзыва — используйте элементы вёрстки из карточки товара

### Структура каталога
Структура каталога должна поддерживать вложенность. 
В рамках дипломного проекта необходимо создать следующую структуру:
* велосипеды
	* горные
	* городские
	* гоночные
	* гибридные
* одежда
* аксессуары
* обувь
* снаряжение
* распродажа

Важно! Распродажа — это отдельный раздел каталога. Один и тот же элемент может находиться сразу в нескольких разделах, в том числе, в обычном разделе и в распродаже.

### Настройки магазина
Заказы на сумму свыше 7000 рублей доставляются бесплатно независимо от адреса доставки и выбранного способа доставки.
Стоимость доставки Почтой России составляет 300 рублей для заказов весом до 3 кг (включительно). Доставкой Почтой России заказов свыше 3 кг стоит 500 рублей.
Для заказов весом свыше 20 кг действуют индивидуальные правила доставки, которые рассчитываются менеджером.

Магазин работает, как с физическими лицами, так и с организациями (юридические лица и ИП). 
Организации могут оплачивать заказ по безналу, для них сразу после оформления заказа формируется счет.
Физические лица могут оплатить заказ наличными при получении, если заказ доставляется курьером.
Для заказов, доставляемых Почтой России, можно выбрать оплату Наложенным платежом, при этом стоимость заказа увеличится на 5%.
Для всех типов покупателей действует оплата банковской картой. Карты принимаются через сервис ЮKassa. При выполнении задания достаточно будет завести соответствующий способ оплаты и выбрать подходящий обработчик. Полностью настраивать подключение к Яндексу не требуется.

В магазине действуют скидки:
1. 5% на товары из категории Распродажа
2. 2% для зарегистрированных пользователей

Посетители могут подписаться на новости магазина и будут получать соответствующую рассылку.

### Шаблон сайта
Внешний вид страниц определяется предоставленным макетом (каталог bicycle-main на github). 
Главная страница (index.html), страница с разделами каталога (catalog.html), страница со списком товаров раздела (section.html) и детальная карточка товара (product.html) должны быть свёрстаны в соответствии с макетом.

Нужно разработать 3 шаблона: главная страница (макет index.html), карточка товара (макет product.html), основной внутренний (макет catalog.html).
 
Для страниц корзина, оформление заказа, личный кабинет покупателя используется основной внутренний шаблон, как для других внутренних страниц сайта, при этом шаблоны компонентов можно использовать стандартные из решения Интернет-магазин.

На страницу со списком товаров раздела (section.html) необходимо добавить компонент горизонтального умного фильтра со стандартным шаблоном.

Важно! Если в каком-то блоке нет данных, то блок не должен отображаться на странице (в том числе заголовок блока)

#### Шапка
Шапка содержит 
* логотип (включаемая область из файла), 
* меню (пункты и внешний вид меню зависят от шаблона), 
* форму быстрого поиска, 
* ссылку (иконку) для перехода на страницу личного кабинета, 
* ссылку (иконку) для перехода на страницу корзины
* в шаблоне внутренних страниц — цепочку навигации (см. section.html)

#### Подвал
Подвал содержит 
* меню, 
* форму подписки (управление подписками осуществляется из личного кабинета пользователя, стандартная страница), 
* ссылки для перехода к аккаунтам соц.сетей (включаемая область из файла), 
* год и копирайт (включаемая область из файла, год выводится текущий при помощи php-функции).

#### Главная страница
Рабочая область главной страницы содержит:
* Блок популярные товары — товары, которые отмечены галочкой Популярные, могут быть из любых разделов
* Баннер "По городу" — нужно подготовить сниппет для визуального редактора, чтобы контент-менеджер мог заменять данный элемент страницы
* Городские велосипеды — рекламный слайдер, в котором выводятся активные элементы из отдельного инфоблока Слайдер. У каждого элемента будет своя картинка, текст анонса, текст кнопки, ссылка для кнопки. Ссылка может вести как на другую страницу сайта, так и на внешние сайты
* Скидка 5% — выводится изображение одного случайного элемента из раздела Распродажа.
* Уже просмотрели — слайдер с товарами ранее просмотренными пользователем. Если таких товаров нет, то блок не должен отображаться на странице

#### Страница с разделами каталога (главная страница каталога)
Рабочая область содержит:
* Скидка 5% — выводится изображение одного случайного элемента из раздела Распродажа.
* Список остальных разделов со слайдером товаров внутри раздела, кроме раздела Распродажа. Какой раздел будет исключен из вывода, указывается в параметрах компонента (доработайте шаблон компонента соответствующим образом). По клику на заголовок происходит переход на страницу раздела. По клику на товар происходит переход на страницу товара.
* Блок Просмотренные выводится после второго по счету раздела
* Блок Распродажа выводится перед последним разделом

#### Страница со списком товаров раздела (страница раздела каталога)
Рабочая область содержит:
* Компонент умный фильтр со стандартным шаблоном
* Плитки с товарами раздела по 5 элементов в ряду. У каждого элемента есть название, цена, изображение, свойство, кнопка перехода в детальную карточку товара
* Блок Распродажа — выводятся элементы, которые привязаны одновременно к текущему разделу, а также к разделу Распродажа. Если таких элементов нет, блок не должен отображаться

#### Карточка товара
Для данной страницы используется отдельный шаблон product.html
* основное изображение товара
* характеристики товара для добавления в корзину: цвет, размер, отметка о наличии, цена, кнопка для добавления в корзину
* дополнительные изображения товара выводятся в один вертикальный блок слева от описания и характеристик
* справа от изображений выводятся 
	* краткое описание товара
	* свойства товара (выбираются в параметрах компонента)
	* полное описание товара
* под этим блоком выводятся элементы инфоблока Отзывы, ссылка под отзывами ведёт на страницу со списком отзывов

#### Корзина, Оформление заказа, Личный кабинет, Подписка, Поиск
Используются стандартные страницы из решения Интернет-магазин. Необходимо подключить к этим страницам шаблон, а также выполнить все необходимые настройки ссылок и других элементов (см. настройки магазина)


## Инструкция к выполнению
1. Установите 1С-Битрикс: Управление сайтом, редакция Бизнес, решение Современный интернет-магазин Одежды
2. Создайте необходимые инфоблоки
3. Отредактируйте структуру сайта (файлы и разделы)
4. Разместите компоненты на страницах
5. Создайте шаблоны сайта и настройте правила их подключения (для детальной, для главной, для всех страниц)
6. Создайте шаблоны компонентов
7. Настройте интернет магазин: типы плательщиков, способы доставки и оплаты
6. Протестируйте, что всё работает

## Правила сдачи работы
При сдаче укажите адрес вашего дипломного сайта и логин/пароль для администратора магазина.

## Критерии оценки
1. Структура сайта соответствует заданию.
2. Заведены все необходимые инфоблоки, в них созданы элементы и разделы (по необходимости), корректно настроены права доступа.
3. Созданы и корректно настроены (соответствуют страницам) шаблоны сайта.
4. Вёрстка шаблонов соответствует предоставленной, на всех указанных страницах шаблоны стандартных компонентов заменены на вёрстку из макетов.
5. Добавлено необходимое количество тестового контента.
6. Выполнены настройки интернет-магазина.
7. Интернет-магазин корректно отображается для пользователей и администраторов сайта. При включении режима Правки вёрстка сохраняется, страница не разваливается.
8. Если в каком-то разделе нет контента, раздел не выводится (нет висящих заголовков и пустых блоков).