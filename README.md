# Лабораторная работа №1. Введение в JavaScript

## Цель работы
Познакомиться с основами JavaScript, научиться писать и выполнять код в браузере и в локальной среде, разобраться с базовыми конструкциями языка.

## Условие

### Задание 1. Выполнение кода в браузере

1. Подготовка среды:
    - Установите текстовый редактор (например, **VS Code**).
    - Установите **Node.js** с официального сайта.
    > ![](/assets/screenshots/Screenshot_1.png)<br>

    > [!NOTE]
    > Команды:<br>**code -v** проверяет наличие **VS Code** на машине;<br>**node -v** проверяет наличие **Node.js** на машине.
    - Откройте **DevTools** в браузере (нажмите ***F12*** и выберите вкладку Консоль).
    > ![](/assets/screenshots/Screenshot_2.png)
2. Выполнение кода JavaScript в браузере
    - Откройте консоль разработчика (***F12 → Console***).
    - Напишите команду **console.log("Hello, world!");** и нажмите Enter.
    - Запишите в консоли **2 + 3** и посмотрите результат.
    > ![](/assets/screenshots/Screenshot_3.png)
3. Создание первой HTML-страницы с JavaScript
    - Создайте файл **index.html** и вставьте в него следующий код.
    ```
    <!DOCTYPE html>
    <html lang="en">
    <head>
    <title>Привет, мир!</title>
    </head>
    <body>
    <script>
        alert("Привет, мир!");
        console.log("Hello, console!");
    </script>
    </body>
    </html>
    ```
    > ![](/assets/screenshots/Screenshot_4.png)
    - Откройте **index.html** в браузере и посмотрите, как выполняется код.
    > ![](/assets/screenshots/Screenshot_5.png)<br>
    > ![](/assets/screenshots/Screenshot_6.png)

4. Подключение внешнего JavaScript-файла
    - Создайте файл **script.js** и добавьте в него код:
    ```
    alert("Этот код выполнен из внешнего файла!");
    console.log("Сообщение в консоли");
    ```
    > ![](/assets/screenshots/Screenshot_7.png)
    - Подключите файл в index.html, добавив в \<head\>
    ```
    <script src="script.js"></script>
    ```
    > ![](/assets/screenshots/Screenshot_8.png)
    - Откройте страницу в браузере.
    > ![](/assets/screenshots/Screenshot_9.png)<br>
    > ![](/assets/screenshots/Screenshot_10.png)

### Задание 2. Работа с типами данных

1. Объявление переменных и работа с типами данных.
    - В файле **script.js** создайте несколько переменных:
        - *userName* - строка с вашим именем.
        - *birthYear* - число, представляющее год вашего рождения.
        - *isStudent* - логическая переменная, указывающая, являетесь ли вы студентом.
    > ![](/assets/screenshots/Screenshot_11.png)
    - Выведите их в консоль.
    > ![](/assets/screenshots/Screenshot_12.png)

2. Управление потоком выполнения (условия и циклы)
    - Добавьте следующий код в **script.js**:
    ```
    let score = prompt("Введите ваш балл:");
    if (score >= 90) {
    console.log("Отлично!");
    } else if (score >= 70) {
    console.log("Хорошо");
    } else {
    console.log("Можно лучше!");
    }

    for (let i = 1; i <= 5; i++) {
    console.log(`Итерация: ${i}`);
    }
    ```
    > ![](/assets/screenshots/Screenshot_13.png)
    - Откройте страницу в браузере и посмотрите, как работают условия и циклы.
    > ![](/assets/screenshots/Screenshot_14.png)<br>
    > ![](/assets/screenshots/Screenshot_15.png)

## Контрольные вопросы

1. Чем отличается **var** от **let** и **const**?
    > **var** -переменные могут быть как обновлены, так и переопределены внутри области видимости;<br>**let** -переменные можно обновлять, но не переопределять;<br>**const** -переменные нельзя ни обновлять, ни переопределять.
2. Что такое неявное преобразование типов в JavaScript?
    > Это автоматическое приведение одного типа данных к другому при выполнении операций.
    ```
    console.log("5" + 2); // "52" (число 2 преобразуется в строку)
    console.log("5" - 2); // 3 ("5" становится числом)
    console.log("10" * "2"); // 20 (оба операнда становятся числами)
    ```
3. Как работает оператор == в сравнении с === ?
    > Оператор == представляет собой **сравнение**, тогда как === представляет собой **_строгое_ сравнение**. Разница между ними в том, что первый *подвергает значения **неявному приведению*** для их сравнения, тогда как второй *сравнивает как и **значение**, так и его **тип***. 
    ```
    console.log("5" == 5);  // true  (строка "5" приводится к числу)
    console.log("5" === 5); // false (разные типы: строка ≠ число)

    console.log(true == 1);  // true  (true → 1)
    console.log(true === 1); // false (boolean ≠ number)

    console.log(null == undefined);  // true  (особое правило в JS)
    console.log(null === undefined); // false (разные типы)

    console.log(0 == false);  // true  (false → 0)
    console.log(0 === false); // false (number ≠ boolean)
    ```