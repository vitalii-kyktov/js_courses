# Данные, Величины, Типы, Операторы

## Величины в JS - блоки информации.

## Основные типы величин:        
#### числа

целые(5), с точкой(5.25), специальные(NaN, Infinity, -Infinity)

#### строки

 "", '', экранирование (\) и спец символы (\t, \n)
 
#### булевые

false, true

#### неопределённые
 
null, undefined 

#### обьекты

{}

#### функции

function

## Основные операторы:
   
####Арифметические

**+ - * / %**

```javascript
5 + 8;
13 - 21;
((8 * 21) - 55 / 5) + 89;
10 / 0; // infinity
0 / 0;  // NaN
```

```javascript
"привет" + " " + "человек";
"это первая строка,\nа это вторая";
```

#### Сравнения

**== === != !== > < >= <=**

```javascript
5 > 8;
3 < 13;
21 == 21;
34 != 34;
"hello" == "hello";
"Hello" == "hello";
```

#### Логические

&& || ! ?:

```javascript
false || true;
false && true;
true && true;
true ? 13 : 21;
false ? 13 : 21
21 > 15 ? "21 больше 15" : "21 меньше 15";
```

#### Определение типа

typeof  

```javascript
typeof 5;
typeof "hello";
typeof true;
typeof {};
typeof undefined;
```
      
## Приведение типов

![coercion](https://github.com/megarocks/js_courses/blob/master/course_2/class_01/coercion2.png)

```javascript
"5" + 3;
"5" - 3;
"" - 7 + 4;
"" + 7 - 4;
7 - "" * 2;
(7 - "") * 2;
"\n8\t" + 12;
"\t12\n" -5;
21 * null;
false == null;
false == 0;
false === 0;
```

## Задачи

1.1 Используя операторы и конкатенацию, вывести в консоль такую информацию:
> "Тип числа 5: **number**"  
"Тип строки 'привет': **string**"  
"Тип булевого занчения true: **boolean**"  
`5 > 3 - это: **true**"  
"10 < 7 - это: **false**"  
"Если разделить число X на 0, то получим: **Infinity**"  
"Если разделить 0 на 0 то получим: **NaN**"
  
  **выделенные значения получить при помощи операторов** `typeof`, `>`, `<`, `/`. 
  Преобразование к строке можно выполнить при помощи функции `String()`. Например: `String(11<8)` даст нам строку `"false"`

1.2 Выполнить в консоли браузера выражения из списка. Прокомментировать каждое полученным результатом,
 а также написать почему результат именно таков. Пример:
> "" + 1 + 0; // результат "10". вначале будет выполнена конкатенация, и 1, при сложении со строкой будет преобразована к "1". Затем будет выполнена еще одна конкатенация 0 будет преобразован к "0". "1" + "0" = "10"

  1. `"" - 1 + 0`
  1. `true + false`
  1. `6 / "3"`
  1. `"2" * "3"`
  1. `4 + 5 + "px"`
  1. `"$" + 4 + 5 `
  1. `"4" - 2 `
  1. `"4px" - 2 `
  1. `7 / 0 `
  1. `"  -9\n" + 5`
  1. `"  -9\n" - 5`
  1. `5 && 2 `
  1. `2 && 5 `
  1. `5 || 0 `
  1. `0 || 5`
  1. `null + 1`
  1. `undefined + 1`
  1. `(1,5 - 1) * 2`


## Материалы по теме

1. Выразительный JavaScript (Величины, типы и операторы): https://habrahabr.ru/post/240223/
2. w3schools (Introduction - Comments) http://www.w3schools.com/js/default.asp
2. W3schools (JavaScript Type Conversion) http://www.w3schools.com/jsref/jsref_type_conversion.asp
2. Учебник JS (шесть типов данных, typeof): http://learn.javascript.ru/types-intro
2. Учебник JS (преобразование типов примитивных величин): https://learn.javascript.ru/types-conversion  
2. Учебник JS (основные операторы): http://learn.javascript.ru/operators
2. Учебник JS (операторы сравнения и логические значения): http://learn.javascript.ru/comparison
3. Скринкаст JavaScript Джедай (видео 1 - 9): https://www.youtube.com/watch?v=H6G63NKRSi8&list=PL363QX7S8MfSxcHzvkNEqMYbOyhLeWwem
 
 

