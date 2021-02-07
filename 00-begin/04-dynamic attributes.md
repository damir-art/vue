# Динамические атрибуты
Чтобы атрибут сделать динамическим, перед его именем нужно поставить `v-bind:` или просто `:`.

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
Создаём тогл атрибут true/false , который будет включать/отключать значение атрибта, на примере класса:

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
- `ts` - свойство элемента

Делаем тоже самое но уже через метод (более правильный подход):

    <div id="app">
        <div :class="tFoo()">
            {{ message }}
        </div>
    </div>

    var app = new Vue({
        el: '#app',
        data: {
            message: 'Вывод информации!',
            tc: true // false
        },
        methods: {
            tFoo() {
                return {
                    out: this.tc
                }
            }
        }
    })

- `tFoo()` - функция, которая возвратит true или false (показать/скрыть), для CSS-класса `out`
