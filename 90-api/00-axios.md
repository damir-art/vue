# Axios
Получаем get запросом JSON. Делаем AJAX запрос на сервер и выводим полученную информацию. Делаем с помощью https://github.com/axios/axios

Устанавливаем, после подключения Vue.js

    <script src="https://cdn.jsdelivr.net/npm/axios/dist/axios.min.js"></script>

## Используем API Приват банка
Используем API (публичные данные) Приват банка, курсы валют https://api.privatbank.ua/#p24/exchange

    <div id="app">
        <ul>
            <li v-for="(course, index) in courses" :key="index">
                За 1 {{ course.ccy }} равен {{ course.sale }} {{ course.base_ccy }} при продаже, {{ course.buy }} при покупке
            </li>
        </ul>
    </div>

    <script src="js/vue.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/axios/dist/axios.min.js"></script>

    <script>
        const app = new Vue({
            el: '#app',
            data: {
                courses: [] // указываем тот тип данных который ожидается получить
            },
            mounted() {
                axios
                    .get('https://api.privatbank.ua/p24api/pubinfo?json&exchange&coursid=5')
                    .then(response => this.courses = response.data)
            }
        })
    </script>

## Добавляем обработку ошибок
Добавляем обработку ошибок, если необходимо. Если появится ошибка, то пользователь увидит сообщение.

    <div id="app">
        <div v-if="errored" class="error">
            Ошибка!
        </div>

        <ul>
            <li v-for="(course, index) in courses" :key="index">
                За 1 {{ course.ccy }} равен {{ course.sale }} {{ course.base_ccy }} при продаже, {{ course.buy }} при покупке
            </li>
        </ul>
    </div>

    <script src="js/vue.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/axios/dist/axios.min.js"></script>

    <script>
        const app = new Vue({
            el: '#app',
            data: {
                courses: [], // указываем тот тип данных который ожидается получить
                errored: false
            },
            mounted() {
                axios
                    .get('https://api1.privatbank.ua/p24api/pubinfo?json&exchange&coursid=5')
                    .then(response => this.courses = response.data)
                    .catch(error => {
                        console.log(error)
                        this.errored = true
                    })
            }
        })
    </script>