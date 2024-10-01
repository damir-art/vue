# Вычисляемые свойства
- не вызывайте методы в шаблоне
- вместо методов в шаблоне используйте `computed`

При нажатии по кнопке в шаблоне, срабатывает сразу два метода вместо одного:

    div A: {{a}}
    div B: {{b}}
    div Age: {{age}}
    div
        button(@click="a++") Add to A
        button(@click="b++") Bdd to B
    div Age + A = {{ addToA() }}
    div Age + B = {{ addToB() }}

    data: {
        a: 0,
        b: 0,
        age: 20
    },
    methods: {
        addToA() {
            console.log('addToA')
            return this.a + this.age
        },
        addToB() {
            console.log('addToB')
            return this.b + this.age
        }
    }

Сделаем так чтобы срабатывал лишь один метод который задействован в коде в данный момент:

Функции перенесенные в `computed` являются не методами, а вычисляемыми своствами. Уберем у них скобки вызова в шаблоне. Теперь каждая функция вызывается лишь тогда когда нужно.

    div A: {{a}}
    div B: {{b}}
    div Age: {{age}}
    div
        button(@click="a++") Add to A
        button(@click="b++") Bdd to B
    div Age + A = {{ addToA }}
    div Age + B = {{ addToB }}

    data: {
        a: 0,
        b: 0,
        age: 20
    },
    methods: {
    },
    computed: {
        addToA() {
            console.log('addToA')
            return this.a + this.age
        },
        addToB() {
            console.log('addToB')
            return this.b + this.age
        }
    }
