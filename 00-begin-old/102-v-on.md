# Директива v-on
Директива v-on предназначена для работы с событиями.

- v-on:click="changeMessage"
- @click="changeMessage"

По нажатию на кнопку, меняем сообщение в свойстве `message`

    <div>
        {{ message }}
    </div>

    <button v-on:click="changeMessage">Кнопка</button>

    var app = new Vue({
        el: '#app',
        data: {
            title: 'Vue.js',
            subtitle: 'Руководство по Vue.js',
            message: 'Вывод информации!'
        },
        methods: {
            
            // Анониманая функция
            changeMessage: function () {
                this.message = 'Сообщение изменено'
            }

            // Обычная тоже работает
            changeTitle() {
                this.title = 'Всем привет!'
            }

        }
    })
