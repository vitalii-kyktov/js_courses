#Обьекты#

## Теория

### Обьявление переменной, содержащей обьект ###
```javascript
var myObject = {}; //empty object
var car = { name: "audi", color: "black", maxSpeed: 100500 };
var user = {
    firstName: 'John',
    lastName: 'Smith',
    age: 77,
    sayHello: function() {
      alert('Hello');  
    }
}
```

### Обращение к свойствам и методам обьекта ###
```javascript
var user = {
    firstName: 'John',
    lastName: 'Smith',
    age: 77,
    sayHello: function() {
      alert('Hello');  
    }
}

console.log(user.firstName);  // John
alert(user['age']);  //  77
user.sayHello();

console.log(user.car);  // undefined
```

### Присваивание значений свойствам обьекта ###

```javascript
var user = {}

user.firstName = 'John';
user.lastName = 'Smith';
user.car = { name: "audi", color: "black", maxSpeed: 100500 };

console.log(user.car.name);
```

### Удаление свойст ###
```javascript
var car = { name: "audi", color: "black", maxSpeed: 100500 };
delete car.color;
```

### Проверка наличия свойства в обьекте ###
```javascript
var car = { name: "audi", color: "black", maxSpeed: 100500 };

console.log('age' in car); // false
console.log('name' in car); // true
```

### Получение списка свойст обьекта ###
```javascript
var car = { name: "audi", color: "black", maxSpeed: 100500 };

Object.keys(car); // ["name", "color", "maxSpeed"]
```

### Ключевое слово this  ###
```javascript
var user = {
    firstName: 'John',
    lastName: 'Smith',
    age: 77,
    introduce: function() {
      alert(`Hello, my name is ${this.firstName} ${this.lastName}`);  
    }
}

user.introduce();
```

### Конструкторы обьектов ###
```javascript

var Car = function(name, color, maxSpeed) {
  return { 
    name: name,
    color: color,
    maxSpeed: maxSpeed,
    drive: function() {
      console.log(`${color} ${name} is flying with speed ${maxSpeed} km\\h`)  
    },
    reflect: function() {
      console.log('I have following props:', Object.keys(this).toString());  
    }
  }
}

var car1 = new Car('audi', 'black', 250);
var car2 = new Car('bmw', 'yellow', 300);
var car3 = new Car('lada', 'magenta', 350);

```

## Задачи

1. Создать переменную cat и присвоить в неё обьект. Обьект должен иметь следующие поля: `name, color, age`
1. Расширить возможности кота методами: run, и meow. Метод run должен выводить в консоль: `{color} cat with {name} is running`
Метод meow должен выводить в консоль: `{color} cat with {name} is saying meow`.
2. Напишите метод meow таким образом, чтобы он принимал параметром число. Кот при этом должен мяукнуть столько раз, сколько было
указано в параметре. 
Например:
```javascript
cat.meow(3);
'red cat with name Ololo is saying meow'
'red cat with name Ololo is saying meow'
'red cat with name Ololo is saying meow'
```
3. Напишите функцию-конструктор обьектов-котов.
4. Используя конструктор и цикл создайте массив из 10 котов. Каждому коту давайте разные имена (можно называть `кот1`, `кот2`,
`кот3`). Выведите массив в консоль
5. При помощи цикла пройдите по массиву котов и попросите каждого побегать (вызовите метод `run`)
6. Добавьте в функцию run параметр указывающий на расстояние, которое должен пробежать кот. 
Пусть каждый кот запоминает то расстояние, котрое пробежал. Конечный результат должен выглядеть так:
```javascript
cat.run(10);  // orange cat with name Blade ran 10 meters
cat.run(20);  // orange cat with name Blade ran 30 meters
cat.run(5);  // orange cat with name Blade ran 35 meters
```
7. Научите кота рефлексии. Добавьте котам метод: `reflect`, при вызове которого кот перечислит свойства, которыми обладает:
```javascript
cat.reflect();  // I have following properties: name,color,age,run,meow,run,reflect
```


