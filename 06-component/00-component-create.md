# Создаем компонент
Сначала пишем имя компонента, потом объект описывающий наш компонент. Если создаём компонент шаблона, то пишем `template` и указываем HTML-разметку внутри кавычек.

    #app
        <product></product>

    Vue.component('product', {
        template: '<h1>Название товара</h1>'
    })

Мы создали шаблон-компонент, сделаем его динамичным.

    Vue.component('product', {
        template: '<h1>{{ title }}</h1>',
        data() {
            return {
                title: 'Название товара'
            }
        }
    })

Изменим заголовок по клику по кнопке:

    Vue.component('product', {
        template: `
            <div>
                <h1>{{ title }}</h1>
                <button @click="changeTitle">Изменить заголовок</button>
            </div>`,
        data() {
            return {
                title: 'Название товара'
            }
        },
        methods: {
            changeTitle() {
                this.title = 'Заголовок изменён!'
            }
        }
    })
