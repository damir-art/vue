# Директива v-if
Директива `v-if` показывает или скрывает элемент, в зависимости от значения `true/false`.

    <div v-if="show">
            
    </div>

    var app = new Vue({
        el: '#app',
        data: {
            show: true // false
        }
    })

Вместо `show` можно поставить любое слово.

## v-if с условием
Создаём несколько блоков и они появляются лишь при совпадении со значением `message`

    <p class="out" v-if="message === `primary`">
        {{ paragraph }} <b>primary</b>
    </p>
    <p class="out" v-if="message === `secondary`">
        {{ paragraph }} <b>secondary</b>
    </p>
    <p class="out" v-if="message === `success`">
        {{ paragraph }} <b>success</b>
    </p>

    const app = new Vue({
        el: '#app',
        data: {
            paragraph: 'Параграф.',
            message: `primary`
        }
    })

## v-else-if, v-else
Используют если нужно вывести хотябы один блок в независимости от значения.

## v-show
Если if полностью удаляет код из HTML, то v-show скрывает визуально, но код в HTML остаётся.

    <p class="out" v-show="show">
        {{ paragraph }}
    </p>

    const app = new Vue({
        el: '#app',
        data: {
            paragraph: 'Параграф.',
            show: true
        }
    })