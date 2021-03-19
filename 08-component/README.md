# Компонент
Зачем нужны компоненты?

Компонент это шаблон кода (HTML, CSS, JS) с помощью которого можно создавать дочерние компоненты. Изменяют только родительский компонент (шаблон), дочерние компоненты изменятся автоматически.

Компоненты ускоряют разработку, поддержку и масштабирование кода. Один из важнейших элементов архитектуры приложения.

Пример компонента: карточка товара.

## Какие бывают компоненты?
- локальные
- глобальные

## Пример компонента

## Разное
- `data` делаем функцией возвращающей объект, чтобы дочерние компоненты были независимы друг от друга

Пример:

    <div id="app">

        <!-- размножаем компонент циклом-->
        <card v-for="component in 1000" v-bind:key="component"></card>

    </div>

    <script src="js/vue.js"></script>

    <script>
        // глобальная регистрация компонента
        Vue.component('card', {
            // data делаем функцией
            data() {
                return {
                    count: 1,
                    countLimit: 4
                }
            },
            template: `
                <div class="card">
                    <h1 class="card__title">Название</h1>
                    <p class="card__descr">Описание</p>
                    <div>
                        <b class="card__price">5 000 руб</b>
                    </div>
                    <button @click="sub">-</button>
                    <input v-model="count" type="text" />
                    <button @click="add">+</button>
                </div>
            `,
            methods: {
                add() {
                    this.count < this.countLimit ? this.count++ : ''
                },
                sub() {
                    this.count > 1 ? this.count-- : ''
                }
            }
        })

        const app = new Vue({
            el: '#app'
        })
    </script>