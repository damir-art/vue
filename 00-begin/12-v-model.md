# v-model
`v-model` - директива позволяющая взаимодействовать с пользователем, например вводим в `input` данные, и эти данные отображаются вместо заголовка. `v-model` связывает элементы форм и состояние приложения.

    <h2>{{ message }}</h2>
    <input v-model="message" type="text" />

    var app = new Vue({
        el: '#app',
        data: {
            message: 'Заголовок'
        }
    })

Свойство `message` должно быть создано в `data`.
Можно ввести сообщение по-умолчанию: `message: 'Привет'`

## .lazy
`.lazy` добавив это слово можно улучшить производительность, для высоконагруженных систем. Текст в заголовке будет менятся только после смены фокуса с инпута:

    <input v-model.lazy="message" type="text" />

## Разное
- v-model обычно вешают на инпуты, радиокнопки, текстареа и т.п.
