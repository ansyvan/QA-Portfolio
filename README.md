# PyTest-Tutorial

<h1>Проєктне завдання 1</h1>

Створити структуру папок і файлів фреймворка.

1. В склонованому з GiHub репозиторії (це той репозиторій, який ви клонували, виконуючи блок лекцій по GIT) створити наступну ієрархію файлі і папок, що ми будемо вважати початково стуктурою фреймворка:

Структура папок від кореневої директорії проєкта:

/config
/modules
/modules/common
/modules/ui
/modules/ui/page_objects
/modules/api
/modules/api/clients
/tests
/tests/ui
/tests/api

Структура файлів від кореневої директорії проєкта:

/config/config.py
modules/common/__init__.py
/modules/ui/page_objects/__init__.py
/modules/api/clients/__init__.py
/tests/ui/test_ui.py
/tests/api/test_api.py

2. Всі створені, змінені та видалені файли додати до коміта і відправити на сервер GitHub за допомогою команди git push

<h1>Проєктне завдання 2</h1>

Розробити тести за допомогою модуля pytest, використовуючи фікстури і мітки

В склонованому з GiHub репозиторії (це той репозиторій, який ви клонували, виконуючи блок лекцій по GIT), використовуючи результати попереднього модуля, розробити тести за допомогою модуля pytest, які відповідають наступним вимогам:

1. Мітки check та change зареєстровані в файлі pytest.ini
2. В файлі conftest.py описати клас User:
  - За допомогою конструктора задати поля name та second_name зі значеннями за замовчування None
  - Клас має метод об’єкта “створити” (create). Метод задає полям name та second_name значення вашого імені та прізвища
  - Клас має метод об’єкта “видалити” (remove). Метод задає полям name та second_name значення пустого рядка
  - В файлі conftest.py описати фікстуру user. Ця фікстура:
3. Створює об’єкт класа User
  - Викликає метод об’єкту create
  - Повертає об’єкт після виклику методу об’єкту create в тести
  - Після виконання тесту викликає метод об’єкту remove
4. В файлі /tests/api/test_fixtures.py створити тест test_change_name:
  - Тест має мітку check
  - Використовує фікстуру user
  - Перевіряє, що поле name об’єкту user відповідає очікуваному
5. В файлі /tests/api/test_fixtures.py створити тест test_change_second_name:
  - Тест має мітку check
  - Використовує фікстуру user
  - Перевіряє, що поле second_name об’єкту user відповідає очікуваному
6. В файлі /tests/api/test_api.py створити тест test_remove_name:
  - Тест має мітку change
  - Використовує фікстуру user
  - Першим кроком тест змінює поле name об’єкта user на пустий рядок
  - Другим кромом тест перевіряє, що зміни відбулися і вони правильні
7. В файлі /tests/api/test_api.py створити тест test_name:
  - Тест має мітку check
  - Використовує фікстуру user
  - Перевіряє, що поле name об’єкту user відповідає очікуваному
8. В файлі /tests/api/test_api.py створити тест test_second_name:
  - Тест має мітку check
  - Використовує фікстуру user
  - Перевіряє, що поле second_name об’єкту user відповідає очікуваному

Всі створені, змінені та видалені файли додати до коміта і відправити на сервер GitHub за допомогою команди git push


<h1>Проєктне завдання 3</h1>

Розробити тести для тестування HTTP протоколу за допомогою модулів pytest та requests, використовуючи фікстури і мітки

В склонованому з GitHub репозиторії (це той репозиторій, який ви клонували, виконуючи блок лекцій по GIT), використовуючи результати попереднього модуля, розробити тести за допомогою модулів pytest та requests, які відповідають наступним вимогам:

1. Мітка http зареєстрована в файлі pytest.ini

