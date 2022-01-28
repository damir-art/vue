# Передача параметров от корневого к дочернему
Передача параметров от корневого комопонента к дочернему

## App.vue:
Корневой компонент:

    <template>
        <div id="app">
            <h1>{{ message }}</h1>
            <!-- Вставляем дочерний компонент и передаем параметры -->
            <counter :title="title" :descr="descr" />
        </div>
    </template>

    <script>
        export default {
            data() {
                return {
                    message: 'Родитель',
                    title: 'Заголовок параметра',
                    descr: 'Описание параметра'
                }
            }
        }
    </script>

## Counter.vue
Родительский компонент:

    <template>
        <div>
            <h2>{{ counter }}</h2>
            <button @click="add">+1</button>
            <p>{{ title }}</p>
            <p>{{ descr }}</p>
        </div>
    </template>

    <script>
    export default {
        // props, во всём коде можно оставить только его
        props: ["title", "descr"],
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