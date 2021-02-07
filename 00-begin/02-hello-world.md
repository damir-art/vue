# Первое приложение

    <div id="app">
        {{ message }}
    </div>

    <script>
        var app = new Vue({
            el: '#app',
            data: {
                message: 'Hello World!'
            }
        })
    </script>

Двойные фигурные скобки `{{ data }}` это шаблон куда вставляются данные.

- `var app =` можно убрать
- `var app = new Vue({` инициализация нового vue-приложения
- `Vue({` - конструктор, которому передаём элемент с `id="app"`
- `el: '#app'` - vue.js работает внутри элемента с `id="app"`, id может быть любым
- `data` - ключ в котором хранятся свойства элемента `#app`
- `methods` - ключ в котором хранятся методы элемента `#app`
- `message` - переменная

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
