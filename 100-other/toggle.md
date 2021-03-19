# toggle
Показываем и скрываем элементы

Скрываем и показываем элемент по нажатию по кнопке, при этом текс у кнопки меняется на Скрыть/Показать:

    <div id="app">
        <p v-if="showEl">
            Показать/Скрыть
        </p>

        <button @click="toggleShowEl" type="button">{{ txtBtnShow }}</button>
    </div>

    <script>
        const app = new Vue({
            el: '#app',
            data: {
                showEl: true
            },
            methods: {
                toggleShowEl() {
                    this.showEl = !this.showEl // стандартный способ во vue
                }
            },
            computed: {
                txtBtnShow() {
                    return this.showEl ? 'Скрыть элемент' : 'Показать элемент'
                }
            }
        })
    </script>

## Добавляем анимацию
Анимацию добавляют в CSS файл, а затем оборачивают элемент тегом `transition`
