# data binding `v-bind:`
Привязка данных. Вставляем данные в атрибуты. Динамические атрибуты.

`v-bind:` - инструкция (директива) обращается к Vue и сообщает ей что что-то нужно связать. `:` сокращенная запись.

Используется для специфических данных, например:
- url адреса для ссылки
- значения для поля input

## Вставляем данные в атрибуты

Добавим в `data` url и кусок HTML-разметки:

    data: {
        link: 'http://ya.ru'

В разметку приложения добавим ссылку:

    <a v-bind:href="link" target="_blank">Ссылка</a>

Связываем атрибут `href` у ссылки с динамическим значением `link`.

# Динамические атрибуты
Возможность изменять значение атрибута. Чтобы атрибут сделать динамическим, перед его именем нужно поставить `v-bind:` или просто `:`.

    <div class="out" v-bind:title="outTitle">
        {{ out }}
    </div>

    var app = new Vue({
        el: '#app',
        data: {
            out: 'Вывод информации!',
            outTitle: 'Динамический атрибут'
        }
    })

В свойства `data` можно вставлять JavaScript-код: `'Динамический атрибут ' + new Date().toLocaleString()`

`v-bind:` директива, директивы имеют префикс `v-`

## Создаём тогл атрибут true/false
Создаём тогл атрибут true/false , который будет включать/отключать значение атрибута, на примере класса, значение CSS-класса - объект:

    <div id="app">
        <div :class="{'out': tc}">
            {{ message }}
        </div>
    </div>

    var app = new Vue({
        el: '#app',
        data: {
            message: 'Вывод информации!',
            tc: true // false
        }
    })

- `out` - имя CSS-класса
- `ts`  - свойство элемента созначениями `true` или `false`

## Работаем через метод
Делаем тоже самое но уже через метод (более правильный подход), возвращает объект:

    <div id="app">
        <h1>{{ title }}</h1>
        <h2>{{ subTitle }}</h2>
        <p v-bind:class="getClassOut()">
            {{ paragraph }}
        </p>
    </div>

    const app = new Vue({
        el: '#app',
        data: {
            title:       'Заголовок ' + new Date().toLocaleString(),
            subTitle:    'Подзаголовок приложения',
            paragraph:   'Параграф',
            toggleClass: true
        },
        methods: {
            getClassOut() {
                return {
                    out: this.toggleClass
                }
            }
        }
    })

- `getClassOut()` - функция возвратит объект `{out: true/false (показать/скрыть)}`, для CSS-класса `out`
