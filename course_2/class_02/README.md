# Переменные

## Обьявление переменных

#### Ключевое слово var
`var myVariable;`

#### Оператор присваивания, инициализация
`var someNumber;`
`var someNumber = 7;`
`var someString = "hello";`

#### Правила именования переменных
`var $ = "possibly it should be jquery";`
`var _ = "possibly it should be underscore";`
`var secretVariable38 = true;`
`var 38secretVariable = false;`

## Использование переменных

#### Получение значения переменной
```javascript
var x = 15;
x;
console.log(x);
alert(x);
```

#### Присваивание и пере-присваивание значения переменной
```javascript
var y = "hello";
console.log(y);
y="goodbye";
console.log(y);
```

#### Использование операторов и манипуляции с данными
```javascript
var ten = 10;
console.log(ten * ten);

var someNumber = 15;
someNumber = someNumber + 5;
console.log(someNumber);
```

## Использование некоторых функций

#### alert

```javascript
alert("привет");
```

```javascript
var message = "ПРИВЕТ!"
alert(message);
```

#### prompt

```javascript
prompt("введите ваше имя");
```

```javascript
var name = prompt("введите ваше имя");
```

```javascript
var name = prompt("введите ваше имя");
alert(name);
```

#### confirm

```javascript
var userConfirm = confirm("вам уже исполнилось 18?");
userConfirm ? alert("доступ разрешён") : alert("доступ запрещён");
```

#### log

```javascript
console.log("hello");
```

```javascript
var name = prompt("Enter your name");
console.log("hello " + name);
console.log("hello", name);
```

```javascript
var firstName = prompt("Enter first name");
var lastName = prompt("Enter last name");
console.log(firstName, lastName);
console.log("fist name is: %s and last name is: %s", firstName, lastName);
```

## Окружение и переменные окружения

#### window, screen, document, console

`console.log`

```javascript
console.log(window);
console.log(window.location);
console.log(screen);
console.log(document);
```

## Использование методов document для вывода данных на страницу


```javascript
document.write('hello world');  
document.write('\n');
document.writeln('result of writeln work');
document.write('<h1>This title written from script</h1>');
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Page Title</title>
</head>
<body>

<div id="content"></div>

<script>
    var contentDiv = document.getElementById('content');
    contentDiv.innerHTML = '<p>hello world</p>';
</script>
</body>
</html>
```



## Практика

2.1 Создайте переменную с именем `carName`, присвойте ей значение `"Audi"` и выведите его в консоль.

2.2 Создайте переменную с именем `number`, присвойте ей значение `50` и выведите в консоль.

2.3 Нижеприведенный код должен вывести на страницу "Hello". Исправьте его
```html
<script>
    var messageToShow = "Hello";
    alert(messageToshow);
</script>
```

2.4 Обьявить переменные и присвоить им значения следующих типов: `string`, `number`, `boolean`, `undefined`, `null`.   
Использовать оператор typeof для проверки типа значения хранимого переменной. Результаты вывести в консоль.

2.5 Присвоить двум переменным цифровые значения и вывести в консоль их сумму, разницу, произведение и результат 
деления первого на второе  

2.6 Обьявить переменную и сохранить в неё цену товара (386) монет. Обьявить еще одну переменную и сохранить в неё 
размер скидки (17.5) %. Обьявить еще одну переменную и сохранить в неё значение скидки в монетах. 
Обьяваить еще одну переменную и сохранить в неё стоимость товара с учётом скидки. Вывести в консоль результаты в виде:
> Product price: 386 coins  
Discount: 17.5%, what in coins is 67.55  
Price considering discount is: 318.45 coins  

**XXX - заменить на расчетные значения**
  
2.7 Использовать prompt и получить от пользователя значение. Присвоить это значение переменной. Вывести в консоль результат ввода в таком виде:
  > "User input is: {here should be user input string}"
    
  **{here should be user input string} - заменить на ту строку которая была введена**
  
2.8 Создайте html документ который содержит `div#content`. Используйте prompt и получите от пользователя 5 значений. 
Сохраните их в переменные. При помощи `document.getElementById` получите `div#content` в переменную. Затем используйте 
свойство `innnerHTML` и добавьте в `div` ненумерованный список из 5 елементов. Элементами списка должны быть значения,
 полученные от пользователя при помощи prompt.
 
 
 ## Материалы по теме:
 
 1. Выразительный JavaScript (Структура программы): http://habrahabr.ru/post/240225/
 1. w3schools (variables - data types) http://www.w3schools.com/js/js_variables.asp
 1. Выразительный JavaScript (DOM, Поиск элементов): https://habrahabr.ru/post/243815/
 2. Учебник JS (переменные): http://learn.javascript.ru/variables
 2. Учебник JS (правильный выбор имени переменной): http://learn.javascript.ru/variable-names
 2. Учебник JS (взаимодействие с пользователем): http://learn.javascript.ru/uibasic
 2. W3scools (getElementById): http://www.w3schools.com/jsref/met_document_getelementbyid.asp
 3. Скринкаст JavaScript Джедай (видео №30) https://www.youtube.com/watch?v=TL1ZWxtV47w&index=31&list=PL363QX7S8MfSxcHzvkNEqMYbOyhLeWwem

