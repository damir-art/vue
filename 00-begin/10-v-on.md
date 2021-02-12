# Директива v-on
Директива v-on предназначена для работы с событиями.

По нажатию кнопки, меняем сообщение в свойстве `message`

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
            changeMessage: function () {
                this.message = 'Сообщение изменено'
            }
        }
    })