# Структура проекта
- `README.md` файл инструкция, описание проекта, для гитхаба
- `package.json` файл инструкция для npm
- `package-lock.json` контроль версий
- `babel.config.js` конфигурация vue для babel
- `.gitignore` игнорируемые файлы для гита
- `node_modules` пакеты для работы с проектом vue
- `public` содержит статические файлы, изображения, верстка
- `src/assets` изображения
- `main.js` импорт vue, компонентов, плагинов (в основном)
- `App.vue` корневой компонент, подключает `/components/HelloWorld.vue`

## Как писать код
- Сначала пишем HTML-код `template`
- Затем JavaScript-код `script`
- После CSS-код `style`

Пример `App.vue`, удаляем папку `assets`, файл-компонент в папке `components`, чистим `App.vue`:

    <template>
        <div id="app">
            <h1>{{ message }}</h1>
            <counter /> <!-- Добавляем после создания компонента Counter.vue -->
        </div>
    </template>

    <script>
    export default {
        data() {
            return {
                message: 'Дефолтный файл'
            }
        }
    };
    </script>

    <style>
    /* Глобальные стили */
    body {
        max-width: 1110px;
        margin: 0 auto;
    }
    </style>

## Подключаем компоненты
Подключаем компоненты через `main.js` Создаём компонент `Counter.vue` и подключаем его в файле `main.js`:

    import Vue from 'vue'
    import App from './App.vue'

    // Регистрируем компонент глобально
    import Counter from './components/Counter.vue'
    Vue.component('counter', Counter)

    Vue.config.productionTip = false

    new Vue({
    render: function (h) { return h(App) },
    }).$mount('#app')

## Counter.vue

    <template>
        <div>
            <h2>{{ counter }}</h2>
            <button @click="add">+1</button>
        </div>
    </template>

    <script>
    export default {
        // Метод возвращает объект, всегда
        data() {
            return {
                counter: 0
            }
        },
        methods: {
            add() {
                this.counter++
            }
        }
    }
    </script>

    <style scoped>

    </style>