2. В файлі /tests/test_http.py створити тест test_first_request:
  - Тест має мітку http
  - Першим кроком тест відправляє HTTP запит з методом GET на адресу https://api.github.com/zen і зберігає відповідь сервера у змінну
  - Другим кроком тест, за допомогою f-рядків виводить на екран атрибут text відповіді від сервера

3. В файлі /tests/test_http.py створити тест test_second_request:
  - Тест має мітку http
  - Першим кроком тест відправляє HTTP запит з методом GET на адресу https://api.github.com/users/defunkt і зберігає відповідь сервера у змінну
  - Тест перевіряє, що атрибут name тіла відповіді від сервера відповідає значенню ‘Chris Wanstrath’
  - Тест перевіряє, що статус код відповіді від сервера відповідає числу 200
  - Тест перевіряє, що заголовок Server відповіді від сервера відповідає значенню ‘GitHub.com’
4. В файлі /tests/test_http.py створити тест test_status_code_request:
  - Тест має мітку http
  - Першим кроком тест відправляє HTTP запит з методом GET на адресу https://api.github.com/users/sergii_butenko і зберігає відповідь сервера у змінну
  - Тест перевіряє, що статус код відповіді від сервера відповідає числу 404

Всі створені, змінені та видалені файли додати до коміта і відправити на сервер GitHub за допомогою команди git push


<h1>Проєктне завдання 4</h1>

Розробити тести для тестування API Github, створивши для цього написаний вами API клієнт, використовуючи при цьому API документацію GitHub https://docs.github.com/en/rest/users/users?apiVersion=2022-11-28, та модулі pytest і requests

Обовязкова частина:

В склонованому репозитрії, використовуючи результати попереднього модуля, розробити тести, використовуючи модуль pytest та requests, які відповідають наступним вимогам:

1. Мітка api зареєстрована в pytest.ini файлі.
2. В файлі /modules/api/clients/github.py створити клас GitHub.
  - В описі методу є обов’язковий параметр username
  - В тілі методу формується адреса, на яку потрібно відправити HTTP запит. Логіка формування адреси - поєднати два рядки:
    1. https://api.github.com/users/
    2. Значення параметра username
    3. В тілі методу відправляється HTTP запит з методом GET на URL адресу з попереднього кроку
    4. Метод повертає тіло відповіді від сервера у форматі json
  - В описі методу є обов’язковий параметр name
  - В тілі методу відправляється HTTP запит з методом GET на URL адресу "https://api.github.com/search/repositories" з параметром рядка запиту q значення якого дорівнює значенню параметра методу name
  - Метод повертає тіло відповіді від сервера у форматі json
    1. Клас має метод об’єкту get_user:
    2. Клас має метод об’єкту search_repo:
3. В файлі conftest.py описати фікстуру github_api Ця фікстура:
    1. Створює об’єкт класа GitHub
    2. Повертає створений об’єкт в тести
4. В файлі /tests/api/test_github_api.py створити тест test_user_exists:
  - Тест має мітку api
  - Використовує фікстуру github_api
  - В тілі тесту використати метод get_user фікстури github_api
  - Використати ім’я користувача для пошуку defunkt
  - Перевірити, що тіло відповіді від сервера має атрибут login, значення якого має дорівнювати  defunkt
5. В файлі /tests/api/test_github_api.py створити тест test_user_not_exists:
  - Тест має мітку api
  - Використовує фікстуру github_api
  - В тілі тесту використати метод get_user фікстури github_api
  - Використати ім’я користувача для пошуку butenkosergii
  - Перевірити, що тіло відповіді від сервера має атрибут message значення якого має дорівнювати  Not Found
6. В файлі /tests/api/test_github_api.py створити тест test_repo_can_be_found:
  - Тест має мітку api
  - Використовує фікстуру github_api
  - В тілі тесту використати метод search_repo фікстури github_api
  - Використати ім’я репозиторія для пошуку become-qa-auto
  - Перевірити, що тіло відповіді від сервера має атрибут total_count, значення якого має дорівнювати очікуваному на момент створення тесту значенню, наприклад 25.
