# События
Работаем с событиями во Vue.js

Записываем тегам в качестве атрибута: `v-on:имя_события="имя_метода"`

    h1 {{ counter }}
    button(v-on:click="plusOne") +1
    button(v-on:click="minusOne") -1

    data: {
        counter: 0
    },
    methods: {
        plusOne () {
            this.counter++
        },
        minusOne () {
            this.counter--
        }
    }

- Если функция то её код можно писать прямо в значении атрибута: `v-on:click="counter++"` здесь this не прописываем.
- Вместо `v-on:click` можно писать `@click`