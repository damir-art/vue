# methods
`data` статична, методы придают ей динамики:

    methods: {
        greet: function () {
            return 'Hello my name is ' + this.name
        },
        upperCase: function() {
            return this.name.toUpperCase()
        }
    }

- methods - свойство, объект в котором хранятся методы
- greet - имя метода, ключ объекта
- function - тело функции, значение метода

## Вызов метода

    {{ greet() }}

## Реактивность Vue.js
Изменение информации внутри модели (data), мгновенно изменяет шабон (id="app").