7. В файлі /tests/api/test_github_api.py створити тест test_repo_cannot_be_found:
  - Тест має мітку api
  - Використовує фікстуру github_api
  - В тілі тесту використати метод search_repo фікстури github_api
  - Використати ім’я репозиторія для пошуку sergiibutenko_repo_non_exist або будь-яке інше ім’я, що не існує на момент створення тесту
  - Перевірити, що тіло відповіді від сервера має атрибут total_count, значення якого має дорівнювати 0.
8. В файлі /tests/api/test_github_api.py створити тест test_repo_with_single_char_be_found:
  - Тест має мітку api
  - Використовує фікстуру github_api
  - В тілі тесту використати метод search_repo фікстури github_api
  - Використати ім’я репозиторія для пошуку s або будь-яке інше ім’я, що складається з одного символу
  - Перевірити, що тіло відповіді від сервера має атрибут total_count, значення якого має не дорівнювати 0.

Всі створені, змінені та видалені файли додати до коміта і відправити на сервер GitHub за допомогою команди git push.



<h1>Проєктне завдання 5</h1>

В склонованому репозиторії, використовуючи результати попереднього модуля, розробити тести, використовуючи модуль pytest та sqlite3, які відповідають наступним вимогам:

1. Мітка database зареєстрована в pytest.ini файлі.
2. В файлі /modules/common/database.py створити клас Database.
  - Клас має конструктор, в якому ініціалізовані два атрибути об’єкта:
    1. self.connection - об’єкт, який реалізує з'єднання з базою даних (див. Лекцію 18.4)
    2. self.cursor - курсор об’єкта self.connection (див. Лекцію 18.4)
  - Клас має метод об’єкта test_connection:
    1. Метод виконує SQL запит SELECT sqlite_version();
    2. Результатом виконання методу є виведена в термінал версія бази даних.
  - Клас має метод об’єкта get_all_users:
    1. Метод має повернути із таблиці customers значення полів name, address, city для всіх користувачів
  - Клас має метод об’єкта get_user_address_by_name:
    1. Метод має обов’язковий параметр name
    2. Метод має повернути із таблиці customers значення полів address, city, postalCode, country для користувача з іменем name
  - Клас має метод об’єкта update_product_qnt_by_id:
    1. Метод має обов’язкові параметри product_id, qnt
    2. Метод має змінити кількість товару за вказаним в парметрі product_id унікальним значенням в таблиці products на значення вказаного в параметрі qnt
  - Клас має метод об’єкта select_product_qnt_by_id:
    1. Метод має обов’язковий параметр product_id
    2. Метод має повернути кількість товару за вказаним в парметрі product_id унікальним значенням із таблиці products
  - Клас має метод об’єкта insert_product:
    1. Метод має обов’язкові параметри product_id, name, description, qnt
    2. Метод має вставити, або замінити дані в таблиці products для колонок id, name, description, quantity. Дані взяти з параметрів product_id, name, description, qnt
  - Клас має метод об’єкта delete_product_by_id:
    1. Метод має обов’язковий параметр product_id
    2. Метод має видалити товар за вказаним в парметрі product_id унікальним значенням із таблиці products
  - Клас має метод об’єкта get_detailed_orders:
    1. Використовуючи команду JOIN та таблиці orders, customers, products, повернути із таблиці orders наступну інформацію у відповідному порядку: унікальний номер замовлення, ім’я покупця, ім’я замовленого продукту, опис замовленого продукту, дату замовлення
3. В файлі /tests/database/test_database.py створити тест test_database_connection:
  - Тест має мітку database
  - В тілі тесту створити екземпляр класу Database
  - В тілі тесту виконати метод об’єкта test_connection
4. В файлі /tests/database/test_database.py створити тест test_check_all_users:
  - Тест має мітку database
  - В тілі тесту створити екземпляр класу Database
  - В тілі тесту виконати метод об’єкта get_all_users
  - Вивести в термінал результат виконання методу об’єкта get_all_users
