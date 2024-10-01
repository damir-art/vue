# First App
Первое приложение, Vue.js через CDN:

    <script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>

    <div id="app">{{ message }}</div>

    <script>
      const { createApp } = Vue

      createApp({
        data() {
          return {
            message: 'Привет Vue!'
          }
        }
      }).mount('#app')
    </script>

Указанная выше ссылка загружает глобальную сборку Vue, где все API верхнего уровня доступны как свойства глобального объекта Vue. Где строка `const { createApp } = Vue` извлекает метод createApp из глобального объекта Vue. В контексте Vue.js, Vue обычно является глобальной переменной, которая представляет основной класс или библиотеку Vue. Метод `createApp` используется для создания нового экземпляра приложения Vue, который служит отправной точкой для создания и настройки компонентов и других аспектов приложения.

`.mount('.sample')` - означает что всё что находится внутри этого контейнера, мы можем вставлять переменные и директивы из data

Помимо идентификаторов, можно приложения подключать к CSS-классам, если таких классов несколько то приложение подключится к первому элементу в списке:

    let sample = Vue.createApp({
      data() {
        return {
          message: 'Message'
        }
      }
    }).mount('.sample');

    // Второе приложение на той же странице
    let sample2 = Vue.createApp({
      data() {
        return {
          message: 'Message 2'
        }
      }
    }).mount('.sample-2');

https://ru.vuejs.org/guide/quick-start.html#using-the-es-module-build - тоже самое, но уже через ES-модули.  
https://ru.vuejs.org/guide/quick-start.html#enabling-import-maps - через import maps.  
https://ru.vuejs.org/guide/best-practices/production-deployment.html#without-build-tools - если используете CDN не только для разработки но и для продакшена.

https://ru.vuejs.org/guide/quick-start.html#splitting-up-the-modules - делим код Vue на модули (отдельные файлы), однако при этом следует помнить что index.html нужно будет открывать через локальный браузер.

Заготовка (при необходимости Vue можно скачать в виде файла и разместить в файловой системе проекта):

    <!DOCTYPE html>
    <html lang="en">
    <head>
      <meta charset="UTF-8">
      <meta http-equiv="X-UA-Compatible" content="IE=edge">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <link rel="stylesheet" href="css/style.css">
      <title>Основные примеры с Vue.js</title>
      <script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
    </head>
    <body>

    <div id="app">{{ message }}</div>

    <script>
    const { createApp } = Vue

    createApp({
      data() {
        return {
          message: 'Привет Vue'
        }
      }
    }).mount('#app')
    </script>

    </body>
    </html>

## Приложение со стилем Options API

Первое приложение Options API.

    <script>
      export default {
        // Свойства возвращаемые из data() становятся реактивным
        // состоянием компонента и к ним можно обращаться через `this`.
        data() {
          return {
            count: 0
          }
        },

        // Методы это функции, которые мутируют состояние и вызывают обновления.
        // Они могут быть привязаны в качестве обработчиков событий в шаблонах.
        methods: {
          increment() {
            this.count++
          }
        },

        // Хуки жизненного цикла вызываются на разных этапах
        // жизненного цикла компонента.
        // Эта функция будет вызвана после монтирования компонента.
        mounted() {
          console.log(`Стартовое значение счётчика — ${this.count}.`)
        }
      }
    </script>

    <template>
      <button @click="increment">Счётчик: {{ count }}</button>
    </template>

## Приложение со стилем Composition API
Первое приложение Composition API.

    <script setup>
      import { ref, onMounted } from 'vue'

      // реактивное состояние
      const count = ref(0)

      // функции которые мутируют состояние и вызывают обновления
      function increment() {
        count.value++
      }

      // хуки жизненного цикла
      onMounted(() => {
        console.log(`Стартовое значение счётчика — ${count.value}.`)
      })
    </script>

    <template>
      <button @click="increment">Счётчик: {{ count }}</button>
    </template>

## Vue app (старый синтаксис)
Рассмотрим своё первое приложение на Vue.

    <div id="app">
      {{ message }}
    </div>

    <script src="js/vue.js"></script>

    <script>
      var app = new Vue({
        el: '#app',
        data: {
          message: 'Hello World!'
        }
      })
    </script>

Двойные фигурные скобки `{{ message }}` это шаблон куда вставляются значения свойств объекта `data`.

- `id="app"` - контейнер для всего приложения, шаблон
- `var app =` можно убрать
- `new Vue()` инициализация нового vue-приложения (объекта), инстанс
- `Vue({})` - конструктор, которому передаём элемент с `id="app"`
- `el: '#app'` - получаем доступ к DOM, к элементу #app
  - vue.js работает внутри элемента с `id="app"`, id может быть любым
- `data` - ключ, объект в котором хранятся свойства элемента `#app`
- `message` - переменная, одно из свойств `data`
- `methods` - ключ в котором хранятся методы элемента `#app`

`new Vue` (объект, инстанс, вью модель) благодаря которому можно манипулировать фреймворком `Vue.js`. Данный объект может создавать и контролировать как маленькие компоненты так и целое приложение.

## Пример

    <div id="content">
      <h1>{{ title }}</h1>
      <h2>{{ subtitle }}</h2>
    </div>

    <script src="js/vue.js"></script>
    <script>
      var app = new Vue({
        el: '#content',
        data: {
          title: 'Vue.js',
          subtitle: 'Руководство по Vue.js'
        }
      })
    </script>

Если в консоли ввести `app.title="hello"` то заголовок изменится.

## Разное
`new Vue` также называют еще экземпляр, инстанс.
