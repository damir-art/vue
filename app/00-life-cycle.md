# Жизненный цикл
Жизненный цикл приложения Vue

- `beforeCreated` (приложение подготавливается к созданию) метод сработает до создания vue приложения
- `created` (приложение создано) но еще не показано пользователю, наиболее частоиспользуемый, например при AJAX запросах на сервер, сначала получаем данные, потом показываем пользователю готовое приложение
- `beforeMount` приложение подготавливается к вставке, ищет элемент с `id='#app'`, вставляет данные
- `mounted` приложение вставлено, показано на экране
- `beforeUpdate` подготовка приложения к обновлению
- `updated` данные обновлены
- `beforeDestroy` подготовка к удалению приложения
- `destroyed` удаление приложения, частоиспользуемый для очистки памяти от приложений

Пример жизненного цикла:

    const app = new Vue({
        el: '#app',
        data: {
            title: 'Заголовок',
        },
        beforeCreate() {
            console.log('before create')
        },
        created() {
            console.log('created')
        },
        beforeMount() {
            console.log('beforeMount')
        },
        mounted() {
            console.log('mounted')
        },
        beforeUpdate() {
            console.log('beforeUpdate')
        },
        updated() {
            console.log('updated')
        },
        beforeDestroy() {
            console.log('beforeDestroy')
        },
        destroyed() {
            console.log('destroyed')
        }
    })

Чтобы в консоль вывелось `beforeUpdate` и `updated`, нужно создать событие:

    <div id="app">
        <h1 @click="title = 'Привет'">{{ title }}</h1>
    </div>

Чтобы в консоль вывелось `beforDestroy` и `destroyed`, нужно удалить приложение:

    <div id="app">
        <h1 @click="title = 'Привет'">{{ title }}</h1>
        <button @click="$destroy()" type="button">Удалить</button>
    </div>

После удаления приложения, событие не работает.