5. В файлі /tests/database/test_database.py створити тест test_check_user_sergii:
  - Тест має мітку database
  - В тілі тесту створити екземпляр класу Database
  - В тілі тесту виконати метод об’єкта get_user_address_by_name зі значенням параметру name = Sergii
  - Перевірити, що дані, які повернув метод get_user_address_by_name  відповідають наступним даним:
    1. Maydan Nezalezhnosti 1
    2. Kyiv
    3. 3127
    4. Ukraine
6. В файлі /tests/database/test_database.py створити тест test_product_qnt_update:
  - Тест має мітку database
  - В тілі тесту створити екземпляр класу Database
  - В тілі тесту виконати метод об’єкта update_product_qnt_by_id зі значенням параметрів product_id = 1 та qnt = 25
  - Перевірити, що після оновлення даних кількість товару з унікальним номером 1 дорівнює 25
7. В файлі /tests/database/test_database.py створити тест test_product_insert:
  - Тест має мітку database
  - В тілі тесту створити екземпляр класу Database
  - В тілі тесту виконати метод об’єкта insert_product зі значенням параметрів product_id = 4, name = печиво, description = солодке, qnt = 30
  - Перевірити, що після оновлення даних, кількість товару з унікальним номером 4 дорівнює 30
8. В файлі /tests/database/test_database.py створити тест test_product_delete:
  - Тест має мітку database
  - В тілі тесту створити екземпляр класу Database
  - В тілі тесту створити тестові дані, створивши продукт в таблиці products зі значеннями параметрів product_id = 99, name = тестові, description = дані, qnt = 999
  - В тілі тесту видалити дані з таблички products зі значенням параметра product_id = 99
  - Перевірити, що кількість рядків, що було знайдено дорівнює 0
9. В файлі /tests/database/test_database.py створити тест test_detailed_orders:
  - Тест має мітку database
  - В тілі тесту створити екземпляр класу Database
  - В тілі тесту вивести в термінал результат виконання методу get_detailed_orders об’єкта класу Database 
  - Перевірити, що кількість знайдених результатів дорівнює 1
  - Перевірити, що дані, які повернув метод get_detailed_orders,  відповідають наступним даним:
    1. 1
    2. Sergii
    3. солодка вода
    4. з цукром

Всі створені, змінені та видалені файли додати до коміта і відправити на сервер GitHub за допомогою команди git push.

<h1>Проєктне завдання 6</h1>

В склонованому репозиторії, використовуючи результати попереднього модуля, розробити тести, використовуючи модулі pytest та selenium, які відповідають наступним вимогам:

1. Мітка ui зареєстрована в pytest.ini файлі.
2. У каталозі modules/ui/page_object створити файл base_page.py, а в ньому клас BasePage. 
  - В конструкторі класу ініціалізувати об’єкт для комунікації з вебдрайвером.
  - Клас має метод об’єкта close, задача якого закрити відкритий браузер.
3. У каталозі modules/ui/page_object створити файл sign_in_page.py, а в ньому клас SignInPage. 
  - Клас SignInPage наслідуваний від BasePage класу.
  - В конструкторі класу викликати конструктор батьківського класу.
  - В класі реалізований метод об’єкту, який приймає параметри username і password. Задача методу ввести в поле email ім’я користувача, в поле password пароль і натиснути кнопку sign in.
  - В класі реалізований метод об’єкту, який перевіряє, чи відповідає заголовок сторінки очікуваному.
4. У каталогу tests/ui створити файл test_ui_page_object.py. А в ньому створити тест, який:
  - Має мітку ui.
  - Виконує такі кроки:
    1. Відкриває сторінку Sign In.
    2. Вводить некоректні дані в поля імені та пароля.
    3. Перевіряє, що заголовок сторінки відповідає очікуваному.
    4. Закриває браузер.