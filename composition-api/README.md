# Composition API
У Vue есть две версии 2 (Options API) и 3 (Composition API).

Options API, компоненты описывались через:

    export default {
      data() {},

      methods: {},

      mounted() {}
    }

Composition API (приближен к нативному JS):

    import { ref, onMounted } from 'vue'

    // Данные
    const count = ref(0)

    // Методы
    function increment() {
      count.value++
    }

    // Монтирование
    onMounted(() => {
      console.log(`The initial count is ${count.value}.`)
    })

В чатGPT можно вставлять код Options API и переводить его на Composition API. Вставляй скрипт и напиши ему `script setup`.
